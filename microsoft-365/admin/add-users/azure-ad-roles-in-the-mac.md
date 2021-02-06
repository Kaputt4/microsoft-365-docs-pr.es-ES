---
title: Roles de Azure Active Directory en el Centro de administración de Microsoft 365
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
ms.custom:
- AdminSurgePortfolio
description: Administre estos roles de administrador de Azure en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 7a4e28667bc16d6619fe87451cd48ea77d89c81d
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126110"
---
# <a name="azure-active-directory-roles-in-the-microsoft-365-admin-center"></a>Roles de Azure Active Directory en el Centro de administración de Microsoft 365

El Centro de administración de Microsoft 365 le permite administrar más de 30 roles de Azure AD. Sin embargo, estos roles son un subconjunto de los roles disponibles en el portal de Azure. Si tiene una empresa grande, es posible que haya roles en el portal de Azure que cubran las necesidades de su organización. ¿Busca las descripciones detalladas de los roles para Azure AD? Consulte [Permisos de rol de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Un usuario que tenga asignado un rol de administrador tendrá el mismo nivel de acceso a los servicios en la nube a los que esté suscrita la organización, independientemente de si asigna el rol en el Centro de administración de Microsoft 365 o en el portal de Azure, o bien mediante el módulo de Azure AD para Windows PowerShell.

::: moniker range="o365-worldwide"

En el Centro de administración de Microsoft 365, puede ir a **Roles** y seleccionar cualquier rol para abrir su respectivo panel de detalles. Seleccione la pestaña **Permisos** para ver la lista detallada de lo que tienen permiso para hacer los administradores con ese rol asignado. Seleccione la pestaña **Asignado** o **Administradores asignados** para agregar usuarios a los roles. Para más información acerca de la asignación de roles en el Centro de administración de Microsoft 365, consulte [Asignar roles de administrador](assign-admin-roles.md).

::: moniker-end

## <a name="all-azure-ad-roles"></a>Todos los roles de Azure AD

A continuación, presentamos una lista de todos los roles de administrador disponibles en el Centro de administración de Microsoft 365. ¿Busca descripciones detalladas de los roles de administrador de Microsoft 365? Consulte [Acerca de los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).

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
|Administrador de Insights     | Administra todos los aspectos de la aplicación Microsoft 365 Insights, lee información de Azure Active Directory, puede supervisar el estado del servicio y crear y administrar solicitudes de servicio.      |
|Administrador empresarial de Insights     | Lee informes y detalles en la aplicación de Microsoft 365 Insights.      |
|Administrador de Intune     | Tiene acceso completo a Intune, administra usuarios y dispositivos para asociar directivas. También crea y administra grupos.      |
|Administrador de Kaizala     |    Tiene acceso completo a todas las características de administración y datos de Kaizala, y administra las solicitudes de servicio.     |
|Administrador de licencias     |     Asigna y elimina las licencias de los usuarios y edita su ubicación de uso.    |
|Lector de privacidad del centro de mensajes     |    Accede a los mensajes de privacidad de datos en el Centro de mensajes y recibe notificaciones por correo electrónico.     |
|Lector del centro de mensajes     | Lee y comparte mensajes habituales en el Centro de mensajes, obtiene resúmenes de correo electrónico semanales, y tiene acceso de solo lectura a usuarios, grupos, dominios y suscripciones.     |
|Administrador de aplicaciones de Office    |   Administra las directivas basadas en la nube para Office y el contenido Novedades que los usuarios ven en sus aplicaciones de Office.   |
|Administrador de contraseñas    |   Restablecer las contraseñas de los usuarios que no sean administradores o miembros de los roles siguientes: lectores de directorio, invitado invitar, administrador de contraseñas. Este rol no puede conceder la capacidad para administrar solicitudes de servicio o supervisar el estado del servicio.   |
|Administrador de Power BI    |   Posee acceso completo a las tareas de administración de Power BI, administra solicitudes de servicio y supervisa el estado del servicio.   |
|Administrador de Power Platform     |    Posee acceso completo a Microsoft Dynamics 365, PowerApps, directivas de prevención de pérdida de datos y Microsoft Flow.     |
|Administrador de roles con privilegios     |    Administra las asignaciones de roles y todas las características de control de acceso de Privileged Identity Management.     |
|Administrador de autenticación con privilegios     |    Restablece contraseñas, actualiza credenciales que no son contraseñas, fuerza el uso del cierre de sesión, supervisa el estado del servicio y administra las solicitudes de servicio.     |
|Lector de informes     |   Lee los datos de informes de uso del panel informes, el paquete de contenido para la adopción de PowerBI, los informes de inicio de sesión y la API de informes de Microsoft Graph.      |
|Administrador de búsqueda     |    Tiene acceso completo a Microsoft Search, asigna los roles de administrador y editor de búsqueda, administra el contenido editorial, supervisa el estado del servicio y crea solicitudes de servicio.     |
|Editor de búsqueda     |    Solo puede crear, editar y eliminar contenido para Microsoft Search, como marcadores, preguntas y respuestas, y ubicaciones.     |
|Administrador de seguridad     |    Controla la seguridad de la organización, administra las directivas de seguridad, revisa los análisis e informes de seguridad y supervisa el panorama de las amenazas.     |
|Operador de seguridad     |    Investiga y responde a las alertas de seguridad, administra las características en el centro de Protección de Identidades y supervisa el estado del servicio.     |
|Lector de seguridad     |    Tiene acceso de solo lectura a las características de seguridad, informes de inicio de sesión y registros de auditoría.     |
|Administrador de soporte técnico del servicio     |    Crea solicitudes de servicio para servicios de Office 365, Microsoft 365 y Azure, y supervisa el estado del servicio.     |
|Administrador de SharePoint     |    Posee acceso completo a SharePoint Online, administra los grupos de Microsoft 365, administra las solicitudes de servicio y supervisa el estado del servicio.     |
|Administrador de Skype Empresarial     | Tiene acceso completo a todas las características de Teams y Skype, y a los atributos de usuario de Skype. También administra solicitudes de servicio y supervisa el estado del servicio.      |
|Administrador de Teams     |    Posee acceso completo al centro de administración de Teams y Skype, administra los grupos de Microsoft 365, las solicitudes de servicio y supervisa el estado del servicio.     |
|Administrador de comunicaciones de Teams     |    Asigna números de teléfono, crea y administra las directivas de voz y reuniones, y lee los análisis de llamadas.     |
|Ingeniero de soporte técnico de comunicaciones de Teams     |    Lee los detalles del registro de llamadas de todos los participantes de la llamada para solucionar problemas de comunicación.     |
|Especialista en soporte técnico de comunicaciones de Teams     |    Lee los detalles de las llamadas de usuario solo para un usuario específico con el fin de solucionar problemas de comunicación.|
|Administrador de usuarios     |   Restablece las contraseñas de usuario, crea y administra usuarios y grupos, incluyendo filtros, administra solicitudes de servicio y supervisa el estado del servicio.|

## <a name="delegated-administration-for-microsoft-partners"></a>Administración delegada para Microsoft Partners

Si está trabajando con un partner de Microsoft, puede asignarle roles de administrador. Por su parte, los partners pueden asignar roles de administrador a los usuarios en sus propias empresas o bien en la suya. Es posible que quiera que lo hagan si, por ejemplo, están configurando y administrando la organización online por usted.
  
Un partner puede asignar estos roles: 

- Administración completa, que tiene privilegios equivalentes a los de un administrador global, con la excepción de administrar la autenticación multifactor mediante el Centro de Partners.

- Administración limitada, que tiene privilegios equivalentes a los de un administrador del departamento de soporte técnico.

Antes de que el partner pueda asignar estos roles a los usuarios, usted debe agregarlo como un administrador delegado a su cuenta. Este proceso puede iniciarlo un partner autorizado. El partner le envía un correo electrónico para preguntarle si quiere concederle permiso para actuar como administrador delegado. Para obtener instrucciones, consulte [Autorizar o quitar relaciones de partner](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Artículos relacionados

[Acerca de los roles de administración de Microsoft 365](about-admin-roles.md)

[Asignar roles de administrador](assign-admin-roles.md)
  
[Informes de actividad en el Centro de administración de Microsoft 365](../activity-reports/activity-reports.md)