---
title: Acerca de los roles de administrador en el Centro de administración de Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
- adminvideo
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: Obtenga información sobre los roles de administrador, como el rol de administrador global o el rol de administrador de servicio. Los roles se asignan a funciones empresariales específicas y conceden permisos para realizar tareas específicas en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 5921762a927e4fd6ed0364da1366f947fb923e47
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785601"
---
# <a name="about-admin-roles-in-the-microsoft-365-admin-center"></a>Acerca de los roles de administrador en el Centro de administración de Microsoft 365

Consulte [ayuda de Microsoft 365 para pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

Microsoft 365 or Office 365 subscription comes with a set of admin roles that you can assign to users in your organization using the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>. Each admin role maps to common business functions and gives people in your organization permissions to do specific tasks in the admin centers.

El <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> le permite administrar roles de Azure AD y de Microsoft Intune. Sin embargo, estos roles son un subconjunto de los roles disponibles en el portal de Azure AD y en el centro de administración de Intune.

> [!TIP]
> Si necesita ayuda con los pasos descritos en este tema, considere la posibilidad de [trabajar con un especialista de Microsoft Small Business](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="watch-what-is-an-admin"></a>Ver: ¿Qué es un administrador?

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198028).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SRc0]

1. Una vez iniciada la sesión en Microsoft 365, seleccione el iniciador de aplicaciones. Si puede ver el botón Administrador, significa que usted es administrador.
1. Seleccione **Administrador** para ir al Centro de administración de Microsoft 365.
1. En el panel de navegación izquierdo, seleccione **Usuarios**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Usuarios activos.**</a>
1. Seleccione la persona a la que desea convertir en administrador. Los detalles del usuario aparecen en el cuadro de diálogo derecho.

## <a name="before-you-begin"></a>Antes de empezar

¿Busca una lista completa de descripciones detalladas de los roles para Azure AD que puede administrar en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>? Consulte Permisos de roles de administrador en Azure Active Directory. [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference).

¿Busca una lista completa de descripciones detalladas de los roles para Intune que puede administrar en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>?  Consulte [Control de acceso basado en roles (RBAC) con Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).

Para más información acerca de la asignación de roles en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, consulte [Asignar roles de administrador](assign-admin-roles.md).

## <a name="security-guidelines-for-assigning-roles"></a>Directrices de seguridad para asignar roles

Debido a que los administradores tienen acceso a archivos y datos confidenciales, le recomendamos que siga estas instrucciones para mantener los datos de su organización más seguros.

| Recomendación                  | ¿Por qué esto es importante?                 |
| :------------------- | :------------------- |
| Tener entre 2 y 4 administradores globales  | Como solo otro administrador global puede restablecer la contraseña de un administrador global, le recomendamos que tenga al menos 2 administradores globales en la organización en caso de que ocurra un bloqueo de la cuenta. Sin embargo, el administrador global tiene casi un acceso ilimitado a la configuración de su organización y a la mayoría de los datos, por lo que también recomendamos que no tenga más de 4 administradores globales, porque esto representaría una amenaza de seguridad. |
| Asignar el rol *menos permisivo*    | Asignar el rol *menos permisivo* significa conceder a los administradores solo el acceso que necesitan para realizar el trabajo. Por ejemplo, si desea que alguien restablezca las contraseñas de los empleados, no debe asignar el rol de administrador global ilimitado, sino asignar un rol de administrador limitado, como el de Administrador de contraseñas o Administrador del departamento de soporte técnico. Esto le ayudará a mantener sus datos seguros.                 |
| Requerir la autenticación multifactor para administradores                  |    En realidad es una buena idea requerir MFA para todos los usuarios, pero definitivamente se debe exigir a los administradores usar la MFA para iniciar sesión. La MFA permite que los usuarios introduzcan un segundo método de identificación para comprobar que son quienes dicen ser. Los administradores pueden tener acceso a una gran cantidad de datos de clientes y empleados y, si se requiere la MFA, incluso si la contraseña del administrador se ve comprometida, esta será inútil sin la segunda forma de identificación.  <br><br>Al activar la MFA, la próxima vez que el usuario inicie sesión, deberá proporcionar una dirección de correo electrónico y un número de teléfono alternativos para recuperar la cuenta.  <br> [Configurar la autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md)          |

Si recibe un mensaje en el centro de administración que le indica que no tiene permisos para editar una configuración o una página, es porque se le ha asignado un rol que no tiene ese permiso.

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>Roles más frecuentes del Centro de administración de Microsoft 365

En el Centro de administración de Microsoft 365, puede ir a <a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">**Asignaciones de roles**</a> y seleccionar cualquier rol para abrir su respectivo panel de detalles. Seleccione la pestaña **Permisos** para ver la lista detallada de lo que tienen permiso para hacer los administradores con ese rol asignado. Seleccione la pestaña **Asignado** o **Administradores asignados** para agregar usuarios a los roles.

Probablemente solo necesitará asignar los siguientes roles en su organización. De forma predeterminada, primero mostramos los roles que usan la mayoría de las organizaciones. Si no encuentra un rol, vaya a la parte inferior de la lista y seleccione **Mostrar todos por categoría**. (Para obtener información detallada, incluidos los cmdlets asociados a un rol, vea [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference)).

|Rol de administrador     |¿A quién se le debe asignar este rol?  |
|---------|---------|
|Administrador de facturación     |   Asigne el rol de administrador de facturación a los usuarios que hagan compras, administren suscripciones y solicitudes de servicio y supervisen el estado del servicio. <br><br> Los administradores de facturación también pueden:<br> - Administrar todos los aspectos de la facturación <br> - Crear y administrar vales de soporte técnico en el portal de Azure <br>  |
|Administrador de Exchange     |   Asigne el rol de administrador de Exchange a los usuarios que necesiten ver y administrar los buzones de correo de sus usuarios, los grupos de Microsoft 365 y Exchange Online. <br><br> Los administradores de Exchange también pueden:<br> - Recuperar elementos eliminados en un buzón de usuario <br> - Configurar los delegados "Enviar como" y "Enviar en nombre de" <br>  |
|Administrador global     |   Asigne el rol de administrador global a los usuarios que necesiten acceso global a la mayoría de las características de administración y datos en los servicios en línea de Microsoft. <br><br> Otorgar acceso global a un gran número de usuarios es un riesgo para la seguridad y le recomendamos que solo tenga entre 2 y 4 administradores globales. <br><br> Solo los administradores globales pueden:<br> - Restablecer las contraseñas de todos los usuarios <br> - Agregar y administrar dominios <br> - Desbloquear a otro administrador global <br> <br> **Nota:**   la persona que se registró en los servicios en línea de Microsoft se convierte automáticamente en administrador global. |
|Lector global    |   Assign the global reader role to users who need to view admin features and settings in admin centers that the global admin can view. The global reader admin can't edit any settings.   |
|Administrador de grupos     |   Asigne el rol de administrador de grupos a los usuarios que necesiten administrar la configuración de todos los grupos en los centros de administración, incluido el Centro de administración de Microsoft 365 y el portal de Azure Active Directory. <br><br> Los administradores de grupos pueden:<br> - Crear, editar, eliminar y restaurar los grupos de Microsoft 365 <br> - Crear y actualizar las directivas de creación, expiración y nomenclatura de grupos <br> - Crear, editar, eliminar y restaurar grupos de seguridad de Azure Active Directory| 
|Administrador del departamento de soporte técnico     |   Asigne el rol de administrador del departamento de soporte técnico a los usuarios que necesiten que hacer lo siguiente:<br> - Restablecer contraseñas <br> - Forzar a los usuarios a cerrar sesión <br> - Administrar solicitudes de servicio <br> - Supervisar el estado del servicio <br> <br> **Nota**: el administrador del departamento de soporte técnico solo puede ayudar a usuarios que no son administradores y a usuarios que tienen asignados estos roles: Lector de directorios, Invitador de usuarios invitados, Administrador del departamento de soporte técnico, Lector del centro de mensajes y Lector de informes.      |
|Administrador de licencias    |   Asigne el rol de administrador de licencias a los usuarios que necesiten asignar y quitar licencias a usuarios y editar su ubicación de uso. <br/><br/> Los administradores de licencias también pueden: <br> - Volver a procesar asignaciones de licencia para licencias basadas en grupos <br> - Asignar licencias de producto a grupos de licencias basadas en grupos  |
|Lector de privacidad del centro de mensajes    |   Asigne el rol de lector de privacidad del Centro de mensajes a los usuarios que necesiten leer mensajes y actualizaciones de privacidad y seguridad en el Centro de mensajes de Microsoft 365. Los lectores de privacidad del centro de mensajes pueden recibir notificaciones por correo electrónico relacionadas con la privacidad de los datos, en función de sus preferencias, y pueden cancelar la suscripción mediante las preferencias del Centro de mensajes. Solo los administradores globales y los lectores de privacidad del Centro de mensajes pueden leer los mensajes de privacidad de datos. Este rol no tiene permiso para ver, crear o administrar solicitudes de servicio. <br><br>Los lectores de privacidad del centro de mensajes también pueden: <br> - Supervisar todas las notificaciones en el Centro de mensajes, incluidos los mensajes de privacidad de datos <br> - Ver grupos, dominios y suscripciones   |
|Lector del Centro de mensajes |   Asigne el rol de Lector del Centro de mensajes a los usuarios que necesiten hacer lo siguiente: <br> - Supervisar las notificaciones del Centro de mensajes <br> - Obtener resúmenes semanales por correo electrónico de las publicaciones y actualizaciones del Centro de mensajes <br> - Compartir publicaciones del Centro de mensajes <br> - Tener acceso de solo lectura a servicios de Azure AD, como usuarios y grupos|
|Administrador de aplicaciones de Office    |   Asigne el rol de administrador de aplicaciones de Office a los usuarios que necesiten hacer lo siguiente: <br> - Uso del servicio de directivas en la nube para Microsoft 365 para crear y administrar directivas basadas en la nube para Office <br> - Crear y administrar solicitudes de servicio <br> - Administrar el contenido de Novedades que los usuarios ven en sus aplicaciones de Office   <br> - Supervisar el estado del servicio  |
|Administrador de contraseñas  |   Asigne el rol de administrador de contraseñas a un usuario que necesite restablecer las contraseñas de los no administradores y los administradores de contraseñas.   |
|Administrador de Power Platform |   Asigne el rol de administrador de Power Platform a los usuarios que necesiten hacer lo siguiente: <br> - Administrar todas las características de administración de Power Apps, Power Automate y prevención de pérdida de datos de Microsoft Purview <br> - Crear y administrar solicitudes de servicio <br> - Supervisar el estado del servicio  |
|Lector de informes |   Asigne el rol de lector de informes a los usuarios que necesiten hacer lo siguiente: <br> - Ver datos de uso e informes de actividad en el Centro de administración de Microsoft 365 <br> - Obtener acceso al paquete de contenido de adopción de Power BI <br> - Obtener acceso a los informes de inicio de sesión y a la actividad en Azure AD <br> - Ver datos devueltos por la API de informes de Microsoft Graph|
|Administrador de soporte técnico del servicio   |   Asigne el rol de administrador de soporte técnico de servicio como un rol adicional a los administradores o usuarios que necesiten hacer, además de su rol de administrador habitual, lo siguiente: <br> - Abrir y administrar solicitudes de servicio <br> - Ver y compartir publicaciones del centro de mensajes <br> - Supervisar el estado del servicio   |
|Administrador de SharePoint    |   Asigne el rol de administrador de SharePoint a los usuarios que necesiten acceder y administrar el centro de administración de SharePoint Online. <br><br>Los administradores de SharePoint también pueden: <br> - Crear y eliminar sitios <br> - Administrar colecciones de sitios y la configuración global de SharePoint   |
|Administrador de Teams    |   Asigne el rol de administrador de Teams a los usuarios que necesiten acceder y administrar el Centro de administración de Teams. <br><br>El administrador de Teams también puede: <br> - Administrar reuniones <br> - Administrar puentes de conferencia <br> - Administrar la configuración de toda la organización, incluida la federación, la actualización de equipos y la configuración de cliente de equipos   |
|Administrador de usuarios     |    Asigne el rol de administrador de usuarios a los usuarios que necesiten hacer lo siguiente para todos los usuarios: <br> - Agregar usuarios y grupos <br> - Asignar licencias <br> - Administrar las propiedades de la mayoría de los usuarios <br> - Crear y administrar vistas de usuarios <br> - Actualizar las directivas de expiración de contraseña <br> - Administrar solicitudes de servicio <br> - Supervisar el estado del servicio <br><br>  El administrador de usuario también puede realizar las siguientes acciones para los usuarios que no sean administradores y para los usuarios que tengan asignados los siguientes roles: Lector de directorios, Invitador de usuarios invitados, Administrador del departamento de soporte técnico, Lector del centro de mensajes y Lector de informes: <br> - Administrar nombres de usuario<br> - Eliminar y restaurar usuarios<br> - Restablecer contraseñas <br> - Forzar a los usuarios a cerrar sesión <br> - Actualizar claves de dispositivo (FIDO)   |

## <a name="delegated-administration-for-microsoft-partners"></a>Administración delegada para Microsoft Partners

If you're working with a Microsoft partner, you can assign them admin roles. They, in turn, can assign users in your company, or their company, admin roles. You might want them to do this, for example, if they're setting up and managing your online organization for you.
  
Un partner puede asignar estos roles: 
  
- **Agente de administración** Privilegios equivalentes a un administrador global, excepto para administrar la autenticación multifactor mediante el Centro de partners.

- **Agente del departamento de soporte técnico** Tiene privilegios equivalentes a los de un administrador del departamento de soporte técnico.

Before the partner can assign these roles to users, you must add the partner as a delegated admin to your account. This process is initiated by an authorized partner. The partner sends you an email to ask you if you want to give them permission to act as a delegated admin. For instructions, see [Authorize or remove partner relationships](../misc/add-partner.md).
  
## <a name="related-content"></a>Contenido relacionado

[Asignar roles de administrador](assign-admin-roles.md) (artículo)\
[Roles de Azure AD en el Centro de administración de Microsoft 365](azure-ad-roles-in-the-mac.md) (artículo)\
[Informes de actividad del Centro de administración de Microsoft 365](../activity-reports/activity-reports.md) (artículo)\
[Rol de administrador de Exchange Online](about-exchange-online-admin-role.md) (artículo)
