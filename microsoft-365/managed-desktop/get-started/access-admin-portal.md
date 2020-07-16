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
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146276"
---
# <a name="access-the-admin-portal"></a>Acceso al portal de administración

La puerta de enlace al servicio de escritorio administrado de Microsoft es el portal de Microsoft [Azure](https://portal.azure.com). Para obtener más información sobre el uso y la personalización de la experiencia del portal de Azure en general, consulte la [documentación de Azure portal](https://docs.microsoft.com/azure/azure-portal/). 

La cuenta administrativa necesita permisos específicos para poder obtener acceso al portal de administración de escritorio administrado de Microsoft. Puede administrar el acceso de administrador a estas características dentro de su organización mediante el control de acceso basado en roles (RBAC). Para obtener más información sobre los roles de Azure Active Directory, consulte [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Asigne a sus cuentas de usuario de administrador cualquiera de las siguientes funciones para garantizar el acceso:

|Rol de Azure AD  |Permisos de escritorio administrado de Microsoft  |
|---------|---------|
|Administrador global     | Los administradores con este rol tendrán **permisos de lectura y escritura** para todas las características del portal de administración de escritorio administrado de Microsoft.         |
|Lector global     | Los administradores con este rol tendrán **permisos de solo lectura** para todas las características del portal de administración de escritorio administrado de Microsoft.         |
|Administrador de servicios de Intune     |  Los administradores con este rol tendrán **permisos de lectura y escritura** para todas las características del portal de administración de escritorio administrado de Microsoft.       |
|Administrador de soporte de servicio     | Los administradores con este rol tendrán **permisos de lectura y escritura** para todas las características del portal de administración de escritorio administrado de Microsoft.         |

> [!IMPORTANT]
> Sólo el rol de administrador global tiene los permisos necesarios para *inscribir* a su organización en el escritorio administrado de Microsoft. Tenga en cuenta que los roles de Azure Active Directory proporcionarán privilegios de cuentas de usuario en una amplia variedad de servicios de Microsoft. Una vez finalizada la inscripción con el escritorio administrado de Microsoft, siempre debe usar el rol con los privilegios *mínimos* necesarios para llevar a cabo las demás tareas.

## <a name="assigning-roles-to-administrators"></a>Asignación de funciones a los administradores

Si necesita ayuda para asignar roles de Azure Active Directory, consulte [permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).
