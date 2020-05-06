---
title: Quitar usuarios bloqueados del portal de Usuarios restringidos
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo quitar usuarios del portal de Usuarios restringidos en Office 365. Se agregan usuarios al portal de Usuarios restringidos para el envío correo no deseado saliente, normalmente porque la cuenta se ha visto comprometida.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 370d2ff5f98b507cd819a57e4b0de613de7ab395
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035425"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a>Quitar usuarios bloqueados del portal de Usuarios restringidos en Office 365

Si un usuario supera uno de los límites de envío saliente, como se especifica en [límites del servicio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) o en [directivas de correo no deseado saliente](configure-the-outbound-spam-policy.md), el usuario no puede enviar correos electrónicos, pero aún podrá recibirlos.

El usuario se agrega al portal de Usuarios restringidos en el Centro de seguridad y cumplimiento. Al intentar enviar un correo electrónico, el mensaje se devuelve en un informe de no entrega (también conocido como NDR o mensajes de devolución) con el código de error [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) y el texto siguiente:

> "No se pudo entregar el mensaje porque el remitente no es válido. La razón más común para este caso es que la dirección de correo electrónico sea sospechosa de que está enviando correo no deseado y ya no se le permite enviar correo.  Póngase en contacto con su administrador, para obtener ayuda. El servidor remoto devolvió "550 5.1.8 acceso denegado, remitente incorrecto de correo saliente".

Los administradores pueden quitar usuarios del portal de Remitentes restringidos en el Centro de seguridad y cumplimiento o en el PowerShell de Exchange Online.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Vaya directamente a la página **Usuarios restringidos**, use <https://protection.office.com/restrictedusers>.

- Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos. Para quitar usuarios del portal de Usuarios restringidos, debe ser miembro de los grupos de roles **Administración de la organización** o **Administrador de seguridad**. Para obtener acceso de solo lectura al portal de Usuarios restringidos, tiene que ser miembro del grupo de roles **Lector de seguridad**. Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

- Un remitente que supera los límites de correo electrónico saliente es un indicador de una cuenta comprometida. Antes de quitar el usuario del portal de Usuarios restringidos, asegúrese de seguir los pasos necesarios para recuperar el control de su cuenta. Para obtener más información, consulte [Responder a una cuenta de correo electrónico comprometida en Office 365](responding-to-a-compromised-email-account.md).

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a>Usar el Centro de seguridad y cumplimiento para quitar a un usuario de la lista de Usuarios restringidos

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Usuarios restringidos**.

2. Busque y seleccione al usuario que desee desbloquear. En la columna **Acciones**, haga clic en **Desbloquear**.

3. Una reaparición irá en los detalles de la cuenta cuyo envío está restringido. Debe revisar las recomendaciones para asegurarse de que está llevando a cabo las acciones adecuadas en caso de que la cuenta se ponga en peligro. Seleccione **Siguiente**cuando termine.

4. En la siguiente pantalla encontrará recomendaciones para evitar comprometer el futuro. Habilitar la autenticación multi factor (MFA) y cambiar las contraseñas es una buena defensa. Haga clic **desbloquear usuario**cuando haya finalizado.

5. Haga clic en **Sí** para confirmar el cambio.

   > [!NOTE]
   > Se pueden tardar 30 minutos o más antes de quitar las restricciones.

## <a name="verify-the-alert-settings-for-restricted-users"></a>Comprobar la configuración de alertas para usuarios restringidos

La directiva de alerta predeterminada denominada **Usuario con restricción de envío de correo electrónico** notificará automáticamente a los administradores cuando se bloquee el envío de correo saliente por parte de los usuarios. Puede comprobar esta configuración y agregar usuarios adicionales a los que notificar. Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en el centro de seguridad y cumplimiento](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Para que las alertas funcionen, debe activarse la búsqueda de registros de auditoría. Para obtener más información, consulte [ Desactivar o activar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

1. En el Centro de seguridad y cumplimiento, vaya a **Alertas** \> **Directivas de alerta**.

2. Busque y seleccione la alerta **Usuario con restricción de envío de correo electrónico**.

3. En el control flotante que aparece, compruebe o configure las siguientes opciones:

   - **Estado**: Compruebe que la alerta está activada![Activación](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

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

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-blockedsenderaddress).

Para quitar a un usuario de la lista de Usuarios restringidos, sustituya \<emailaddress\> por su dirección de correo electrónico y ejecute el siguiente comando:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-blockedsenderaddress).
