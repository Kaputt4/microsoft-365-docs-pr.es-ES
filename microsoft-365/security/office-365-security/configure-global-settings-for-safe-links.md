---
title: Configuración global de los valores de Vínculos seguros en Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a ver y configurar la configuración global (la lista "Bloquear las siguientes direcciones URL" y la protección para aplicaciones de Office 365) para vínculos seguros en Microsoft Defender para Office 365.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: ed217c73b626d2b6320c1f5b6d391545f5854015
ms.sourcegitcommit: 651610ca73bfd1d008d97311b59782790df664fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "67613129"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Configuración global de vínculos seguros en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md). Si es un usuario principal que busca información sobre Safelinks en Outlook, consulte [Seguridad avanzada de Outlook.com](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros es una característica de [Microsoft Defender para Office 365](defender-for-office-365.md) que proporciona el examen de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y la hora de verificación de clic de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones. Para obtener más información, vea [Vínculos seguros en Microsoft Defender para Office 365](safe-links.md).

La mayoría de los valores de Vínculos seguros se configuran en directivas de vínculos seguros, incluida la [configuración de vínculos seguros para aplicaciones de Office compatibles](safe-links.md#safe-links-settings-for-office-apps). Para obtener instrucciones, consulte [Configuración de directivas de vínculos seguros en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

Sin embargo, Vínculos seguros también usa las siguientes opciones globales que se configuran fuera de las directivas de vínculos seguros:

- **La lista Bloquear las siguientes direcciones URL**. Esta configuración se aplica a todos los usuarios que se incluyen en las directivas de vínculos seguros activas. Para obtener más información, consulte [la lista "Bloquear las siguientes direcciones URL" para vínculos seguros](safe-links.md#block-the-following-urls-list-for-safe-links).

Puede configurar los valores globales de Vínculos seguros en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 aptas con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin Exchange Online buzones de correo, pero con Microsoft Defender para Office 365 suscripciones de complemento).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Aunque no hay ninguna directiva de vínculos seguros predeterminada, la directiva de seguridad preestablecida **de protección integrada** proporciona protección de vínculos seguros a todos los destinatarios (usuarios que no están definidos en las directivas de seguridad preestablecidas estándar o estricta o en directivas de vínculos seguros personalizadas). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md). También puede crear directivas de vínculos seguros para aplicarlas a usuarios, grupos o dominios específicos. Para obtener instrucciones, consulte [Configuración de directivas de vínculos seguros en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Vínculos seguros** , use <https://security.microsoft.com/safelinksv2>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para configurar los valores globales de Vínculos seguros, debe ser miembro de los grupos de roles **Administración de la organización** o **Administrador de seguridad** .
  - Para obtener acceso de solo lectura a la configuración global de Vínculos seguros, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para ver nuestros valores recomendados para la configuración global de Vínculos seguros, consulte [Configuración de vínculos seguros](recommended-settings-for-eop-and-office365.md#safe-links-settings).

- Espere hasta 30 minutos para que se aplique una directiva nueva o actualizada.

- [Las nuevas características se agregan continuamente a Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365). A medida que se agregan nuevas características, es posible que tenga que realizar ajustes en las directivas de vínculos seguros existentes.

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a>Configurar la lista "Bloquear las siguientes direcciones URL" en el portal de Microsoft 365 Defender

> [!NOTE]
> Ahora puede administrar las entradas de dirección URL de bloque en la [lista de permitidos o bloqueados de inquilinos](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list). La lista "Bloquear las siguientes direcciones URL" está en desuso. Intentaremos migrar las entradas existentes de la lista "Bloquear las siguientes direcciones URL" para bloquear las entradas de dirección URL en la lista de permitidos o bloqueados de inquilinos. Los mensajes que contienen la dirección URL bloqueada se pondrán en cuarentena.

La lista **Bloquear las siguientes direcciones URL** identifica los vínculos que siempre deben bloquearse mediante el examen de vínculos seguros en aplicaciones admitidas. Para obtener más información, consulte [la lista "Bloquear las siguientes direcciones URL" para vínculos seguros](safe-links.md#block-the-following-urls-list-for-safe-links).

1. En el portal de Microsoft 365 Defender de <https://security.microsoft.com>, vaya a Email & Directivas de **colaboración** \> **& Reglas** \> **Vínculos seguros** de **directivas** \> de amenazas en la sección **Directivas**. Para ir directamente a la página **Vínculos seguros** , use <https://security.microsoft.com/safelinksv2>.

2. En la página **Vínculos seguros** , haga clic en **Configuración global**. En la **directiva vínculos seguros de su organización** , vaya al cuadro **Bloquear las siguientes direcciones URL** .

3. Configure una o varias entradas como se describe en [Sintaxis de entrada para la lista "Bloquear las siguientes direcciones URL"](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configuración de la lista "Bloquear las siguientes direcciones URL" en PowerShell

Para obtener más información sobre la sintaxis de entrada, vea [Sintaxis de entrada para la lista "Bloquear las siguientes direcciones URL"](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

Puede usar el cmdlet **Get-AtpPolicyForO365** para ver las entradas existentes en la propiedad _BlockURLs_ .

- Para agregar valores que reemplazarán las entradas existentes, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  En este ejemplo se agregan las siguientes entradas a la lista:

  - Bloquee el dominio, los subdominios y las rutas de acceso para fabrikam.com.
  - Bloquee la investigación del subdominio, pero no el dominio primario u otros subdominios de tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Para agregar o quitar valores sin afectar a otras entradas existentes, use la sintaxis siguiente:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  En este ejemplo se agrega una nueva entrada para adatum.com y se quita la entrada de fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado correctamente la configuración global de Vínculos seguros (la lista **Bloquear las direcciones URL siguientes** y la configuración de protección de aplicaciones de Office 365), realice cualquiera de los pasos siguientes:

- En la página **Vínculos seguros** del portal de Microsoft 365 Defender en <https://security.microsoft.com/safelinksv2>, haga clic en **Configuración global** y compruebe la configuración del control flotante que aparece.

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, ejecute el siguiente comando y compruebe la configuración:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).
