---
title: Configurar la configuración global de vínculos seguros en Defender para Office 365
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
description: Los administradores pueden aprender a ver y configurar la configuración global (la lista "Bloquear las siguientes direcciones URL" y la protección para aplicaciones de Office 365) para Vínculos seguros en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38614d070f4ac9bfda978301eaeed6029b47e0ca
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406119"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Configuración global de vínculos seguros en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](office-365-atp.md). Si es un usuario principal que busca información sobre safelinks en Outlook, vea [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros es una característica de [Microsoft Defender para Office 365](office-365-atp.md) que proporciona el examen de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el tiempo de comprobación de clics de las direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones. Para obtener más información, vea [Vínculos seguros en Microsoft Defender para Office 365](atp-safe-links.md).

La mayoría de las opciones de vínculos seguros se configuran en directivas de vínculos seguros. Para obtener instrucciones, vea [Configurar directivas de vínculos seguros en Microsoft Defender para Office 365](set-up-atp-safe-links-policies.md).

Sin embargo, Vínculos seguros también usa la configuración global que se aplica a todos los usuarios incluidos en cualquier directiva de vínculos seguros activa. Este área de configuración global:

- La **lista Bloquear las siguientes direcciones** URL. Para obtener más información, vea ["Bloquear las siguientes direcciones URL" para Vínculos seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Protección de vínculos seguros para aplicaciones de Office 365. Para obtener más información, vea [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).

Puede configurar la configuración global de vínculos seguros en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones elegibles de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online, pero con suscripciones de complementos de Microsoft Defender para Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Las características proporcionadas por la configuración global de vínculos seguros solo se aplican a los usuarios que se incluyen en las directivas de vínculos seguros activas. No hay ninguna directiva de vínculos seguros integrada o predeterminada, por lo que debe crear al menos una directiva de vínculos seguros para que esta configuración global esté activa. Para obtener instrucciones, vea [Configurar directivas de vínculos seguros en Microsoft Defender para Office 365](set-up-atp-safe-links-policies.md).

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Vínculos seguros,** use <https://protection.office.com/safelinksv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener asignados permisos en **Exchange Online** para poder realizar los procedimientos descritos en este artículo:
  - Para configurar la configuración global de vínculos seguros, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a la configuración global de vínculos seguros, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.

  Para obtener más información, consulte los [permisos en Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos y permisos necesarios para _otras_ características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para obtener los valores recomendados para la configuración global de vínculos seguros, consulte [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).

- Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.

- [Las nuevas características se agregan continuamente a Microsoft Defender para Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365). A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos seguros existentes.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Configurar la lista "Bloquear las siguientes direcciones URL" en el Centro de seguridad & cumplimiento

La **lista Bloquear las siguientes direcciones URL** identifica los vínculos que siempre deben bloquearse mediante el examen de vínculos seguros en aplicaciones compatibles. Para obtener más información, vea ["Bloquear las siguientes direcciones URL" para Vínculos seguros.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)

1. En el Centro de & cumplimiento, vaya a **Directiva** de administración de amenazas \>  \> **Vínculos** seguros de ATP y, a continuación, haga clic en **Configuración global**.

2. En la **directiva vínculos seguros de la organización** que aparece, vaya al cuadro Bloquear las siguientes direcciones **URL.**

3. Configure una o más entradas como se describe en Sintaxis Entry para la lista ["Bloquear las siguientes direcciones URL".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurar la lista "Bloquear las siguientes direcciones URL" en PowerShell

Para obtener más información acerca de la sintaxis de entrada, vea [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

Puede usar el cmdlet **Get-AtpPolicyForO365** para ver las entradas existentes en la _propiedad BlockURLs._

- Para agregar valores que reemplacen las entradas existentes, use la siguiente sintaxis en PowerShell de Exchange Online o Exchange Online Protection PowerShell:

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

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Configurar la protección de vínculos seguros para aplicaciones de Office 365 en el Centro de seguridad & cumplimiento

La protección de vínculos seguros para aplicaciones de Office 365 se aplica a documentos en aplicaciones de escritorio, móviles y web de Office compatibles. Para obtener más información, vea [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).

1. En el Centro de & cumplimiento, vaya a **Directiva** de administración de amenazas \>  \> **Vínculos** seguros de ATP y, a continuación, haga clic en **Configuración global**.

2. En la **directiva vínculos seguros de la** organización que aparece, configure las siguientes opciones en la sección Configuración que se aplican al contenido excepto el **correo** electrónico:

   - **Aplicaciones de Office 365:** compruebe que la alternancia está a la derecha para habilitar vínculos seguros para aplicaciones compatibles de Office 365: ![ Activar ](../../media/scc-toggle-on.png) .

   - **No** realice un seguimiento cuando los usuarios hagan clic en Vínculos seguros: mueva el botón de alternancia a la izquierda para realizar un seguimiento de los clics de usuario relacionados con direcciones URL bloqueadas en aplicaciones compatibles de Office 365: ![ Desactivar ](../../media/scc-toggle-off.png) .

   - No permitir que los usuarios hagan clic en vínculos seguros a la **dirección URL original:** compruebe que la alternancia está a la derecha para impedir que los usuarios hagan clic en la dirección URL bloqueada original en aplicaciones compatibles de Office 365: ![ Activar ](../../media/scc-toggle-on.png) .

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurar la protección de vínculos seguros para aplicaciones de Office 365 en PowerShell

Si prefiere usar PowerShell para configurar la protección de vínculos seguros para aplicaciones de Office 365, use la sintaxis siguiente en Exchange Online PowerShell o Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

En este ejemplo se configuran las siguientes opciones para la protección de vínculos seguros en aplicaciones de Office 365:

- Vínculos seguros para aplicaciones de Office 365 está activado (no estamos usando el parámetro _EnableSafeLinksForO365Clients_ y el valor predeterminado es $true).
- Se realiza un seguimiento de los clics de usuario relacionados con direcciones URL bloqueadas en aplicaciones compatibles de Office 365.
- Los usuarios no pueden hacer clic en la dirección URL bloqueada original en aplicaciones compatibles de Office 365 (no estamos usando el parámetro _AllowClickThrough_ y el valor predeterminado es $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado correctamente la configuración global de vínculos seguros (la lista Bloquear las siguientes direcciones **URL** y la configuración de protección de aplicaciones de Office 365), siga estos pasos:

- En el Centro de seguridad &  cumplimiento, vaya a Directiva de administración de amenazas Vínculos seguros de ATP, haga clic en Configuración global y compruebe la configuración del control emergente \>  \> que aparece. 

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, ejecute el siguiente comando y compruebe la configuración:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).
