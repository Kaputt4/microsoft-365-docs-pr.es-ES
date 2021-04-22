---
title: Información general sobre las detecciones personalizadas en Microsoft 365 Defender
description: Comprender cómo puede usar la búsqueda avanzada para crear detecciones personalizadas y generar alertas
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: bf635ed03cb0d99d54fc94b622bf244447b32a80
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935706"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="2a25b-104">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="2a25b-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2a25b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2a25b-105">**Applies to:**</span></span>
- <span data-ttu-id="2a25b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a25b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2a25b-107">Con las detecciones personalizadas, puede supervisar proactivamente y responder a varios eventos y estados del sistema, incluidos la actividad de infracciones sospechosas y los extremos mal configurados.</span><span class="sxs-lookup"><span data-stu-id="2a25b-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="2a25b-108">Esto es posible mediante reglas de detección personalizables que desencadenan automáticamente alertas, así como acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="2a25b-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="2a25b-109">Las detecciones personalizadas funcionan [con](advanced-hunting-overview.md)búsqueda avanzada, lo que proporciona un lenguaje de consulta eficaz y flexible que cubre un amplio conjunto de información de eventos e sistema de la red.</span><span class="sxs-lookup"><span data-stu-id="2a25b-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="2a25b-110">Puede configurarlos para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.</span><span class="sxs-lookup"><span data-stu-id="2a25b-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="2a25b-111">Las detecciones personalizadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="2a25b-111">Custom detections provide:</span></span>
- <span data-ttu-id="2a25b-112">Alertas para detecciones basadas en reglas creadas a partir de consultas de búsqueda avanzadas</span><span class="sxs-lookup"><span data-stu-id="2a25b-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="2a25b-113">Acciones de respuesta automáticas</span><span class="sxs-lookup"><span data-stu-id="2a25b-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="2a25b-114">Ver también</span><span class="sxs-lookup"><span data-stu-id="2a25b-114">See also</span></span>
- [<span data-ttu-id="2a25b-115">Crear y administrar reglas de detección personalizadas</span><span class="sxs-lookup"><span data-stu-id="2a25b-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="2a25b-116">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="2a25b-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2a25b-117">Migrar consultas de búsqueda avanzada desde Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="2a25b-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
