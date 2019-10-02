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
ms.openlocfilehash: 3bc0872eefa71288d25ce83ebb8f3c51d8959678
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370387"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="b9c3f-103">Paso 7: Configurar Identity Governance</span><span class="sxs-lookup"><span data-stu-id="b9c3f-103">Step 6: Configure identity governance</span></span>

![Identity Fase 2](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="b9c3f-105">El gobierno de identidades consiste en proteger, supervisar y auditar el acceso a recursos críticos mientras se garantiza la productividad de los empleados.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-105">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="b9c3f-106">Por ejemplo, con la gobernanza de identidades puede asegurarse de que los usuarios adecuados tengan el acceso adecuado a los recursos adecuados y determinar si este acceso cambia a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-106">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="b9c3f-107">Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para obtener más información sobre el gobierno de identidades de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b9c3f-107">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="b9c3f-108">*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b9c3f-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="b9c3f-109">Revisiones de acceso de Azure AD</span><span class="sxs-lookup"><span data-stu-id="b9c3f-109">Set up Azure AD access reviews</span></span>

<span data-ttu-id="b9c3f-110">*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b9c3f-110">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b9c3f-111">En este paso, configurará las revisiones de acceso de Azure AD, lo que le permitirá revisar el acceso de un usuario para asegurarse de que solo las personas adecuadas puedan seguir teniendo acceso.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-111">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="b9c3f-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b9c3f-112">For example:</span></span>

- <span data-ttu-id="b9c3f-113">Cuando un nuevo empleado se une a la organización, usted debe asegurarse de que tiene un acceso adecuado para ser productivo.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-113">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="b9c3f-114">Cuando este empleado sea derivado a otros equipos, ubicaciones o departamentos, usted debe asegurarse de que su acceso a los equipos, ubicaciones o departamentos anteriores se elimine en función de las necesidades.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-114">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="b9c3f-115">Cuando ese empleado o un invitado deje la organización, usted debe asegurarse de que su acceso se elimine.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-115">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="b9c3f-116">Esto es especialmente importante si su organización está sujeta a auditorías de seguridad para determinar si las cuentas de usuario tienen un acceso excesivo, lo que podría derivar en infracciones por incumplimiento de normativas del sector o de la región.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-116">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="b9c3f-117">Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) para obtener más información acerca de las revisiones de acceso de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-117">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="b9c3f-118">Azure AD Privileged Identity Management (PIM) dispone de controles adicionales que están adaptados para proteger los derechos de acceso de los recursos en Azure AD, Azure y otros servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-118">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="b9c3f-119">Azure AD PIM ofrece un conjunto completo de controles de gobierno para ayudar a proteger los recursos de la empresa, como directorio, Office 365 y roles de recursos de Azure.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-119">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="b9c3f-120">Al igual que con otras formas de acceso, las organizaciones pueden usar las revisiones de acceso para configurar nuevas certificaciones de acceso periódicas para todos los usuarios con roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-120">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="b9c3f-121">Azure AD PIM solo está disponible con la versión E5 de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-121">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="b9c3f-122">Consulte estos artículos para configurar diferentes tipos de revisiones de acceso:</span><span class="sxs-lookup"><span data-stu-id="b9c3f-122">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="b9c3f-123">Grupos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b9c3f-123">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="b9c3f-124">Roles de Azure AD</span><span class="sxs-lookup"><span data-stu-id="b9c3f-124">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="b9c3f-125">Roles de recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="b9c3f-125">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="b9c3f-126">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-access-reviews) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="b9c3f-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="b9c3f-127">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="b9c3f-127">Next step</span></span>

[<span data-ttu-id="b9c3f-128">Criterios de salida de infraestructura de identidades</span><span class="sxs-lookup"><span data-stu-id="b9c3f-128">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

