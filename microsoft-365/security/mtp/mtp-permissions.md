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
ms.openlocfilehash: a619a6ff5256b3b70302d1bef4f0bc21bd7ac3e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927911"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="4eef4-104">Administrar el acceso a Microsoft 365 Defender con roles globales de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4eef4-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4eef4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4eef4-105">**Applies to:**</span></span>
- <span data-ttu-id="4eef4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eef4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4eef4-107">Hay dos formas de administrar el acceso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eef4-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="4eef4-108">**Roles globales de Azure Active Directory (AD)**</span><span class="sxs-lookup"><span data-stu-id="4eef4-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="4eef4-109">**Acceso a roles personalizado**</span><span class="sxs-lookup"><span data-stu-id="4eef4-109">**Custom role access**</span></span>

<span data-ttu-id="4eef4-110">Las cuentas asignadas a los **siguientes roles globales de Azure Active Directory (AD)** pueden tener acceso a datos y funciones de Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="4eef4-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="4eef4-111">Administrador global</span><span class="sxs-lookup"><span data-stu-id="4eef4-111">Global administrator</span></span>
- <span data-ttu-id="4eef4-112">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="4eef4-112">Security administrator</span></span>
- <span data-ttu-id="4eef4-113">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="4eef4-113">Security Operator</span></span>
- <span data-ttu-id="4eef4-114">Lector global</span><span class="sxs-lookup"><span data-stu-id="4eef4-114">Global Reader</span></span>
- <span data-ttu-id="4eef4-115">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="4eef4-115">Security Reader</span></span>

<span data-ttu-id="4eef4-116">Para revisar cuentas con estos roles, [vea los permisos en el centro de seguridad 365 de Microsoft](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="4eef4-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="4eef4-117">**El acceso** a roles personalizado es una nueva funcionalidad de Microsoft 365 Defender y le permite administrar el acceso a datos, tareas y capacidades específicos en Microsoft Defender 365.</span><span class="sxs-lookup"><span data-stu-id="4eef4-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="4eef4-118">Los roles personalizados ofrecen más control que los roles globales de Azure AD, lo que proporciona a los usuarios solo el acceso que necesitan con los roles menos permisivos necesarios.</span><span class="sxs-lookup"><span data-stu-id="4eef4-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="4eef4-119">Los roles personalizados se pueden crear además de los roles globales de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4eef4-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="4eef4-120">[Obtenga más información sobre los roles personalizados](custom-roles.md).</span><span class="sxs-lookup"><span data-stu-id="4eef4-120">[Learn more about custom roles](custom-roles.md).</span></span>

> <span data-ttu-id="4eef4-121">! [NOTA] Este artículo solo se aplica a la administración de roles globales de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4eef4-121">![NOTE] This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="4eef4-122">Para obtener más información acerca del uso del control de acceso basado en roles personalizado, vea [Roles personalizados para el control de](custom-roles.md) acceso basado en roles</span><span class="sxs-lookup"><span data-stu-id="4eef4-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="4eef4-123">Acceso a la funcionalidad</span><span class="sxs-lookup"><span data-stu-id="4eef4-123">Access to functionality</span></span>
<span data-ttu-id="4eef4-124">El acceso a la funcionalidad específica está determinado por el de [roles de de Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="4eef4-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="4eef4-125">Póngase en contacto con un administrador global si necesita tener acceso a funciones específicas que requieren que usted o el grupo de usuarios tenga asignado un nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="4eef4-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="4eef4-126">Aprobar tareas automatizadas pendientes</span><span class="sxs-lookup"><span data-stu-id="4eef4-126">Approve pending automated tasks</span></span>
<span data-ttu-id="4eef4-127">[Investigación y corrección automatizadas](mtp-autoir-actions.md)puede actuar en los mensajes de correo electrónico, las reglas de reenvío, los archivos, los mecanismos de persistencia y otros artefactos presentes durante las investigaciones.</span><span class="sxs-lookup"><span data-stu-id="4eef4-127">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="4eef4-128">Para aprobar o rechazar acciones pendientes que requieran aprobación explícita, debe tener determinadas funciones asignadas en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4eef4-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="4eef4-129">Para obtener más información, consulte [permisos del centro de actividades](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="4eef4-129">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="4eef4-130">Acceso a datos</span><span class="sxs-lookup"><span data-stu-id="4eef4-130">Access to data</span></span>
<span data-ttu-id="4eef4-131">El acceso a los datos de Microsoft 365 Defender se puede controlar mediante el ámbito asignado a grupos de usuarios en Microsoft Defender para el control de acceso basado en roles de extremo (RBAC).</span><span class="sxs-lookup"><span data-stu-id="4eef4-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="4eef4-132">Si el acceso no se ha establecido en un conjunto específico de dispositivos en Defender for Endpoint, tendrá acceso total a los datos en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4eef4-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="4eef4-133">Sin embargo, una vez que su cuenta está en el ámbito, solo verá los datos de los dispositivos de su ámbito.</span><span class="sxs-lookup"><span data-stu-id="4eef4-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="4eef4-134">Por ejemplo, si pertenece a un solo grupo de usuarios con un rol de Microsoft Defender para endpoint y ese grupo de usuarios solo tiene acceso a dispositivos de ventas, solo verá datos sobre dispositivos de ventas en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4eef4-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="4eef4-135">Más información sobre la configuración de RBAC en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="4eef4-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="4eef4-136">Controles de acceso a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4eef4-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="4eef4-137">Durante la vista previa, Microsoft 365 Defender no aplica controles de acceso basados en la configuración de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4eef4-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="4eef4-138">El acceso a los datos de Microsoft 365 Defender no se ve afectado por esta configuración.</span><span class="sxs-lookup"><span data-stu-id="4eef4-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4eef4-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4eef4-139">Related topics</span></span>
- [<span data-ttu-id="4eef4-140">Roles personalizados en el control de acceso basado en roles para Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eef4-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="4eef4-141">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="4eef4-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="4eef4-142">Rbac de Microsoft Defender para extremo</span><span class="sxs-lookup"><span data-stu-id="4eef4-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="4eef4-143">Roles de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4eef4-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)