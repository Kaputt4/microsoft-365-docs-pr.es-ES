---
title: Migraciones de inquilino a inquilino de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo migrar inquilinos de Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17aabbd945c6dec699384eb9f203029255ae62f6
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447155"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="c6722-103">Migraciones de inquilino a inquilino de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c6722-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="c6722-104">Existen varios métodos de arquitectura para fusiones, adquisiciones, desinversiones y otros escenarios que podrían llevar a migrar un inquilino de Microsoft 365 existente a un nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="c6722-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="c6722-105">La mayoría de los clientes trabaja con los servicios de consultoría de Microsoft o con un socio de Microsoft para migrar inquilinos, incluido el uso de herramientas de terceros para migrar contenido.</span><span class="sxs-lookup"><span data-stu-id="c6722-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="c6722-106">Use el [modelo de arquitectura de migración de inquilino a inquilino](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) para comprender cómo planear las migraciones de inquilino a inquilino de Microsoft 365 y los pasos de una migración.</span><span class="sxs-lookup"><span data-stu-id="c6722-106">Use the [Tenant-to-tenant migration architecture model](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="c6722-107">[![Modelo de migración de inquilino a inquilino](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="c6722-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="c6722-108">También puede descargar este modelo en formatos [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) o [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) e imprimirlo en papel de tamaño carta, legal o tabloide (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="c6722-108">You can also download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) or [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="c6722-109">Este modelo proporciona instrucciones y un punto de partida para la planeación con secciones en:</span><span class="sxs-lookup"><span data-stu-id="c6722-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="c6722-110">Asignación de escenarios empresariales a enfoques de arquitectura</span><span class="sxs-lookup"><span data-stu-id="c6722-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="c6722-111">Consideraciones sobre diseño</span><span class="sxs-lookup"><span data-stu-id="c6722-111">Design considerations</span></span>

<span data-ttu-id="c6722-112">Este modelo también contiene ejemplos detallados de:</span><span class="sxs-lookup"><span data-stu-id="c6722-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="c6722-113">Un flujo de migración de evento único</span><span class="sxs-lookup"><span data-stu-id="c6722-113">A single event migration flow</span></span>
- <span data-ttu-id="c6722-114">Un flujo de migración por fases</span><span class="sxs-lookup"><span data-stu-id="c6722-114">A phased migration flow</span></span>
- <span data-ttu-id="c6722-115">Un movimiento de inquilino o un flujo dividido</span><span class="sxs-lookup"><span data-stu-id="c6722-115">A tenant move or split flow</span></span>
