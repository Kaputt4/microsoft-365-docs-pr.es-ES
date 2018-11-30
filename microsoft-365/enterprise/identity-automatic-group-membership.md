---
title: 'Paso 15: Configurar la pertenencia a grupos dinámicos'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure la pertenencia a grupos automática basada en atributos de cuenta.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871675"
---
# <a name="step-15-set-up-dynamic-group-membership"></a><span data-ttu-id="069c9-103">Paso 15: Configurar la pertenencia a grupos dinámicos</span><span class="sxs-lookup"><span data-stu-id="069c9-103">Step 15: Set up dynamic group membership</span></span>

<span data-ttu-id="069c9-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="069c9-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="069c9-p101">En este paso, creará una serie de reglas que agreguen o quiten automáticamente cuentas de usuario como miembros de un grupo de Azure AD. Esto se conoce como *pertenencia a grupos dinámicos*. La regla se basa en atributos de cuenta de usuario, como Departamento o País.</span><span class="sxs-lookup"><span data-stu-id="069c9-p101">In Step 12, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as *dynamic group membership*. The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="069c9-108">Las reglas se aplican de esta forma:</span><span class="sxs-lookup"><span data-stu-id="069c9-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="069c9-109">Si la nueva cuenta de usuario coincide con todas las reglas del grupo, se convierte en un miembro.</span><span class="sxs-lookup"><span data-stu-id="069c9-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="069c9-110">Si una cuenta de usuario no es miembro del grupo, pero sus atributos cambian para que coincidan con todas las reglas del grupo, se convierte en un miembro de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="069c9-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="069c9-111">Si una cuenta de usuario no coincide con todas las reglas del grupo, no se agregará al grupo.</span><span class="sxs-lookup"><span data-stu-id="069c9-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="069c9-112">Si una cuenta de usuario es miembro del grupo, pero sus atributos cambian, por lo que ya no coinciden con todas las reglas del grupo, se quitará como miembro del grupo.</span><span class="sxs-lookup"><span data-stu-id="069c9-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="069c9-p102">Para usar la pertenencia dinámica, primero necesita determinar los conjuntos de grupos que tienen un conjunto común de atributos de cuenta de usuario. Por ejemplo, todos los miembros del departamento de ventas necesitan estar en el grupo de Azure AD “Ventas”, basándose en el atributo de cuenta de usuario “Departamento” establecido en “Ventas”.</span><span class="sxs-lookup"><span data-stu-id="069c9-p102">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="069c9-115">Vea las [instrucciones para crear y configurar las reglas para un grupo de Azure AD dinámico](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="069c9-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="069c9-116">Los resultados de este paso son:</span><span class="sxs-lookup"><span data-stu-id="069c9-116">The results of this step are:</span></span>

- <span data-ttu-id="069c9-117">Un conjunto de grupos de Azure AD que se puede configurar para la pertenencia dinámica.</span><span class="sxs-lookup"><span data-stu-id="069c9-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="069c9-118">Un conjunto de reglas para cada grupo dinámico.</span><span class="sxs-lookup"><span data-stu-id="069c9-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="069c9-120">Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="069c9-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="069c9-121">Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-dyn-groups) de este paso.</span><span class="sxs-lookup"><span data-stu-id="069c9-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="069c9-122">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="069c9-122">Next step</span></span>

[<span data-ttu-id="069c9-123">Criterios de salida de infraestructura de identidades</span><span class="sxs-lookup"><span data-stu-id="069c9-123">Identity exit criteria</span></span>](identity-exit-criteria.md)
