---
title: Puntuación de exposición en la administración de amenazas y vulnerabilidades
description: La puntuación de exposición a la administración de amenazas y vulnerabilidades refleja lo vulnerable que es su organización a las amenazas de ciberseguridad.
keywords: puntuación de exposición, puntuación de exposición mdatp, mdatp tvm exposure score, organization exposure score, tvm organization exposure score, threat and vulnerability management, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34c3122b017b14605fdbb3358f31f73e26361a4d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500126"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a>Puntuación de exposición: administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

La puntuación de exposición está visible en el panel [de administración](tvm-dashboard-insights.md) de amenazas y vulnerabilidades del Centro de seguridad de Microsoft Defender. Refleja lo vulnerable que es su organización a las amenazas de ciberseguridad. Una puntuación de exposición baja significa que los dispositivos son menos vulnerables a la explotación.

- Comprenda e identifique rápidamente los resultados de alto nivel sobre el estado de seguridad en su organización.
- Detectar y responder a áreas que requieren investigación o acción para mejorar el estado actual.
- Comunicarse con compañeros y administración sobre el impacto de los esfuerzos de seguridad.

La tarjeta te ofrece una vista de alto nivel de la tendencia de puntuación de exposición con el tiempo. Los picos del gráfico le dan una indicación visual de una alta exposición a amenazas de ciberseguridad que puede investigar más a fondo.

![Tarjeta de puntuación de exposición](images/tvm_exp_score.png)

## <a name="how-it-works"></a>Cómo funciona

La puntuación de exposición se divide en los siguientes niveles:

- 0–29: puntuación de exposición baja
- 30–69: puntuación de exposición media
- 70–100: puntuación de exposición alta

Puede corregir los problemas en función de las recomendaciones de seguridad prioritarias [para](tvm-security-recommendation.md) reducir la puntuación de exposición. Cada software tiene debilidades que se transforman en recomendaciones y se priorizan en función del riesgo para la organización.

## <a name="reduce-your-threat-and-vulnerability-exposure"></a>Reducir la exposición a amenazas y vulnerabilidades

Reduzca la exposición a amenazas y vulnerabilidades mediante la corrección de [recomendaciones de seguridad](tvm-security-recommendation.md). Para obtener el mayor impacto en la puntuación de exposición, corrija las recomendaciones de seguridad más importantes, que se pueden ver en el panel de administración de amenazas y [vulnerabilidades.](tvm-dashboard-insights.md)

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Puntuación de seguridad de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
- [Línea de tiempo de eventos](threat-and-vuln-mgt-event-timeline.md)
