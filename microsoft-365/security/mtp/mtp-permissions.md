---
title: Administrar el acceso a los datos de Microsoft 365 Defender en el Centro de seguridad de Microsoft 365
description: Obtenga información sobre cómo administrar permisos para datos en Microsoft 365 Defender
keywords: Access, permisos, MTP, seguridad de las amenazas de Microsoft, M365, seguridad, MCAS, MDATP, Cloud App Security, protección contra amenazas avanzada de Microsoft defender, ámbito, ámbito, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930143"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Administrar el acceso a Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden acceder a la funcionalidad y los datos de Microsoft 365 Defender:
- Administrador global
- Administrador de seguridad
- Operador de seguridad
- Lector global
- Lector de seguridad

Para revisar cuentas con estos roles, [vea los permisos en el centro de seguridad 365 de Microsoft](https://security.microsoft.com/permissions).

## <a name="access-to-functionality"></a>Acceso a la funcionalidad
El acceso a la funcionalidad específica está determinado por el de [roles de de Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Póngase en contacto con un administrador global si necesita tener acceso a funciones específicas que requieren que usted o el grupo de usuarios tenga asignado un nuevo rol.

### <a name="approve-pending-automated-tasks"></a>Aprobar tareas automatizadas pendientes
[Investigación y corrección automatizadas](mtp-autoir-actions.md)puede actuar en los mensajes de correo electrónico, las reglas de reenvío, los archivos, los mecanismos de persistencia y otros artefactos presentes durante las investigaciones. Para aprobar o rechazar acciones pendientes que requieran aprobación explícita, debe tener determinadas funciones asignadas en Microsoft 365. Para obtener más información, consulte [permisos del centro de actividades](mtp-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Acceso a datos
El acceso a los datos de Microsoft 365 Defender se puede controlar mediante el ámbito asignado a grupos de usuarios en Microsoft Defender para el control de acceso basado en roles (RBAC) de Endpoint. Si su acceso no se ha limitado a un conjunto específico de dispositivos en Defender for Endpoint, tendrá acceso completo a los datos en Microsoft 365 Defender. Sin embargo, una vez que su cuenta está en el ámbito, solo verá los datos de los dispositivos de su ámbito.

Por ejemplo, si pertenece a un solo grupo de usuarios con un rol de Microsoft Defender para puntos de conexión y solo se ha concedido acceso a ese grupo de usuarios a los dispositivos de ventas, solo verá los datos sobre los dispositivos de ventas en Microsoft 365 Defender. [Más información sobre la configuración de RBAC en Microsoft Defender para puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controles de acceso a Microsoft Cloud App Security
Durante la versión preliminar, Microsoft 365 Defender no aplica controles de acceso basados en la configuración de Cloud App Security. El acceso a los datos de Microsoft 365 Defender no se ve afectado por esta configuración.

## <a name="related-topics"></a>Temas relacionados

- [Roles de Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [RBAC de Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Roles de Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
