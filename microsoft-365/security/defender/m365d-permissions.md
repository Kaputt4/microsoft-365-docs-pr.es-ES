---
title: Administrar el acceso a Microsoft 365 Defender datos en el centro Microsoft 365 seguridad
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
ms.openlocfilehash: 738315c446fd57d4cd027de92eb77b0029f84323
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177535"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="804b3-104">Administrar el acceso a Microsoft 365 Defender con Azure Active Directory roles globales</span><span class="sxs-lookup"><span data-stu-id="804b3-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="804b3-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="804b3-105">**Applies to:**</span></span>
- <span data-ttu-id="804b3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="804b3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="804b3-107">Hay dos maneras de administrar el acceso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="804b3-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="804b3-108">**Roles Azure Active Directory global (AD)**</span><span class="sxs-lookup"><span data-stu-id="804b3-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="804b3-109">**Acceso a roles personalizado**</span><span class="sxs-lookup"><span data-stu-id="804b3-109">**Custom role access**</span></span>

<span data-ttu-id="804b3-110">Las cuentas asignadas a **los siguientes roles Azure Active Directory global (AD)** pueden tener acceso Microsoft 365 Defender funcionalidad y datos:</span><span class="sxs-lookup"><span data-stu-id="804b3-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="804b3-111">Administrador global</span><span class="sxs-lookup"><span data-stu-id="804b3-111">Global administrator</span></span>
- <span data-ttu-id="804b3-112">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="804b3-112">Security administrator</span></span>
- <span data-ttu-id="804b3-113">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="804b3-113">Security Operator</span></span>
- <span data-ttu-id="804b3-114">Lector global</span><span class="sxs-lookup"><span data-stu-id="804b3-114">Global Reader</span></span>
- <span data-ttu-id="804b3-115">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="804b3-115">Security Reader</span></span>

<span data-ttu-id="804b3-116">Para revisar cuentas con estos roles, [vea los permisos en el centro de seguridad 365 de Microsoft](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="804b3-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="804b3-117">**El acceso** a roles personalizado es una nueva funcionalidad en Microsoft 365 Defender y le permite administrar el acceso a datos, tareas y capacidades específicos en Microsoft Defender 365.</span><span class="sxs-lookup"><span data-stu-id="804b3-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="804b3-118">Los roles personalizados ofrecen más control que los roles globales de Azure AD, lo que proporciona a los usuarios solo el acceso que necesitan con los roles menos permisivos necesarios.</span><span class="sxs-lookup"><span data-stu-id="804b3-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="804b3-119">Los roles personalizados se pueden crear además de los roles globales de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="804b3-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="804b3-120">[Obtenga más información sobre los roles personalizados](custom-roles.md).</span><span class="sxs-lookup"><span data-stu-id="804b3-120">[Learn more about custom roles](custom-roles.md).</span></span>

> [!NOTE]
> <span data-ttu-id="804b3-121">Este artículo solo se aplica a la administración de roles Azure Active Directory global.</span><span class="sxs-lookup"><span data-stu-id="804b3-121">This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="804b3-122">Para obtener más información acerca del uso del control de acceso basado en roles personalizado, vea [Roles personalizados para el control de](custom-roles.md) acceso basado en roles</span><span class="sxs-lookup"><span data-stu-id="804b3-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="804b3-123">Acceso a la funcionalidad</span><span class="sxs-lookup"><span data-stu-id="804b3-123">Access to functionality</span></span>
<span data-ttu-id="804b3-124">El acceso a la funcionalidad específica está determinado por el de [roles de de Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="804b3-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="804b3-125">Póngase en contacto con un administrador global si necesita tener acceso a funciones específicas que requieren que usted o el grupo de usuarios tenga asignado un nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="804b3-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="804b3-126">Aprobar tareas automatizadas pendientes</span><span class="sxs-lookup"><span data-stu-id="804b3-126">Approve pending automated tasks</span></span>
<span data-ttu-id="804b3-127">[Investigación y corrección automatizadas](m365d-autoir-actions.md)puede actuar en los mensajes de correo electrónico, las reglas de reenvío, los archivos, los mecanismos de persistencia y otros artefactos presentes durante las investigaciones.</span><span class="sxs-lookup"><span data-stu-id="804b3-127">[Automated investigation and remediation](m365d-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="804b3-128">Para aprobar o rechazar acciones pendientes que requieran aprobación explícita, debe tener determinadas funciones asignadas en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="804b3-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="804b3-129">Para obtener más información, consulte [permisos del centro de actividades](m365d-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="804b3-129">To learn more, see [Action center permissions](m365d-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="804b3-130">Acceso a datos</span><span class="sxs-lookup"><span data-stu-id="804b3-130">Access to data</span></span>
<span data-ttu-id="804b3-131">El acceso Microsoft 365 Defender datos se puede controlar mediante el ámbito asignado a grupos de usuarios en Microsoft Defender para el control de acceso basado en roles (RBAC) de Microsoft Defender para el extremo.</span><span class="sxs-lookup"><span data-stu-id="804b3-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="804b3-132">Si el acceso no se ha establecido en un conjunto específico de dispositivos en defender para el punto de conexión, tendrá acceso total a los datos en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="804b3-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="804b3-133">Sin embargo, una vez que su cuenta está en el ámbito, solo verá los datos de los dispositivos de su ámbito.</span><span class="sxs-lookup"><span data-stu-id="804b3-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="804b3-134">Por ejemplo, si perteneces a un solo grupo de usuarios con un rol de Microsoft Defender para endpoint y ese grupo de usuarios solo tiene acceso a dispositivos de ventas, solo verás datos sobre dispositivos de ventas en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="804b3-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="804b3-135">Más información sobre la configuración de RBAC en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="804b3-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="804b3-136">Controles de acceso a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="804b3-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="804b3-137">Durante la vista previa, Microsoft 365 Defender aplica controles de acceso en función de Cloud App Security configuración.</span><span class="sxs-lookup"><span data-stu-id="804b3-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="804b3-138">El acceso a Microsoft 365 Defender datos no se ve afectado por esta configuración.</span><span class="sxs-lookup"><span data-stu-id="804b3-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="804b3-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="804b3-139">Related topics</span></span>
- [<span data-ttu-id="804b3-140">Roles personalizados en el control de acceso basado en roles para Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="804b3-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="804b3-141">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="804b3-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="804b3-142">Rbac de Microsoft Defender para extremo</span><span class="sxs-lookup"><span data-stu-id="804b3-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="804b3-143">Roles de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="804b3-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)
