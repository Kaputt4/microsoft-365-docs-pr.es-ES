---
title: Acceso al portal de administración
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: deeced350ad867a374a486967c2cbd278ba91710
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519334"
---
# <a name="access-the-admin-portal"></a>Acceso al portal de administración

La puerta de enlace al servicio de escritorio administrado de Microsoft es el portal de Microsoft [Azure](https://portal.azure.com). Para obtener más información sobre el uso y la personalización de la experiencia del portal de Azure en general, consulte la [documentación de Azure portal](https://docs.microsoft.com/azure/azure-portal/). Disponible en la versión preliminar ahora, también puede encontrar Microsoft Managed Desktop en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Si no está familiarizado con las capacidades de este portal para la administración de dispositivos, consulte la [documentación de Microsoft Endpoint Manager](https://docs.microsoft.com/mem/).

> [!NOTE]
> Sin embargo, usted elige tener acceso a escritorio administrado de Microsoft, en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) o en [Azure portal](https://portal.azure.com), se admiten los siguientes exploradores:
> - Microsoft Edge (versión más reciente)
> - Microsoft Internet Explorer 11
> - Safari (versión más reciente, solo Mac)
> - Chrome (versión más reciente)
> - Firefox (versión más reciente)

Su cuenta administrativa necesita permisos específicos para obtener acceso a las características administrativas del escritorio administrado de Microsoft en Azure portal o en Microsoft Endpoint Manager. Puede administrar el acceso de administrador a estas características dentro de su organización mediante el control de acceso basado en roles (RBAC). Hay disponibles varios roles de administrador de Azure Active Directory (Azure AD) y roles personalizados integrados para proporcionar un control más granular de las diferentes características dentro del portal de administración de escritorio administrado de Microsoft. Para obtener más información sobre los roles de Azure Active Directory, consulte [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). A diferencia de los roles de administrador de Azure AD que se aplican a diversos productos y servicios de Microsoft, las funciones personalizadas son específicas del escritorio administrado de Microsoft y solo garantizarán el acceso a las características de administración de este servicio. Los administradores pueden asignar roles personalizados a los usuarios de forma individual o en combinación con los roles de administrador de Azure AD para agregar permisos de escritorio administrado de Microsoft a cuentas de administrador existentes.

Cada una de las funciones siguientes se puede asignar para proporcionar diferentes niveles de acceso:

|Rol de Azure AD  |Permisos de escritorio administrado de Microsoft  |
|---------|---------|
|Administrador global     | Los administradores con este rol tendrán **permisos de lectura y escritura para todas las características** del portal de administración de escritorio administrado de Microsoft.         |
|Lector global     | Los administradores con este rol tendrán **permisos de solo lectura para todas las características** del portal de administración de escritorio administrado de Microsoft.         |
|Administrador de servicios de Intune     |  Los administradores con este rol tendrán **permisos de lectura y escritura para las características no relacionadas con la seguridad** en el portal de administración de escritorio administrado de Microsoft.       |
|Administrador de soporte de servicio     | Los administradores con este rol tendrán **permisos de solo lectura para las características no relacionadas** con los permisos de seguridad y **escritura para administrar las solicitudes de soporte técnico** en el portal de administración de escritorio administrado de Microsoft.         |
|Administrador de seguridad | Los administradores con este rol tendrán **permisos de solo lectura para todas las características** y **permisos de escritura de las características relacionadas con la seguridad** en el escritorio administrado de Microsoft en el portal de administración. |
|Lector de seguridad |Los administradores con este rol tendrán **permisos de solo lectura para todas las características** del portal de administración de escritorio administrado de Microsoft.|

> [!IMPORTANT]
> Sólo el rol de administrador global tiene los permisos necesarios para *inscribir* a su organización en el escritorio administrado de Microsoft. Tenga en cuenta que los roles de Azure Active Directory proporcionarán privilegios de cuentas de usuario en una amplia variedad de servicios de Microsoft. Una vez finalizada la inscripción con el escritorio administrado de Microsoft, siempre debe usar el rol con los privilegios *mínimos* necesarios para llevar a cabo las demás tareas.

 
|Rol personalizado  |Permisos de escritorio administrado de Microsoft  |
|---------|---------|
|Administrador del servicio de escritorio administrado de Microsoft  | Cuando se asigna a un usuario, este rol concede al administrador **permisos de lectura y escritura para las características no relacionadas con la seguridad** en el portal de administración de escritorio administrado de Microsoft.  |
|Lector de servicios de escritorio administrados de Microsoft | Cuando se asigna a un usuario, este rol concede al administrador **permisos de solo lectura en características no relacionadas con la seguridad** en el portal de administración de escritorio administrado de Microsoft. |
|Administrador de seguridad de escritorio administrada de Microsoft |Cuando se asigna a un usuario, este rol concede a ese administrador **permisos de lectura y escritura solo para las características relacionadas con la seguridad** en el portal de administración de escritorio administrado de Microsoft.   |

> [!NOTE]
> Las características de seguridad incluyen comunicaciones relacionadas con la seguridad, administración de los contactos de seguridad, administración de solicitudes de soporte relacionadas con la seguridad y acceso a los informes relacionados con la seguridad. 

## <a name="assigning-roles-to-administrators"></a>Asignación de funciones a los administradores

Si necesita ayuda para asignar roles de Azure Active Directory, consulte [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Para facilitar la administración de las funciones integradas, se ha creado un grupo de seguridad para cada rol personalizado (por ejemplo, "funciones del área de trabajo modernas – administrador de seguridad"). Para asignar usuarios a uno de los grupos de seguridad, siga estos pasos:
1.  Ir al portal de Microsoft Endpoint Manager
2.  Seleccione grupos en el lado izquierdo.
3.  Busque funciones modernas del área de trabajo y, a continuación, seleccione el grupo asociado con el rol que desea asignar. 
4.  Seleccione miembros en la parte izquierda y, a continuación, seleccione + Agregar miembros en la barra de comandos.
5.  Escriba el correo electrónico de la persona que se va a agregar. Si es un usuario externo, debe invitar a ellos para que pueda asignar el grupo.
6.  Seleccione seleccionar en la parte inferior.

> [!NOTE]
> Actualmente no se admite la anidación de grupos de seguridad para la asignación de roles. 
