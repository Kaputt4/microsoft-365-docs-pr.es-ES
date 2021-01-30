---
title: Acceso al portal de administración
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
description: Cómo buscar y usar el portal de administración, incluido el control del acceso a él.
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: c2a5b7f837d6c43369301820019732ca3aef83bf
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053852"
---
# <a name="access-the-admin-portal"></a>Acceder al portal de administración

La puerta de enlace al servicio de escritorio administrado de Microsoft es [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Si no estás familiarizado con las capacidades de este portal para la administración de dispositivos, consulta la documentación [de Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/)

> [!NOTE]
> En [Microsoft Endpoint Manager se](https://endpoint.microsoft.com/) admiten los siguientes exploradores:
> - Microsoft Edge (versión más reciente)
> - Microsoft Internet Explorer 11
> - Safari (versión más reciente, solo para Mac)
> - Chrome (versión más reciente)
> - Firefox (versión más reciente)

Su cuenta administrativa necesita permisos específicos para tener acceso a las características administrativas de Escritorio administrado de Microsoft en Azure Portal o Microsoft Endpoint Manager. Puede administrar el acceso de administrador a estas características dentro de la organización mediante el Control de acceso basado en roles (RBAC). Hay disponibles varios roles de administrador de Azure Active Directory (Azure AD) y roles personalizados integrados para proporcionar un control más detallado a las distintas características del portal de administración de escritorio administrado de Microsoft. Para obtener más información acerca de los roles de Azure Active Directory, consulte Permisos de [roles de administrador en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) A diferencia de los roles de administrador de Azure AD que se aplican a diversos productos y servicios de Microsoft, los roles personalizados son específicos del Escritorio administrado de Microsoft y solo garantizarán el acceso a las características de administración de este servicio. Los administradores pueden asignar roles personalizados a los usuarios individualmente o en combinación con los roles de administrador de Azure AD para agregar permisos de Escritorio administrado de Microsoft a las cuentas de administrador existentes.

Cada uno de los siguientes roles se puede asignar para proporcionar distintos niveles de acceso:

|Rol de Azure AD  |Permisos de Escritorio administrado de Microsoft  |
|---------|---------|
|Administrador global     | Los administradores con este rol tendrán permisos de lectura y **escritura en todas las características** del portal de administración de Escritorio administrado de Microsoft.         |
|Lector global     | Los administradores con este rol tendrán permisos **de solo lectura para todas las características** del portal de administración de Escritorio administrado de Microsoft.         |
|Administrador de servicios de Intune     |  Los administradores con este rol **tendrán** permisos de lectura y escritura para características no relacionadas con la seguridad en el portal de administración de escritorio administrado de Microsoft.       |
|Administrador de soporte técnico del servicio     | Los administradores con  este rol tendrán permisos de solo  lectura para características no relacionadas con la seguridad y permisos de escritura para administrar solicitudes de soporte técnico en el portal de administración de escritorio administrado de Microsoft.         |
|Administrador de seguridad | Los administradores con  este rol tendrán permisos  de solo lectura para todas las características y permisos de escritura para las características relacionadas con la seguridad en escritorio administrado de Microsoft en el portal de administración. |
|Lector de seguridad |Los administradores con este rol tendrán permisos **de solo lectura para todas las características** del portal de administración de Escritorio administrado de Microsoft.|

> [!IMPORTANT]
> Solo el rol de administrador global tiene los permisos necesarios para *inscribir* su organización en el Escritorio administrado de Microsoft. Tenga en cuenta que los roles de Azure Active Directory darán privilegios a las cuentas de usuario en una variedad de servicios Microsoft. Después de completar la inscripción con el Escritorio administrado  de Microsoft, siempre debe usar el rol con los privilegios mínimos necesarios para realizar las otras tareas.

 
|Rol personalizado  |Permisos de Escritorio administrado de Microsoft  |
|---------|---------|
|Administrador del servicio de escritorio administrado de Microsoft  | Cuando se asigna a un usuario, este rol concede al administrador permisos de lectura y escritura para las características que no están relacionadas con la seguridad en el portal de administración de Escritorio administrado de Microsoft.   |
|Lector de servicio de escritorio administrado de Microsoft | Cuando se asigna a un usuario, este rol concede al administrador permisos de solo lectura para las características que no están relacionadas con la seguridad en el portal de administración de escritorio administrado de Microsoft.  |
|Administrador de seguridad de escritorio administrado de Microsoft |Cuando se asigna a un usuario, este rol proporciona a ese administrador permisos de lectura y escritura solo para las características relacionadas con la seguridad en el portal de administración de Escritorio administrado de Microsoft.    |

> [!NOTE]
> Las características de seguridad incluyen las comunicaciones relacionadas con la seguridad, la administración de contactos de seguridad, la administración de solicitudes de soporte técnico relacionadas con la seguridad y el acceso a informes relacionados con la seguridad. 

## <a name="assigning-roles-to-administrators"></a>Asignación de roles a administradores

Si necesita ayuda para asignar roles de Azure Active Directory, consulte Permisos de rol [de administrador en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

Para facilitar la administración de roles integrados, hay un grupo de seguridad para cada rol personalizado (por ejemplo, "Roles de área de trabajo modernos: Administrador de seguridad"). Para asignar usuarios a uno de los grupos de seguridad, siga estos pasos:
1.  Ve al portal de Microsoft Endpoint Manager.
2.  Seleccione **Grupos** en el lado izquierdo.
3.  Busque roles **de área de** trabajo modernos y, a continuación, seleccione el grupo asociado con el rol que desea asignar. 
4.  Seleccione **Miembros** en el lado izquierdo y, a continuación, **seleccione + Agregar miembros** en la barra de comandos.
5.  Escriba el correo electrónico de la persona que se va a agregar. Si son invitados, debe invitarlos para poder asignar el grupo.
6.  Seleccione **Seleccionar** en la parte inferior.

> [!NOTE]
> Actualmente no se admite el anidamiento de grupos de seguridad para la asignación de roles. 
