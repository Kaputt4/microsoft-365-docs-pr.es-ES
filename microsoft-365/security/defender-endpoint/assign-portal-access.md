---
title: Asignar el acceso de usuario al Centro de seguridad de Microsoft Defender
description: Asigne acceso de solo lectura y escritura al portal de Microsoft Defender para punto de conexión.
keywords: asignar roles de usuario, asignar acceso de lectura y escritura, asignar acceso de solo lectura, usuario, roles de usuario, roles
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.service: microsoft-365-security
ms.subservice: mde
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.openlocfilehash: aca5eb43b29076e0a320b472e55f35abfbaa42a6
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68146819"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Asignar el acceso de usuario al Centro de seguridad de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- Azure Active Directory
- Office 365
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint admite dos maneras de administrar permisos:

- **Administración básica de permisos**: establezca los permisos en acceso completo o de solo lectura.
- **Control de acceso basado en rol (RBAC):** establezca permisos granulares mediante la definición de roles, la asignación de grupos de usuarios de Azure AD a los roles y la concesión de acceso a los grupos de usuarios a los grupos de dispositivos. Para obtener más información sobre RBAC, consulte [Administración del acceso al portal mediante el control de acceso basado en rol](rbac.md).

> [!NOTE]
> Si ya ha asignado permisos básicos, puede cambiar a RBAC en cualquier momento. Tenga en cuenta lo siguiente antes de realizar el cambio:
> - A los usuarios con acceso completo (a los usuarios a los que se les asigna el rol de directorio Administrador global o Administrador de seguridad en Azure AD), se les asigna automáticamente el rol de administrador predeterminado de Defender para punto de conexión, que también tiene acceso completo. Se pueden asignar grupos de usuarios de Azure AD adicionales al rol de administrador de Defender para punto de conexión después de cambiar a RBAC. Solo los usuarios asignados al rol de administrador de Defender para punto de conexión pueden administrar permisos mediante RBAC. 
> - Los usuarios que tienen acceso de solo lectura (lectores de seguridad) perderán el acceso al portal hasta que se les asigne un rol. Tenga en cuenta que solo se puede asignar un rol a los grupos de usuarios de Azure AD en RBAC.
> - Después de cambiar a RBAC, no podrá volver a usar la administración básica de permisos.
>
>  La creación de grupos de dispositivos se admite en El plan 1 y el plan 2 de Defender para punto de conexión.

## <a name="related-topics"></a>Temas relacionados

- [Uso de permisos básicos para acceder al portal](basic-permissions.md)
- [Administrar el acceso al portal con RBAC](rbac.md)
