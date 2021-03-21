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
ms.openlocfilehash: 7293c8ced43332f84ced56908ea5203ba867e600
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925909"
---
# <a name="access-the-admin-portal"></a>Acceso al portal de administración

La puerta de enlace al servicio de Escritorio administrado de Microsoft es [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Si no está familiarizado con las capacidades de este portal para la administración de dispositivos, consulte la documentación de [Microsoft Endpoint Manager](/mem/).

> [!NOTE]
> En [Microsoft Endpoint Manager se](https://endpoint.microsoft.com/) admiten los siguientes exploradores:
> - Microsoft Edge (versión más reciente)
> - Microsoft Internet Explorer 11
> - Safari (versión más reciente, solo Mac)
> - Chrome (versión más reciente)
> - Firefox (versión más reciente)

Su cuenta administrativa necesitará permisos específicos para tener acceso a las características administrativas de Microsoft Managed Desktop en Microsoft Endpoint Manager. Puede administrar el acceso de administrador a estas características dentro de la organización mediante el control de acceso basado en roles. Hay varios roles de administrador de Azure Active Directory (Azure AD) y roles integrados de Escritorio administrado de Microsoft disponibles para proporcionar un control más detallado a las distintas características del portal de administración de escritorio administrado de Microsoft. Para obtener más información acerca de los roles de Azure Active Directory, vea [Permisos de roles de administrador en Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). A diferencia de los roles de administrador de Azure AD que se aplican a varios productos y servicios de Microsoft, los roles integrados son específicos del escritorio administrado de Microsoft y solo garantizan el acceso a las características de administrador de este servicio. Los administradores pueden asignar roles integrados a los usuarios individualmente o en combinación con roles de administrador de Azure AD para agregar permisos de Escritorio administrado de Microsoft a cuentas de administrador existentes.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Roles de Azure Active Directory con acceso a Escritorio administrado de Microsoft

|Rol de Azure AD  |Permisos de Escritorio administrado de Microsoft  |
|---------|---------|
|Administrador global     | Los administradores con este rol tendrán permisos de lectura y escritura **en todas** las características del portal de administración de escritorio administrado de Microsoft.         |
|Lector global     | Los administradores con este rol tendrán permisos de solo lectura para todas las **características** del portal de administración de escritorio administrado de Microsoft.         |
|Administrador de servicios de Intune     |  Los administradores con este rol tendrán permisos de **lectura** y escritura para características que no están relacionadas con la seguridad en el portal de administración de escritorio administrado de Microsoft.       |
|Administrador de soporte técnico de servicio     | Los administradores con  este rol tendrán permisos de solo  lectura para características que no están relacionadas con la seguridad y los permisos de escritura para administrar solicitudes de soporte técnico en el portal de administración de Escritorio administrado de Microsoft.         |
|Administrador de seguridad | Los administradores con  este rol tendrán permisos  de solo lectura para todas las características y permisos de escritura para las características relacionadas con la seguridad en Microsoft Managed Desktop en el portal de administración. |
|Lector de seguridad |Los administradores con este rol tendrán permisos de solo lectura para todas las **características** del portal de administración de escritorio administrado de Microsoft.|

Si necesita ayuda para asignar roles de Azure Active Directory, consulte [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

> [!IMPORTANT]
> Solo el rol Administrador global tiene los permisos necesarios para *inscribir* su organización en Microsoft Managed Desktop. Tenga en cuenta que los roles de Azure Active Directory le darán privilegios de cuentas de usuario en una variedad de servicios de Microsoft. Después de completar la inscripción con Microsoft Managed Desktop, siempre debes usar el rol con los privilegios mínimos necesarios para realizar tus otras tareas. 

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Roles integrados proporcionados por Microsoft Managed Desktop


|Rol integrado  |Permisos de Escritorio administrado de Microsoft  |
|---------|---------|
|Administrador del servicio de escritorio administrado de Microsoft  | Cuando se asigna a un usuario, este rol concede al administrador permisos de lectura y escritura a características que no están relacionadas con la seguridad en el portal de administración de escritorio administrado de Microsoft.   |
|Lector de servicio de escritorio administrado de Microsoft | Cuando se asigna a un usuario, este rol concede al administrador permisos de solo lectura a características que no están relacionadas con la seguridad en el portal de administración de escritorio administrado de Microsoft.  |
|Administrador de seguridad de Escritorio administrado de Microsoft |Cuando se asigna a un usuario, este rol proporciona a ese **administrador** permisos de lectura y escritura solo para las características relacionadas con la seguridad en el portal de administración de escritorio administrado de Microsoft.   |

> [!NOTE]
> Las características de seguridad incluyen comunicaciones relacionadas con la seguridad, administración de contactos de seguridad, administración de solicitudes de soporte técnico relacionadas con la seguridad y acceso a informes relacionados con la seguridad. 

### <a name="assigning-built-in-roles-to-user"></a>Asignar roles integrados al usuario

Para facilitar la administración de roles integrados, hay un grupo de seguridad para cada rol personalizado con el nombre "Roles modernos del lugar de trabajo _-_ Nombre de rol" (por ejemplo, "Roles modernos del lugar de trabajo – Administrador de seguridad"). Para asignar usuarios a uno de estos grupos de seguridad, siga estos pasos:
1.  Vaya al portal de Microsoft Endpoint Manager.
2.  Seleccione **Grupos** en el lado izquierdo.
3.  Busque Roles **modernos del lugar de** trabajo y, a continuación, seleccione el grupo asociado con el rol que desea asignar. 
4.  Seleccione **Miembros** en el lado izquierdo y, a continuación, **seleccione + Agregar miembros** en la barra de comandos.
5.  Escriba el correo electrónico de la persona que se va a agregar. Si son invitados, debe invitarlos antes de poder asignar el grupo.
6.  Seleccione **Seleccionar** en la parte inferior.

> [!NOTE]
> Actualmente, no se admite el anidamiento de grupos de seguridad para la asignación de roles. 

### <a name="assigning-built-in-roles-to-groups"></a>Asignar roles integrados a grupos

Si necesita asignar uno o varios de los roles integrados a un grupo existente, siga estos pasos:
1. Vaya a [portal.azure.com](https://portal.azure.com/).
2. Buscar y abrir aplicaciones **enterprise**.
3. Cambie el **filtro Tipo de** aplicación a Aplicaciones de _Microsoft_ y, a continuación, **seleccione Aplicar**.
4. Busque y seleccione API de _clientes de Modern Workplace_.
5. Seleccione **Usuarios y grupos en** el panel de la izquierda y, a continuación, seleccione + Agregar **usuario/grupo**.
6. Busque el grupo que desee de **Usuarios y grupos**.
7. Busque el rol aplicable en **Seleccionar un rol** y, a continuación, selecciónelo.
8. Seleccione **Asignar**.
