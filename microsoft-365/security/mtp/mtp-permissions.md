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
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="e9d7c-104">Administrar el acceso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9d7c-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e9d7c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e9d7c-105">**Applies to:**</span></span>
- <span data-ttu-id="e9d7c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9d7c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e9d7c-107">Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden acceder a la funcionalidad y los datos de Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="e9d7c-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="e9d7c-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e9d7c-108">Global administrator</span></span>
- <span data-ttu-id="e9d7c-109">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="e9d7c-109">Security administrator</span></span>
- <span data-ttu-id="e9d7c-110">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="e9d7c-110">Security Operator</span></span>
- <span data-ttu-id="e9d7c-111">Lector global</span><span class="sxs-lookup"><span data-stu-id="e9d7c-111">Global Reader</span></span>
- <span data-ttu-id="e9d7c-112">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="e9d7c-112">Security Reader</span></span>

<span data-ttu-id="e9d7c-113">Para revisar cuentas con estos roles, [vea los permisos en el centro de seguridad 365 de Microsoft](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="e9d7c-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="e9d7c-114">Acceso a la funcionalidad</span><span class="sxs-lookup"><span data-stu-id="e9d7c-114">Access to functionality</span></span>
<span data-ttu-id="e9d7c-115">El acceso a la funcionalidad específica está determinado por el de [roles de de Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="e9d7c-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="e9d7c-116">Póngase en contacto con un administrador global si necesita tener acceso a funciones específicas que requieren que usted o el grupo de usuarios tenga asignado un nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="e9d7c-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="e9d7c-117">Aprobar tareas automatizadas pendientes</span><span class="sxs-lookup"><span data-stu-id="e9d7c-117">Approve pending automated tasks</span></span>
<span data-ttu-id="e9d7c-118">[Investigación y corrección automatizadas](mtp-autoir-actions.md)puede actuar en los mensajes de correo electrónico, las reglas de reenvío, los archivos, los mecanismos de persistencia y otros artefactos presentes durante las investigaciones.</span><span class="sxs-lookup"><span data-stu-id="e9d7c-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="e9d7c-119">Para aprobar o rechazar acciones pendientes que requieran aprobación explícita, debe tener determinadas funciones asignadas en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9d7c-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="e9d7c-120">Para obtener más información, consulte [permisos del centro de actividades](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="e9d7c-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="e9d7c-121">Acceso a datos</span><span class="sxs-lookup"><span data-stu-id="e9d7c-121">Access to data</span></span>
<span data-ttu-id="e9d7c-122">El acceso a los datos de Microsoft 365 Defender se puede controlar mediante el ámbito asignado a grupos de usuarios en Microsoft Defender para el control de acceso basado en roles (RBAC) de Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e9d7c-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="e9d7c-123">Si su acceso no se ha limitado a un conjunto específico de dispositivos en Defender for Endpoint, tendrá acceso completo a los datos en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e9d7c-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="e9d7c-124">Sin embargo, una vez que su cuenta está en el ámbito, solo verá los datos de los dispositivos de su ámbito.</span><span class="sxs-lookup"><span data-stu-id="e9d7c-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="e9d7c-125">Por ejemplo, si pertenece a un solo grupo de usuarios con un rol de Microsoft Defender para puntos de conexión y solo se ha concedido acceso a ese grupo de usuarios a los dispositivos de ventas, solo verá los datos sobre los dispositivos de ventas en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e9d7c-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="e9d7c-126">Más información sobre la configuración de RBAC en Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="e9d7c-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="e9d7c-127">Controles de acceso a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e9d7c-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="e9d7c-128">Durante la versión preliminar, Microsoft 365 Defender no aplica controles de acceso basados en la configuración de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="e9d7c-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="e9d7c-129">El acceso a los datos de Microsoft 365 Defender no se ve afectado por esta configuración.</span><span class="sxs-lookup"><span data-stu-id="e9d7c-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e9d7c-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e9d7c-130">Related topics</span></span>

- [<span data-ttu-id="e9d7c-131">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="e9d7c-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="e9d7c-132">RBAC de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="e9d7c-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="e9d7c-133">Roles de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e9d7c-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
