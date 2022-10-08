---
title: Descripción del informe expertos de Defender para la búsqueda en Microsoft 365 Defender
ms.reviewer: ''
description: El servicio Expertos de Defender para la búsqueda publica informes mensuales para ayudarle a comprender todas las amenazas que el servicio de búsqueda ha surgido en su entorno.
keywords: informe de analistas, informe de expertos de defender, detecciones, notificación de expertos de defender, búsqueda, notificaciones, categorías de amenazas, informes de búsqueda
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a47884f4918359278b192c3314e5b2374d64f3f
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68362846"
---
# <a name="understand-the-defender-experts-for-hunting-report-in-microsoft-365-defender"></a>Descripción del informe expertos de Defender para la búsqueda en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender Expertos en Búsqueda de capas de inteligencia humana y tecnología entrenada por expertos para ayudar a Microsoft 365 Defender clientes a comprender las amenazas significativas a las que se enfrentan. Muestra cómo las aptitudes de búsqueda de amenazas de Defender Expert, la comprensión exhaustiva del panorama de amenazas y el conocimiento de las amenazas emergentes pueden ayudarle a identificar, priorizar y abordar esas amenazas en su entorno. 

El servicio Expertos de Defender para la búsqueda publica informes mensuales para ayudarle a comprender todas las amenazas que el servicio de búsqueda ha surgido en su entorno, junto con las alertas generadas por los productos de Microsoft 365 Defender.

Para ver el informe más reciente en el portal de Microsoft 365 Defender, vaya a **Informes** y seleccione **Expertos de Defender Expertos** > **de Defender para el informe de búsqueda**.

## <a name="scan-the-defender-experts-for-hunting-report-to-know-what-to-prioritize"></a>Examen del informe Expertos de Defender para la búsqueda para saber qué priorizar

Cada sección del informe está diseñada para proporcionar más información sobre las amenazas que nuestros expertos de Defender encuentran en su entorno. Los informes incluyen las secciones descritas en la tabla siguiente:

| Sección informe | Descripción |
|--|--|
| Cazado y triagedo | El número total de posibles problemas de ciberseguridad que se encuentran en su entorno. |
| Investigado | El número de problemas de ciberseguridad que necesitan análisis adicionales para determinar su naturaleza y extensión. |
| Notificado (Ver notificación) | Número de notificaciones de expertos de Defender que enviaron los expertos de Defender. Estas notificaciones están relacionadas con las posibles actividades de amenazas investigadas en su entorno que deben priorizarse en función de la urgencia y el impacto. |
| Mitre ATT&tácticas de CK observadas | El número de tácticas y técnicas de ataque observadas en su entorno y asignadas según el [marco DE ATT de MITRE&CK](https://attack.mitre.org/). En esta sección se visualiza el número de ataques alcanzados por cada táctica para que pueda realizar las acciones adecuadas, como revisar los que avanzaron más adelante en primer lugar. |
| Categorías de amenazas observadas | En las categorías se describen las amenazas y riesgos más significativos observados en su entorno. Las categorías más críticas se resaltan para ayudarle a evaluar aún más la posición de seguridad en función de las características conocidas, el comportamiento y el posible impacto de las amenazas. También le permite centrarse y priorizar las tareas urgentes a abordar. |

Consulte la siguiente captura de pantalla de un informe de ejemplo:

![Captura de pantalla de un informe de expertos en búsqueda de Microsoft Defender en Microsoft 365 Defender portal.](../../media/mte/defenderexperts/defender-experts-report.png)

## <a name="view-defender-experts-notifications"></a>Ver notificaciones de expertos de Defender

Una notificación de expertos de Defender describe la actividad de amenaza significativa Expertos de Defender para la búsqueda observada en su entorno y proporciona recomendaciones para corregir y defender su organización.

Los informes de expertos de Defender para la búsqueda le proporcionan el número total de notificaciones de expertos de Defender que nuestros expertos de Defender han enviado durante el tiempo que ha elegido. Para ver estas notificaciones, seleccione **Ver notificación** junto a **Notificación**.

Este vínculo le redirige a la página de incidentes de Microsoft 365 Defender. Las alertas de expertos de Defender para la búsqueda o las notificaciones de expertos de Defender se etiquetan con **expertos de Defender**.

> [!NOTE]
> El vínculo **Ver notificación** solo aparece si el valor mostrado en **Notificación** es al menos 1.

## <a name="identify-potential-attack-entry-points-and-other-security-weak-spots"></a>Identificar posibles puntos de entrada de ataque y otros puntos débiles de seguridad

Las tácticas MITRE ATT&CK representan objetivos adversarios, lo que intentan lograr en cada fase de ataque. La sección **mitre att&tácticas de CK observada** del informe realiza un seguimiento de la progresión del ataque contra la fase que alcanzaron:

1. Reconocimiento
2. Desarrollo de recursos
3. Acceso inicial
4. Ejecución
5. Persistencia
6. Escalación de privilegios
7. Evasión de defensa
8. Acceso a credenciales
9. Descubrimiento
10. Movimiento lateral
11. Colección
12. Comando y control
13. Filtración
14. Impacto

Las señales de Microsoft 365 Defender e investigaciones de expertos de Defender para la búsqueda ayudan a identificar estas tácticas, representadas en el gráfico de barras. Este gráfico le ayuda a visualizar dónde está el aumento y le proporciona la información que necesita para planear las acciones de contención y corrección correspondientes.

## <a name="know-and-understand-the-prevalent-threats-in-your-environment"></a>Conocer y comprender las amenazas frecuentes en su entorno

Las categorías de amenazas ayudan a identificar y organizar las amenazas de seguridad en clases para evaluar y evaluar su impacto y desarrollar estrategias para prevenir o mitigar estas amenazas en el entorno. En la sección **Categorías de amenazas observadas** del informe se muestra un gráfico de barras con riesgos y amenazas significativos detectados en su entorno, lo que le ayuda a comprender la amplitud y el ámbito de la exposición.

Entre las distintas categorías de amenazas disponibles, las siguientes categorías se eligen cuidadosamente porque no están cubiertas bajo el ámbito de MITRE ATT&marco CK:

- Ransomware
- Malware
- Militarización
- Explotar
- Entrega

Puede priorizar la corrección en función de la categoría más afectada, como se muestra en el gráfico de barras.
