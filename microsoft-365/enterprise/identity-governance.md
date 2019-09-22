---
title: 'Paso 7: Configurar Identity Governance'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure el gobierno de identidades para su cuenta empresarial de Azure AD.
ms.openlocfilehash: 1c0eab574e5436dd0c88a0b46d1916281bcf0577
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047363"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="2dc0a-103">Paso 7: Configurar Identity Governance</span><span class="sxs-lookup"><span data-stu-id="2dc0a-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="2dc0a-104">El gobierno de identidades consiste en proteger, supervisar y auditar el acceso a recursos críticos mientras se garantiza la productividad de los empleados.</span><span class="sxs-lookup"><span data-stu-id="2dc0a-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="2dc0a-105">Por ejemplo, con la gobernanza de identidades puede asegurarse de que los usuarios adecuados tengan el acceso adecuado a los recursos adecuados y determinar si este acceso cambia a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="2dc0a-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="2dc0a-106">Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para obtener más información sobre el gobierno de identidades de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="2dc0a-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="2dc0a-107">Configurar revisiones de acceso de Azure AD</span><span class="sxs-lookup"><span data-stu-id="2dc0a-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="2dc0a-108">*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2dc0a-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="2dc0a-109">En este paso, configurará las revisiones de acceso de Azure AD, lo que le permitirá revisar el acceso de un usuario para asegurarse de que solo las personas adecuadas puedan seguir teniendo acceso.</span><span class="sxs-lookup"><span data-stu-id="2dc0a-109">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="2dc0a-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2dc0a-110">For example:</span></span>

- <span data-ttu-id="2dc0a-111">Cuando un nuevo empleado se une a la organización, usted debe asegurarse de que tiene un acceso adecuado para ser productivo.</span><span class="sxs-lookup"><span data-stu-id="2dc0a-111">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="2dc0a-112">Cuando este empleado sea derivado a otros equipos, ubicaciones o departamentos, usted debe asegurarse de que su acceso a los equipos, ubicaciones o departamentos anteriores se elimine en función de las necesidades.</span><span class="sxs-lookup"><span data-stu-id="2dc0a-112">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="2dc0a-113">Cuando ese empleado o un invitado deje la organización, usted debe asegurarse de que su acceso se elimine.</span><span class="sxs-lookup"><span data-stu-id="2dc0a-113">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="2dc0a-114">Esto es especialmente importante si su organización está sujeta a auditorías de seguridad para determinar si las cuentas de usuario tienen un acceso excesivo, lo que podría derivar en infracciones por incumplimiento de normativas del sector o de la región.</span><span class="sxs-lookup"><span data-stu-id="2dc0a-114">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="2dc0a-115">Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) para obtener más información acerca de las revisiones de acceso de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2dc0a-115">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="2dc0a-116">Consulte estos artículos para configurar diferentes tipos de revisiones de acceso:</span><span class="sxs-lookup"><span data-stu-id="2dc0a-116">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="2dc0a-117">Grupos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2dc0a-117">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="2dc0a-118">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="2dc0a-118">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="2dc0a-119">Roles de recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="2dc0a-119">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="2dc0a-120">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-access-reviews) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="2dc0a-120">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="2dc0a-121">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2dc0a-121">Next step</span></span>

[<span data-ttu-id="2dc0a-122">Criterios de salida de infraestructura de identidades</span><span class="sxs-lookup"><span data-stu-id="2dc0a-122">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

