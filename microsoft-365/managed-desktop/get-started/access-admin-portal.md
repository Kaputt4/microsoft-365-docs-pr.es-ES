---
title: Acceso al portal de administración
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
description: Cómo buscar y usar el portal de administración, incluido el control del acceso a él.
ms.service: m365-md
ms.author: tiaraquan
author: tiaraquan
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.openlocfilehash: aee590f7479119ee7e8679b1048a691f156ccc77
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315083"
---
# <a name="access-the-admin-portal"></a>Acceso al portal de administración

La puerta de enlace al servicio de Escritorio administrado de Microsoft [es Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Si no estás familiarizado con las capacidades de este portal para la administración de dispositivos, consulta la [Microsoft Endpoint Manager datos](/mem/).

> [!NOTE]
> En [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) se admiten los siguientes exploradores:
> - Microsoft Edge (última versión)
> - Safari (última versión, solo en Mac)
> - Chrome (última versión)
> - Firefox (última versión)

Su cuenta administrativa necesitará permisos específicos para tener acceso a las características administrativas de Escritorio administrado de Microsoft en Microsoft Endpoint Manager.

Puede administrar el acceso de administrador a estas características dentro de la organización mediante el control de acceso basado en roles. Hay Azure Active Directory (Azure AD) de administrador y roles integrados de Escritorio administrado de Microsoft para proporcionar un control más detallado a las diferentes características del portal de administración de escritorio administrado de Microsoft. Para obtener más información acerca Azure Active Directory roles, [vea Azure AD roles integrados](/azure/active-directory/roles/permissions-reference).

A diferencia Azure AD roles de administrador que se aplican a varios productos y servicios de Microsoft, los roles integrados son específicos de Microsoft Managed Desktop y solo garantizan el acceso a las características de administrador de este servicio. Los administradores pueden asignar roles integrados a los usuarios individualmente o en combinación Azure AD roles de administrador para agregar permisos de Escritorio administrado de Microsoft a cuentas de administrador existentes.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory roles con acceso a Escritorio administrado de Microsoft

| Azure AD rol | Permisos de Escritorio administrado de Microsoft |
| ----- | ----- |
| Administrador global | Los administradores con este rol tendrán permisos de **lectura y escritura en todas las características** del portal de administración de escritorio administrado de Microsoft. |
| Lector global | Los administradores con este rol tendrán permisos de **solo lectura para** todas las características del portal de administración de escritorio administrado de Microsoft. |
| Administrador del servicio de Intune | Los administradores con este rol tendrán permisos de **lectura** y escritura para características que no están relacionadas con la seguridad en el portal de administración de escritorio administrado de Microsoft. |
| Administrador de soporte técnico de servicio | Los administradores con este rol tendrán  permisos de solo lectura para características que no están relacionadas con la  seguridad y los permisos de escritura para administrar solicitudes de soporte técnico, incluidas las solicitudes de escalado en el portal de administración de escritorio administrado de Microsoft. |
| Administrador de seguridad | Los administradores con este rol tendrán  permisos de solo lectura para todas las características y  permisos de escritura para las características relacionadas con la seguridad en Microsoft Managed Desktop en el portal de administración. |
| Lector de seguridad |Los administradores con este rol tendrán permisos de **solo lectura para** todas las características del portal de administración de escritorio administrado de Microsoft. |

Si necesita ayuda para asignar Azure Active Directory roles, [consulte Azure AD roles integrados](/azure/active-directory/roles/permissions-reference).

> [!IMPORTANT]
> Solo el rol Administrador global tiene los permisos necesarios para *inscribir* su organización en Microsoft Managed Desktop. Ten en cuenta que Azure Active Directory roles de usuario darán privilegios a las cuentas de usuario en una variedad de servicios Microsoft. Después de completar la inscripción con Microsoft Managed Desktop, siempre debes usar el rol con los  privilegios mínimos necesarios para realizar tus otras tareas.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Roles integrados proporcionados por Microsoft Managed Desktop

Los siguientes son los roles integrados proporcionados por Microsoft Managed Desktop:

| Rol integrado | Permisos de Escritorio administrado de Microsoft |
| ----- | ----- |
| Administrador del servicio de escritorio administrado de Microsoft | Cuando se asigna a un usuario, este rol concede al administrador permisos de lectura y escritura para las características de Escritorio administrado de **Microsoft** que no están relacionadas con la seguridad en el portal de administración de Escritorio administrado de Microsoft. |
| Lector de servicio de escritorio administrado de Microsoft | Cuando se asigna a un usuario, este rol concede al administrador permisos de solo lectura para las características de Escritorio administrado de **Microsoft** que no están relacionadas con la seguridad en el portal de administración de Escritorio administrado de Microsoft. |
| Administrador de seguridad de Escritorio administrado de Microsoft | Cuando se asigna a un usuario, este rol proporciona a **ese administrador permisos** de lectura y escritura solo para las características relacionadas con la seguridad en el portal de administración de escritorio administrado de Microsoft. |
| Partner de soporte técnico de Escritorio administrado de Microsoft |Cuando se asigna a un usuario, este rol proporciona al administrador permisos de lectura y escritura solo para crear y administrar solicitudes de elevación y admitir las solicitudes de escalación **comprometidas** por el partner en el portal de administración de escritorio administrado de Microsoft. |

> [!NOTE]
> Las características de seguridad incluyen comunicaciones relacionadas con la seguridad, administración de contactos de seguridad, administración de solicitudes de soporte técnico relacionadas con la seguridad y acceso a informes relacionados con la seguridad.

### <a name="assigning-built-in-roles-to-user"></a>Asignar roles integrados al usuario

Para facilitar la administración de roles integrados, hay un grupo de seguridad para cada rol personalizado con el nombre "Roles modernos del lugar de trabajo: _nombre del rol_". Por ejemplo, "Roles modernos del lugar de trabajo : Administrador de seguridad").

**Para asignar usuarios a uno de estos grupos de seguridad:**

1. Vaya al Microsoft Endpoint Manager web.
2. En el panel izquierdo, seleccione **Grupos**.
3. Busque Roles **modernos del lugar de** trabajo y, a continuación, seleccione el grupo asociado con el rol que desea asignar.
4. Seleccione **Miembros** en el lado izquierdo y, a continuación, **seleccione + Agregar miembros** en la barra de comandos.
5. Escriba el correo electrónico de la persona que se va a agregar. Si son invitados, debe invitarlos antes de poder asignar el grupo.
6. Seleccione **Seleccionar** en la parte inferior.

> [!NOTE]
> Actualmente, no se admite el anidamiento de grupos de seguridad para la asignación de roles.

### <a name="assigning-built-in-roles-to-groups"></a>Asignar roles integrados a grupos

**Para asignar uno o varios de los roles integrados a un grupo existente:**

1. Vaya a [portal.azure.com](https://portal.azure.com/).
2. Busque y abra Enterprise **aplicaciones**.
3. Cambie el **filtro Tipo de** aplicación a _Aplicaciones de Microsoft_ y, a continuación, seleccione **Aplicar**.
4. Busque y seleccione API de _clientes de Modern Workplace_.
5. Seleccione **Usuarios y grupos en** el panel de la izquierda y, a continuación, **seleccione + Agregar usuario o grupo**.
6. Busque el grupo que desee de **Usuarios y grupos**.
7. Busque el rol aplicable en **Seleccionar un rol** y, a continuación, selecciónelo.
8. Seleccione **Asignar**.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. Portal de administración de Access (este artículo).
1. [Agregar y verificar los contactos de administración en el portal de administrador](add-admin-contacts.md).
1. [Ajustar la configuración después de la inscripción](conditional-access.md).
1. Implementar y asignar el [Portal de empresa de Intune](company-portal.md).
1. [Asignar las licencias](assign-licenses.md).
1. [Implementar las aplicaciones](deploy-apps.md).
1. [Preparar dispositivos](prepare-devices.md).
1. Configurar la [experiencia de primera ejecución con el Autopilot y la página de estado de inscripción](esp-first-run.md).
1. [Habilitar las características de soporte técnico para el usuario](enable-support.md).
1. [Preparar a los usuarios para que usen los dispositivos](get-started-devices.md).
1. [Comenzar a usar el control de aplicaciones](get-started-app-control.md).
