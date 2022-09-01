---
title: Administración del acceso a datos de Microsoft 365 Defender en el portal de Microsoft 365 Defender
description: Obtenga información sobre cómo administrar permisos para los datos de Microsoft 365 Defender
keywords: access, permissions, Microsoft 365 Defender, M365, security, Defender for Cloud Apps, Microsoft Defender para punto de conexión, scope, scoping, RBAC
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 41cfe8d191f553ce2a6498d9badfd46e19f4c61e
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67495135"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Administración del acceso a Microsoft 365 Defender con roles globales de Azure Active Directory

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Hay dos maneras de administrar el acceso a Microsoft 365 Defender:
- **Roles globales de Azure Active Directory (AD)**
- **Acceso a roles personalizados**

Las cuentas asignadas a los siguientes **roles globales de Azure Active Directory (AD)** pueden acceder a Microsoft 365 Defender funcionalidad y datos:
- Administrador global
- Administrador de seguridad
- Operador de seguridad
- Lector global
- Lector de seguridad

Para revisar las cuentas con estos roles, [vea Permisos en el portal de Microsoft 365 Defender](https://security.microsoft.com/permissions).

El acceso a **roles personalizados** es una nueva funcionalidad de Microsoft 365 Defender y le permite administrar el acceso a datos, tareas y funcionalidades específicos en Microsoft 365 Defender. Los roles personalizados ofrecen más control que los roles globales de Azure AD, lo que proporciona a los usuarios solo el acceso que necesitan con los roles menos permisivos necesarios.  Los roles personalizados se pueden crear además de los roles globales de Azure AD. [Obtenga más información sobre los roles personalizados](custom-roles.md).

> [!NOTE]
> Este artículo solo se aplica a la administración de roles globales de Azure Active Directory. Para obtener más información sobre el uso del control de acceso basado en rol personalizado, consulte [Roles personalizados para el control de acceso basado en rol](custom-roles.md).

## <a name="access-to-functionality"></a>Acceso a la funcionalidad
El acceso a la funcionalidad específica está determinado por el de [roles de de Azure AD](/azure/active-directory/roles/permissions-reference). Póngase en contacto con un administrador global si necesita tener acceso a funciones específicas que requieren que usted o el grupo de usuarios tenga asignado un nuevo rol.

### <a name="approve-pending-automated-tasks"></a>Aprobar tareas automatizadas pendientes
[Investigación y corrección automatizadas](m365d-autoir-actions.md)puede actuar en los mensajes de correo electrónico, las reglas de reenvío, los archivos, los mecanismos de persistencia y otros artefactos presentes durante las investigaciones. Para aprobar o rechazar acciones pendientes que requieran aprobación explícita, debe tener determinadas funciones asignadas en Microsoft 365. Para obtener más información, consulte [permisos del centro de actividades](m365d-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Acceso a datos
El acceso a Microsoft 365 Defender datos se puede controlar mediante el ámbito asignado a grupos de usuarios en Microsoft Defender para punto de conexión control de acceso basado en rol (RBAC). Si el acceso no se ha limitado a un conjunto específico de dispositivos en Defender para punto de conexión, tendrá acceso total a los datos en Microsoft 365 Defender. Sin embargo, una vez que su cuenta está en el ámbito, solo verá los datos de los dispositivos de su ámbito.

Por ejemplo, si solo pertenece a un grupo de usuarios con un rol de Microsoft Defender para punto de conexión y a ese grupo de usuarios solo se le ha dado acceso a los dispositivos de ventas, solo verá datos sobre los dispositivos de ventas en Microsoft 365 Defender. [Más información sobre la configuración de RBAC en Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-defender-for-cloud-apps-access-controls"></a>Microsoft Defender for Cloud Apps controles de acceso
Durante la versión preliminar, Microsoft 365 Defender no aplica controles de acceso basados en la configuración de Defender for Cloud Apps. El acceso a Microsoft 365 Defender datos no se ve afectado por esta configuración.

## <a name="related-topics"></a>Temas relacionados
- [Roles personalizados en el control de acceso basado en rol para Microsoft 365 Defender](custom-roles.md)
- [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference)
- [Microsoft Defender para punto de conexión RBAC](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Roles de Defender for Cloud Apps](/cloud-app-security/manage-admins)
