---
title: Incidentes en Microsoft 365 Defender
description: Investigar incidentes vistos en todos los dispositivos, usuarios y buzones de correo.
keywords: incidentes, alertas, investigar, correlación, ataque, equipos, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, Microsoft, M365
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
ms.openlocfilehash: 5b2baa2041a8cffcea212eb449d40b9a9cbfc22a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759510"
---
# <a name="incidents-in-microsoft-365-defender"></a>Incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).
>

Un incidente en Microsoft 365 Defender es una colección de alertas correlacionadas y datos asociados que son la historia de un ataque. 

Los servicios y aplicaciones de Microsoft 365 crean alertas cuando detectan un evento o actividad sospechosos o malintencionados. Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso. Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones. El resultado son varias alertas para varias entidades del espacio empresarial. 

Dado que unir las alertas individuales para obtener información sobre un ataque puede ser un desafío y un consumo de tiempo, Microsoft 365 Defender agrega automáticamente las alertas y su información asociada en un incidente.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Cómo Microsoft 365 Defender correlaciona eventos de entidades en un incidente":::

Vea esta breve introducción a los incidentes en Microsoft 365 Defender (4 minutos).

<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

La agrupación de alertas relacionadas en un incidente le ofrece una vista completa de un ataque. Por ejemplo, puede ver:

- Donde se inició el ataque.
- Qué tácticas se usaron.
- Cuánto ha llegado el ataque a su inquilino.
- El ámbito del ataque, como el número de dispositivos, usuarios y buzones de correo afectados. 
- Todos los datos asociados con el ataque.

Si [está habilitado,](m365d-enable.md)Microsoft 365 Defender puede investigar y resolver alertas automáticamente a través de la automatización y la inteligencia artificial. También puedes realizar pasos de corrección adicionales para resolver el ataque. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Incidentes y alertas en el centro de seguridad de Microsoft 365

Puede administrar incidentes desde incidentes **& alertas > incidentes** en el inicio rápido del centro de seguridad de Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)). Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="La página Incidentes en el Centro de seguridad de Microsoft 365":::

Al seleccionar un nombre de incidente, se muestra un resumen del incidente y se proporciona acceso a las pestañas con información adicional.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Ejemplo de la página Resumen de un incidente en el Centro de seguridad de Microsoft 365":::

Las pestañas adicionales para un incidente son:

- Alertas 

  Todas las alertas relacionadas con el incidente y su información.

- Dispositivos

  Todos los dispositivos que se han identificado para formar parte o relacionados con el incidente.

- Usuarios

  Todos los usuarios identificados para formar parte del incidente o relacionados con ellos.

- Buzones

  Todos los buzones que se han identificado para formar parte o relacionados con el incidente.

- Investigaciones

  Todas las investigaciones automatizadas desencadenadas por alertas en el incidente.

- Evidencia y respuesta

  Todos los eventos admitidos y las entidades sospechosas en las alertas del incidente.

Esta es la relación entre un incidente y sus datos y las pestañas de un incidente en el Centro de seguridad de Microsoft 365.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="La relación de un incidente y sus datos con las pestañas de un incidente en el Centro de seguridad de Microsoft 365":::

## <a name="next-step"></a>Paso siguiente

La cola de incidentes de **la página Incidentes** enumera los incidentes más recientes. Desde aquí, puede:

- Vea qué incidentes deben [priorizarse en](incident-queue.md) función de la gravedad y otros factores. 
- Realice una [investigación](investigate-incidents.md) de un incidente.
- [Administrar incidentes, lo](manage-incidents.md)que incluye cambiar el nombre, asignarlos, clasificarlos y agregar etiquetas para el flujo de trabajo de administración de incidentes.
