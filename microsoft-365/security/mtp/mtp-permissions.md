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
ms.openlocfilehash: 110bbe6fe48932217c9bdc009d175161fe9226cd
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235199"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="3b248-104">Administre el acceso a la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b248-104">Manage access to Microsoft Threat Protection</span></span>

<span data-ttu-id="3b248-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3b248-105">**Applies to:**</span></span>
- <span data-ttu-id="3b248-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b248-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="3b248-107">Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden acceder a los datos y a la funcionalidad de protección contra amenazas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="3b248-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="3b248-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="3b248-108">Global administrator</span></span>
- <span data-ttu-id="3b248-109">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="3b248-109">Security administrator</span></span>
- <span data-ttu-id="3b248-110">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="3b248-110">Security Operator</span></span>
- <span data-ttu-id="3b248-111">Lector global</span><span class="sxs-lookup"><span data-stu-id="3b248-111">Global Reader</span></span>
- <span data-ttu-id="3b248-112">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="3b248-112">Security Reader</span></span>

<span data-ttu-id="3b248-113">Para revisar cuentas con estos roles, [vea los permisos en el centro de seguridad 365 de Microsoft](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="3b248-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="3b248-114">Acceso a la funcionalidad</span><span class="sxs-lookup"><span data-stu-id="3b248-114">Access to functionality</span></span>
<span data-ttu-id="3b248-115">El acceso a la funcionalidad específica está determinado por el de [roles de de Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="3b248-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="3b248-116">Póngase en contacto con un administrador global si necesita tener acceso a funciones específicas que requieren que usted o el grupo de usuarios tenga asignado un nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="3b248-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="3b248-117">Aprobar tareas automatizadas pendientes</span><span class="sxs-lookup"><span data-stu-id="3b248-117">Approve pending automated tasks</span></span>
<span data-ttu-id="3b248-118">[Investigación y corrección automatizadas](mtp-autoir-actions.md)puede actuar en los mensajes de correo electrónico, las reglas de reenvío, los archivos, los mecanismos de persistencia y otros artefactos presentes durante las investigaciones.</span><span class="sxs-lookup"><span data-stu-id="3b248-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="3b248-119">Para aprobar o rechazar acciones pendientes que requieran aprobación explícita, debe tener determinadas funciones asignadas en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b248-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="3b248-120">Para obtener más información, consulte [permisos del centro de actividades](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="3b248-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="3b248-121">Acceso a datos</span><span class="sxs-lookup"><span data-stu-id="3b248-121">Access to data</span></span>
<span data-ttu-id="3b248-122">El acceso a los datos de Protección contra amenazas de Microsoft puede controlarse con el ámbito asignado a los grupos de usuarios en el control de acceso basado en roles (RBAC) ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="3b248-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="3b248-123">Si su acceso no se ha asignado a un conjunto específico de dispositivos en la ATP de Microsoft defender, tendrá acceso completo a los datos de Protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b248-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="3b248-124">Sin embargo, una vez que su cuenta está en el ámbito, solo verá los datos de los dispositivos de su ámbito.</span><span class="sxs-lookup"><span data-stu-id="3b248-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="3b248-125">Por ejemplo, si solo pertenece en un grupo de usuario con una función ATP de Microsoft Defender y se le ha concedido acceso solo a los dispositivos de ventas, solo verá los datos de los dispositivos de ventas en la Protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b248-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="3b248-126">Más información acerca de la configuración de RBAC en Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="3b248-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="3b248-127">Controles de acceso a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3b248-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="3b248-128">Durante la versión preliminar, la Protección contra amenazas de Microsoft no exige los controles de acceso en función de la configuración de seguridad de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="3b248-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="3b248-129">El acceso a los datos de protección contra amenazas de Microsoft no se ve afectado por esta configuración.</span><span class="sxs-lookup"><span data-stu-id="3b248-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3b248-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3b248-130">Related topics</span></span>

- [<span data-ttu-id="3b248-131">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="3b248-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- <span data-ttu-id="3b248-132">[ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac).</span><span class="sxs-lookup"><span data-stu-id="3b248-132">[Microsoft Defender ATP RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)</span></span>
- [<span data-ttu-id="3b248-133">Roles de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3b248-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
