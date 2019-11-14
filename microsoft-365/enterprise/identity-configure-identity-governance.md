---
title: 'Paso 7: Configurar Identity Governance'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure el gobierno de identidades para su cuenta empresarial de Azure AD.
ms.openlocfilehash: d9a9a63f46230a07b35052a3b02231f7b5315d9e
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302927"
---
# <a name="step-6-configure-identity-governance"></a><span data-ttu-id="7d970-103">Paso 6: Configurar el gobierno de identidad</span><span class="sxs-lookup"><span data-stu-id="7d970-103">Step 6: Configure identity governance</span></span>

![Fase 2-Identidad](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="7d970-105">El gobierno de identidades consiste en proteger, supervisar y auditar el acceso a recursos críticos mientras se garantiza la productividad de los empleados.</span><span class="sxs-lookup"><span data-stu-id="7d970-105">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="7d970-106">Por ejemplo, con la gobernanza de identidades puede asegurarse de que los usuarios adecuados tengan el acceso adecuado a los recursos adecuados y determinar si este acceso cambia a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="7d970-106">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="7d970-107">Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para obtener más información sobre el gobierno de identidades de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7d970-107">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="7d970-108">*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7d970-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="7d970-109">Revisiones de acceso de Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d970-109">Set up Azure AD access reviews</span></span>

<span data-ttu-id="7d970-110">*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7d970-110">*This is optional and only applies to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7d970-111">En este paso, configurará las revisiones de acceso de Azure AD, lo que le permitirá revisar el acceso de un usuario para asegurarse de que solo las personas adecuadas puedan seguir teniendo acceso.</span><span class="sxs-lookup"><span data-stu-id="7d970-111">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="7d970-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d970-112">For example:</span></span>

- <span data-ttu-id="7d970-113">Cuando un nuevo empleado se une a la organización, usted debe asegurarse de que tiene un acceso adecuado para ser productivo.</span><span class="sxs-lookup"><span data-stu-id="7d970-113">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="7d970-114">Cuando este empleado sea derivado a otros equipos, ubicaciones o departamentos, usted debe asegurarse de que su acceso a los equipos, ubicaciones o departamentos anteriores se elimine en función de las necesidades.</span><span class="sxs-lookup"><span data-stu-id="7d970-114">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="7d970-115">Cuando ese empleado o un invitado deje la organización, usted debe asegurarse de que su acceso se elimine.</span><span class="sxs-lookup"><span data-stu-id="7d970-115">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="7d970-116">Esto es especialmente importante si su organización está sujeta a auditorías de seguridad para determinar si las cuentas de usuario tienen un acceso excesivo, lo que podría derivar en infracciones por incumplimiento de normativas del sector o de la región.</span><span class="sxs-lookup"><span data-stu-id="7d970-116">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="7d970-117">Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) para obtener más información acerca de las revisiones de acceso de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d970-117">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="7d970-118">Azure AD Privileged Identity Management (PIM) dispone de controles adicionales que están adaptados para proteger los derechos de acceso de los recursos en Azure AD, Azure y otros servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d970-118">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="7d970-119">Azure AD PIM ofrece un conjunto completo de controles de gobierno para ayudar a proteger los recursos de la empresa, como directorio, Office 365 y roles de recursos de Azure.</span><span class="sxs-lookup"><span data-stu-id="7d970-119">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="7d970-120">Al igual que con otras formas de acceso, las organizaciones pueden usar las revisiones de acceso para configurar nuevas certificaciones de acceso periódicas para todos los usuarios con roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="7d970-120">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="7d970-121">Azure AD PIM solo está disponible con la versión E5 de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7d970-121">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="7d970-122">Consulte estos artículos para configurar diferentes tipos de revisiones de acceso:</span><span class="sxs-lookup"><span data-stu-id="7d970-122">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="7d970-123">Grupos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7d970-123">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="7d970-124">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d970-124">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="7d970-125">Roles de recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="7d970-125">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="7d970-126">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-access-reviews) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="7d970-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="7d970-127">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7d970-127">Next step</span></span>

[<span data-ttu-id="7d970-128">Criterios de salida de infraestructura de identidades</span><span class="sxs-lookup"><span data-stu-id="7d970-128">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

