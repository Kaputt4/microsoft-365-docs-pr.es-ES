---
title: Cambios de nomenclatura en el esquema de búsqueda avanzada de Microsoft 365 Defender
description: Realizar un seguimiento y revisar las tablas y columnas de cambios de nomenclatura en el esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos, cambios de nomenclatura, cambiar el nombre, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932207"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="196d0-104">Esquema de búsqueda avanzada: cambios de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="196d0-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="196d0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="196d0-105">**Applies to:**</span></span>
- <span data-ttu-id="196d0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="196d0-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="196d0-107">El [esquema de búsqueda avanzada se](advanced-hunting-schema-tables.md) actualiza periódicamente para agregar nuevas tablas y columnas.</span><span class="sxs-lookup"><span data-stu-id="196d0-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="196d0-108">En algunos casos, se cambia el nombre de los nombres de las columnas existentes o se reemplazan para mejorar la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="196d0-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="196d0-109">Consulte este artículo para revisar los cambios de nomenclatura que podrían afectar a las consultas.</span><span class="sxs-lookup"><span data-stu-id="196d0-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="196d0-110">Los cambios de nomenclatura se aplican automáticamente a las consultas que se guardan en el centro de seguridad, incluidas las consultas usadas por reglas de detección personalizadas.</span><span class="sxs-lookup"><span data-stu-id="196d0-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="196d0-111">No es necesario actualizar estas consultas manualmente.</span><span class="sxs-lookup"><span data-stu-id="196d0-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="196d0-112">Sin embargo, tendrá que actualizar las siguientes consultas:</span><span class="sxs-lookup"><span data-stu-id="196d0-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="196d0-113">Consultas que se ejecutan con la API</span><span class="sxs-lookup"><span data-stu-id="196d0-113">Queries that are run using the API</span></span>
- <span data-ttu-id="196d0-114">Consultas que se guardan en otro lugar fuera del centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="196d0-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="196d0-115">Diciembre de 2020</span><span class="sxs-lookup"><span data-stu-id="196d0-115">December 2020</span></span>

| <span data-ttu-id="196d0-116">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="196d0-116">Table name</span></span> | <span data-ttu-id="196d0-117">Nombre de columna original</span><span class="sxs-lookup"><span data-stu-id="196d0-117">Original column name</span></span> | <span data-ttu-id="196d0-118">Nombre de columna nueva</span><span class="sxs-lookup"><span data-stu-id="196d0-118">New column name</span></span> | <span data-ttu-id="196d0-119">Motivo de la modificación</span><span class="sxs-lookup"><span data-stu-id="196d0-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="196d0-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="196d0-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="196d0-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="196d0-121">FinalEmailAction</span></span> | <span data-ttu-id="196d0-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="196d0-122">EmailAction</span></span> | <span data-ttu-id="196d0-123">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="196d0-123">Customer feedback</span></span> |
| [<span data-ttu-id="196d0-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="196d0-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="196d0-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="196d0-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="196d0-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="196d0-126">EmailActionPolicy</span></span> | <span data-ttu-id="196d0-127">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="196d0-127">Customer feedback</span></span> |
| [<span data-ttu-id="196d0-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="196d0-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="196d0-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="196d0-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="196d0-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="196d0-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="196d0-131">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="196d0-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="196d0-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="196d0-132">Related topics</span></span>
- [<span data-ttu-id="196d0-133">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="196d0-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="196d0-134">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="196d0-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)