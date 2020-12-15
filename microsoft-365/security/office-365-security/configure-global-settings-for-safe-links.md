---
title: Establecer la configuración global para la configuración de vínculos seguros en defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo ver y configurar las opciones globales (la lista "bloquear las siguientes direcciones URL" y la protección de las aplicaciones de Office 365) para obtener vínculos seguros en Microsoft defender para Office 365.
ms.openlocfilehash: bc44432d4d9478e4c6a2414a70acc785c5b2c005
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682911"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Establecer la configuración global para vínculos seguros en Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](office-365-atp.md). Si es un usuario doméstico que busca información sobre Safelinks en Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros es una característica de [Microsoft defender para Office 365](office-365-atp.md) que proporciona análisis de URL de los mensajes de correo electrónico entrantes en el flujo de correo y la hora de la comprobación de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones. Para obtener más información, vea [vínculos a prueba de errores en Microsoft defender para Office 365](atp-safe-links.md).

La configuración de vínculos más seguros se configura en directivas de vínculos a prueba de errores. Para obtener instrucciones, consulte [configurar directivas de vínculos seguros en Microsoft defender para Office 365](set-up-atp-safe-links-policies.md).

Sin embargo, vínculos seguros también usa la configuración global que se aplica a todos los usuarios incluidos en las directivas de vínculos seguros activos. Este área de configuración global:

- La lista **bloquear las siguientes direcciones URL** . Para obtener más información, consulte [la lista "bloquear las siguientes direcciones URL" para vínculos seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Protección de vínculos seguros para aplicaciones de Office 365. Para obtener más información, vea [configuración de vínculos seguros para aplicaciones de Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).

Puede establecer la configuración global de vínculos seguros en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para las organizaciones de Microsoft 365 con buzones de correo en Exchange Online; independiente de EOP para organizaciones sin buzones de Exchange Online, pero con Microsoft defender para Office 365 para las suscripciones complementarias).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Las características que proporciona la configuración global para vínculos seguros solo se aplican a los usuarios que se incluyen en las directivas de vínculos seguros activos. No hay una directiva de vínculos a prueba de errores integrada o predeterminada, por lo que debe crear al menos una directiva de vínculos seguros para que esta configuración global esté activa. Para obtener instrucciones, consulte [configurar directivas de vínculos seguros en Microsoft defender para Office 365](set-up-atp-safe-links-policies.md).

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página de **vínculos seguros** , use <https://protection.office.com/safelinksv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento de Office 365 antes de que pueda usar este cmdlet.
  - Para establecer la configuración global de vínculos seguros, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** .
  - Para tener acceso de solo lectura a la configuración global de vínculos seguros, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para conocer los valores recomendados para la configuración global de vínculos seguros, consulte [configuración de vínculos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).

- Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.

- [Las nuevas características se agregan continuamente a Microsoft defender para Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365). A medida que se agreguen nuevas características, es posible que deba realizar ajustes en las directivas de vínculos a prueba de errores existentes.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Configurar la lista "bloquear las siguientes direcciones URL" en el centro de seguridad & cumplimiento

La lista **bloquear las siguientes direcciones URL** identifica los vínculos que deben bloquearse siempre mediante la detección de vínculos seguros en las aplicaciones compatibles. Para obtener más información, consulte [la lista "bloquear las siguientes direcciones URL" para vínculos seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links).

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \>  \> **ATP Safe links** y, a continuación, haga clic en **configuración global**.

2. En la **Directiva de vínculos seguros de la organización** que aparece, vaya al cuadro **bloquear las siguientes direcciones URL** .

3. Configure una o más entradas como se describe en [la sintaxis de entrada de la lista "bloquear las siguientes direcciones URL"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurar la lista "bloquear las siguientes direcciones URL" en PowerShell

Para obtener información detallada sobre la sintaxis de la entrada, consulte [entry Syntax para la lista "bloquear las siguientes direcciones URL"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

Puede usar el cmdlet **Get-AtpPolicyForO365** para ver las entradas existentes en la propiedad _BlockURLs_ .

- Para agregar valores que van a reemplazar las entradas existentes, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  En este ejemplo se agregan las siguientes entradas a la lista:

  - Bloquee el dominio, los subdominios y las rutas de fabrikam.com.
  - Bloquear la investigación del subdominio, pero no el dominio principal u otros subdominios de tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Para agregar o quitar valores sin que ello afecte a las entradas existentes, use la sintaxis siguiente:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  En este ejemplo se agrega una nueva entrada para adatum.com y se quita la entrada de fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Configurar la protección de vínculos seguros para las aplicaciones de Office 365 en el centro de seguridad & cumplimiento

La protección de vínculos seguros para las aplicaciones de Office 365 se aplica a los documentos de aplicaciones Web, móviles y de escritorio de Office compatibles. Para obtener más información, vea [configuración de vínculos seguros para aplicaciones de Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \>  \> **ATP Safe links** y, a continuación, haga clic en **configuración global**.

2. En la **Directiva de vínculos a prueba de errores de la organización** hacia fuera que aparece, configure las siguientes opciones en la sección **configuración que se aplica a contenido, excepto correo electrónico** :

   - **Aplicaciones de office 365**: Compruebe que el botón de alternancia sea el derecho para habilitar vínculos seguros para las aplicaciones de Office 365 compatibles: ![ activar o desactivar ](../../media/scc-toggle-on.png) .

   - **No realizar seguimiento cuando los usuarios hacen clic en vínculos seguros**: mueva el botón de alternancia a la izquierda para realizar un seguimiento de los clics de usuario relacionados con direcciones URL bloqueadas en aplicaciones de Office 365 compatibles: desactivar ![ ](../../media/scc-toggle-off.png) .

   - **No permita que los usuarios hagan clic en los vínculos seguros a la dirección URL original**: Compruebe que el botón de alternancia es hacia la derecha para impedir que los usuarios hagan clic a través de la URL bloqueada original en aplicaciones admitidas de Office 365: ![ activar o desactivar ](../../media/scc-toggle-on.png) .

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurar la protección de vínculos seguros para las aplicaciones de Office 365 en PowerShell

Si prefiere usar PowerShell para configurar la protección de vínculos seguros para las aplicaciones de Office 365, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

En este ejemplo se configura la siguiente configuración para la protección de vínculos seguros en las aplicaciones de Office 365:

- Vínculos seguros para las aplicaciones de Office 365 está activado (no se usa el parámetro _EnableSafeLinksForO365Clients_ y el valor predeterminado es $true).
- Se realiza un seguimiento de los clics de usuario relacionados con las direcciones URL bloqueadas en las aplicaciones de Office 365 compatibles.
- Los usuarios no pueden hacer clic a través de la dirección URL bloqueada original en las aplicaciones de Office 365 compatibles (no se usa el parámetro _AllowClickThrough_ y el valor predeterminado es $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado correctamente la configuración global para vínculos seguros (la lista **bloquear las siguientes direcciones URL** y la configuración de protección de aplicaciones de Office 365), siga uno de estos pasos:

- En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \>  \> **ATP Safe links**, haga clic en **configuración global** y Compruebe la configuración de la volar hacia fuera que aparece.

- En PowerShell de Exchange Online PowerShell o Exchange Online Protection, ejecute el siguiente comando y Compruebe la configuración:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).
