---
title: Tabla AlertInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación de alertas en la tabla AlertInfo del esquema de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, gravedad, categoría, MITRE, ATT&CK, Microsoft defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS
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
ms.openlocfilehash: 7672d974666a381a48da15e0917a46c97df88895
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847673"
---
# <a name="alertinfo"></a><span data-ttu-id="a6be1-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="a6be1-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a6be1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a6be1-105">**Applies to:**</span></span>
- <span data-ttu-id="a6be1-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="a6be1-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="a6be1-107">La `AlertInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las alertas de Microsoft defender para el punto de conexión, Microsoft defender para Office 365, Microsoft Cloud App Security y Microsoft defender para identidad.</span><span class="sxs-lookup"><span data-stu-id="a6be1-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="a6be1-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="a6be1-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a6be1-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a6be1-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a6be1-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="a6be1-110">Column name</span></span> | <span data-ttu-id="a6be1-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a6be1-111">Data type</span></span> | <span data-ttu-id="a6be1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6be1-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a6be1-113">datetime</span><span class="sxs-lookup"><span data-stu-id="a6be1-113">datetime</span></span> | <span data-ttu-id="a6be1-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="a6be1-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="a6be1-115">string</span><span class="sxs-lookup"><span data-stu-id="a6be1-115">string</span></span> | <span data-ttu-id="a6be1-116">Identificador único de alerta.</span><span class="sxs-lookup"><span data-stu-id="a6be1-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="a6be1-117">cadena</span><span class="sxs-lookup"><span data-stu-id="a6be1-117">string</span></span> | <span data-ttu-id="a6be1-118">Título de la alerta.</span><span class="sxs-lookup"><span data-stu-id="a6be1-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="a6be1-119">cadena</span><span class="sxs-lookup"><span data-stu-id="a6be1-119">string</span></span> | <span data-ttu-id="a6be1-120">Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta</span><span class="sxs-lookup"><span data-stu-id="a6be1-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="a6be1-121">cadena</span><span class="sxs-lookup"><span data-stu-id="a6be1-121">string</span></span> | <span data-ttu-id="a6be1-122">El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta.</span><span class="sxs-lookup"><span data-stu-id="a6be1-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="a6be1-123">cadena</span><span class="sxs-lookup"><span data-stu-id="a6be1-123">string</span></span> | <span data-ttu-id="a6be1-124">Producto o servicio que ha proporcionado la información de alerta</span><span class="sxs-lookup"><span data-stu-id="a6be1-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="a6be1-125">string</span><span class="sxs-lookup"><span data-stu-id="a6be1-125">string</span></span> | <span data-ttu-id="a6be1-126">Tecnología o sensor de detección que identificó el componente o la actividad más importante</span><span class="sxs-lookup"><span data-stu-id="a6be1-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="a6be1-127">string</span><span class="sxs-lookup"><span data-stu-id="a6be1-127">string</span></span> | <span data-ttu-id="a6be1-128">MITRE ATT&CK las técnicas asociadas con la actividad que desencadenó la alerta</span><span class="sxs-lookup"><span data-stu-id="a6be1-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a6be1-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a6be1-129">Related topics</span></span>
- [<span data-ttu-id="a6be1-130">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="a6be1-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a6be1-131">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="a6be1-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a6be1-132">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="a6be1-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a6be1-133">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="a6be1-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a6be1-134">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="a6be1-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a6be1-135">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="a6be1-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
