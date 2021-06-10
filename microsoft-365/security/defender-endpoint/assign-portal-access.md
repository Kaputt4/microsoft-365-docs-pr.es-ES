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
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="7fb9b-104">Asignar acceso de usuario a Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7fb9b-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7fb9b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7fb9b-105">**Applies to:**</span></span>
- <span data-ttu-id="7fb9b-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7fb9b-106">Azure Active Directory</span></span>
- <span data-ttu-id="7fb9b-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="7fb9b-107">Office 365</span></span>
- [<span data-ttu-id="7fb9b-108">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7fb9b-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7fb9b-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fb9b-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="7fb9b-110">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7fb9b-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7fb9b-111">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="7fb9b-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="7fb9b-112">Defender for Endpoint admite dos formas de administrar permisos:</span><span class="sxs-lookup"><span data-stu-id="7fb9b-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="7fb9b-113">**Administración de permisos básicos:** establezca los permisos en acceso completo o de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="7fb9b-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="7fb9b-114">Control de acceso basado en roles **(RBAC):** establezca permisos granulares definiendo roles, asignando grupos de usuarios de Azure AD a los roles y concediendo a los grupos de usuarios acceso a grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7fb9b-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="7fb9b-115">Para obtener más información sobre RBAC, vea [Manage portal access using role-based access control](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="7fb9b-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7fb9b-116">Si ya ha asignado permisos básicos, puede cambiar a RBAC en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="7fb9b-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="7fb9b-117">Tenga en cuenta lo siguiente antes de realizar el cambio:</span><span class="sxs-lookup"><span data-stu-id="7fb9b-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="7fb9b-118">A los usuarios con acceso completo (usuarios a los que se les asigna el rol de directorio Administrador global o Administrador de seguridad en Azure AD), se les asigna automáticamente el rol de administrador de Defender for Endpoint predeterminado, que también tiene acceso completo.</span><span class="sxs-lookup"><span data-stu-id="7fb9b-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="7fb9b-119">Después de cambiar a RBAC, se pueden asignar grupos de usuarios de Azure AD adicionales al rol de administrador Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7fb9b-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="7fb9b-120">Solo los usuarios asignados al rol de administrador Defender for Endpoint pueden administrar permisos mediante RBAC.</span><span class="sxs-lookup"><span data-stu-id="7fb9b-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="7fb9b-121">Los usuarios con acceso de solo lectura (lectores de seguridad) perderán el acceso al portal hasta que se les asigne un rol.</span><span class="sxs-lookup"><span data-stu-id="7fb9b-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="7fb9b-122">Tenga en cuenta que solo se puede asignar un rol a los grupos de usuarios de Azure AD en RBAC.</span><span class="sxs-lookup"><span data-stu-id="7fb9b-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="7fb9b-123">Después de cambiar a RBAC, no podrá volver a usar la administración de permisos básicos.</span><span class="sxs-lookup"><span data-stu-id="7fb9b-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7fb9b-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7fb9b-124">Related topics</span></span>

- [<span data-ttu-id="7fb9b-125">Uso de permisos básicos para acceder al portal</span><span class="sxs-lookup"><span data-stu-id="7fb9b-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="7fb9b-126">Administrar el acceso al portal con RBAC</span><span class="sxs-lookup"><span data-stu-id="7fb9b-126">Manage portal access using RBAC</span></span>](rbac.md)
