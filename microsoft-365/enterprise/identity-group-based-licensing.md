---
title: 'Paso 12: Configurar las licencias automáticas'
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
description: Comprenda y configure las licencias basadas en grupos para grupos de Azure AD.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871141"
---
# <a name="step-12-set-up-automatic-licensing"></a><span data-ttu-id="e9a16-103">Paso 12: Configurar las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="e9a16-103">Step 12: Set up automatic licensing</span></span>

<span data-ttu-id="e9a16-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e9a16-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="e9a16-p101">En este paso, configurará los grupos de seguridad en Azure AD para que se asignen automáticamente licencias de un conjunto de suscripciones a todos los miembros del grupo. Esto se conoce como *licencias basadas en grupos*. Si se agrega o quita del grupo una cuenta de usuario, las licencias de las suscripciones del grupo se asignarán o quitarán automáticamente de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e9a16-p101">In Step 11, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as *group-based licensing*. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="e9a16-108">Para Microsoft 365 Enterprise, configurará grupos de seguridad de Azure AD para asignar estas dos licencias:</span><span class="sxs-lookup"><span data-stu-id="e9a16-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="e9a16-109">Office 365 Enterprise E3 o E5</span><span class="sxs-lookup"><span data-stu-id="e9a16-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="e9a16-110">Enterprise Mobility + Security (EMS) E3 o E5</span><span class="sxs-lookup"><span data-stu-id="e9a16-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="e9a16-p102">Con los grupos que identificó en el paso 2, busque grupos que contengan una lista de cuentas donde todos los usuarios del grupo necesiten tener licencias de Office 365 y EMS. Asegúrese de tener licencias suficientes para todos los miembros del grupo. Si se queda sin licencias, no se asignarán licencias a los nuevos usuarios hasta que haya más licencias disponibles.</span><span class="sxs-lookup"><span data-stu-id="e9a16-p102">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="e9a16-114">No configure las *licencias basadas en grupos* para los grupos que contengan cuentas entre empresas (B2B) de Azure.</span><span class="sxs-lookup"><span data-stu-id="e9a16-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="e9a16-115">Para obtener más información, vea [Conceptos básicos de las licencias basadas en grupos de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="e9a16-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="e9a16-116">Vea los [pasos para configurar las licencias basadas en grupos para un grupo de seguridad de Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="e9a16-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="e9a16-117">Los resultados de este paso son:</span><span class="sxs-lookup"><span data-stu-id="e9a16-117">The results of this step are:</span></span>

- <span data-ttu-id="e9a16-118">Identificó los grupos de seguridad adecuados para las licencias basadas en grupos.</span><span class="sxs-lookup"><span data-stu-id="e9a16-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="e9a16-119">Configuró estos grupos para las licencias basadas en grupos.</span><span class="sxs-lookup"><span data-stu-id="e9a16-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="e9a16-121">Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="e9a16-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="e9a16-122">Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-group-license) de este paso.</span><span class="sxs-lookup"><span data-stu-id="e9a16-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e9a16-123">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e9a16-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="e9a16-124">Supervisar la actividad de inicio de sesión y del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="e9a16-124">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |

