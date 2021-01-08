---
title: Cambios de nomenclatura en el esquema de búsqueda avanzada de Microsoft 365 Defender
description: Seguimiento y revisión de las tablas y columnas de cambios de nomenclatura en el esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos, cambios de nomenclatura, cambiar el nombre, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780828"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="18894-104">Esquema de búsqueda avanzada: cambios de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="18894-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="18894-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="18894-105">**Applies to:**</span></span>
- <span data-ttu-id="18894-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18894-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="18894-107">El [esquema de búsqueda avanzada se](advanced-hunting-schema-tables.md) actualiza periódicamente para agregar nuevas tablas y columnas.</span><span class="sxs-lookup"><span data-stu-id="18894-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="18894-108">En algunos casos, se cambia el nombre de los nombres de las columnas existentes o se reemplazan para mejorar la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="18894-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="18894-109">Consulte este artículo para revisar los cambios de nomenclatura que podrían afectar a las consultas.</span><span class="sxs-lookup"><span data-stu-id="18894-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="18894-110">Los cambios de nomenclatura se aplican automáticamente a las consultas que se guardan en el centro de seguridad, incluidas las consultas usadas por reglas de detección personalizadas.</span><span class="sxs-lookup"><span data-stu-id="18894-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="18894-111">No es necesario actualizar estas consultas manualmente.</span><span class="sxs-lookup"><span data-stu-id="18894-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="18894-112">Sin embargo, tendrá que actualizar las siguientes consultas:</span><span class="sxs-lookup"><span data-stu-id="18894-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="18894-113">Consultas que se ejecutan con la API</span><span class="sxs-lookup"><span data-stu-id="18894-113">Queries that are run using the API</span></span>
- <span data-ttu-id="18894-114">Consultas que se guardan en otro lugar fuera del centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="18894-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="18894-115">Diciembre de 2020</span><span class="sxs-lookup"><span data-stu-id="18894-115">December 2020</span></span>

| <span data-ttu-id="18894-116">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="18894-116">Table name</span></span> | <span data-ttu-id="18894-117">Nombre de columna original</span><span class="sxs-lookup"><span data-stu-id="18894-117">Original column name</span></span> | <span data-ttu-id="18894-118">Nombre de columna nueva</span><span class="sxs-lookup"><span data-stu-id="18894-118">New column name</span></span> | <span data-ttu-id="18894-119">Motivo de la modificación</span><span class="sxs-lookup"><span data-stu-id="18894-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="18894-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="18894-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="18894-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="18894-121">FinalEmailAction</span></span> | <span data-ttu-id="18894-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="18894-122">EmailAction</span></span> | <span data-ttu-id="18894-123">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="18894-123">Customer feedback</span></span> |
| [<span data-ttu-id="18894-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="18894-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="18894-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="18894-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="18894-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="18894-126">EmailActionPolicy</span></span> | <span data-ttu-id="18894-127">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="18894-127">Customer feedback</span></span> |
| [<span data-ttu-id="18894-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="18894-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="18894-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="18894-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="18894-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="18894-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="18894-131">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="18894-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="18894-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="18894-132">Related topics</span></span>
- [<span data-ttu-id="18894-133">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="18894-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="18894-134">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="18894-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)