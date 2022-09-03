---
title: Descripción de los conceptos de inteligencia sobre amenazas en Microsoft Defender para punto de conexión
description: Cree alertas de amenazas personalizadas para su organización y conozca los conceptos relacionados con la inteligencia sobre amenazas en Microsoft Defender para punto de conexión
keywords: inteligencia sobre amenazas, definiciones de alertas, indicadores de riesgo, ioc
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 9b859e5ae75b2d00a1592c40f67838d6cdfce5fd
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585144"
---
# <a name="understand-threat-intelligence-concepts"></a>Comprender conceptos de inteligencia sobre amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-threatindicator-abovefoldlink)

Los ataques de ciberseguridad avanzados constan de varios eventos malintencionados complejos, atributos e información contextual. Identificar y decidir cuál de estas actividades califica como sospechosas puede ser una tarea difícil. Su conocimiento de los atributos conocidos y las actividades anómalas específicas de su sector es fundamental para saber cuándo llamar a un comportamiento observado como sospechoso.

Con Microsoft 365 Defender, puede crear alertas de amenazas personalizadas que puedan ayudarle a realizar un seguimiento de las posibles actividades de ataque en su organización. Puede marcar eventos sospechosos para crear pistas y posiblemente detener una cadena de ataques. Estas alertas de amenazas personalizadas solo aparecerán en su organización y marcarán los eventos que establezca para realizar el seguimiento.

Antes de crear alertas de amenazas personalizadas, es importante conocer los conceptos subyacentes a las definiciones de alertas e indicadores de riesgo (IOC) y la relación entre ellas.

## <a name="alert-definitions"></a>Definiciones de alertas
Las definiciones de alertas son atributos contextuales que se pueden usar colectivamente para identificar pistas tempranas sobre un posible ataque de ciberseguridad. Estos indicadores suelen ser una combinación de actividades, características y acciones realizadas por un atacante para lograr con éxito el objetivo de un ataque. La supervisión de estas combinaciones de atributos es fundamental para obtener un punto de vista frente a ataques y posiblemente interferir con la cadena de eventos antes de que se alcance el objetivo de un atacante.

## <a name="indicators-of-compromise-ioc"></a>Indicadores de compromiso (COI)
Los IOC son eventos malintencionados conocidos individualmente que indican que ya se ha infringido una red o un dispositivo. A diferencia de las definiciones de alerta, estos indicadores se consideran evidencia de una infracción. A menudo se ven después de que ya se ha llevado a cabo un ataque y se ha alcanzado el objetivo, como la filtración. El seguimiento de los IOC también es importante durante las investigaciones forenses. Aunque es posible que no pueda intervenir con una cadena de ataques, la recopilación de estos indicadores puede ser útil para crear mejores defensas para posibles ataques futuros.

## <a name="relationship-between-alert-definitions-and-iocs"></a>Relación entre definiciones de alerta e IOC
En el contexto de Microsoft 365 Defender y Microsoft Defender para punto de conexión, las definiciones de alerta son contenedores para IOC y definen la alerta, incluidos los metadatos que se generan para una coincidencia de IOC específica. Se proporcionan varios metadatos como parte de las definiciones de alerta. Los metadatos, como el nombre de definición de alerta de ataque, gravedad y descripción, se proporcionan junto con otras opciones.

Cada COI define la lógica de detección concreta en función de su tipo, valor y acción, que determina cómo se compara. Se enlaza a una definición de alerta específica que define cómo se muestra una detección como una alerta en la consola de Microsoft 365 Defender.

Este es un ejemplo de un IOC:
- Tipo: Sha1
- Valor: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- Acción: igual a

Los IOC tienen una relación de varios a uno con definiciones de alertas, de modo que una definición de alerta puede tener muchos IOC que se correspondan con ella.


## <a name="related-topics"></a>Temas relacionados
- [Administrar indicadores](manage-indicators.md)
