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
ms.openlocfilehash: 345ae56a1c328dad7b777468dd03bcab40f9b4e1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286878"
---
# <a name="access-the-admin-portal"></a>Acceso al portal de administración

La puerta de enlace al servicio Escritorio administrado de Microsoft es [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Si no estás familiarizado con las capacidades de este portal para la administración de dispositivos, consulta la [Microsoft Endpoint Manager de administración de dispositivos.](/mem/)

> [!NOTE]
> En [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) se admiten los siguientes exploradores:
> - Microsoft Edge (versión más reciente)
> - Safari (versión más reciente, solo Mac)
> - Chrome (versión más reciente)
> - Firefox (versión más reciente)

Su cuenta administrativa necesitará permisos específicos para tener acceso a las características Escritorio administrado de Microsoft administrativas de Microsoft Endpoint Manager. Puede administrar el acceso de administrador a estas características dentro de la organización mediante el control de acceso basado en roles. Hay Azure Active Directory roles de administrador (Azure AD) y roles Escritorio administrado de Microsoft integrados para proporcionar un control más detallado a las distintas características dentro del portal de administración Escritorio administrado de Microsoft administración. Para obtener más información acerca Azure Active Directory roles, vea [Permisos de roles de](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)administrador en Azure Active Directory . A diferencia de los roles de administrador de Azure AD que se aplican a varios productos y servicios de Microsoft, los roles integrados son específicos de Escritorio administrado de Microsoft y solo garantizarán el acceso a las características de administrador de este servicio. Los administradores pueden asignar roles integrados a los usuarios individualmente o en combinación con roles de administrador de Azure AD para agregar Escritorio administrado de Microsoft a cuentas de administrador existentes.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory roles con Escritorio administrado de Microsoft acceso

|Rol de Azure AD  |Escritorio administrado de Microsoft permisos  |
|---------|---------|
|Administrador global     | Los administradores con este rol tendrán permisos de **lectura** y escritura en todas las características del portal Escritorio administrado de Microsoft administración.         |
|Lector global     | Los administradores con este rol tendrán permisos de **solo** lectura para todas las características del portal Escritorio administrado de Microsoft administración.         |
|Administrador de servicios de Intune     |  Los administradores con este rol tendrán permisos de **lectura** y escritura para características que no están relacionadas con la seguridad en el portal Escritorio administrado de Microsoft administración.       |
|Administrador de soporte técnico de servicio     | Los administradores con  este rol tendrán permisos de solo  lectura para las características que no están relacionadas con la seguridad y los permisos de escritura para administrar solicitudes de soporte técnico en el portal de administración Escritorio administrado de Microsoft administración.         |
|Administrador de seguridad | Los administradores con este rol **tendrán** permisos  de solo lectura para todas las características y permisos de escritura para las características relacionadas con la seguridad Escritorio administrado de Microsoft en el portal de administración. |
|Lector de seguridad |Los administradores con este rol tendrán permisos de **solo** lectura para todas las características del portal Escritorio administrado de Microsoft administración.|

Si necesita ayuda con la asignación de Azure Active Directory, vea Permisos de roles de administrador [en Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

> [!IMPORTANT]
> Solo el rol Administrador global tiene los permisos necesarios para *inscribir* la organización en Escritorio administrado de Microsoft. Ten en cuenta que Azure Active Directory roles de usuario darán privilegios a las cuentas de usuario en una variedad de servicios Microsoft. Después de completar la inscripción Escritorio administrado de Microsoft, siempre debe  usar el rol con los privilegios mínimos necesarios para realizar sus otras tareas.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Roles integrados proporcionados por Escritorio administrado de Microsoft


|Rol integrado  |Escritorio administrado de Microsoft permisos  |
|---------|---------|
|Escritorio administrado de Microsoft Administrador de servicios  | Cuando se asigna a un usuario, este rol concede al administrador permisos de lectura y escritura para características que no están relacionadas con la seguridad en el portal Escritorio administrado de Microsoft administración.   |
|Escritorio administrado de Microsoft Lector de servicios | Cuando se asigna a un usuario, este rol concede al administrador permisos de solo lectura a características que no están relacionadas con la seguridad en el portal de administración Escritorio administrado de Microsoft administración.  |
|Escritorio administrado de Microsoft Administrador de seguridad |Cuando se asigna a un usuario, este rol proporciona a ese administrador permisos de lectura y escritura solo para las características relacionadas con la seguridad en el portal de administración Escritorio administrado de Microsoft administración.    |

> [!NOTE]
> Las características de seguridad incluyen comunicaciones relacionadas con la seguridad, administración de contactos de seguridad, administración de solicitudes de soporte técnico relacionadas con la seguridad y acceso a informes relacionados con la seguridad. 

### <a name="assigning-built-in-roles-to-user"></a>Asignar roles integrados al usuario

Para facilitar la administración de roles integrados, hay un grupo de seguridad para cada rol personalizado con el nombre "Roles modernos del lugar de trabajo _-_ Nombre de rol" (por ejemplo, "Roles modernos del lugar de trabajo – Administrador de seguridad"). Para asignar usuarios a uno de estos grupos de seguridad, siga estos pasos:
1. Vaya al portal Microsoft Endpoint Manager web.
2. Seleccione **Grupos** en el lado izquierdo.
3. Busque Roles **modernos del lugar de** trabajo y, a continuación, seleccione el grupo asociado con el rol que desea asignar. 
4. Seleccione **Miembros** en el lado izquierdo y, a continuación, **seleccione + Agregar miembros** en la barra de comandos.
5. Escriba el correo electrónico de la persona que se va a agregar. Si son invitados, debe invitarlos antes de poder asignar el grupo.
6. Seleccione **Seleccionar** en la parte inferior.

> [!NOTE]
> Actualmente, no se admite el anidamiento de grupos de seguridad para la asignación de roles. 

### <a name="assigning-built-in-roles-to-groups"></a>Asignar roles integrados a grupos

Si necesita asignar uno o varios de los roles integrados a un grupo existente, siga estos pasos:

1. Vaya a [portal.azure.com](https://portal.azure.com/).
2. Busque y abra Enterprise **aplicaciones**.
3. Cambie el **filtro Tipo de** aplicación a Aplicaciones de _Microsoft_ y, a continuación, **seleccione Aplicar**.
4. Busque y seleccione API de _clientes de Modern Workplace_.
5. Seleccione **Usuarios y grupos en** el panel de la izquierda y, a continuación, seleccione + Agregar **usuario/grupo**.
6. Busque el grupo que desee de **Usuarios y grupos**.
7. Busque el rol aplicable en **Seleccionar un rol** y, a continuación, selecciónelo.
8. Seleccione **Asignar**.
