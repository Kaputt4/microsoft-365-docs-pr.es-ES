---
title: Asignar acceso de usuario a Centro de seguridad de Microsoft Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: fa0157a37cf25efcdcf1b578473b4dc2f6deb10d
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166967"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Asignar acceso de usuario a Centro de seguridad de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- Azure Active Directory
- Office 365
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint admite dos formas de administrar permisos:

- **Administración de permisos básicos:** establezca los permisos en acceso completo o de solo lectura.
- Control de acceso basado en roles **(RBAC):** establezca permisos granulares definiendo roles, asignando Azure AD grupos de usuarios a los roles y otorgando a los grupos de usuarios acceso a grupos de dispositivos. Para obtener más información sobre RBAC, vea [Manage portal access using role-based access control](rbac.md).

> [!NOTE]
> Si ya ha asignado permisos básicos, puede cambiar a RBAC en cualquier momento. Tenga en cuenta lo siguiente antes de realizar el cambio:
>
> - A los usuarios con acceso completo (usuarios a los que se les asigna el rol de directorio Administrador global o Administrador de seguridad en Azure AD), se les asigna automáticamente el rol de administrador de Defender para extremo predeterminado, que también tiene acceso completo. Los Azure AD usuarios adicionales se pueden asignar al rol de administrador Defender for Endpoint después de cambiar a RBAC. Solo los usuarios asignados al rol de administrador Defender for Endpoint pueden administrar permisos mediante RBAC. 
> - Los usuarios con acceso de solo lectura (lectores de seguridad) perderán el acceso al portal hasta que se les asigne un rol. Tenga en cuenta que solo Azure AD grupos de usuarios pueden tener asignado un rol en RBAC.
> - Después de cambiar a RBAC, no podrá volver a usar la administración de permisos básicos.

## <a name="related-topics"></a>Temas relacionados

- [Uso de permisos básicos para acceder al portal](basic-permissions.md)
- [Administrar el acceso al portal con RBAC](rbac.md)
