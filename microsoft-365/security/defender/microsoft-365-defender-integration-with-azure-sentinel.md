---
title: Microsoft 365 Integración de Defender con Azure Sentinel
description: Usa Azure Sentinel como SIEM para Microsoft 365 y eventos de Defender.
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
ms.openlocfilehash: b5a53131733d1c7c539676c1d45abe7eabbe2de7
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707353"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Integración de Defender con Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

El conector de Microsoft 365 Defender para Azure Sentinel (versión preliminar) envía toda la información de alertas y incidentes de Microsoft 365 Defender a Azure Sentinel y mantiene los incidentes sincronizados. 

Una vez que agrega el conector, los incidentes de Microsoft 365 Defender que incluyen todas las alertas asociadas, entidades e información relevante recibida de Microsoft Defender para Endpoint, Microsoft Defender para Identity, Microsoft Defender para Office 365 y Microsoft Cloud App Security se transmiten a Azure Sentinel como datos de información de seguridad y administración de eventos (SIEM), lo que le proporciona contexto para realizar triaje e respuesta a incidentes con &mdash; &mdash; Azure Sentinel. 

Una vez en Azure Sentinel, los incidentes permanecen sincronizados bidireccionalmente con Microsoft 365 Defender, lo que le permite aprovechar las ventajas del centro de seguridad de Microsoft 365 y Azure Sentinel en Azure Portal para la investigación y respuesta de incidentes.

Así es como funciona.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flujo y uso compartido de datos de incidentes entre Microsoft 365 Defender y Azure Sentinel":::

## <a name="next-steps"></a>Siguientes pasos

1. Obtenga una mejor comprensión de [la integración Microsoft 365 Defender con Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)
2. [Conectar datos de Microsoft 365 Defender a Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).

## <a name="see-also"></a>Consulte también

- [Información general sobre incidentes en Microsoft 365 Defender](incidents-overview.md)
- [Investigar incidentes con Azure Sentinel](/azure/sentinel/tutorial-investigate-cases)
