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
ms.openlocfilehash: 5093bf64614f30c7daa145484453d7c9000ef2c7
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "52060890"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="b36d7-104">Notas de la versión de api de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="b36d7-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="b36d7-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b36d7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b36d7-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b36d7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b36d7-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b36d7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b36d7-108">La siguiente información enumera las actualizaciones realizadas en Microsoft Defender para las API de punto de conexión y las fechas en que se realizaron.</span><span class="sxs-lookup"><span data-stu-id="b36d7-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="b36d7-109">Fuente RSS: recibe una notificación cuando se actualiza esta página copiando y pegando la siguiente dirección URL en el lector de fuentes:</span><span class="sxs-lookup"><span data-stu-id="b36d7-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```


## <a name="release-notes---newest-to-oldest"></a><span data-ttu-id="b36d7-110">Notas de la versión: más reciente a más antigua</span><span class="sxs-lookup"><span data-stu-id="b36d7-110">Release notes - newest to oldest</span></span>

### <a name="23042021"></a><span data-ttu-id="b36d7-111">23.04.2021</span><span class="sxs-lookup"><span data-stu-id="b36d7-111">23.04.2021</span></span>

- <span data-ttu-id="b36d7-112">Se agregó una nueva API: [Propiedades y métodos de actividad de corrección.](get-remediation-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="b36d7-112">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="b36d7-113">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="b36d7-113">10.02.2021</span></span>

- <span data-ttu-id="b36d7-114">Se agregó una nueva API: [Alertas de actualización por lotes](batch-update-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="b36d7-114">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="b36d7-115">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="b36d7-115">25.01.2021</span></span>

- <span data-ttu-id="b36d7-116">Limitaciones de velocidad actualizadas para [la API de](run-advanced-query-api.md) búsqueda avanzada de 15 a 45 solicitudes por minuto.</span><span class="sxs-lookup"><span data-stu-id="b36d7-116">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="b36d7-117">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="b36d7-117">21.01.2021</span></span>

- <span data-ttu-id="b36d7-118">Se agregó una nueva API: [Buscar dispositivos por etiqueta.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="b36d7-118">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="b36d7-119">Se agregó una nueva API: [Importar indicadores](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="b36d7-119">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="b36d7-120">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="b36d7-120">03.01.2021</span></span>

- <span data-ttu-id="b36d7-121">Evidencia de alerta actualizada: se agregaron ***detectionStatus** _, _*_parentProcessFilePath_*_ y _ *_parentProcessFileName_** propiedades.</span><span class="sxs-lookup"><span data-stu-id="b36d7-121">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="b36d7-122">Entidad [Alert actualizada:](alerts.md)se agregó ***la propiedad detectorId.***</span><span class="sxs-lookup"><span data-stu-id="b36d7-122">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="b36d7-123">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="b36d7-123">15.12.2020</span></span>

- <span data-ttu-id="b36d7-124">Entidad [Device](machine.md) actualizada: lista ***de IpInterfaces*** agregada.</span><span class="sxs-lookup"><span data-stu-id="b36d7-124">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="b36d7-125">Consulte [Enumerar dispositivos](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="b36d7-125">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="b36d7-126">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="b36d7-126">04.11.2020</span></span>

- <span data-ttu-id="b36d7-127">Se agregó una nueva API: [Establecer el valor del dispositivo](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="b36d7-127">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="b36d7-128">Entidad [Device](machine.md) actualizada: se agregó ***la propiedad deviceValue.***</span><span class="sxs-lookup"><span data-stu-id="b36d7-128">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="b36d7-129">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="b36d7-129">01.09.2020</span></span>

- <span data-ttu-id="b36d7-130">Se agregó la opción para expandir la entidad Alert con su evidencia relacionada.</span><span class="sxs-lookup"><span data-stu-id="b36d7-130">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="b36d7-131">Vea [Enumerar alertas](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="b36d7-131">See [List Alerts](get-alerts.md).</span></span>
