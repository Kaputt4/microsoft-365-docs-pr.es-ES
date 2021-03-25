---
title: Asignar acceso de usuario al Centro de seguridad de Microsoft Defender
description: Asigne acceso de solo lectura y escritura o de solo lectura al portal de Microsoft Defender para endpoint.
keywords: asignar roles de usuario, asignar acceso de lectura y escritura, asignar acceso de solo lectura, usuario, roles de usuario, roles
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164782"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Asignar acceso de usuario al Centro de seguridad de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- Azure Active Directory
- Office 365
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint admite dos formas de administrar permisos:

- **Administración de permisos básicos:** establezca los permisos en acceso completo o de solo lectura.
- Control de acceso basado en roles **(RBAC):** establezca permisos granulares definiendo roles, asignando grupos de usuarios de Azure AD a los roles y concediendo a los grupos de usuarios acceso a grupos de dispositivos. Para obtener más información sobre RBAC, vea [Manage portal access using role-based access control](rbac.md).

> [!NOTE]
> Si ya ha asignado permisos básicos, puede cambiar a RBAC en cualquier momento. Tenga en cuenta lo siguiente antes de realizar el cambio:
> 
> - A los usuarios con acceso completo (usuarios a los que se les asigna el rol de directorio Administrador global o Administrador de seguridad en Azure AD), se les asigna automáticamente el rol de administrador de Defender for Endpoint predeterminado, que también tiene acceso completo. Después de cambiar a RBAC, se pueden asignar grupos de usuarios de Azure AD adicionales al rol de administrador Defender for Endpoint.  Solo los usuarios asignados al rol de administrador Defender for Endpoint pueden administrar permisos mediante RBAC. 
> - Los usuarios con acceso de solo lectura (lectores de seguridad) perderán el acceso al portal hasta que se les asigne un rol. Tenga en cuenta que solo se puede asignar un rol a los grupos de usuarios de Azure AD en RBAC.
> - Después de cambiar a RBAC, no podrá volver a usar la administración de permisos básicos.

## <a name="related-topics"></a>Temas relacionados

- [Usar permisos básicos para obtener acceso al portal](basic-permissions.md)
- [Administrar el acceso al portal mediante RBAC](rbac.md)
