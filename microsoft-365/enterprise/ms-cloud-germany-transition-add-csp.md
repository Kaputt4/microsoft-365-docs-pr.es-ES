---
title: Información adicional para proveedores de soluciones en la nube
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: información adicional para proveedores de soluciones en la nube relevante para la migración desde Microsoft Cloud Deutschland.'
ms.openlocfilehash: 7a7c377d8e0b72a0179ff28a93018f88d22a5325
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52931058"
---
# <a name="additional-information-for-cloud-solution-providers"></a><span data-ttu-id="3f2ae-103">Información adicional para proveedores de soluciones en la nube</span><span class="sxs-lookup"><span data-stu-id="3f2ae-103">Additional information for Cloud Solution Providers</span></span>

<span data-ttu-id="3f2ae-104">Los proveedores de soluciones en la nube (CSP) que admiten clientes deben tomar medidas adicionales durante la migración de Microsoft Cloud Deutschland a la nueva región del centro de datos alemán.</span><span class="sxs-lookup"><span data-stu-id="3f2ae-104">Cloud Solution Providers (CSPs) supporting customers  need to take additional steps during the migration from Microsoft Cloud Deutschland to the new German datacenter region.</span></span>

## <a name="partner-tenant-migration"></a><span data-ttu-id="3f2ae-105">Migración de inquilinos asociados</span><span class="sxs-lookup"><span data-stu-id="3f2ae-105">Partner tenant migration</span></span>

<span data-ttu-id="3f2ae-106">Los inquilinos de Microsoft Cloud Deutschland asociados no se migrarán.</span><span class="sxs-lookup"><span data-stu-id="3f2ae-106">Partner Microsoft Cloud Deutschland tenants won't be migrated.</span></span> <span data-ttu-id="3f2ae-107">En su lugar, se creará un nuevo inquilino Office 365 servicios de correo electrónico para cada partner de Microsoft en la nueva región del centro de datos alemán.</span><span class="sxs-lookup"><span data-stu-id="3f2ae-107">Instead, a new Office 365 services tenant will be created for each Microsoft Partner in the new German datacenter region.</span></span>

<span data-ttu-id="3f2ae-108">Los inquilinos de clientes csp se migrarán a la nueva región del centro de datos alemán y se vincularán al nuevo inquilino de Office 365 de servicios del mismo partner.</span><span class="sxs-lookup"><span data-stu-id="3f2ae-108">CSP customer tenants will be migrated to the new German datacenter region and be linked to the new Office 365 services tenant of the same partner.</span></span> <span data-ttu-id="3f2ae-109">Después de la transición del cliente, el partner puede administrar el cliente mediante el nuevo inquilino de Office 365 servicios en la región del centro de datos alemán.</span><span class="sxs-lookup"><span data-stu-id="3f2ae-109">After customer transition, the partner can manage the customer using the new Office 365 services tenant in the German datacenter region.</span></span>

## <a name="missing-subscriptions-in-azure"></a><span data-ttu-id="3f2ae-110">Faltan suscripciones en Azure</span><span class="sxs-lookup"><span data-stu-id="3f2ae-110">Missing subscriptions in Azure</span></span>

<span data-ttu-id="3f2ae-111">Una vez completada la transición de suscripción y licencia [(fase 3),](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) los proveedores de soluciones en la nube ya no tendrán acceso a la suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="3f2ae-111">After [the subscription and license transition (phase 3)](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed, Cloud Solution Providers will not have access to the Azure subscription anymore.</span></span>

<span data-ttu-id="3f2ae-112">Para recuperar el acceso, siga estos pasos para elevar el acceso para administrar todas las [suscripciones y grupos de administración de Azure.](/azure/role-based-access-control/elevate-access-global-admin)</span><span class="sxs-lookup"><span data-stu-id="3f2ae-112">To recover access, follow these steps to [elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin).</span></span>
