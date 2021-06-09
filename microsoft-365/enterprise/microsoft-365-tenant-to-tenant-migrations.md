---
title: Microsoft 365 de inquilino a inquilino
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
description: Obtenga información sobre cómo migrar Microsoft 365 inquilinos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6e8277a7ca768db3a4a4acd2488859b7764a40c
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819719"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="671ee-103">Microsoft 365 de inquilino a inquilino</span><span class="sxs-lookup"><span data-stu-id="671ee-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="671ee-104">Existen varios enfoques de arquitectura para fusiones, adquisiciones, desinstituras y otros escenarios que pueden llevar a migrar un inquilino de Microsoft 365 existente a un nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="671ee-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="671ee-105">La mayoría de los clientes trabajan con Microsoft Consulting Services o un partner de Microsoft para migrar inquilinos, incluido el uso de herramientas de terceros para migrar contenido.</span><span class="sxs-lookup"><span data-stu-id="671ee-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="671ee-106">Use el [modelo de arquitectura de](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) migración de inquilino a inquilino para comprender cómo planear Microsoft 365 de inquilino a inquilino y los pasos de una migración.</span><span class="sxs-lookup"><span data-stu-id="671ee-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="671ee-107">[![Modelo de migración de inquilino a inquilino](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="671ee-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="671ee-108">Puede descargar este modelo en [formato PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) e imprimirlo en papel de tamaño carta, legal o tabloide (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="671ee-108">You download this model in [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="671ee-109">Este modelo proporciona instrucciones y un punto de partida para planear con secciones sobre:</span><span class="sxs-lookup"><span data-stu-id="671ee-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="671ee-110">Asignación de escenarios empresariales a enfoques de arquitectura</span><span class="sxs-lookup"><span data-stu-id="671ee-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="671ee-111">Consideraciones sobre diseño</span><span class="sxs-lookup"><span data-stu-id="671ee-111">Design considerations</span></span>

<span data-ttu-id="671ee-112">Este modelo también contiene ejemplos detallados de:</span><span class="sxs-lookup"><span data-stu-id="671ee-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="671ee-113">Flujo de migración de un solo evento</span><span class="sxs-lookup"><span data-stu-id="671ee-113">A single event migration flow</span></span>
- <span data-ttu-id="671ee-114">Flujo de migración por fases</span><span class="sxs-lookup"><span data-stu-id="671ee-114">A phased migration flow</span></span>
- <span data-ttu-id="671ee-115">Movimiento de inquilino o flujo dividido</span><span class="sxs-lookup"><span data-stu-id="671ee-115">A tenant move or split flow</span></span>
