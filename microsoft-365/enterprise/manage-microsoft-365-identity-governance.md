---
title: Administración de Microsoft 365 Identity Governance
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
description: Obtenga información sobre cómo usar las características de gobernanza de identidad de Microsoft 365.
ms.openlocfilehash: d5bcafb5b452e693bf3ff706c436a9986eeeae76
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328545"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="967ae-103">Administración de Microsoft 365 Identity Governance</span><span class="sxs-lookup"><span data-stu-id="967ae-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="967ae-104">El gobierno de identidades consiste en proteger, supervisar y auditar el acceso a recursos críticos mientras se garantiza la productividad de los empleados.</span><span class="sxs-lookup"><span data-stu-id="967ae-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="967ae-105">Por ejemplo, con la gobernanza de identidades puede asegurarse de que los usuarios adecuados tengan el acceso adecuado a los recursos adecuados y determinar si este acceso cambia a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="967ae-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="967ae-106">Para obtener más información, vea esta información [General sobre el gobierno de identidades para Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="967ae-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="967ae-107">Revisiones de acceso de Azure AD</span><span class="sxs-lookup"><span data-stu-id="967ae-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="967ae-108">Las revisiones de acceso de Azure AD permiten revisar el acceso de un usuario para asegurarse de que solo las personas adecuadas tienen acceso continuado.</span><span class="sxs-lookup"><span data-stu-id="967ae-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="967ae-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="967ae-109">For example:</span></span>

- <span data-ttu-id="967ae-110">Cuando un nuevo empleado se une a la organización, usted debe asegurarse de que tiene un acceso adecuado para ser productivo.</span><span class="sxs-lookup"><span data-stu-id="967ae-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="967ae-111">Cuando este empleado sea derivado a otros equipos, ubicaciones o departamentos, usted debe asegurarse de que su acceso a los equipos, ubicaciones o departamentos anteriores se elimine en función de las necesidades.</span><span class="sxs-lookup"><span data-stu-id="967ae-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="967ae-112">Cuando ese empleado o un invitado deje la organización, usted debe asegurarse de que su acceso se elimine.</span><span class="sxs-lookup"><span data-stu-id="967ae-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="967ae-113">Esto es especialmente importante si su organización está sujeta a auditorías de seguridad para determinar si las cuentas de usuario tienen un acceso excesivo, lo que podría derivar en infracciones por incumplimiento de normativas del sector o de la región.</span><span class="sxs-lookup"><span data-stu-id="967ae-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="967ae-114">Para obtener más información, vea información [General sobre las revisiones de Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="967ae-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="967ae-115">Azure AD Privileged Identity Management (PIM) dispone de controles adicionales que están adaptados para proteger los derechos de acceso de los recursos en Azure AD, Azure y otros servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="967ae-115">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="967ae-116">Azure AD PIM ofrece un conjunto completo de controles de gobierno para ayudar a proteger los recursos de la empresa, como directorio, Office 365 y roles de recursos de Azure.</span><span class="sxs-lookup"><span data-stu-id="967ae-116">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="967ae-117">Al igual que con otras formas de acceso, las organizaciones pueden usar las revisiones de acceso para configurar nuevas certificaciones de acceso periódicas para todos los usuarios con roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="967ae-117">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="967ae-118">Azure AD PIM solo está disponible con la versión E5 de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="967ae-118">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="967ae-119">Consulte estos artículos para configurar diferentes tipos de revisiones de acceso:</span><span class="sxs-lookup"><span data-stu-id="967ae-119">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="967ae-120">Grupos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="967ae-120">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="967ae-121">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="967ae-121">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="967ae-122">Roles de recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="967ae-122">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="967ae-123">Configurar la administración de derechos de Azure AD</span><span class="sxs-lookup"><span data-stu-id="967ae-123">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="967ae-124">Wiht administración de derechos de Azure AD, puede administrar el ciclo de vida de identidad y acceso a escala mediante la automatización de los flujos de trabajo de solicitud de acceso, las asignaciones de acceso, las revisiones y la expiración.</span><span class="sxs-lookup"><span data-stu-id="967ae-124">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="967ae-125">Los empleados necesitan tener acceso a varios grupos, aplicaciones y sitios para realizar su trabajo.</span><span class="sxs-lookup"><span data-stu-id="967ae-125">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="967ae-126">La administración de este acceso puede ser complicada porque los requisitos cambian, se agregan nuevas aplicaciones o los usuarios necesitan derechos de acceso adicionales.</span><span class="sxs-lookup"><span data-stu-id="967ae-126">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="967ae-127">Cuando colabora con otras organizaciones, es posible que no sepa quién en la otra organización necesita acceso a los recursos de la organización, y los usuarios externos no sabrán qué aplicaciones, grupos o sitios está usando la organización.</span><span class="sxs-lookup"><span data-stu-id="967ae-127">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="967ae-128">La administración de derechos de Azure AD puede ayudarle a administrar de forma más eficiente el acceso a los grupos, aplicaciones y sitios de SharePoint para los usuarios internos y externos.</span><span class="sxs-lookup"><span data-stu-id="967ae-128">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="967ae-129">Para obtener más información, vea la [información general sobre la administración de derechos de Azure ad](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span><span class="sxs-lookup"><span data-stu-id="967ae-129">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
