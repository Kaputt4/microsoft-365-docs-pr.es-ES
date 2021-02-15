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
ms.openlocfilehash: d22cef41fb1d6dc3fde39681ad84edc510440b11
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110012"
---
# <a name="access-the-admin-portal"></a>Acceder al portal de administración

La puerta de enlace al servicio de escritorio administrado de Microsoft es [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Si no estás familiarizado con las funcionalidades de este portal para la administración de dispositivos, consulta la documentación [de Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/)

> [!NOTE]
> En [Microsoft Endpoint Manager se](https://endpoint.microsoft.com/) admiten los siguientes exploradores:
> - Microsoft Edge (versión más reciente)
> - Microsoft Internet Explorer 11
> - Safari (versión más reciente, solo para Mac)
> - Chrome (versión más reciente)
> - Firefox (versión más reciente)

Tu cuenta administrativa necesitará permisos específicos para acceder a las características administrativas de Escritorio administrado de Microsoft en Microsoft Endpoint Manager. Puede administrar el acceso de administrador a estas características dentro de la organización mediante el control de acceso basado en roles. Hay disponibles varios roles de administrador de Azure Active Directory (Azure AD) y roles integrados de Escritorio administrado de Microsoft para proporcionar un control más detallado a las distintas características del portal de administración de escritorio administrado de Microsoft. Para obtener más información acerca de los roles de Azure Active Directory, consulte Permisos de [roles de administrador en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) A diferencia de los roles de administrador de Azure AD que se aplican a diversos productos y servicios de Microsoft, los roles integrados son específicos del Escritorio administrado de Microsoft y solo garantizarán el acceso a las características de administración de este servicio. Los administradores pueden asignar roles integrados a los usuarios individualmente o en combinación con los roles de administrador de Azure AD para agregar permisos de Escritorio administrado de Microsoft a las cuentas de administrador existentes.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Roles de Azure Active Directory con acceso al Escritorio administrado de Microsoft

|Rol de Azure AD  |Permisos de Escritorio administrado de Microsoft  |
|---------|---------|
|Administrador global     | Los administradores con este rol tendrán permisos de lectura y **escritura en todas las características** del portal de administración de Escritorio administrado de Microsoft.         |
|Lector global     | Los administradores con este rol tendrán permisos **de solo lectura para todas las características** del portal de administración de Escritorio administrado de Microsoft.         |
|Administrador de servicios de Intune     |  Los administradores con este rol tendrán permisos de lectura y escritura **para** características no relacionadas con la seguridad en el portal de administración de escritorio administrado de Microsoft.       |
|Administrador de soporte técnico del servicio     | Los administradores con  este rol tendrán permisos de solo  lectura para características no relacionadas con la seguridad y permisos de escritura para administrar solicitudes de soporte técnico en el portal de administración de escritorio administrado de Microsoft.         |
|Administrador de seguridad | Los administradores con  este rol tendrán permisos  de solo lectura para todas las características y permisos de escritura para las características relacionadas con la seguridad en escritorio administrado de Microsoft en el portal de administración. |
|Lector de seguridad |Los administradores con este rol tendrán permisos **de solo lectura para todas las características** del portal de administración de Escritorio administrado de Microsoft.|

Si necesita ayuda para asignar roles de Azure Active Directory, consulte Permisos de rol [de administrador en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

> [!IMPORTANT]
> Solo el rol de administrador global tiene los permisos necesarios para *inscribir* su organización en el Escritorio administrado de Microsoft. Tenga en cuenta que los roles de Azure Active Directory darán privilegios a las cuentas de usuario en una variedad de servicios Microsoft. Después de completar la inscripción con escritorio administrado de  Microsoft, siempre debe usar el rol con los privilegios mínimos necesarios para realizar las otras tareas.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Roles integrados proporcionados por escritorio administrado de Microsoft


|Rol integrado  |Permisos de Escritorio administrado de Microsoft  |
|---------|---------|
|Administrador del servicio de escritorio administrado de Microsoft  | Cuando se asigna a un usuario, este rol concede al administrador permisos de lectura y escritura para las características que no están relacionadas con la seguridad en el portal de administración de Escritorio administrado de Microsoft.   |
|Lector de servicio de escritorio administrado de Microsoft | Cuando se asigna a un usuario, este rol concede al administrador permisos de solo lectura para las características que no están relacionadas con la seguridad en el portal de administración de escritorio administrado de Microsoft.  |
|Administrador de seguridad de escritorio administrado de Microsoft |Cuando se asigna a un usuario, este rol concede a ese administrador permisos de lectura y escritura solo para las características relacionadas con la seguridad en el portal de administración de Escritorio administrado de Microsoft.    |

> [!NOTE]
> Las características de seguridad incluyen las comunicaciones relacionadas con la seguridad, la administración de contactos de seguridad, la administración de solicitudes de soporte técnico relacionadas con la seguridad y el acceso a informes relacionados con la seguridad. 

### <a name="assigning-built-in-roles-to-user"></a>Asignación de roles integrados al usuario

Para facilitar la administración de roles integrados, hay un grupo de seguridad para cada rol personalizado con el nombre "Roles de área de trabajo _modernos_- Nombre de rol" (por ejemplo, "Roles de área de trabajo modernos– Administrador de seguridad"). Para asignar usuarios a uno de estos grupos de seguridad, siga estos pasos:
1.  Ve al portal de Microsoft Endpoint Manager.
2.  Seleccione **Grupos** en el lado izquierdo.
3.  Busque roles **de área de** trabajo modernas y, a continuación, seleccione el grupo asociado con el rol que desea asignar. 
4.  Seleccione **Miembros** en el lado izquierdo y, a continuación, **seleccione + Agregar miembros** en la barra de comandos.
5.  Escriba el correo electrónico de la persona que se va a agregar. Si son invitados, debe invitarlos para poder asignar el grupo.
6.  Seleccione **Seleccionar** en la parte inferior.

> [!NOTE]
> Actualmente no se admite el anidamiento de grupos de seguridad para la asignación de roles. 

### <a name="assigning-built-in-roles-to-groups"></a>Asignación de roles integrados a grupos

Si necesita asignar uno o varios de los roles integrados a un grupo existente, siga estos pasos:
1. Vaya a [portal.azure.com](https://portal.azure.com/).
2. Buscar y abrir aplicaciones **de empresa.**
3. Cambie el **filtro de tipo de** aplicación a Aplicaciones de _Microsoft_ y, a continuación, **seleccione Aplicar**.
4. Busque y seleccione las API _de clientes de Modern Workplace._
5. Seleccione **Usuarios y grupos en** el panel de la izquierda y, a continuación, seleccione + Agregar usuario o **grupo.**
6. Busque el grupo que desee en **Usuarios y grupos.**
7. Busque el rol aplicable en **Seleccionar un rol** y, a continuación, selecciónelo.
8. Seleccione **Asignar**.
 
