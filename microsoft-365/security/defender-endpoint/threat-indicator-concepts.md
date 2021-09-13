---
title: Comprender los conceptos de inteligencia de amenazas en Microsoft Defender para endpoint
description: Crear alertas de amenazas personalizadas para su organización y aprender los conceptos en torno a la inteligencia de amenazas en Microsoft Defender para endpoint
keywords: inteligencia de amenazas, definiciones de alertas, indicadores de peligro, ioc
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d901366e74969b0b128a49a6bd65a56046049085
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59166899"
---
# <a name="understand-threat-intelligence-concepts"></a>Comprender conceptos de inteligencia sobre amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-threatindicator-abovefoldlink)

Los ataques de ciberseguridad avanzados constan de varios eventos malintencionados complejos, atributos e información contextual. Identificar y decidir cuáles de estas actividades califican como sospechosas puede ser una tarea difícil. El conocimiento de atributos conocidos y actividades anormales específicas de su sector es fundamental para saber cuándo llamar sospechoso un comportamiento observado.

Con Microsoft Defender para endpoint, puede crear alertas de amenazas personalizadas que le ayudarán a realizar un seguimiento de las posibles actividades de ataque en su organización. Puedes marcar eventos sospechosos para juntar pistas y, posiblemente, detener una cadena de ataques. Estas alertas de amenazas personalizadas solo aparecerán en la organización y marcarán los eventos que establezcas para realizar el seguimiento.

Antes de crear alertas de amenazas personalizadas, es importante conocer los conceptos detrás de las definiciones de alertas y los indicadores de peligro (IIC) y la relación entre ellas.

## <a name="alert-definitions"></a>Definiciones de alerta
Las definiciones de alerta son atributos contextuales que se pueden usar colectivamente para identificar las primeras pistas sobre un posible ataque de ciberseguridad. Estos indicadores suelen ser una combinación de actividades, características y acciones realizadas por un atacante para lograr correctamente el objetivo de un ataque. La supervisión de estas combinaciones de atributos es fundamental para obtener un punto de vista frente a los ataques y posiblemente interferir con la cadena de eventos antes de que se alcance el objetivo de un atacante.

## <a name="indicators-of-compromise-ioc"></a>Indicadores de compromiso (COI)
Los IIC son eventos malintencionados conocidos individualmente que indican que ya se ha infringido una red o dispositivo. A diferencia de las definiciones de alerta, estos indicadores se consideran como evidencia de una infracción. A menudo se ven después de que ya se ha llevado a cabo un ataque y se ha alcanzado el objetivo, como la exfiltración. También es importante realizar un seguimiento de los IIC durante las investigaciones forenses. Aunque podría no proporcionar la capacidad de intervenir con una cadena de ataques, recopilar estos indicadores puede ser útil para crear mejores defensas para posibles ataques futuros.

## <a name="relationship-between-alert-definitions-and-iocs"></a>Relación entre definiciones de alerta e IIC
En el contexto de Microsoft Defender para endpoint, las definiciones de alerta son contenedores para IOC y definen la alerta, incluidos los metadatos que se genera en caso de una coincidencia de IOC específica. Se proporcionan varios metadatos como parte de las definiciones de alerta. Los metadatos, como el nombre de definición de alerta de ataque, gravedad y descripción, se proporcionan junto con otras opciones.

Cada IOC define la lógica de detección concreta en función de su tipo y valor, así como de su acción, que determina cómo se compara. Está enlazado a una definición de alerta específica que define cómo se muestra una detección como una alerta en la consola de Microsoft Defender para endpoint.

Este es un ejemplo de un COI:
- Tipo: Sha1
- Valor: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- Action: Equals

Los IIC tienen una relación de varios a uno con definiciones de alerta, de modo que una definición de alerta puede tener muchos IIC que le corresponden.

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
:---|:---
[Extraer detecciones a las herramientas SIEM](configure-siem.md)| Obtenga información sobre diferentes formas de extraer detecciones.
[Habilitar la integración de SIEM en Microsoft Defender para endpoint](enable-siem-integration.md)| Obtenga información sobre cómo habilitar la característica de integración siem en la **página Configuración** en el portal para que pueda usar y generar la información necesaria para configurar las herramientas SIEM compatibles.
[Configurar Splunk para extraer Microsoft Defender para detecciones de puntos de conexión](configure-siem.md)| Obtenga información sobre cómo instalar la aplicación de entrada modular de la API de REST y otras opciones de configuración para habilitar Splunk para extraer Microsoft Defender para las detecciones de puntos de conexión.
[Configurar HP ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión](configure-arcsight.md)| Obtenga información sobre cómo instalar el paquete REST FlexConnector de HP ArcSight y los archivos que necesita para configurar ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión.
[Campos de Microsoft Defender para detección de puntos de conexión](api-portal-mapping.md) | Comprender qué campos de datos se exponen como parte de la API de alertas y cómo se asignan a Centro de seguridad de Microsoft Defender.
[Extraer Microsoft Defender para detecciones de puntos de conexión mediante la API de REST](pull-alerts-using-rest-api.md) | Use el flujo de OAuth 2.0 de credenciales de cliente para extraer detecciones de Microsoft Defender para endpoint mediante la API de REST.
[Solucionar problemas de integración de la herramienta SIEM](troubleshoot-siem.md) | Solucionar problemas que puede encontrar al usar la característica de integración siem.



## <a name="related-topics"></a>Temas relacionados
- [Administrar indicadores](manage-indicators.md)
