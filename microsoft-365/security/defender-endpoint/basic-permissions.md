---
title: Use permisos básicos para obtener acceso a Centro de seguridad de Microsoft Defender
description: Obtenga información sobre cómo usar permisos básicos para obtener acceso al portal de Microsoft Defender para endpoints.
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
ms.technology: mde
ms.openlocfilehash: 2d022e903111c498d6f3b7411857748fcb637b64
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844663"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="3313e-104">Uso de permisos básicos para acceder al portal</span><span class="sxs-lookup"><span data-stu-id="3313e-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3313e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3313e-105">**Applies to:**</span></span>
- <span data-ttu-id="3313e-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3313e-106">Azure Active Directory</span></span>
- [<span data-ttu-id="3313e-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3313e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3313e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3313e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3313e-109">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3313e-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3313e-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="3313e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="3313e-111">Consulte las instrucciones siguientes para usar la administración de permisos básicos.</span><span class="sxs-lookup"><span data-stu-id="3313e-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="3313e-112">Puede usar cualquiera de las siguientes soluciones:</span><span class="sxs-lookup"><span data-stu-id="3313e-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="3313e-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="3313e-113">Azure PowerShell</span></span>
- <span data-ttu-id="3313e-114">Portal de Azure</span><span class="sxs-lookup"><span data-stu-id="3313e-114">Azure portal</span></span>

<span data-ttu-id="3313e-115">Para el control granular sobre los permisos, [cambie al control de](rbac.md)acceso basado en roles .</span><span class="sxs-lookup"><span data-stu-id="3313e-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="3313e-116">Asignar acceso de usuario mediante Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="3313e-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="3313e-117">Puede asignar usuarios con uno de los siguientes niveles de permisos:</span><span class="sxs-lookup"><span data-stu-id="3313e-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="3313e-118">Acceso completo (lectura y escritura)</span><span class="sxs-lookup"><span data-stu-id="3313e-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="3313e-119">Acceso de solo lectura</span><span class="sxs-lookup"><span data-stu-id="3313e-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="3313e-120">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="3313e-120">Before you begin</span></span>

- <span data-ttu-id="3313e-121">Instale Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3313e-121">Install Azure PowerShell.</span></span> <span data-ttu-id="3313e-122">Para obtener más información, vea [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span><span class="sxs-lookup"><span data-stu-id="3313e-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="3313e-123">Debe ejecutar los cmdlets de PowerShell en una línea de comandos con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="3313e-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="3313e-124">Conectar a su Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3313e-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="3313e-125">Para obtener más información, [vea Conectar-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="3313e-125">For more information, see [Connect-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="3313e-126">**Acceso completo**</span><span class="sxs-lookup"><span data-stu-id="3313e-126">**Full access**</span></span> <br>
<span data-ttu-id="3313e-127">Los usuarios con acceso completo pueden iniciar sesión, ver toda la información del sistema y resolver alertas, enviar archivos para un análisis profundo y descargar el paquete de incorporación.</span><span class="sxs-lookup"><span data-stu-id="3313e-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="3313e-128">La asignación de derechos de acceso completo requiere agregar los usuarios a los roles integrados "Administrador de seguridad" o "Administrador global" de AAD.</span><span class="sxs-lookup"><span data-stu-id="3313e-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="3313e-129">**Acceso de solo lectura**</span><span class="sxs-lookup"><span data-stu-id="3313e-129">**Read-only access**</span></span> <br>
<span data-ttu-id="3313e-130">Los usuarios con acceso de solo lectura pueden iniciar sesión, ver todas las alertas e información relacionada.</span><span class="sxs-lookup"><span data-stu-id="3313e-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="3313e-131">No podrán cambiar los estados de alerta, enviar archivos para un análisis profundo o realizar operaciones de cambio de estado.</span><span class="sxs-lookup"><span data-stu-id="3313e-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="3313e-132">La asignación de derechos de acceso de solo lectura requiere agregar los usuarios al rol integrado de Azure AD "Lector de seguridad".</span><span class="sxs-lookup"><span data-stu-id="3313e-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="3313e-133">Siga estos pasos para asignar roles de seguridad:</span><span class="sxs-lookup"><span data-stu-id="3313e-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="3313e-134">Para **obtener acceso de lectura y** escritura, asigne usuarios al rol de administrador de seguridad mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3313e-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="3313e-135">Para **el acceso de solo** lectura, asigne usuarios al rol de lector de seguridad mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3313e-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="3313e-136">Para obtener más información, vea [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="3313e-136">For more information, see [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="3313e-137">Asignar acceso de usuario mediante Azure Portal</span><span class="sxs-lookup"><span data-stu-id="3313e-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="3313e-138">Para obtener más información, vea [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="3313e-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="3313e-139">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="3313e-139">Related topic</span></span>

- [<span data-ttu-id="3313e-140">Administrar el acceso al portal con RBAC</span><span class="sxs-lookup"><span data-stu-id="3313e-140">Manage portal access using RBAC</span></span>](rbac.md)
