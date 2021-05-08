---
title: Configurar la configuración global para Caja fuerte de vínculos en Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a ver y configurar la configuración global (la lista "Bloquear las siguientes direcciones URL" y la protección para aplicaciones de Office 365) para Caja fuerte Vínculos en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11544953bf348c47e697b3210da709cccdb31a7e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245845"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Configurar la configuración global para Caja fuerte vínculos en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md). Si es un usuario principal que busca información sobre safelinks en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Caja fuerte Vínculos es una característica de [Microsoft Defender](defender-for-office-365.md) para Office 365 que proporciona el examen de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el tiempo de comprobación de clics de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones. Para obtener más información, [vea Caja fuerte Links in Microsoft Defender for Office 365](safe-links.md).

Puede configurar la mayoría de Caja fuerte de vínculos en Caja fuerte de vínculos. Para obtener instrucciones, vea [Configurar directivas Caja fuerte vínculos en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

Sin embargo, Caja fuerte links también usa la siguiente configuración global que se configura fuera de las directivas de vínculos de Caja fuerte:

- La **lista Bloquear las siguientes direcciones** URL. Esta configuración se aplica a todos los usuarios incluidos en las directivas de vínculos Caja fuerte activas. Para obtener más información, vea ["Bloquear las siguientes direcciones URL" para](safe-links.md#block-the-following-urls-list-for-safe-links) obtener Caja fuerte vínculos
- Caja fuerte Vincula la protección para Office 365 aplicaciones. Esta configuración se aplica a todos los usuarios de la organización con licencia para Defender para Office 365, independientemente de si los usuarios se incluyen en directivas de vínculos de Caja fuerte activas o no. Para obtener más información, [consulta Caja fuerte configuración de vínculos para Office 365 aplicaciones](safe-links.md#safe-links-settings-for-office-365-apps).

Puede configurar la configuración global de vínculos de Caja fuerte en el Centro de seguridad y cumplimiento de & o en PowerShell (PowerShell de Exchange Online para organizaciones Microsoft 365 elegibles con buzones de correo en Exchange Online; PowerShell EOP independiente para organizaciones sin buzones de Exchange Online, pero con Microsoft Defender para suscripciones de complemento Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- No hay ninguna directiva de vínculos Caja fuerte integrada o predeterminada, por lo que debe crear al  menos una directiva de vínculos de Caja fuerte para que la lista Bloquear las siguientes direcciones URL esté activa. Para obtener instrucciones, vea [Configurar directivas Caja fuerte vínculos en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Caja fuerte vínculos,** use <https://protection.office.com/safelinksv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para configurar la configuración global de Caja fuerte, debe ser miembro  de los grupos de roles Administración de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a la configuración global de Caja fuerte links, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para obtener los valores recomendados para la configuración global de Caja fuerte vínculos, vea [Caja fuerte configuración de vínculos](recommended-settings-for-eop-and-office365.md#safe-links-settings).

- Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.

- [Las nuevas características se agregan continuamente a Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365). A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos de Caja fuerte existentes.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Configurar la lista "Bloquear las siguientes direcciones URL" en el Centro de seguridad & cumplimiento

La **lista Bloquear las siguientes direcciones URL** identifica los vínculos que siempre deben bloquearse mediante el examen de vínculos Caja fuerte en aplicaciones compatibles. Para obtener más información, vea ["Bloquear las siguientes direcciones URL" para obtener Caja fuerte vínculos](safe-links.md#block-the-following-urls-list-for-safe-links).

1. En el Centro de seguridad &  cumplimiento, vaya a Directiva de administración de amenazas \>  \> **ATP Caja fuerte vínculos** y, a continuación, haga clic en **Configuración global**.

2. En el **Caja fuerte de vínculos** de la organización que aparece, vaya al cuadro **Bloquear las siguientes direcciones URL.**

3. Configure una o más entradas como se describe en Sintaxis Entry para la lista ["Bloquear las siguientes direcciones URL".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurar la lista "Bloquear las siguientes direcciones URL" en PowerShell

Para obtener más información acerca de la sintaxis de entrada, vea [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

Puede usar el cmdlet **Get-AtpPolicyForO365** para ver las entradas existentes en la _propiedad BlockURLs._

- Para agregar valores que reemplacen las entradas existentes, use la siguiente sintaxis Exchange Online PowerShell o Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  En este ejemplo se agregan las siguientes entradas a la lista:

  - Bloquee el dominio, los subdominios y las rutas de acceso fabrikam.com.
  - Bloquee la investigación de subdominios, pero no el dominio primario u otros subdominios de tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Para agregar o quitar valores sin afectar a otras entradas existentes, use la sintaxis siguiente:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  En este ejemplo se agrega una nueva entrada para adatum.com y se quita la entrada para fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Configurar Caja fuerte de vínculos para Office 365 aplicaciones en el Centro de seguridad y & cumplimiento

Caja fuerte La protección de vínculos Office 365 aplicaciones se aplica a documentos en aplicaciones Office de escritorio, móviles y web compatibles. Para obtener más información, [consulta Caja fuerte configuración de vínculos para Office 365 aplicaciones](safe-links.md#safe-links-settings-for-office-365-apps).

1. En el Centro de seguridad &  cumplimiento, vaya a Directiva de administración de amenazas \>  \> **ATP Caja fuerte vínculos** y, a continuación, haga clic en **Configuración global**.

2. En la **directiva Caja fuerte vínculos** de la organización que aparece, configure las siguientes opciones en la sección Configuración que se aplican al contenido excepto **el** correo electrónico:

   - **Office 365:** compruebe que la alternancia está a la derecha para habilitar Caja fuerte vínculos para aplicaciones Office 365 compatibles: ![ Activar ](../../media/scc-toggle-on.png) .

   - **No** realizar un seguimiento cuando los usuarios hacen clic en Caja fuerte Vínculos: mueva el botón de alternancia a la izquierda para realizar un seguimiento de los clics de usuario relacionados con las direcciones URL bloqueadas en las aplicaciones Office 365 compatibles: Desactivar ![ ](../../media/scc-toggle-off.png) .

   - No permitir que los usuarios hagan clic en Caja fuerte Vínculos a la **dirección URL original:** compruebe que la alternancia está a la derecha para impedir que los usuarios hagan clic en la dirección URL bloqueada original en las aplicaciones Office 365 compatibles: Activar ![ ](../../media/scc-toggle-on.png) .

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurar Caja fuerte de vínculos para Office 365 aplicaciones en PowerShell

Si prefiere usar PowerShell para configurar la protección de vínculos de Caja fuerte para aplicaciones de Office 365, use la sintaxis siguiente en Exchange Online PowerShell o Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

En este ejemplo se configuran las siguientes opciones para la protección Caja fuerte vínculos en Office 365 aplicaciones:

- Caja fuerte Los vínculos Office 365 aplicaciones están activados (no estamos usando el parámetro _EnableSafeLinksForO365Clients_ y el valor predeterminado es $true).
- Se realiza un seguimiento de los clics de usuario relacionados con las direcciones URL bloqueadas Office 365 aplicaciones admitidas.
- Los usuarios no pueden hacer clic en la dirección URL bloqueada original en aplicaciones Office 365 compatibles (no estamos usando el parámetro _AllowClickThrough_ y el valor predeterminado es $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado correctamente la configuración global de los vínculos de Caja fuerte (la lista Bloquear las siguientes direcciones **URL** y la configuración de protección de aplicaciones de Office 365), siga estos pasos:

- En el Centro de seguridad &  cumplimiento, vaya a Directiva de administración de amenazas \>  \> **ATP Caja fuerte Vínculos,** haga clic en Configuración global y compruebe la configuración en el menú desplegable que aparece.

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, ejecute el siguiente comando y compruebe la configuración:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).
