---
title: Integración de Microsoft 365 Defender con Azure Sentinel.
description: Use Azure Sentinel como SIEM para Microsoft 365 Defender incidentes y eventos.
keywords: incidentes, alertas, investigar, analizar, responder, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b9a9a6381c93e2d252f75710adc206868c0a5546
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229916"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="43599-104">Integración de Microsoft 365 Defender con Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="43599-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="43599-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="43599-105">**Applies to:**</span></span>
- <span data-ttu-id="43599-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43599-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="43599-107">El Microsoft 365 Defender para Azure Sentinel (versión preliminar) envía toda la información Microsoft 365 Defender incidentes y alertas a Azure Sentinel y mantiene los incidentes sincronizados.</span><span class="sxs-lookup"><span data-stu-id="43599-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="43599-108">Una vez que agregue el conector, los incidentes de Microsoft 365 Defender que incluyen todas las alertas asociadas, entidades e información relevante recibida de Microsoft Defender para endpoint, Microsoft Defender para Identity, Microsoft Defender para Office 365 y Microsoft Cloud App Security se transmiten a Azure Sentinel como datos de información de seguridad y administración de eventos (SIEM), lo que le proporciona contexto para realizar triaje y respuesta a incidentes con &mdash; &mdash; Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="43599-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="43599-109">Una vez en Azure Sentinel, los incidentes permanecen sincronizados bidireccionalmente con Microsoft 365 Defender, lo que le permite aprovechar las ventajas tanto del centro de seguridad de Microsoft 365 como de Azure Sentinel en Azure Portal para la investigación y respuesta de incidentes.</span><span class="sxs-lookup"><span data-stu-id="43599-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="43599-110">Vea esta breve introducción a la integración de Azure Sentinel Microsoft 365 Defender (4 minutos).</span><span class="sxs-lookup"><span data-stu-id="43599-110">Watch this short overview of Azure Sentinel integration with Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


<span data-ttu-id="43599-111">Así es como funciona.</span><span class="sxs-lookup"><span data-stu-id="43599-111">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flujo y uso compartido de datos de incidentes entre Microsoft 365 Defender y Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="43599-113">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="43599-113">Next steps</span></span>

1. <span data-ttu-id="43599-114">Obtenga una comprensión más profunda de [Microsoft 365 Defender integración con Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span><span class="sxs-lookup"><span data-stu-id="43599-114">Get a deeper understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="43599-115">[Conectar datos de Microsoft 365 Defender a Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="43599-115">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="43599-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="43599-116">See also</span></span>

- [<span data-ttu-id="43599-117">Información general sobre incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43599-117">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="43599-118">Investigar incidentes con Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="43599-118">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
