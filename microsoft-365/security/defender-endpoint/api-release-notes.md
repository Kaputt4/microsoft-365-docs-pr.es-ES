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
ms.technology: mde
ms.openlocfilehash: 7bae413028a0add7e5288e52bc3184e30f319c46
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073844"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="bd124-104">Notas de la versión de api de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="bd124-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="bd124-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="bd124-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="bd124-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="bd124-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bd124-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bd124-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="bd124-108">La siguiente información enumera las actualizaciones realizadas en Microsoft Defender para las API de punto de conexión y las fechas en que se realizaron.</span><span class="sxs-lookup"><span data-stu-id="bd124-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="bd124-109">Fuente RSS: recibe una notificación cuando se actualiza esta página copiando y pegando la siguiente dirección URL en el lector de fuentes:</span><span class="sxs-lookup"><span data-stu-id="bd124-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest"></a><span data-ttu-id="bd124-110">Notas de la versión: más reciente a más antigua</span><span class="sxs-lookup"><span data-stu-id="bd124-110">Release notes - newest to oldest</span></span>

### <a name="10022021"></a><span data-ttu-id="bd124-111">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="bd124-111">10.02.2021</span></span>

- <span data-ttu-id="bd124-112">Se agregó una nueva API: [Alertas de actualización por lotes](batch-update-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="bd124-112">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="bd124-113">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="bd124-113">25.01.2021</span></span>

- <span data-ttu-id="bd124-114">Limitaciones de velocidad actualizadas para [la API de](run-advanced-query-api.md) búsqueda avanzada de 15 a 45 solicitudes por minuto.</span><span class="sxs-lookup"><span data-stu-id="bd124-114">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="bd124-115">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="bd124-115">21.01.2021</span></span>

- <span data-ttu-id="bd124-116">Se agregó una nueva API: [Buscar dispositivos por etiqueta.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="bd124-116">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="bd124-117">Se agregó una nueva API: [Importar indicadores](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="bd124-117">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="bd124-118">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="bd124-118">03.01.2021</span></span>

- <span data-ttu-id="bd124-119">Evidencia de alerta actualizada: se agregaron ***detectionStatus** _, _*_parentProcessFilePath_*_ y _ *_parentProcessFileName_** propiedades.</span><span class="sxs-lookup"><span data-stu-id="bd124-119">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="bd124-120">Entidad [Alert actualizada:](alerts.md)se agregó ***la propiedad detectorId.***</span><span class="sxs-lookup"><span data-stu-id="bd124-120">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="bd124-121">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="bd124-121">15.12.2020</span></span>

- <span data-ttu-id="bd124-122">Entidad [Device](machine.md) actualizada: lista ***de IpInterfaces*** agregada.</span><span class="sxs-lookup"><span data-stu-id="bd124-122">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="bd124-123">Consulte [Enumerar dispositivos](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="bd124-123">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="bd124-124">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="bd124-124">04.11.2020</span></span>

- <span data-ttu-id="bd124-125">Se agregó una nueva API: [Establecer el valor del dispositivo](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="bd124-125">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="bd124-126">Entidad [Device](machine.md) actualizada: se agregó ***la propiedad deviceValue.***</span><span class="sxs-lookup"><span data-stu-id="bd124-126">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="bd124-127">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="bd124-127">01.09.2020</span></span>

- <span data-ttu-id="bd124-128">Se agregó la opción para expandir la entidad Alert con su evidencia relacionada.</span><span class="sxs-lookup"><span data-stu-id="bd124-128">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="bd124-129">Vea [Enumerar alertas](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="bd124-129">See [List Alerts](get-alerts.md).</span></span>
