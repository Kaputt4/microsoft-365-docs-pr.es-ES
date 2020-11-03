---
title: Administración del acceso a los datos de Microsoft 365 defender en el centro de seguridad de Microsoft 365
description: Obtenga información sobre cómo administrar los permisos para datos en Microsoft 365 defender
keywords: Access, permisos, MTP, seguridad de las amenazas de Microsoft, M365, seguridad, MCAS, MDATP, Cloud App Security, protección contra amenazas avanzada de Microsoft defender, ámbito, ámbito, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 55b7b8c5755b773a4d53c95017a0a17a85495dee
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847253"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Administración del acceso a Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender

Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden tener acceso a los datos y la funcionalidad de Microsoft 365 defender:
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
El acceso a los datos de Microsoft 365 defender se puede controlar mediante el ámbito asignado a los grupos de usuarios en Microsoft defender para el control de acceso basado en roles de extremo (RBAC). Si no se ha establecido el ámbito de acceso a un conjunto específico de dispositivos de defender para el punto de conexión, tendrá acceso total a los datos de Microsoft 365 defender. Sin embargo, una vez que su cuenta está en el ámbito, solo verá los datos de los dispositivos de su ámbito.

Por ejemplo, si solo pertenece a un grupo de usuarios con un rol de Microsoft defender para extremo y ese grupo de usuarios solo tiene acceso a los dispositivos de ventas, verá solo los datos sobre los dispositivos de ventas en Microsoft 365 defender. [Obtenga más información sobre la configuración de RBAC en Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controles de acceso a Microsoft Cloud App Security
Durante la vista previa, Microsoft 365 defender no exige los controles de acceso basados en la configuración de Cloud App Security. El acceso a los datos de Microsoft 365 defender no se ve afectado por esta configuración.

## <a name="related-topics"></a>Temas relacionados

- [Roles de Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft defender para el RBAC de extremo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Roles de Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
