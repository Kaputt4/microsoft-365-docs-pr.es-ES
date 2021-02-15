---
title: Planear el gobierno de la organización y el ciclo de vida para los grupos de Microsoft 365 y Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Información sobre las opciones de gobierno del ciclo de vida para herramientas de colaboración en Microsoft 365
ms.openlocfilehash: 4d779701d241fc7178ab759063be1b8cdf2e960c
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613025"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="b0efd-103">Planear el gobierno de la organización y el ciclo de vida para los grupos de Microsoft 365 y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0efd-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="b0efd-104">Los grupos de Microsoft 365 tienen un amplio conjunto de herramientas para implementar las capacidades de gobierno que necesita su organización.</span><span class="sxs-lookup"><span data-stu-id="b0efd-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="b0efd-105">En la siguiente sección se describen las capacidades, se recomiendan los procedimientos recomendados y se proporcionan instrucciones para hacer las preguntas adecuadas para determinar los requisitos de gobierno y cómo cumplirlas.</span><span class="sxs-lookup"><span data-stu-id="b0efd-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="b0efd-106">Controlar quién puede crear grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0efd-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="b0efd-107">Los usuarios finales pueden crear grupos desde varios puntos finales, incluidos Outlook, SharePoint, Teams y otros entornos.</span><span class="sxs-lookup"><span data-stu-id="b0efd-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![image desc](../media/04.png)

<span data-ttu-id="b0efd-109">Se recomienda encarecidamente autoservicio para dar poder a los propietarios del grupo y ayudar a los usuarios a realizar su trabajo con mayor facilidad.</span><span class="sxs-lookup"><span data-stu-id="b0efd-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="b0efd-110">Limitar la creación de grupos y equipos puede ralentizar la productividad de los usuarios, ya que muchos servicios de Microsoft 365 requieren la creación de grupos para que el servicio funcione.</span><span class="sxs-lookup"><span data-stu-id="b0efd-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="b0efd-111">Tenga en cuenta las siguientes opciones de gobierno para la creación de grupos:</span><span class="sxs-lookup"><span data-stu-id="b0efd-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="b0efd-112">Para limitar la expansión de grupos, use directivas de expiración [de](microsoft-365-groups-expiration-policy.md) grupos para eliminar automáticamente los grupos que no se usan.</span><span class="sxs-lookup"><span data-stu-id="b0efd-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="b0efd-113">Limitar la creación de grupos a los miembros de un grupo [de seguridad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) con pertenencia dinámica que contenga, por ejemplo, todos los empleados a tiempo completo.</span><span class="sxs-lookup"><span data-stu-id="b0efd-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="b0efd-114">Limite la creación de grupos a un grupo de seguridad y requiera que los usuarios completen la formación en las directivas de uso de grupos de su organización para convertirse en miembros del grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b0efd-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="b0efd-115">Si desea limitar quién puede crear grupos, consulte Administrar quién puede crear grupos de [Microsoft 365](manage-creation-of-groups.md) para obtener información sobre cómo configurarlo.</span><span class="sxs-lookup"><span data-stu-id="b0efd-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="b0efd-116">Eliminación, restauración y archivado de grupos</span><span class="sxs-lookup"><span data-stu-id="b0efd-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="b0efd-117">Cuando se elimina un grupo de Microsoft 365, de forma predeterminada se conserva durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="b0efd-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="b0efd-118">Este período de 30 días se denomina "eliminación temporal", ya que todavía estará a tiempo de restaurar el grupo.</span><span class="sxs-lookup"><span data-stu-id="b0efd-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="b0efd-119">Después de los 30 días, el grupo y el contenido asociado se eliminarán permanentemente y no se podrán restaurar.</span><span class="sxs-lookup"><span data-stu-id="b0efd-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="b0efd-120">Si tiene directivas de retención para conservar el chat, los archivos o el correo, estos elementos se conservarán después de eliminar el grupo.</span><span class="sxs-lookup"><span data-stu-id="b0efd-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="b0efd-121">Vea [más información sobre las directivas de retención](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b0efd-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="b0efd-122">Si desea eliminar un grupo pero conservar el contenido de uno o varios de los servicios conectados a grupos, consulte Grupos de archivo, equipos y [Yammer](end-life-cycle-groups-teams-sites-yammer.md) para obtener información.</span><span class="sxs-lookup"><span data-stu-id="b0efd-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="b0efd-123">Directiva de nomenclatura de grupos</span><span class="sxs-lookup"><span data-stu-id="b0efd-123">Group naming policy</span></span>

<span data-ttu-id="b0efd-124">Una directiva de nomenclatura de grupos puede ayudarle a gobernar los grupos de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="b0efd-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="b0efd-125">Se puede usar una directiva de nomenclatura de prefijos o sufijos para aplicar cadenas fijas o atributos de Azure AD al principio o al final de un nombre de grupo y su dirección de correo electrónico asociada.</span><span class="sxs-lookup"><span data-stu-id="b0efd-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="b0efd-126">Al hacerlo, puede garantizar la inclusión de, por ejemplo, nombres de departamento o regiones en los nombres de grupo.</span><span class="sxs-lookup"><span data-stu-id="b0efd-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="b0efd-127">Una directiva de palabras bloqueadas puede garantizar que determinadas palabras, como los nombres de ejecutivos, no se usan en los nombres de grupo.</span><span class="sxs-lookup"><span data-stu-id="b0efd-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="b0efd-128">Las directivas de nomenclatura se aplican cuando se crean grupos a partir de cualquiera de los servicios conectados a grupos.</span><span class="sxs-lookup"><span data-stu-id="b0efd-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="b0efd-129">Si decide usar directivas de nomenclatura para grupos, consulte La directiva de nomenclatura de grupos [de Microsoft 365](groups-naming-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b0efd-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="b0efd-130">Directiva de expiración de grupo</span><span class="sxs-lookup"><span data-stu-id="b0efd-130">Group expiration policy</span></span>

<span data-ttu-id="b0efd-131">Puede especificar un período de expiración y se eliminará cualquier grupo que llegue al final de ese período y no se renueve.</span><span class="sxs-lookup"><span data-stu-id="b0efd-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="b0efd-132">El período de expiración comienza cuando se crea el grupo o en la fecha en que se renovó por última vez.</span><span class="sxs-lookup"><span data-stu-id="b0efd-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="b0efd-133">Una vez que haya establecido que los grupos expiren:</span><span class="sxs-lookup"><span data-stu-id="b0efd-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="b0efd-134">Se notifica a los propietarios del grupo que renueve el grupo a medida que se acerca la expiración.</span><span class="sxs-lookup"><span data-stu-id="b0efd-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="b0efd-135">Los grupos activos se renuevan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b0efd-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="b0efd-136">Se elimina cualquier grupo que no se renueve.</span><span class="sxs-lookup"><span data-stu-id="b0efd-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="b0efd-137">Los propietarios del grupo o el administrador pueden restaurar cualquier grupo que se elimine en un plazo de 30 días.</span><span class="sxs-lookup"><span data-stu-id="b0efd-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="b0efd-138">Las directivas de expiración son una buena manera de limitar la expansión de grupos al garantizar que se eliminen los grupos que ya no están en uso.</span><span class="sxs-lookup"><span data-stu-id="b0efd-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="b0efd-139">Si desea crear una directiva de expiración de grupo, consulte Directiva de [expiración de grupo de Microsoft 365](microsoft-365-groups-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b0efd-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0efd-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b0efd-140">Related topics</span></span>

[<span data-ttu-id="b0efd-141">Planeación paso a paso de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="b0efd-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="b0efd-142">Crear un plan de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="b0efd-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)
