---
title: Tabla AlertInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación de alertas en la tabla AlertInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, gravedad, categoría, MITRE, ATT&CK, ATP de Microsoft Defender, MDATP, ATP de Office 365, Microsoft Cloud App Security, MCAS y Azure ATP
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
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929975"
---
# <a name="alertinfo"></a><span data-ttu-id="66f4f-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="66f4f-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="66f4f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="66f4f-105">**Applies to:**</span></span>
- <span data-ttu-id="66f4f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66f4f-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="66f4f-107">La tabla del esquema de búsqueda avanzada contiene información sobre las alertas de Microsoft Defender para Endpoint, Microsoft Defender para `AlertInfo` Office 365, Microsoft Cloud App Security y Microsoft Defender for Identity. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="66f4f-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="66f4f-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="66f4f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="66f4f-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="66f4f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="66f4f-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="66f4f-110">Column name</span></span> | <span data-ttu-id="66f4f-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="66f4f-111">Data type</span></span> | <span data-ttu-id="66f4f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="66f4f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="66f4f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="66f4f-113">datetime</span></span> | <span data-ttu-id="66f4f-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="66f4f-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="66f4f-115">string</span><span class="sxs-lookup"><span data-stu-id="66f4f-115">string</span></span> | <span data-ttu-id="66f4f-116">Identificador único de alerta.</span><span class="sxs-lookup"><span data-stu-id="66f4f-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="66f4f-117">cadena</span><span class="sxs-lookup"><span data-stu-id="66f4f-117">string</span></span> | <span data-ttu-id="66f4f-118">Título de la alerta.</span><span class="sxs-lookup"><span data-stu-id="66f4f-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="66f4f-119">cadena</span><span class="sxs-lookup"><span data-stu-id="66f4f-119">string</span></span> | <span data-ttu-id="66f4f-120">Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta</span><span class="sxs-lookup"><span data-stu-id="66f4f-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="66f4f-121">cadena</span><span class="sxs-lookup"><span data-stu-id="66f4f-121">string</span></span> | <span data-ttu-id="66f4f-122">El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta.</span><span class="sxs-lookup"><span data-stu-id="66f4f-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="66f4f-123">cadena</span><span class="sxs-lookup"><span data-stu-id="66f4f-123">string</span></span> | <span data-ttu-id="66f4f-124">Producto o servicio que proporcionaba la información de alerta</span><span class="sxs-lookup"><span data-stu-id="66f4f-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="66f4f-125">string</span><span class="sxs-lookup"><span data-stu-id="66f4f-125">string</span></span> | <span data-ttu-id="66f4f-126">Tecnología de detección o sensor que identifica el componente o la actividad relevantes</span><span class="sxs-lookup"><span data-stu-id="66f4f-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="66f4f-127">string</span><span class="sxs-lookup"><span data-stu-id="66f4f-127">string</span></span> | <span data-ttu-id="66f4f-128">MITRE ATT&técnicas de CK asociadas con la actividad que desencadenó la alerta</span><span class="sxs-lookup"><span data-stu-id="66f4f-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="66f4f-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="66f4f-129">Related topics</span></span>
- [<span data-ttu-id="66f4f-130">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="66f4f-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="66f4f-131">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="66f4f-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="66f4f-132">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="66f4f-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="66f4f-133">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="66f4f-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="66f4f-134">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="66f4f-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="66f4f-135">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="66f4f-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
