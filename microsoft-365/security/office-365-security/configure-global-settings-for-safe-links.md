---
title: Configuración global de la configuración de vínculos seguros en Defender para Office 365
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
description: Los administradores pueden aprender a ver y configurar las opciones globales (la lista "Bloquear las siguientes direcciones URL" y la protección para aplicaciones de Office 365) para Vínculos seguros en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d52a4dc5ed35ec73c1410d6428a581b098bf2c52
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287466"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Configuración global de vínculos seguros en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](office-365-atp.md). Si es un usuario principal que busca información sobre safelinks en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros es una característica de Microsoft Defender para [Office 365](office-365-atp.md) que proporciona el análisis de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el tiempo de comprobación de clics de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones. Para obtener más información, vea [Vínculos seguros en Microsoft Defender para Office 365.](atp-safe-links.md)

La mayoría de las opciones de vínculos seguros se configuran en las directivas de vínculos seguros. Para obtener instrucciones, [vea Configurar directivas de vínculos seguros en Microsoft Defender para Office 365.](set-up-atp-safe-links-policies.md)

Sin embargo, Vínculos seguros también usa la configuración global que se aplica a todos los usuarios incluidos en cualquier directiva de vínculos seguros activa. Este área de configuración global:

- La **lista Bloquear las siguientes direcciones** URL. Para obtener más información, vea [la lista "Bloquear las siguientes direcciones URL" para vínculos seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Protección de vínculos seguros para aplicaciones de Office 365. Para obtener más información, vea [La configuración de vínculos seguros para aplicaciones de Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

Puede configurar las opciones globales de vínculos seguros en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones elegibles de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online, pero con Suscripciones de complemento de Microsoft Defender para Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Las características proporcionadas por la configuración global de vínculos seguros solo se aplican a los usuarios incluidos en las directivas de vínculos seguros activas. No hay ninguna directiva de vínculos seguros integrada o predeterminada, por lo que debe crear al menos una directiva de vínculos seguros para que esta configuración global esté activa. Para obtener instrucciones, [vea Configurar directivas de vínculos seguros en Microsoft Defender para Office 365.](set-up-atp-safe-links-policies.md)

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Vínculos seguros,** use <https://protection.office.com/safelinksv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - Para configurar las opciones globales de Vínculos seguros,  debe ser miembro de los grupos de roles Administración de la organización o **Administrador de** seguridad.
  - Para obtener acceso de solo lectura a la configuración global de Vínculos seguros, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para obtener los valores recomendados para la configuración global de Vínculos seguros, vea [La configuración de vínculos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)

- Espere hasta 30 minutos para que se aplique una directiva nueva o actualizada.

- [Las nuevas características se agregan continuamente a Microsoft Defender para Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos seguros existentes.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Configurar la lista "Bloquear las siguientes direcciones URL" en el Centro de & cumplimiento

La **lista Bloquear las siguientes direcciones URL** identifica los vínculos que siempre deben bloquearse mediante el examen de vínculos seguros en las aplicaciones compatibles. Para obtener más información, [vea la lista "Bloquear las siguientes direcciones URL" para Vínculos seguros.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)

1. En el Centro de & cumplimiento,  vaya a Vínculos seguros de ATP de directiva de administración de amenazas y, a continuación, haga clic \>  \> en **Configuración global.**

2. En la **directiva de vínculos seguros de su organización** que aparece, vaya al cuadro Bloquear las siguientes **direcciones** URL.

3. Configure una o más entradas como se describe en la sintaxis Entry para la lista ["Bloquear las siguientes direcciones URL".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurar la lista "Bloquear las siguientes direcciones URL" en PowerShell

Para obtener más información acerca de la sintaxis de entrada, vea La sintaxis [de entrada para la lista "Bloquear las siguientes direcciones URL".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

Puede usar el cmdlet **Get-AtpPolicyForO365** para ver las entradas existentes en la _propiedad BlockURLs._

- Para agregar valores que reemplacen las entradas existentes, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  En este ejemplo se agregan las siguientes entradas a la lista:

  - Bloquee el dominio, los subdominios y las rutas de acceso fabrikam.com.
  - Bloquee la investigación de subdominios, pero no el dominio primario u otros subdominios de tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Para agregar o quitar valores sin que ello afecte a otras entradas existentes, use la siguiente sintaxis:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  En este ejemplo se agrega una nueva entrada para adatum.com y se quita la entrada para fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Configurar la protección de vínculos seguros para aplicaciones de Office 365 en el Centro de & cumplimiento

La protección de vínculos seguros para aplicaciones de Office 365 se aplica a documentos en aplicaciones de escritorio, móviles y web de Office compatibles. Para obtener más información, vea [La configuración de vínculos seguros para aplicaciones de Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

1. En el Centro de & cumplimiento,  vaya a Vínculos seguros de ATP de directiva de administración de amenazas y, a continuación, haga clic \>  \> en **Configuración global.**

2. En la **directiva de vínculos seguros** de su organización que aparece, configure las siguientes opciones en la sección Configuración que se aplican al contenido excepto al **correo** electrónico:

   - **Aplicaciones de Office 365:** compruebe que el botón de alternancia está a la derecha para habilitar vínculos seguros para las aplicaciones de Office 365 compatibles: ![ activar. ](../../media/scc-toggle-on.png)

   - **No** realice un seguimiento de cuándo los usuarios hacen clic en Vínculos seguros: mueva el botón de alternancia a la izquierda para realizar un seguimiento de los clics del usuario relacionados con las direcciones URL bloqueadas en las aplicaciones compatibles de Office 365: ![ ](../../media/scc-toggle-off.png) desactivar.

   - No permitir que los usuarios hagan clic a través de Vínculos seguros a la dirección **URL original:** Compruebe que el botón de alternancia está a la derecha para evitar que los usuarios hagan clic en la dirección URL bloqueada original en las aplicaciones compatibles de Office 365: Activar. ![ ](../../media/scc-toggle-on.png)

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurar la protección de vínculos seguros para aplicaciones de Office 365 en PowerShell

Si prefiere usar PowerShell para configurar la protección de vínculos seguros para aplicaciones de Office 365, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

En este ejemplo se configuran las siguientes opciones para la protección de vínculos seguros en aplicaciones de Office 365:

- Vínculos seguros para aplicaciones de Office 365 está activado (no estamos usando el parámetro _EnableSafeLinksForO365Clients_ y el valor predeterminado es $true).
- Se realiza un seguimiento de los clics del usuario relacionados con las direcciones URL bloqueadas en las aplicaciones compatibles de Office 365.
- Los usuarios no pueden hacer clic en la dirección URL bloqueada original en aplicaciones compatibles de Office 365 (no estamos usando el parámetro _AllowClickThrough_ y el valor predeterminado es $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado correctamente la configuración global de Vínculos seguros (la lista Bloquear las siguientes direcciones **URL** y la configuración de protección de aplicaciones de Office 365), siga uno de estos pasos:

- En el Centro de & cumplimiento,  vaya a Vínculos seguros de ATP de directiva de administración de amenazas, haga clic en Configuración global y compruebe la configuración en el control emergente \>  \> que aparece. 

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, ejecute el siguiente comando y compruebe la configuración:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).
