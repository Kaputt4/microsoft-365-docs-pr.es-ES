---
title: Administre el acceso a los datos de protección contra amenazas de Microsoft en el centro de seguridad de Microsoft 365
description: Obtenga información acerca de cómo administrar permisos en los datos de protección contra amenazas de Microsoft
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
ms.openlocfilehash: f747737fc94241ca5f65ad9881715f517d5fbe3c
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773844"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Administre el acceso a la protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden acceder a los datos y a la funcionalidad de protección contra amenazas de Microsoft:
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
El acceso a los datos de Protección contra amenazas de Microsoft puede controlarse con el ámbito asignado a los grupos de usuarios en el control de acceso basado en roles (RBAC) ATP de Microsoft defender. Si su acceso no se ha asignado a un conjunto específico de dispositivos en la ATP de Microsoft defender, tendrá acceso completo a los datos de Protección contra amenazas de Microsoft. Sin embargo, una vez que su cuenta está en el ámbito, solo verá los datos de los dispositivos de su ámbito.

Por ejemplo, si solo pertenece en un grupo de usuario con una función ATP de Microsoft Defender y se le ha concedido acceso solo a los dispositivos de ventas, solo verá los datos de los dispositivos de ventas en la Protección contra amenazas de Microsoft. [Más información acerca de la configuración de RBAC en Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controles de acceso a Microsoft Cloud App Security
Durante la versión preliminar, la Protección contra amenazas de Microsoft no exige los controles de acceso en función de la configuración de seguridad de aplicaciones en la nube. El acceso a los datos de protección contra amenazas de Microsoft no se ve afectado por esta configuración.

## <a name="related-topics"></a>Temas relacionados

- [Roles de Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac).
- [Roles de Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
