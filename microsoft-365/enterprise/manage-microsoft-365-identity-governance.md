---
title: Administrar Microsoft 365 de identidades
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Obtenga información sobre cómo usar Microsoft 365 de gobierno de identidades.
ms.openlocfilehash: 6a97ca24c609724a2cab93feec9e90f25d3361e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910959"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="5e8d5-103">Administrar Microsoft 365 de identidades</span><span class="sxs-lookup"><span data-stu-id="5e8d5-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="5e8d5-104">El gobierno de identidades consiste en proteger, supervisar y auditar el acceso a recursos críticos mientras se garantiza la productividad de los empleados.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="5e8d5-105">Por ejemplo, con la gobernanza de identidades puede asegurarse de que los usuarios adecuados tengan el acceso adecuado a los recursos adecuados y determinar si este acceso cambia a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="5e8d5-106">Para obtener más información, vea esta introducción al gobierno de [identidades para Azure Active Directory (Azure AD).](/azure/active-directory/governance/identity-governance-overview)</span><span class="sxs-lookup"><span data-stu-id="5e8d5-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="5e8d5-107">Revisiones de acceso de Azure AD</span><span class="sxs-lookup"><span data-stu-id="5e8d5-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="5e8d5-108">Las revisiones de acceso de Azure AD le permiten revisar el acceso de un usuario para asegurarse de que solo las personas correctas tienen acceso continuo.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="5e8d5-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5e8d5-109">For example:</span></span>

- <span data-ttu-id="5e8d5-110">Cuando un nuevo empleado se une a la organización, usted debe asegurarse de que tiene un acceso adecuado para ser productivo.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="5e8d5-111">Cuando este empleado sea derivado a otros equipos, ubicaciones o departamentos, usted debe asegurarse de que su acceso a los equipos, ubicaciones o departamentos anteriores se elimine en función de las necesidades.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="5e8d5-112">Cuando ese empleado o un invitado deje la organización, usted debe asegurarse de que su acceso se elimine.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="5e8d5-113">Esto es especialmente importante si su organización está sujeta a auditorías de seguridad para determinar si las cuentas de usuario tienen un acceso excesivo, lo que podría derivar en infracciones por incumplimiento de normativas del sector o de la región.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="5e8d5-114">Para obtener más información, vea [la introducción a las revisiones de acceso.](/azure/active-directory/governance/access-reviews-overview)</span><span class="sxs-lookup"><span data-stu-id="5e8d5-114">For more information, see the [overview of access reviews](/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="5e8d5-115">Consulte estos artículos para configurar diferentes tipos de revisiones de acceso:</span><span class="sxs-lookup"><span data-stu-id="5e8d5-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="5e8d5-116">Grupos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5e8d5-116">Groups and apps</span></span>](/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="5e8d5-117">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="5e8d5-117">Azure AD roles</span></span>](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="5e8d5-118">Roles de recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="5e8d5-118">Azure resource roles</span></span>](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="5e8d5-119">Configurar la administración de derechos de Azure AD</span><span class="sxs-lookup"><span data-stu-id="5e8d5-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="5e8d5-120">Administración de derechos de Azure AD wiht, puede administrar la identidad y el ciclo de vida de acceso a escala mediante la automatización de flujos de trabajo de solicitudes de acceso, asignaciones de acceso, revisiones y expiración.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="5e8d5-121">Los empleados necesitan acceso a varios grupos, aplicaciones y sitios para realizar su trabajo.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="5e8d5-122">Administrar este acceso puede ser difícil porque cambian los requisitos, se agregan nuevas aplicaciones o los usuarios necesitan derechos de acceso adicionales.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="5e8d5-123">Al colaborar con otras organizaciones, es posible que no sepa quién de la otra organización necesita acceso a los recursos de la organización y los usuarios externos no sabrán qué aplicaciones, grupos o sitios usa su organización.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="5e8d5-124">La administración de derechos de Azure AD puede ayudarle a administrar de forma más eficaz el acceso a grupos, aplicaciones y sitios SharePoint para usuarios internos y externos.</span><span class="sxs-lookup"><span data-stu-id="5e8d5-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="5e8d5-125">Para obtener más información, vea [la introducción a la administración de derechos de Azure AD](/azure/active-directory/governance/entitlement-management-overview).</span><span class="sxs-lookup"><span data-stu-id="5e8d5-125">For more information, see the [overview of Azure AD entitlement management](/azure/active-directory/governance/entitlement-management-overview).</span></span>