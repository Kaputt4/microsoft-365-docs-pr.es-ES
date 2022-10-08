---
title: integración de Microsoft 365 Defender con Microsoft Sentinel
description: Use Microsoft Sentinel como SIEM para Microsoft 365 Defender incidentes y eventos.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365-security
- tier1
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: da57ca47c4c95246f7ed3278cc475ef313daec45
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68075521"
---
# <a name="microsoft-365-defender-integration-with-microsoft-sentinel"></a>integración de Microsoft 365 Defender con Microsoft Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

El conector de Microsoft 365 Defender para Microsoft Sentinel (versión preliminar) envía toda la información de alertas y incidentes Microsoft 365 Defender a Microsoft Sentinel y mantiene los incidentes sincronizados. 

Una vez que agregue el conector, Microsoft 365 Defender incidentes que incluyan todas las alertas&mdash;, entidades y la información pertinente asociada recibida de Microsoft Defender para punto de conexión, Microsoft Defender for Identity, Microsoft Defender para Office 365 y Microsoft Defender for Cloud Apps&mdash; se transmiten a Microsoft Sentinel como datos de administración de eventos e información de seguridad (SIEM), lo que le proporciona contexto para realizar la evaluación de prioridades y la respuesta a incidentes con Microsoft Sentinel. 

Una vez en Microsoft Sentinel, los incidentes permanecen sincronizados bidireccionalmente con Microsoft 365 Defender, lo que le permite aprovechar las ventajas del portal de Microsoft 365 Defender y Microsoft Sentinel en el Azure Portal para la investigación y respuesta de incidentes.

Vea esta breve introducción a la integración de Microsoft Sentinel con Microsoft 365 Defender (4 minutos).

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


Así es como funciona.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flujo y uso compartido de datos de incidentes para los portales de Microsoft 365 Defender y Microsoft Sentinel" lightbox="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png":::

## <a name="next-steps"></a>Pasos siguientes

1. Obtenga un conocimiento más profundo de [Microsoft 365 Defender integración con Microsoft Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).
2. [Conecte datos de Microsoft 365 Defender a Microsoft Sentinel](/azure/sentinel/connect-microsoft-365-defender).

## <a name="see-also"></a>Vea también

- [Introducción a los incidentes en Microsoft 365 Defender](incidents-overview.md)
- [Investigación de incidentes con Microsoft Sentinel](/azure/sentinel/tutorial-investigate-cases)
