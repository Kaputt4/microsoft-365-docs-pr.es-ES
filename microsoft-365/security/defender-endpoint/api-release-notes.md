---
title: Notas de la versión de api de Microsoft Defender para endpoint
description: Notas de la versión de las actualizaciones realizadas en el conjunto de API de Microsoft Defender para endpoint.
keywords: Notas de la versión de la API de Microsoft Defender para Endpoint, mde, API, Microsoft Defender para la API de endpoint, actualizaciones, notas, versión
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 5e72db8d986ad096d6312f90530d9f9ff246afc3
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022299"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="de924-104">Notas de la versión de api de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="de924-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="de924-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="de924-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="de924-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="de924-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="de924-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="de924-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="de924-108">La siguiente información enumera las actualizaciones realizadas en Microsoft Defender para las API de punto de conexión y las fechas en que se realizaron.</span><span class="sxs-lookup"><span data-stu-id="de924-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="de924-109">Fuente RSS: recibe una notificación cuando se actualiza esta página copiando y pegando la siguiente dirección URL en el lector de fuentes:</span><span class="sxs-lookup"><span data-stu-id="de924-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="de924-110">Notas de la versión: más reciente a más antigua (dd.mm.yyyyy)</span><span class="sxs-lookup"><span data-stu-id="de924-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="06102021"></a><span data-ttu-id="de924-111">06.10.2021</span><span class="sxs-lookup"><span data-stu-id="de924-111">06.10.2021</span></span>

- <span data-ttu-id="de924-112">Se agregó el nuevo método de la API de evaluación de exportación: evaluación de vulnerabilidades de software de _exportación delta (respuesta JSON) Exportar_ métodos de evaluación y propiedades por [dispositivo.](get-assessment-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="de924-112">Added new Export assessment API method  - _Delta Export software vulnerabilities assessment (JSON response)_ [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="05252021"></a><span data-ttu-id="de924-113">05.25.2021</span><span class="sxs-lookup"><span data-stu-id="de924-113">05.25.2021</span></span>

- <span data-ttu-id="de924-114">Se agregaron nuevos métodos y propiedades de evaluación de exportación de API [por dispositivo.](get-assessment-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="de924-114">Added new API [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="03052021"></a><span data-ttu-id="de924-115">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="de924-115">03.05.2021</span></span>

- <span data-ttu-id="de924-116">Se agregó una nueva API: [Propiedades y métodos de actividad de corrección.](get-remediation-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="de924-116">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="de924-117">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="de924-117">10.02.2021</span></span>

- <span data-ttu-id="de924-118">Se agregó una nueva API: [Alertas de actualización por lotes](batch-update-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="de924-118">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="de924-119">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="de924-119">25.01.2021</span></span>

- <span data-ttu-id="de924-120">Limitaciones de velocidad actualizadas para [la API de](run-advanced-query-api.md) búsqueda avanzada de 15 a 45 solicitudes por minuto.</span><span class="sxs-lookup"><span data-stu-id="de924-120">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="de924-121">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="de924-121">21.01.2021</span></span>

- <span data-ttu-id="de924-122">Se agregó una nueva API: [Buscar dispositivos por etiqueta.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="de924-122">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="de924-123">Se agregó una nueva API: [Importar indicadores](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="de924-123">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="de924-124">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="de924-124">03.01.2021</span></span>

- <span data-ttu-id="de924-125">Evidencia de alerta actualizada: se agregaron ***detectionStatus** _, _*_parentProcessFilePath_*_ y _ *_parentProcessFileName_** propiedades.</span><span class="sxs-lookup"><span data-stu-id="de924-125">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="de924-126">Entidad [Alert actualizada:](alerts.md)se agregó ***la propiedad detectorId.***</span><span class="sxs-lookup"><span data-stu-id="de924-126">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="de924-127">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="de924-127">15.12.2020</span></span>

- <span data-ttu-id="de924-128">Entidad [Device](machine.md) actualizada: lista ***de IpInterfaces*** agregada.</span><span class="sxs-lookup"><span data-stu-id="de924-128">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="de924-129">Consulte [Enumerar dispositivos](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="de924-129">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="de924-130">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="de924-130">04.11.2020</span></span>

- <span data-ttu-id="de924-131">Se agregó una nueva API: [Establecer el valor del dispositivo](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="de924-131">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="de924-132">Entidad [Device](machine.md) actualizada: se agregó ***la propiedad deviceValue.***</span><span class="sxs-lookup"><span data-stu-id="de924-132">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="de924-133">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="de924-133">01.09.2020</span></span>

- <span data-ttu-id="de924-134">Se agregó la opción para expandir la entidad Alert con su evidencia relacionada.</span><span class="sxs-lookup"><span data-stu-id="de924-134">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="de924-135">Vea [Enumerar alertas](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="de924-135">See [List Alerts](get-alerts.md).</span></span>
