---
title: Acceso al portal de administración
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 8a5de1673a7b67481c368c5c76444e817f237fe7
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315782"
---
# <a name="access-the-admin-portal"></a>Acceso al portal de administración

La puerta de enlace al servicio de escritorio administrado de Microsoft es el portal de Microsoft [Azure](https://portal.azure.com). Para obtener más información sobre el uso y la personalización de la experiencia del portal de Azure en general, consulte la [documentación de Azure portal](https://docs.microsoft.com/azure/azure-portal/). Disponible en la versión preliminar ahora, también puede encontrar Microsoft Managed Desktop en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Si no está familiarizado con las capacidades de este portal para la administración de dispositivos, consulte la [documentación de Microsoft Endpoint Manager](https://docs.microsoft.com/mem/).

Su cuenta administrativa necesita permisos específicos para obtener acceso a las características administrativas del escritorio administrado de Microsoft en Azure portal o en Microsoft Endpoint Manager. Puede administrar el acceso de administrador a estas características dentro de su organización mediante el control de acceso basado en roles (RBAC). Varios roles de administrador de Azure AD y roles personalizados integrados están disponibles para proporcionar un control más granular de las diferentes características dentro del portal de administración de escritorio administrado de Microsoft. Para obtener más información sobre los roles de Azure Active Directory, consulte [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). A diferencia de los roles de administrador de AAD que se aplican a una variedad de productos y servicios de Microsoft, los roles personalizados son específicos del escritorio administrado de Microsoft y solo garantizan el acceso a las características de administración de este servicio. Los administradores pueden asignar roles personalizados a los usuarios de forma individual o en combinación con los roles de administrador de AAD para agregar permisos de escritorio administrado de Microsoft a cuentas de administrador existentes.

Cada una de las funciones siguientes se puede asignar para proporcionar diferentes niveles de acceso:

|Rol de Azure AD  |Permisos de escritorio administrado de Microsoft  |
|---------|---------|
|Administrador global     | Los administradores con este rol tendrán **permisos de lectura y escritura** para todas las características del portal de administración de escritorio administrado de Microsoft.         |
|Lector global     | Los administradores con este rol tendrán **permisos de solo lectura** para todas las características del portal de administración de escritorio administrado de Microsoft.         |
|Administrador de servicios de Intune     |  Los administradores con este rol tendrán **permisos de lectura y escritura** para todas las características del portal de administración de escritorio administrado de Microsoft. **Cambiar:** A partir de septiembre 2020 los administradores con este rol no tendrán acceso a las características de seguridad de escritorio administradas por Microsoft.       |
|Administrador de soporte de servicio     | Los administradores con este rol tendrán **permisos de lectura y escritura** para todas las características del portal de administración de escritorio administrado de Microsoft. **Cambiar:** A partir de septiembre 2020 los administradores con este rol no tendrán acceso a las características de seguridad de escritorio administradas por Microsoft.         |
|Administrador de seguridad | **(En versión preliminar 2020 de septiembre)** Los administradores con este rol tendrán permisos de solo lectura para todas las características y permisos de escritura de las características relacionadas con la seguridad en el escritorio administrado de Microsoft en el portal de administración. |
|Lector de seguridad | **(En versión preliminar 2020 de septiembre)**  Los administradores con este rol tendrán permisos de solo lectura para todas las características del portal de administración de escritorio administrado de Microsoft.|

> [!IMPORTANT]
> Sólo el rol de administrador global tiene los permisos necesarios para *inscribir* a su organización en el escritorio administrado de Microsoft. Tenga en cuenta que los roles de Azure Active Directory proporcionarán privilegios de cuentas de usuario en una amplia variedad de servicios de Microsoft. Una vez finalizada la inscripción con el escritorio administrado de Microsoft, siempre debe usar el rol con los privilegios *mínimos* necesarios para llevar a cabo las demás tareas.

 
|Rol personalizado  |Permisos de escritorio administrado de Microsoft  |
|---------|---------|
|Administrador del servicio de escritorio administrado de Microsoft  | **(En versión preliminar 2020 de septiembre)** Cuando se asigna a un usuario, este rol permite al administrador **leer & escribir en características no relacionadas con la seguridad** en el portal de administración de escritorio administrado de Microsoft.  |
|Lector de servicios de escritorio administrados de Microsoft | **(En versión preliminar 2020 de septiembre)** Cuando se asigna a un usuario, este rol concede al administrador **permisos de solo lectura en características no relacionadas con la seguridad** en el portal de administración de escritorio administrado de Microsoft. |
|Administrador de seguridad de escritorio administrada de Microsoft | **(En versión preliminar 2020 de septiembre)** Cuando se asigna a un usuario, este rol le da a ese administrador **& de lectura permisos de escritura solo para las características relacionadas con la seguridad** en el portal de administración de escritorio administrado de Microsoft.   |

> [!NOTE]
> Las características de seguridad incluyen comunicaciones relacionadas con la seguridad, administración de los contactos de seguridad, administración de solicitudes de soporte relacionadas con la seguridad y acceso a los informes relacionados con la seguridad. 

## <a name="assigning-roles-to-administrators"></a>Asignación de funciones a los administradores

Si necesita ayuda para asignar roles de Azure Active Directory, consulte [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Para facilitar la administración de las funciones integradas, se ha creado un grupo de seguridad para cada rol personalizado (por ejemplo, "funciones del área de trabajo modernas – administrador de seguridad"). Para asignar usuarios a uno de los grupos de seguridad, siga estos pasos:
1.  Vaya al portal de Azure y navegue hasta la hoja Azure Active Directory.
2.  Seleccione grupos en el lado izquierdo.
3.  Busque funciones modernas del área de trabajo y, a continuación, seleccione el grupo asociado con el rol que desea asignar. 
4.  Seleccione miembros en la parte izquierda y, a continuación, seleccione + Agregar miembros en la barra de comandos.
5.  Escriba el correo electrónico de la persona que se va a agregar. Si es un usuario externo, debe invitar a ellos para que pueda asignar el grupo.
6.  Seleccione seleccionar en la parte inferior.

> [!NOTE]
> Actualmente no se admite la anidación de grupos de seguridad para la asignación de roles. 
