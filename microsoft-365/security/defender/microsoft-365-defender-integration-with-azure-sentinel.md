---
title: integración de Microsoft 365 Defender con Microsoft Sentinel
description: Use Microsoft Sentinel como SIEM para Microsoft 365 Defender incidentes y eventos.
keywords: incidentes, alertas, investigar, analizar, responder, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: d0add9fe000966cdeb2ffc5ce23e4ba0690bbadb
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320289"
---
# <a name="microsoft-365-defender-integration-with-microsoft-sentinel"></a>integración de Microsoft 365 Defender con Microsoft Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

El Microsoft 365 Defender para Microsoft Sentinel (versión preliminar) envía toda la información Microsoft 365 Defender incidentes y alertas a Microsoft Sentinel y mantiene los incidentes sincronizados. 

Una vez que agregue el conector, Microsoft 365 Defender incidentes que incluyan todas las alertas asociadas&mdash;, entidades e información relevante recibida de Microsoft Defender para endpoint, Microsoft Defender para Identity, Microsoft Defender para Office 365 y Microsoft Defender para&mdash; aplicaciones en la nube se transmiten a Microsoft Sentinel como datos de información de seguridad y administración de eventos (SIEM), lo que proporciona contexto para realizar triajes y respuesta a incidentes con Microsoft Sentinel. 

Una vez en Microsoft Sentinel, los incidentes permanecen sincronizados bidireccionalmente con Microsoft 365 Defender, lo que le permite aprovechar las ventajas del portal de Microsoft 365 Defender y Microsoft Sentinel en Azure Portal para la investigación y respuesta de incidentes.

Vea esta breve introducción a la integración de Microsoft Sentinel Microsoft 365 Defender (4 minutos).

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


Así es como funciona.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flujo y uso compartido de datos de incidentes entre Microsoft 365 Defender y Microsoft Sentinel.":::

## <a name="next-steps"></a>Pasos siguientes

1. Obtenga una comprensión más profunda de [Microsoft 365 Defender integración con Microsoft Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).
2. [Conectar datos de Microsoft 365 Defender a Microsoft Sentinel](/azure/sentinel/connect-microsoft-365-defender).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes en Microsoft 365 Defender](incidents-overview.md)
- [Investigar incidentes con Microsoft Sentinel](/azure/sentinel/tutorial-investigate-cases)
