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
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="2a11e-104">Administración del acceso a Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="2a11e-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2a11e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2a11e-105">**Applies to:**</span></span>
- <span data-ttu-id="2a11e-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="2a11e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2a11e-107">Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden tener acceso a los datos y la funcionalidad de Microsoft 365 defender:</span><span class="sxs-lookup"><span data-stu-id="2a11e-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="2a11e-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="2a11e-108">Global administrator</span></span>
- <span data-ttu-id="2a11e-109">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="2a11e-109">Security administrator</span></span>
- <span data-ttu-id="2a11e-110">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="2a11e-110">Security Operator</span></span>
- <span data-ttu-id="2a11e-111">Lector global</span><span class="sxs-lookup"><span data-stu-id="2a11e-111">Global Reader</span></span>
- <span data-ttu-id="2a11e-112">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="2a11e-112">Security Reader</span></span>

<span data-ttu-id="2a11e-113">Para revisar cuentas con estos roles, [vea los permisos en el centro de seguridad 365 de Microsoft](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="2a11e-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="2a11e-114">Acceso a la funcionalidad</span><span class="sxs-lookup"><span data-stu-id="2a11e-114">Access to functionality</span></span>
<span data-ttu-id="2a11e-115">El acceso a la funcionalidad específica está determinado por el de [roles de de Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="2a11e-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="2a11e-116">Póngase en contacto con un administrador global si necesita tener acceso a funciones específicas que requieren que usted o el grupo de usuarios tenga asignado un nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="2a11e-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="2a11e-117">Aprobar tareas automatizadas pendientes</span><span class="sxs-lookup"><span data-stu-id="2a11e-117">Approve pending automated tasks</span></span>
<span data-ttu-id="2a11e-118">[Investigación y corrección automatizadas](mtp-autoir-actions.md)puede actuar en los mensajes de correo electrónico, las reglas de reenvío, los archivos, los mecanismos de persistencia y otros artefactos presentes durante las investigaciones.</span><span class="sxs-lookup"><span data-stu-id="2a11e-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="2a11e-119">Para aprobar o rechazar acciones pendientes que requieran aprobación explícita, debe tener determinadas funciones asignadas en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2a11e-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="2a11e-120">Para obtener más información, consulte [permisos del centro de actividades](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="2a11e-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="2a11e-121">Acceso a datos</span><span class="sxs-lookup"><span data-stu-id="2a11e-121">Access to data</span></span>
<span data-ttu-id="2a11e-122">El acceso a los datos de Microsoft 365 defender se puede controlar mediante el ámbito asignado a los grupos de usuarios en Microsoft defender para el control de acceso basado en roles de extremo (RBAC).</span><span class="sxs-lookup"><span data-stu-id="2a11e-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="2a11e-123">Si no se ha establecido el ámbito de acceso a un conjunto específico de dispositivos de defender para el punto de conexión, tendrá acceso total a los datos de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="2a11e-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="2a11e-124">Sin embargo, una vez que su cuenta está en el ámbito, solo verá los datos de los dispositivos de su ámbito.</span><span class="sxs-lookup"><span data-stu-id="2a11e-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="2a11e-125">Por ejemplo, si solo pertenece a un grupo de usuarios con un rol de Microsoft defender para extremo y ese grupo de usuarios solo tiene acceso a los dispositivos de ventas, verá solo los datos sobre los dispositivos de ventas en Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="2a11e-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="2a11e-126">Obtenga más información sobre la configuración de RBAC en Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2a11e-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="2a11e-127">Controles de acceso a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2a11e-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="2a11e-128">Durante la vista previa, Microsoft 365 defender no exige los controles de acceso basados en la configuración de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="2a11e-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="2a11e-129">El acceso a los datos de Microsoft 365 defender no se ve afectado por esta configuración.</span><span class="sxs-lookup"><span data-stu-id="2a11e-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a11e-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2a11e-130">Related topics</span></span>

- [<span data-ttu-id="2a11e-131">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="2a11e-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="2a11e-132">Microsoft defender para el RBAC de extremo</span><span class="sxs-lookup"><span data-stu-id="2a11e-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="2a11e-133">Roles de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2a11e-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
