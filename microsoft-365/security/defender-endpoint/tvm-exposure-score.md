---
title: Puntuación de exposición en Administración de amenazas y vulnerabilidades
description: La Administración de amenazas y vulnerabilidades de exposición refleja lo vulnerable que es su organización a las amenazas de ciberseguridad.
keywords: puntuación de exposición, puntuación de exposición de Microsoft Defender para endpoint, puntuación de exposición de Microsoft Defender para endpoint tvm, puntuación de exposición de la organización, puntuación de exposición de la organización tvm, Administración de amenazas y vulnerabilidades, Microsoft Defender para endpoint
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
ms.openlocfilehash: be60d8f4c8adae02a1a5e388a5b75e717dd5eb51
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59166790"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a>Puntuación de exposición: Administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

La puntuación de exposición está visible en el panel [de amenazas y administración de vulnerabilidades del](tvm-dashboard-insights.md) portal Microsoft 365 Defender exposición. Refleja lo vulnerable que es su organización a las amenazas de ciberseguridad. Una puntuación de exposición baja significa que los dispositivos son menos vulnerables a la explotación.

- Comprenda e identifique rápidamente los resultados de alto nivel sobre el estado de seguridad en su organización.
- Detectar y responder a áreas que requieren investigación o acción para mejorar el estado actual.
- Comunicarse con compañeros y administración sobre el impacto de los esfuerzos de seguridad.

La tarjeta te ofrece una vista de alto nivel de la tendencia de puntuación de exposición con el tiempo. Los picos del gráfico le dan una indicación visual de una alta exposición a amenazas de ciberseguridad que puede investigar más a fondo.

![Tarjeta de puntuación de exposición.](images/tvm_exp_score.png)

## <a name="how-it-works"></a>Funcionamiento

La puntuación de exposición se divide en los siguientes niveles:

- 0-29: puntuación de exposición baja
- 30-69: puntuación de exposición media
- 70-100: puntuación de exposición alta

Puede corregir los problemas en función de las recomendaciones de seguridad prioritarias [para](tvm-security-recommendation.md) reducir la puntuación de exposición. Cada software tiene debilidades que se transforman en recomendaciones y se priorizan en función del riesgo para la organización.

## <a name="reduce-your-threat-and-vulnerability-exposure"></a>Reducir la exposición a amenazas y vulnerabilidades

Reduzca la exposición a amenazas y vulnerabilidades mediante la corrección de [recomendaciones de seguridad](tvm-security-recommendation.md). Para obtener el mayor impacto en la puntuación de exposición, corrija las recomendaciones de seguridad principales, que se pueden ver en el panel de Administración de amenazas y vulnerabilidades [exposición.](tvm-dashboard-insights.md)

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre amenazas administración de vulnerabilidades amenazas](next-gen-threat-and-vuln-mgt.md)
- [Puntuación de seguridad de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
- [Línea de tiempo de eventos](threat-and-vuln-mgt-event-timeline.md)
