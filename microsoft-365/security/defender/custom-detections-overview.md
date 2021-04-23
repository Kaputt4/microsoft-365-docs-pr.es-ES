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
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952541"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="43d81-104">Introducción a las detecciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="43d81-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="43d81-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="43d81-105">**Applies to:**</span></span>
- <span data-ttu-id="43d81-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43d81-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="43d81-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="43d81-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="43d81-108">Con las detecciones personalizadas, puede supervisar proactivamente y responder a varios eventos y estados del sistema, incluidos la actividad de infracciones sospechosas y los extremos mal configurados.</span><span class="sxs-lookup"><span data-stu-id="43d81-108">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="43d81-109">Esto es posible mediante reglas de detección personalizables que desencadenan automáticamente alertas, así como acciones de respuesta.</span><span class="sxs-lookup"><span data-stu-id="43d81-109">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="43d81-110">Las detecciones personalizadas funcionan [con](advanced-hunting-overview.md)búsqueda avanzada, lo que proporciona un lenguaje de consulta eficaz y flexible que cubre un amplio conjunto de información de eventos e sistema de la red.</span><span class="sxs-lookup"><span data-stu-id="43d81-110">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="43d81-111">Puede configurarlos para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.</span><span class="sxs-lookup"><span data-stu-id="43d81-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="43d81-112">Las detecciones personalizadas proporcionan:</span><span class="sxs-lookup"><span data-stu-id="43d81-112">Custom detections provide:</span></span>
- <span data-ttu-id="43d81-113">Alertas para detecciones basadas en reglas creadas a partir de consultas de búsqueda avanzadas</span><span class="sxs-lookup"><span data-stu-id="43d81-113">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="43d81-114">Acciones de respuesta automáticas</span><span class="sxs-lookup"><span data-stu-id="43d81-114">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="43d81-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="43d81-115">See also</span></span>
- [<span data-ttu-id="43d81-116">Crear y administrar reglas de detección personalizadas</span><span class="sxs-lookup"><span data-stu-id="43d81-116">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="43d81-117">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="43d81-117">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="43d81-118">Migrar consultas de búsqueda avanzada desde Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="43d81-118">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
