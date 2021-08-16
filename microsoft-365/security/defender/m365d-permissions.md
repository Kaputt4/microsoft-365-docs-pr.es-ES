---
title: Administrar el acceso a Microsoft 365 Defender datos en el portal Microsoft 365 Defender web
description: Obtenga información sobre cómo administrar los permisos de los datos en Microsoft 365 Defender
keywords: access, permissions, Microsoft 365 Defender, M365, security, MCAS, Cloud App Security, Microsoft Defender for Endpoint, scope, scoping, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 61d76d873005c2bdd37fc37f05cf6e520a302647
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58247961"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Administrar el acceso a Microsoft 365 Defender con Azure Active Directory roles globales

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Hay dos maneras de administrar el acceso a Microsoft 365 Defender
- **Roles Azure Active Directory global (AD)**
- **Acceso a roles personalizado**

Las cuentas asignadas a **los siguientes roles Azure Active Directory global (AD)** pueden tener acceso Microsoft 365 Defender funcionalidad y datos:
- Administrador global
- Administrador de seguridad
- Operador de seguridad
- Lector global
- Lector de seguridad

Para revisar las cuentas con estos roles, [vea Permisos en el portal de Microsoft 365 Defender.](https://security.microsoft.com/permissions)

**El acceso** a roles personalizado es una nueva funcionalidad en Microsoft 365 Defender y le permite administrar el acceso a datos, tareas y capacidades específicos en Microsoft Defender 365. Los roles personalizados ofrecen más control que los roles globales de Azure AD, lo que proporciona a los usuarios solo el acceso que necesitan con los roles menos permisivos necesarios.  Los roles personalizados se pueden crear además de los roles globales de Azure AD. [Obtenga más información sobre los roles personalizados](custom-roles.md).

> [!NOTE]
> Este artículo solo se aplica a la administración de roles Azure Active Directory global. Para obtener más información acerca del uso del control de acceso basado en roles personalizado, vea [Roles personalizados para el control de](custom-roles.md) acceso basado en roles

## <a name="access-to-functionality"></a>Acceso a la funcionalidad
El acceso a la funcionalidad específica está determinado por el de [roles de de Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Póngase en contacto con un administrador global si necesita tener acceso a funciones específicas que requieren que usted o el grupo de usuarios tenga asignado un nuevo rol.

### <a name="approve-pending-automated-tasks"></a>Aprobar tareas automatizadas pendientes
[Investigación y corrección automatizadas](m365d-autoir-actions.md)puede actuar en los mensajes de correo electrónico, las reglas de reenvío, los archivos, los mecanismos de persistencia y otros artefactos presentes durante las investigaciones. Para aprobar o rechazar acciones pendientes que requieran aprobación explícita, debe tener determinadas funciones asignadas en Microsoft 365. Para obtener más información, consulte [permisos del centro de actividades](m365d-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Acceso a datos
El acceso Microsoft 365 Defender datos se puede controlar mediante el ámbito asignado a grupos de usuarios en Microsoft Defender para el control de acceso basado en roles (RBAC) de Microsoft Defender para el extremo. Si el acceso no se ha establecido en un conjunto específico de dispositivos en defender para el punto de conexión, tendrá acceso total a los datos en Microsoft 365 Defender. Sin embargo, una vez que su cuenta está en el ámbito, solo verá los datos de los dispositivos de su ámbito.

Por ejemplo, si perteneces a un solo grupo de usuarios con un rol de Microsoft Defender para endpoint y ese grupo de usuarios solo tiene acceso a dispositivos de ventas, solo verás datos sobre dispositivos de ventas en Microsoft 365 Defender. [Más información sobre la configuración de RBAC en Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controles de acceso a Microsoft Cloud App Security
Durante la vista previa, Microsoft 365 Defender aplica controles de acceso en función de Cloud App Security configuración. El acceso a Microsoft 365 Defender datos no se ve afectado por esta configuración.

## <a name="related-topics"></a>Temas relacionados
- [Roles personalizados en el control de acceso basado en roles para Microsoft 365 Defender](custom-roles.md)
- [Roles de Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Rbac de Microsoft Defender para extremo](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Roles de Cloud App Security](/cloud-app-security/manage-admins)
