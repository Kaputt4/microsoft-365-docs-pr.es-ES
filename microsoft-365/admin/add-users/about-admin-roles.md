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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: Los roles de administrador se asignan a funciones empresariales y dan permisos para realizar tareas específicas en el centro de administración. Por ejemplo, el Administrador del servicio puede abrir tickets de soporte técnico a través del centro de administración.
ms.openlocfilehash: ddea8a06af2b529a369ea045913b639b84c6f9d4
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867987"
---
# <a name="about-admin-roles"></a>Acerca de los roles de administrador

La suscripción a Microsoft 365 u Office 365 incluye un conjunto de roles de administrador que puede asignar a los usuarios de su organización usando el Centro de administración de Microsoft 365. Cada rol de administrador se asigna a una función empresarial común y da permisos a los usuarios de su organización para realizar tareas específicas en los centros de administración.

El Centro de administración de Microsoft 365 le permite administrar roles de Azure AD y de Microsoft Intune. Sin embargo, estos roles son un subconjunto de los roles disponibles en el portal de Azure AD y en el centro de administración de Intune.

## <a name="before-you-begin"></a>Antes de empezar

¿Busca una lista completa de descripciones detalladas de los roles para Azure AD que puede administrar en el Centro de administración de Microsoft 365? Consulte Permisos de roles de administrador en Azure Active Directory. [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

¿Busca una lista completa de descripciones detalladas de los roles para Intune que puede administrar en el Centro de administración de Microsoft 365?  Consulte [Control de acceso basado en roles (RBAC) con Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

Para más información acerca de la asignación de roles en el Centro de administración de Microsoft 365, consulte [Asignar roles de administrador](assign-admin-roles.md).

### <a name="watch-what-is-an-admin"></a>Ver: ¿Qué es un administrador?

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SRc0]

## <a name="security-guidelines-for-assigning-roles"></a>Directrices de seguridad para asignar roles

Debido a que los administradores tienen acceso a archivos y datos confidenciales, le recomendamos que siga estas instrucciones para mantener los datos de su organización más seguros.

| Recomendación                  | ¿Por qué esto es importante?                 |
| :------------------- | :------------------- |
| Tener entre 2 y 4 administradores globales  | Como solo otro administrador global puede restablecer la contraseña de un administrador global, le recomendamos que tenga al menos 2 administradores globales en la organización en caso de que ocurra un bloqueo de la cuenta. Sin embargo, el administrador global tiene casi un acceso ilimitado a la configuración de su organización y a la mayoría de los datos, por lo que también recomendamos que no tenga más de 4 administradores globales, porque esto representaría una amenaza de seguridad. |
| Asignar el rol *menos permisivo*    | Asignar el rol *menos permisivo* significa conceder a los administradores solo el acceso que necesitan para realizar el trabajo. Por ejemplo, si desea que alguien restablezca las contraseñas de los empleados, no debe asignar el rol de administrador global ilimitado, sino asignar un rol de administrador limitado, como el de Administrador de contraseñas o Administrador del departamento de soporte técnico. Esto le ayudará a mantener sus datos seguros.                 |
| Requerir la autenticación multifactor para administradores                  |    En realidad es una buena idea requerir MFA para todos los usuarios, pero definitivamente se debe exigir a los administradores usar la MFA para iniciar sesión. La MFA permite que los usuarios introduzcan un segundo método de identificación para comprobar que son quienes dicen ser. Los administradores pueden tener acceso a una gran cantidad de datos de clientes y empleados y, si se requiere la MFA, incluso si la contraseña del administrador se ve comprometida, esta será inútil sin la segunda forma de identificación.  <br><br>Al activar la MFA, la próxima vez que el usuario inicie sesión, deberá proporcionar una dirección de correo electrónico y un número de teléfono alternativos para recuperar la cuenta.  <br> [Configurar la autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md)          |

Si recibe un mensaje en el centro de administración que le indica que no tiene permisos para editar una configuración o una página, es porque se le ha asignado un rol que no tiene ese permiso.

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>Roles más frecuentes del Centro de administración de Microsoft 365

::: moniker range="o365-worldwide"

En el Centro de administración de Microsoft 365, puede ir a **Roles** y seleccionar cualquier rol para abrir su respectivo panel de detalles. Seleccione la pestaña **Permisos** para ver la lista detallada de lo que tienen permiso para hacer los administradores con ese rol asignado. Seleccione la pestaña **Asignado** o **Administradores asignados** para agregar usuarios a los roles.

::: moniker-end

Probablemente solo necesitará asignar los siguientes roles en su organización. De forma predeterminada, primero mostramos los roles que usan la mayoría de las organizaciones. Si no encuentra un rol, vaya a la parte inferior de la lista y seleccione **Mostrar todos por categoría**. (Para obtener información detallada, incluidos los cmdlets asociados a un rol, consulte [Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)).

|Rol de administrador     |¿A quién se le debe asignar este rol?  |
|---------|---------|
|Administrador de Exchange     |   Asigne el rol de administrador de Exchange a los usuarios que necesiten ver y administrar los buzones de correo de sus usuarios, los grupos de Microsoft 365 y Exchange Online. <br><br> Los administradores de Exchange también pueden:<br> - Recuperar elementos eliminados en un buzón de usuario <br> - Configurar los delegados "Enviar como" y "Enviar en nombre de" <br>  |
|Administrador global     |   Asigne el rol de administrador global a los usuarios que necesiten acceso global a la mayoría de las características de administración y datos en los servicios en línea de Microsoft. <br><br> Otorgar acceso global a un gran número de usuarios es un riesgo para la seguridad y le recomendamos que solo tenga entre 2 y 4 administradores globales. <br><br> Solo los administradores globales pueden:<br> - Restablecer las contraseñas de todos los usuarios <br> - Agregar y administrar dominios <br> <br> **Nota:**   la persona que se registró en los servicios en línea de Microsoft se convierte automáticamente en administrador global. |
|Lector global    |   Asigne el rol de lector global a los usuarios que necesiten ver la configuración y las funciones de administración en los centros de administración que el administrador global puede ver. El administrador del lector global no puede editar ninguna configuración.   |
|Administrador de grupos     |   Asigne el rol de administrador de grupos a los usuarios que necesiten administrar la configuración de todos los grupos en los centros de administración, incluido el Centro de administración de Microsoft 365 y el portal de Azure Active Directory. <br><br> Los administradores de grupos pueden:<br> - Crear, editar, eliminar y restaurar los grupos de Microsoft 365 <br> - Crear y actualizar las directivas de creación, expiración y nomenclatura de grupos <br> - Crear, editar, eliminar y restaurar grupos de seguridad de Azure Active Directory| 
|Administrador del departamento de soporte técnico     |   Asigne el rol de administrador del departamento de soporte técnico a los usuarios que necesiten que hacer lo siguiente:<br> - Restablecer contraseñas <br> - Forzar a los usuarios a cerrar sesión <br> - Administrar solicitudes de servicio <br> - Supervisar el estado del servicio <br> <br> **Nota**: el administrador del departamento de soporte técnico solo puede ayudar a usuarios que no son administradores y a usuarios que tienen asignados estos roles: Lector de directorios, Invitador de usuarios invitados, Administrador del departamento de soporte técnico, Lector del centro de mensajes y Lector de informes.      |
|Administrador de aplicaciones de Office    |   Asigne el rol de administrador de aplicaciones de Office a los usuarios que necesiten hacer lo siguiente: <br> - Usar el servicio de directivas en la nube de Office para crear y administrar directivas basadas en la nube para Office <br> - Crear y administrar solicitudes de servicio <br> - Administrar el contenido de Novedades que los usuarios ven en sus aplicaciones de Office   <br> - Supervisar el estado del servicio  |
|Administrador de soporte técnico del servicio   |   Asigne el rol de Administrador de soporte de servicio como un rol adicional para administradores o usuarios que necesiten hacer lo siguiente, pero cuyos roles asignados no lo incluyen: <br> - Abrir y administrar solicitudes de servicio <br> - Ver y compartir publicaciones del centro de mensajes   |
|Administrador de SharePoint    |   Asigne el rol de administrador de SharePoint a los usuarios que necesiten acceder y administrar el centro de administración de SharePoint Online. <br><br>Los administradores de SharePoint también pueden: <br> - Crear y eliminar sitios <br> - Administrar colecciones de sitios y la configuración global de SharePoint   |
|Administrador de servicios de Teams    |   Asigne el rol de administrador de servicios de Teams a los usuarios que necesiten acceder y administrar el centro de administración de Teams. <br><br>Los administradores de servicio de Teams también pueden: <br> - Administrar reuniones <br> - Administrar puentes de conferencia <br> - Administrar la configuración de toda la organización, incluida la federación, la actualización de equipos y la configuración de cliente de equipos   |
|Administrador de usuarios     |    Asigne el rol de administrador de usuarios a los usuarios que necesiten hacer lo siguiente para todos los usuarios: <br> - Agregar usuarios y grupos <br> - Asignar licencias <br> - Administrar las propiedades de la mayoría de los usuarios <br> - Crear y administrar vistas de usuarios <br> - Actualizar las directivas de expiración de contraseña <br> - Administrar solicitudes de servicio <br> - Supervisar el estado del servicio <br><br>  El administrador de usuario también puede realizar las siguientes acciones para los usuarios que no sean administradores y para los usuarios que tengan asignados los siguientes roles: Lector de directorios, Invitador de usuarios invitados, Administrador del departamento de soporte técnico, Lector del centro de mensajes y Lector de informes: <br> - Administrar nombres de usuario<br> - Eliminar y restaurar usuarios<br> - Restablecer contraseñas <br> - Forzar a los usuarios a cerrar sesión <br> - Actualizar claves de dispositivo (FIDO)   |

## <a name="delegated-administration-for-microsoft-partners"></a>Administración delegada para Microsoft Partners

Si está trabajando con un partner de Microsoft, puede asignarle roles de administrador. Por su parte, los partners pueden asignar roles de administrador a los usuarios en sus propias empresas o bien en la suya. Es posible que quiera que lo hagan si, por ejemplo, están configurando y administrando la organización online por usted.
  
Un partner puede asignar estos roles: 
  
- **Agente de administración** Tiene privilegios equivalentes a los de un administrador global, con la excepción de administrar la autenticación multifactor mediante el Centro de Partners.

- **Agente del departamento de soporte técnico** Tiene privilegios equivalentes a los de un administrador del departamento de soporte técnico.

Antes de que el partner pueda asignar estos roles a los usuarios, usted debe agregarlo como un administrador delegado a su cuenta. Este proceso puede iniciarlo un partner autorizado. El partner le envía un correo electrónico para preguntarle si quiere concederle permiso para actuar como administrador delegado. Para obtener instrucciones, consulte [Autorizar o quitar relaciones de partner](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Artículos relacionados

[Asignar roles de administrador](assign-admin-roles.md)

[Roles de Azure AD en el Centro de administración de Microsoft 365](azure-ad-roles-in-the-mac.md)

[Rol de administrador de Exchange Online](about-exchange-online-admin-role.md)
  
[Informes de actividad en el Centro de administración de Microsoft 365](../activity-reports/activity-reports.md)
