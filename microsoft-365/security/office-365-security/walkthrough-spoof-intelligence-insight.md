---
title: Administración de remitentes suplantados mediante la directiva de inteligencia de suplantación de identidad y la información de inteligencia de suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar la directiva de inteligencia de suplantación de identidad y la información de inteligencia de suplantación de identidad para permitir o bloquear remitentes suplantados detectados.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 55ed1bd871d78c6d130a933799ec3f62d36d7736
ms.sourcegitcommit: 58ec09f1fd66af9717dc2743585d06d358ec7360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2022
ms.locfileid: "65144707"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>Administración de remitentes suplantados mediante la directiva de inteligencia de suplantación de identidad y la información de inteligencia de suplantación de identidad en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> La administración de remitentes suplantados en el portal de Microsoft 365 Defender ahora solo está disponible en la pestaña **Suplantación de** identidad de la Lista de permitidos o bloqueados de inquilinos. Para ver los procedimientos actuales en el portal de Microsoft 365 Defender, consulte [Spoof intelligence insight in EOP (Información de inteligencia de suplantación de identidad en EOP](learn-about-spoof-intelligence.md)).
>
> La administración de remitentes suplantados en Exchange Online PowerShell o PowerShell EOP independiente está en proceso de migración exclusiva a los cmdlets **-TenantAllowBlockListSpoofItems, Get-SpoofIntelligenceInsight y Get-SpoofMailReport relacionados\***.  Para conocer los procedimientos que usan estos cmdlets, consulte los artículos siguientes:
>
> - [Visualización de entradas de remitente suplantadas mediante PowerShell](tenant-allow-block-list.md#view-spoofed-sender-entries)
> - [Adición de entradas permitidas del remitente suplantado mediante PowerShell](manage-tenant-allows.md#add-spoofed-sender-allow-entries-using-powershell)
> - [Adición de entradas de bloque de remitentes falsificados mediante PowerShell](manage-tenant-blocks.md#add-spoofed-sender-block-entries)
> - [Modificación de entradas de remitente suplantadas mediante PowerShell](modify-remove-entries-tenant-allow-block.md#modify-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list)
> - [Eliminación de entradas de remitente suplantadas mediante PowerShell](modify-remove-entries-tenant-allow-block.md#remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list)
>
> La experiencia anterior de administración de remitentes suplantados mediante los cmdlets **Get-PhishFilterPolicy** y **Set-PhishFilterPolicy** está en desuso, pero todavía se presenta en este artículo para mayor integridad hasta que los cmdlets se quitan en todas partes.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para modificar la directiva de inteligencia de suplantación de identidad o habilitar o deshabilitar la inteligencia de suplantación de identidad, debe ser miembro de:
    - **Administración de organizaciones**
    - **Administrador de seguridad** <u>y</u> **Configuración de solo vista** o **Administración de la organización de solo vista**.
  - Para obtener acceso de solo lectura a la directiva de inteligencia de suplantación de identidad, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Las opciones de inteligencia sobre suplantación de identidad se describen en [Configuración de suplantación de identidad en directivas contra suplantación de identidad (phishing).](set-up-anti-phishing-policies.md#spoof-settings)

- Puede habilitar, deshabilitar y configurar los valores de inteligencia de suplantación de identidad en las directivas contra suplantación de identidad (phishing). Para obtener instrucciones basadas en su suscripción, consulte uno de los temas siguientes:

  - [Configurar directivas contra suplantación de identidad (phishing) en EOP](configure-anti-phishing-policies-eop.md).
  - [Configure las directivas contra phishing en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md).

- Para ver nuestra configuración recomendada para la inteligencia de suplantación de identidad, consulte Configuración de la [directiva de suplantación de identidad (EOP).](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)

## <a name="use-powershell-to-manage-spoofed-senders"></a>Uso de PowerShell para administrar remitentes suplantados

Para ver los remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, use la sintaxis siguiente:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

En este ejemplo se devuelve información detallada sobre todos los remitentes que pueden suplantar a los usuarios de los dominios.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).

Para configurar remitentes permitidos y bloqueados en inteligencia de suplantación de identidad, siga estos pasos:

1. Capture la lista actual de remitentes suplantados detectados escribiendo la salida del cmdlet **Get-PhishFilterPolicy** en un archivo CSV mediante la ejecución del siguiente comando:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Edite el archivo CSV para agregar o modificar los valores siguientes:
   - **Remitente** (dominio en el registro PTR del servidor de origen o dirección IP/24)
   - **SpoofedUser**: uno de los valores siguientes:
     - Dirección de correo electrónico del usuario interno.
     - Dominio de correo electrónico del usuario externo.
     - Valor en blanco que indica que desea bloquear o permitir todos y cada uno de los mensajes suplantados del **remitente** especificado, independientemente de la dirección de correo electrónico suplantada.
   - **AllowedToSpoof** (Sí o No)
   - **SpoofType** (interno o externo)

   Guarde el archivo, lea el archivo y almacene el contenido como una variable denominada `$UpdateSpoofedSenders` mediante la ejecución del siguiente comando:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Use la `$UpdateSpoofedSenders` variable para configurar la directiva de inteligencia de suplantación de identidad mediante la ejecución del siguiente comando:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado la inteligencia de suplantación de identidad con remitentes a los que se les permite y no se les permite suplantar, ejecute los siguientes comandos en PowerShell para ver los remitentes a los que se les permite y no se les permite suplantar:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- En PowerShell, ejecute el siguiente comando para exportar la lista de todos los remitentes suplantados a un archivo CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
