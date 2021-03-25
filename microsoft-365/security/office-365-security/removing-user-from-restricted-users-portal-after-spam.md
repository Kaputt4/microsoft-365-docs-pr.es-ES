---
title: Quitar usuarios bloqueados del portal de Usuarios restringidos
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo quitar usuarios del portal de Usuarios restringidos en Office 365. Se agregan usuarios al portal de Usuarios restringidos para el envío correo no deseado saliente, normalmente porque la cuenta se ha visto comprometida.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 32748d717762d7af727a1583226b6d47ee7697c6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205742"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a>Quitar usuarios bloqueados del portal de Usuarios restringidos en Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Si un usuario supera uno de los límites de envío saliente, como se especifica en [límites del servicio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) o en [directivas de correo no deseado saliente](configure-the-outbound-spam-policy.md), el usuario no puede enviar correos electrónicos, pero aún podrá recibirlos.

El usuario se agrega al portal de Usuarios restringidos en el Centro de seguridad y cumplimiento. Al intentar enviar un correo electrónico, el mensaje se devuelve en un informe de no entrega (también conocido como NDR o mensajes de devolución) con el código de error [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) y el texto siguiente:

> "No se pudo entregar el mensaje porque el remitente no es válido. La razón más común para este caso es que la dirección de correo electrónico sea sospechosa de que está enviando correo no deseado y ya no se le permite enviar correo.  Póngase en contacto con su administrador, para obtener ayuda. El servidor remoto devolvió "550 5.1.8 acceso denegado, remitente incorrecto de correo saliente".

Los administradores pueden quitar usuarios del portal de Remitentes restringidos en el Centro de seguridad y cumplimiento o en el PowerShell de Exchange Online.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Vaya directamente a la página **Usuarios restringidos**, use <https://protection.office.com/restrictedusers>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para quitar usuarios del portal de Usuarios restringidos, debe ser miembro de los grupos de roles **Administración de la organización** o **Administrador de seguridad**.
  - Para obtener acceso de solo lectura al portal de Usuarios restringidos, tiene que ser miembro de los grupos de roles **Lector global** o **Lector de seguridad**.

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Un remitente que supera los límites de correo electrónico saliente es un indicador de una cuenta comprometida. Antes de quitar el usuario del portal de Usuarios restringidos, asegúrese de seguir los pasos necesarios para recuperar el control de su cuenta. Para obtener más información, consulte [Responder a una cuenta de correo electrónico comprometida en Office 365](responding-to-a-compromised-email-account.md).

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a>Usar el Centro de seguridad y cumplimiento para quitar a un usuario de la lista de Usuarios restringidos

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Usuarios restringidos**.

2. Busque y seleccione al usuario que desee desbloquear. En la columna **Acciones**, haga clic en **Desbloquear**.

3. Una reaparición irá en los detalles de la cuenta cuyo envío está restringido. Debe revisar las recomendaciones para asegurarse de que está llevando a cabo las acciones adecuadas en caso de que la cuenta se ponga en peligro. Seleccione **Siguiente** cuando termine.

4. En la siguiente pantalla encontrará recomendaciones para evitar comprometer el futuro. Habilitar la autenticación multi factor (MFA) y cambiar las contraseñas es una buena defensa. Haga clic **desbloquear usuario** cuando haya finalizado.

5. Haga clic en **Sí** para confirmar el cambio.

   > [!NOTE]
   > Puede que el usuario pasen hasta 24 horas hasta la eliminación de todas las restricciones del usuario.

## <a name="verify-the-alert-settings-for-restricted-users"></a>Comprobar la configuración de alertas para usuarios restringidos

La directiva de alerta predeterminada denominada **Usuario con restricción de envío de correo electrónico** notificará automáticamente a los administradores cuando se bloquee el envío de correo saliente por parte de los usuarios. Puede comprobar esta configuración y agregar usuarios adicionales a los que notificar. Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en el centro de seguridad y cumplimiento](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Para que las alertas funcionen, debe activarse la búsqueda de registros de auditoría. Para obtener más información, consulte [ Desactivar o activar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

1. En el Centro de seguridad y cumplimiento, vaya a **Alertas** \> **Directivas de alerta**.

2. Busque y seleccione la alerta **Usuario con restricción de envío de correo electrónico**.

3. En el control flotante que aparece, compruebe o configure las siguientes opciones:

   - **Estado**: Compruebe que la alerta está activada![Activación](../../media/scc-toggle-on.png).

   - **Destinatarios de correo electrónico**: Haga clic en **Editar** y compruebe o configure las siguientes opciones en el control flotante **Editar destinatarios** que aparece:

     - **Enviar notificaciones de correo electrónico**: Compruebe que la casilla de verificación está (**Activada**).

     - **Destinatarios de correo electrónico**: El valor predeterminado es **TenantAdmins** (lo que significa miembros de **Administrador global**). Para agregar más destinatarios, haga clic en un área en blanco del cuadro. Se mostrará una lista de destinatarios y puede empezar a escribir un nombre para filtrar y seleccionar un destinatario. Para quitar un destinatario existente del cuadro, haga clic en el ![Icono quitar](../../media/scc-remove-icon.png) junto a su nombre.

     - **Límite diario de notificaciones**: El valor predeterminado es **Sin límite**, pero puede seleccionar un límite para el número máximo de notificaciones al día.

     Cuando haya terminado, haga clic en **Guardar**.

4. Vuelva al control flotante **Usuario con restricción de envío de correo electrónico** y haga clic en **Cerrar**.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Usar PowerShell de Exchange Online para ver y quitar usuarios de la lista de Usuarios restringidos

Para ver la lista de usuarios a los que se les ha restringido el envío de correo electrónico, ejecute el siguiente comando:

```powershell
Get-BlockedSenderAddress
```

Para ver los detalles de un usuario específico, sustituya \<emailaddress\> por su dirección de correo electrónico y ejecute el siguiente comando:

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).

Para quitar a un usuario de la lista de Usuarios restringidos, sustituya \<emailaddress\> por su dirección de correo electrónico y ejecute el siguiente comando:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).