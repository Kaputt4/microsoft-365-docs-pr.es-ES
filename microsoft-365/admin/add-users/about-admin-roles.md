---
title: Acerca de los roles de administrador en el Centro de administración de Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: Los roles de administrador se asignan a funciones empresariales y dan permisos para realizar tareas específicas en el centro de administración. Por ejemplo, el Administrador de servicios abre vales de soporte técnico con Microsoft.
ms.custom: okr_smb
ms.openlocfilehash: 446af9ad49649487f4df1982613f8e84fdf39910
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857196"
---
# <a name="about-admin-roles"></a>Acerca de los roles de administrador

Su suscripción incluye un conjunto de roles de administrador que puede asignar a los usuarios de su organización. Cada rol de administrador se asigna a una función empresarial común y da permisos a los usuarios de su organización para realizar tareas específicas en los centros de administración. Para más información, vea [Asignar roles de administrador](assign-admin-roles.md).

> [!TIP] 
> ¿Busca las descripciones detalladas de los roles? Consulte [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

## <a name="things-to-consider"></a>Aspectos que se deben tener en cuenta...

Debido a que los administradores tienen acceso a archivos y datos confidenciales, le recomendamos que siga estas instrucciones para mantener los datos de su organización más seguros.

| Recomendación                  | ¿Por qué esto es importante?                 |
| :------------------- | :------------------- |
| Tener entre 2 y 4 administradores globales  | Como solo otro administrador global puede restablecer la contraseña de un administrador global, le recomendamos que tenga al menos 2 administradores globales en la organización en caso de que ocurra un bloqueo de la cuenta. Sin embargo, el administrador global tiene casi un acceso ilimitado a la configuración de su organización y a la mayoría de los datos, por lo que también recomendamos que no tenga más de 4 administradores globales, porque esto representaría una amenaza de seguridad. |
| Asignar el rol *menos permisivo*    | Asignar el rol *menos permisivo* significa conceder a los administradores solo el acceso que necesitan para realizar el trabajo. Por ejemplo, si desea que alguien restablezca las contraseñas de los empleados, no debe asignar el rol de administrador global ilimitado, sino asignar un rol de administrador limitado, como el de Administrador de contraseñas o Administrador del departamento de soporte técnico. Esto le ayudará a mantener sus datos seguros.                 |
| Requerir la autenticación multifactor para administradores                  |    En realidad es una buena idea requerir MFA para todos los usuarios, pero definitivamente se debe exigir a los administradores usar la MFA para iniciar sesión. La MFA permite que los usuarios introduzcan un segundo método de identificación para comprobar que son quienes dicen ser. Los administradores pueden tener acceso a una gran cantidad de datos de clientes y empleados y, si se requiere la MFA, incluso si la contraseña del administrador se ve comprometida, esta será inútil sin la segunda forma de identificación.  <br><br>Al activar la MFA, la próxima vez que el usuario inicie sesión, deberá proporcionar una dirección de correo electrónico y un número de teléfono alternativos para recuperar la cuenta.  <br> [Configurar la autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md)          |

  
## <a name="some-roles-are-missing-from-active-users--manage-admin-roles-where-did-they-go"></a>Faltan algunos roles en Usuarios activos > Administrar roles de administrador. ¿Dónde se encuentran?
De forma predeterminada, primero mostramos los roles que usan la mayoría de las organizaciones. Si no encuentra un rol, vaya a la parte inferior de la lista y seleccione **Ver más roles**.

## <a name="how-can-i-tell-which-permissions-are-assigned-to-me"></a>¿Cómo puedo saber qué permisos fueron asignados a mí?
Si recibe un mensaje en el centro de administración que le indica que no tiene permisos para editar una configuración o una página, es porque se le ha asignado un rol que no tiene ese permiso.

## <a name="what-about-the-azure-active-directory-roles"></a>¿Y qué hay sobre los roles de Azure Active Directory? 

El portal de Azure tiene más roles que los que están disponibles en el Centro de administración de Microsoft 365. Si tiene una empresa grande, es posible que haya roles en el portal de Azure que cubran las necesidades de su organización.

Para obtener una lista y la descripción de todos los roles de Azure Active Directory, consulte [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Un usuario que tenga asignado un rol de administrador tendrá el mismo nivel de acceso a los servicios en la nube a los que esté suscrita la organización, independientemente de si asigna el rol en el Centro de administración de Microsoft 365 o en el portal de Azure, o bien mediante el módulo de Azure AD para Windows PowerShell.
  
## <a name="roles-available-in-the-microsoft-365-admin-center"></a>Roles disponibles en el Centro de administración de Microsoft 365

El Centro de administración de Microsoft 365 le permite administrar más de 30 roles de Azure AD. Sin embargo, estos roles son un subconjunto de los roles disponibles en el portal de Azure.

::: moniker range="o365-worldwide"

En el centro de administración, puede ir a **Roles** y después, seleccionar cualquier rol para abrir su respectivo panel de detalles. Seleccione la pestaña **Permisos** para ver la lista detallada de lo que tienen permiso para hacer los administradores con ese rol asignado.

::: moniker-end

Probablemente solo necesitará asignar los siguientes roles en su organización. (Para obtener información detallada, incluidos los cmdlets asociados a un rol, consulte [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)).

|Rol de administrador     |¿A quién se le debe asignar este rol?  |
|---------|---------|
|Administrador de Exchange     |   Asigne el rol de administrador de Exchange a los usuarios que necesiten ver y administrar los buzones de correo de su usuario, los grupos de Office 365 y Exchange Online. <br><br> Los administradores de Exchange también pueden:<br> - Recuperar elementos eliminados en un buzón de usuario <br> - Configurar los delegados "Enviar como" y "Enviar en nombre de" <br>  |
|Administrador global     |   Asigne el rol de administrador global a los usuarios que necesiten acceso global a la mayoría de las características de administración y datos en los servicios en línea de Microsoft. <br><br> Otorgar acceso global a un gran número de usuarios es un riesgo para la seguridad y le recomendamos que solo tenga entre 2 y 4 administradores globales. <br><br> Solo los administradores globales pueden:<br> - Restablecer las contraseñas de todos los usuarios <br> - Agregar y administrar dominios <br> <br> **Nota:**   la persona que se registró en los servicios en línea de Microsoft se convierte automáticamente en administrador global. |
|Lector global    |   Asigne el rol de lector global a los usuarios que necesiten ver la configuración y las funciones de administración en los centros de administración que el administrador global puede ver. El administrador del lector global no puede editar ninguna configuración.   |
|Administrador de grupos     |   Asigne el rol de administrador de grupos a los usuarios que necesiten administrar la configuración de todos los grupos en los centros de administración, incluido el Centro de administración de Microsoft 365 y el portal de Azure Active Directory. <br><br> Los administradores de grupos pueden:<br> - Crear, editar, eliminar y restaurar Grupos de Office 365 <br> - Crear y actualizar las directivas de creación, expiración y nomenclatura de grupos <br> - Crear, editar, eliminar y restaurar grupos de seguridad de Azure Active Directory| 
|Administrador del departamento de soporte técnico     |   Asigne el rol de administrador del departamento de soporte técnico a los usuarios que necesiten que hacer lo siguiente:<br> - Restablecer contraseñas <br> - Forzar a los usuarios a cerrar sesión <br> - Administrar solicitudes de servicio <br> - Supervisar el estado del servicio <br> <br> **Nota**: el administrador del departamento de soporte técnico solo puede ayudar a usuarios que no son administradores y a usuarios que tienen asignados estos roles: Lector de directorios, Invitador de usuarios invitados, Administrador del departamento de soporte técnico, Lector del centro de mensajes y Lector de informes.      |
|Administrador de aplicaciones de Office    |   Asigne el rol de administrador de aplicaciones de Office a los usuarios que necesiten hacer lo siguiente: <br> - Usar el servicio de directivas en la nube de Office para crear y administrar directivas basadas en la nube para Office <br> - Crear y administrar solicitudes de servicio <br> - Administrar el contenido de Novedades que los usuarios ven en sus aplicaciones de Office   <br> - Supervisar el estado del servicio  |
|Administrador de servicios    |   Asigne el rol de administrador de servicios como un rol adicional para administradores o usuarios que necesiten hacer lo siguiente, pero el rol que tienen asignado no lo incluye: <br> - Abrir y administrar solicitudes de servicio <br> - Ver y compartir publicaciones del centro de mensajes   |
|Administrador de SharePoint    |   Asigne el rol de administrador de SharePoint a los usuarios que necesiten acceder y administrar el centro de administración de SharePoint Online. <br><br>Los administradores de SharePoint también pueden: <br> - Crear y eliminar sitios <br> - Administrar colecciones de sitios y la configuración global de SharePoint   |
|Administrador de servicios de Teams    |   Asigne el rol de administrador de servicios de Teams a los usuarios que necesiten acceder y administrar el centro de administración de Teams. <br><br>Los administradores de servicio de Teams también pueden: <br> - Administrar reuniones <br> - Administrar puentes de conferencia <br> - Administrar la configuración de toda la organización, incluida la federación, la actualización de equipos y la configuración de cliente de equipos   |
|Administrador de usuarios     |    Asigne el rol de administrador de usuarios a los usuarios que necesiten hacer lo siguiente para todos los usuarios: <br> - Agregar usuarios y grupos <br> - Asignar licencias <br> - Administrar las propiedades de la mayoría de los usuarios <br> - Crear y administrar vistas de usuarios <br> - Actualizar las directivas de expiración de contraseña <br> - Administrar solicitudes de servicio <br> - Supervisar el estado del servicio <br><br>  El administrador de usuario también puede realizar las siguientes acciones para los usuarios que no sean administradores y para los usuarios que tengan asignados los siguientes roles: Lector de directorios, Invitador de usuarios invitados, Administrador del departamento de soporte técnico, Lector del centro de mensajes y Lector de informes: <br> - Administrar nombres de usuario<br> - Eliminar y restaurar usuarios<br> - Restablecer contraseñas <br> - Forzar a los usuarios a cerrar sesión <br> - Actualizar claves de dispositivo (FIDO)   |

### <a name="all-roles"></a>Todos los roles

 A continuación, presentamos una lista de todos los roles de administrador disponibles en el Centro de administración de Microsoft 365.

|Rol de administrador     |Descripción  |
|---------|---------|
|Administrador de aplicación     |    Tiene acceso completo a las aplicaciones empresariales, los registros de aplicaciones y la configuración del proxy de aplicación.     |
|Desarrollador de la aplicación     |    Crea registros de aplicaciones y consiente el acceso a la aplicación en su propio nombre.     |
|Administrador de autenticación     |    Puede requerir que los usuarios vuelvan a registrar la autenticación de las credenciales que no son de contraseña, como la MFA.     |
|Administrador de Azure Information Protection     |   Administra las etiquetas para la directiva de Azure Information Protection, administra las plantillas de protección y activa la protección.       |
|Administrador de facturación     |    Realiza las compras, administra las suscripciones, las solicitudes de servicio y supervisa el estado del servicio.     |
|Administrador de aplicaciones en la nube     | Tiene acceso completo a las aplicaciones empresariales y los registros de aplicaciones. Sin proxy de aplicación.     |
|Administrador de dispositivos en la nube     |    Habilita, deshabilita y elimina dispositivos y puede leer claves de BitLocker de Windows 10.     |
|Administrador de cumplimiento     |    Administra los requisitos reglamentarios y los casos de eDiscovery, y mantiene el gobierno de datos de las ubicaciones, identidades y aplicaciones.     |
|Administrador de datos de cumplimiento     |    Realiza un seguimiento de los datos, se asegura de que estén protegidos, obtiene información sobre los problemas y ayuda a mitigar el riesgo.     |
|Administrador de acceso condicional     |   Administra la configuración de acceso condicional de Azure Active Directory, pero no la directiva de acceso condicional de Exchange ActiveSync.      |
|Aprobador del acceso a la Caja de seguridad del cliente     |      Administra las solicitudes de Caja de seguridad del cliente y puede activarla o desactivarla.   |
|Administrador de análisis de escritorio     |   Puede administrar y acceder a herramientas y servicios de administración de escritorio.      |
|Administrador de Dynamics 365     |  Posee acceso completo a Microsoft Dynamics 365 Online, administra las solicitudes de servicio y supervisa el estado del servicio.       |
|Administrador de Exchange     |  Posee acceso completo a Exchange Online, crea y administra grupos, administra solicitudes de servicio y supervisa el estado del servicio.    |
|Administrador del proveedor de identidad externa    |     Configura los proveedores de identidades para su uso en federación directa.    |
|Administrador global     |    Tiene acceso ilimitado a todas las características de administración y a la mayoría de los datos en todos los centros de administración.     |
|Lector global     |    Tiene acceso de solo lectura a todas las características de administración y a la mayoría de los datos en los centros de administración. Para obtener una descripción detallada de los derechos de acceso y las limitaciones de este rol, consulte [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).    |
|Administrador de grupos   |Permite crear grupos y administrar la configuración de todos los grupos en los centros de administración.|
|Invitador de usuarios invitados     |    Administra las invitaciones de usuarios invitados B2B de Azure Active Directory.     |
|Administrador del departamento de soporte técnico     | Restablece las contraseñas y vuelve a autenticarlas para todos los usuarios que no sean administradores y para algunos roles de administrador. Administra solicitudes de servicio y supervisa el estado del servicio.      |
|Administrador de Intune     | Tiene acceso completo a Intune, administra usuarios y dispositivos para asociar directivas. También crea y administra grupos.      |
|Administrador de Kaizala     |    Tiene acceso completo a todas las características de administración y datos de Kaizala, y administra las solicitudes de servicio.     |
|Administrador de licencias     |     Asigna y elimina las licencias de los usuarios y edita su ubicación de uso.    |
|Lector de privacidad del centro de mensajes     |    Accede a los mensajes de privacidad de datos en el Centro de mensajes y recibe notificaciones por correo electrónico.     |
|Lector del centro de mensajes     | Lee y comparte mensajes habituales en el Centro de mensajes, obtiene resúmenes de correo electrónico semanales, y tiene acceso de solo lectura a usuarios, grupos, dominios y suscripciones.     |
|Administrador de aplicaciones de Office    |   Administra las directivas basadas en la nube para Office y el contenido Novedades que los usuarios ven en sus aplicaciones de Office.   |
|Administrador de Power BI    |   Posee acceso completo a las tareas de administración de Power BI, administra solicitudes de servicio y supervisa el estado del servicio.   |
|Administrador de Power Platform     |    Posee acceso completo a Microsoft Dynamics 365, PowerApps, directivas de prevención de pérdida de datos y Microsoft Flow.     |
|Administrador de roles con privilegios     |    Administra las asignaciones de roles y todas las características de control de acceso de Privileged Identity Management.     |
|Lector de informes     |   Lee los datos de informes de uso del panel informes, el paquete de contenido para la adopción de PowerBI, los informes de inicio de sesión y la API de informes de Microsoft Graph.      |
|Administrador de búsqueda     |    Tiene acceso completo a Microsoft Search, asigna los roles de administrador y editor de búsqueda, administra el contenido editorial, supervisa el estado del servicio y crea solicitudes de servicio.     |
|Editor de búsqueda     |    Solo puede crear, editar y eliminar contenido para Microsoft Search, como marcadores, preguntas y respuestas, y ubicaciones.     |
|Administrador de seguridad     |    Controla la seguridad de la organización, administra las directivas de seguridad, revisa los análisis e informes de seguridad y supervisa el panorama de las amenazas.     |
|Operador de seguridad     |    Investiga y responde a las alertas de seguridad, administra las características en el centro de Protección de Identidades y supervisa el estado del servicio.     |
|Lector de seguridad     |    Tiene acceso de solo lectura a las características de seguridad, informes de inicio de sesión y registros de auditoría.     |
|Administrador de soporte técnico del servicio     |    Crea solicitudes de servicio para servicios de Office 365, Microsoft 365 y Azure, y supervisa el estado del servicio.     |
|Administrador de SharePoint     |    Posee acceso completo a SharePoint Online, administra grupos de Office 365, administra solicitudes de servicio y supervisa el estado del servicio.     |
|Administrador de Skype Empresarial     | Tiene acceso completo a todas las características de Teams y Skype, y a los atributos de usuario de Skype. También administra solicitudes de servicio y supervisa el estado del servicio.      |
|Administrador de Teams     |    Posee acceso completo al centro de administración de Teams y Skype, administra grupos de Office 365, solicitudes de servicio y supervisa el estado del servicio.     |
|Administrador de comunicaciones de Teams     |    Asigna números de teléfono, crea y administra las directivas de voz y reuniones, y lee los análisis de llamadas.     |
|Ingeniero de soporte técnico de comunicaciones de Teams     |    Lee los detalles del registro de llamadas de todos los participantes de la llamada para solucionar problemas de comunicación.     |
|Especialista en soporte técnico de comunicaciones de Teams     |    Lee los detalles de las llamadas de usuario solo para un usuario específico con el fin de solucionar problemas de comunicación.|
|Administrador de usuarios     |   Restablece las contraseñas de usuario, crea y administra usuarios y grupos, incluyendo filtros, administra solicitudes de servicio y supervisa el estado del servicio.|

## <a name="delegated-administration-for-microsoft-partners"></a>Administración delegada para Microsoft Partners

Si está trabajando con un partner de Microsoft, puede asignarle roles de administrador. Por su parte, los partners pueden asignar roles de administrador a los usuarios en sus propias empresas o bien en la suya. Es posible que quiera que lo hagan si, por ejemplo, están configurando y administrando la organización online por usted.
  
Un partner puede asignar estos roles: 
  
- Administración completa, que tiene privilegios equivalentes a los de un administrador global, con la excepción de administrar la autenticación multifactor mediante el Centro de Partners.
    
- Administración limitada, que tiene privilegios equivalentes a los de un administrador del departamento de soporte técnico.

Antes de que el partner pueda asignar estos roles a los usuarios, usted debe agregarlo como un administrador delegado a su cuenta. Este proceso puede iniciarlo un partner autorizado. El partner le envía un correo electrónico para preguntarle si quiere concederle permiso para actuar como administrador delegado. Para obtener instrucciones, consulte [Autorizar o quitar relaciones de partner](https://support.office.com/article/201ccb3b-6011-4bf1-a6b2-84e7cc1ee2d0.aspx).
  
## <a name="related-articles"></a>Artículos relacionados

[Asignar roles de administrador](assign-admin-roles.md)
  
[Informes de actividad en el Centro de administración de Microsoft 365](../activity-reports/activity-reports.md)
