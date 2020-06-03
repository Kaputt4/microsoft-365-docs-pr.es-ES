---
title: Información general sobre las detecciones personalizadas en la protección contra amenazas de Microsoft
description: Comprenda cómo puede usar la búsqueda avanzada para crear detecciones personalizadas y generar alertas
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, Microsoft 365, protección contra amenazas de Microsoft
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498356"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="69e18-104">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="69e18-104">Custom detections overview</span></span>

<span data-ttu-id="69e18-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="69e18-105">**Applies to:**</span></span>
- <span data-ttu-id="69e18-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="69e18-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="69e18-107">Con las detecciones personalizadas, puede supervisar de forma proactiva y responder a varios eventos y Estados del sistema, incluidos la actividad de infracciones y los extremos mal configurados.</span><span class="sxs-lookup"><span data-stu-id="69e18-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="69e18-108">Esto es posible gracias a reglas de detección personalizables que activan automáticamente alertas y acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="69e18-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="69e18-109">Las detecciones personalizadas funcionan con la [búsqueda avanzada](advanced-hunting-overview.md), que proporciona un lenguaje de consultas eficaz y flexible que cubre un amplio conjunto de información de eventos y del sistema de la red.</span><span class="sxs-lookup"><span data-stu-id="69e18-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="69e18-110">Puede establecer que se ejecuten a intervalos regulares, generando alertas y realizando acciones de respuesta siempre que haya coincidencias.</span><span class="sxs-lookup"><span data-stu-id="69e18-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="69e18-111">Las detecciones personalizadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="69e18-111">Custom detections provide:</span></span>
- <span data-ttu-id="69e18-112">Alertas para detecciones basadas en reglas creadas a partir de consultas de caza avanzadas</span><span class="sxs-lookup"><span data-stu-id="69e18-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="69e18-113">Acciones de respuesta automáticas</span><span class="sxs-lookup"><span data-stu-id="69e18-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="69e18-114">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="69e18-114">Related topic</span></span>
- [<span data-ttu-id="69e18-115">Creación y administración de reglas de detección personalizadas</span><span class="sxs-lookup"><span data-stu-id="69e18-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="69e18-116">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="69e18-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)