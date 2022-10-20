---
title: introducción a la implementación de Microsoft Defender para punto de conexión
description: Aprenda a implementar Microsoft Defender para punto de conexión mediante la preparación, configuración e incorporación de puntos de conexión a ese servicio.
keywords: implementar, preparar, configurar, incorporar, fase, implementación, implementación, adopción, configuración
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-endpointprotect
- m365solution-overview
- highpri
- tier1
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 8316bb05d3fed831479ebadc3c6f2bb5e318e5fd
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68642753"
---
# <a name="microsoft-defender-for-endpoint-deployment-overview"></a>introducción a la implementación de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Obtenga información sobre cómo implementar Microsoft Defender para punto de conexión para que su empresa pueda aprovechar la protección preventiva, la detección posterior a la vulneración, la investigación automatizada y la respuesta.

Esta guía le ayuda a trabajar entre las partes interesadas para preparar el entorno y, a continuación, incorporar dispositivos de forma metódica, pasando de la evaluación, a un piloto significativo, a una implementación completa.

Cada sección corresponde a un artículo independiente de esta solución.

:::image type="content" source="images/deployment-guide-phases.png" alt-text="Fases de implementación con detalles de la tabla" lightbox="images/deployment-guide-phases.png":::


:::image type="content" source="images/phase-diagrams/deployment-phases.png" alt-text="Resumen de las fases de implementación: preparación, configuración, incorporación" lightbox="images/phase-diagrams/deployment-phases.png":::

<br>

****

|Fase|Descripción|
|---|---|
|[Fase 1: Preparación](prepare-deployment.md)|Obtenga información sobre lo que debe tener en cuenta al implementar Defender para punto de conexión, como las aprobaciones de las partes interesadas, las consideraciones del entorno, los permisos de acceso y el orden de adopción de las funcionalidades.|
|[Fase 2: Configuración](production-deployment.md)|Obtenga instrucciones sobre los pasos iniciales que debe seguir para poder acceder al portal, como la validación de licencias, la finalización del asistente de configuración y la configuración de red.|
|[Fase 3: Incorporación](onboarding.md)|Obtenga información sobre cómo usar los anillos de implementación, las herramientas de incorporación admitidas en función del tipo de punto de conexión y la configuración de las funcionalidades disponibles.|
|

Una vez completada esta guía, se configurará con los permisos de acceso adecuados, se incorporarán los puntos de conexión y se notificarán los datos del sensor al servicio, y se aplicarán funcionalidades como la protección de próxima generación y la reducción de la superficie expuesta a ataques.

Independientemente de la arquitectura del entorno y el método de implementación que elija descritos en la guía [Planeamiento de la implementación](deployment-strategy.md) , esta guía le admitirá en la incorporación de puntos de conexión.

## <a name="key-capabilities"></a>Principales funcionalidades

Aunque Microsoft Defender para punto de conexión proporciona muchas funcionalidades, el propósito principal de esta guía de implementación es empezar a incorporar dispositivos. Además de la incorporación, esta guía le permite empezar con las siguientes funcionalidades.

<br>

****

|Funcionalidad|Descripción|
|---|---|
|Detección y respuesta de puntos de conexión|Las funcionalidades de detección y respuesta de puntos de conexión se implementan para detectar, investigar y responder a intentos de intrusiones y infracciones activas.|
|Protección de última generación|Para reforzar aún más el perímetro de seguridad de la red, Microsoft Defender para punto de conexión usa la protección de próxima generación diseñada para detectar todos los tipos de amenazas emergentes.|
|Reducción de la superficie expuesta a ataques|Proporcione la primera línea de defensa en la pila. Al garantizar que los valores de configuración se establecen correctamente y se aplican las técnicas de mitigación de vulnerabilidades de seguridad, estas funcionalidades resisten los ataques y la explotación.|
|

Todas estas funcionalidades están disponibles para Microsoft Defender para punto de conexión titulares de licencias. Para obtener más información, consulte [Requisitos de licencias](minimum-requirements.md#licensing-requirements).

## <a name="scope"></a>Ámbito

### <a name="in-scope"></a>En el ámbito

- Uso de Microsoft Endpoint Manager y Microsoft Endpoint Configuration Manager para incorporar puntos de conexión al servicio y configurar funcionalidades
- Habilitación de las funcionalidades de detección y respuesta de puntos de conexión de Defender para punto de conexión (EDR)
- Habilitación de las funcionalidades de la plataforma de protección de puntos de conexión (EPP) de Defender para punto de conexión
  - Protección de última generación
  - Reducción de la superficie expuesta a ataques

### <a name="out-of-scope"></a>Fuera de ámbito

Las siguientes opciones están fuera del ámbito de esta guía de implementación:

- Configuración de soluciones de terceros que podrían integrarse con Defender para punto de conexión
- Pruebas de penetración en el entorno de producción

## <a name="see-also"></a>Vea también

- [Fase 1: Preparación](prepare-deployment.md)
- [Fase 2: Configuración](production-deployment.md)
- [Fase 3: Incorporación](onboarding.md)
- [Planeación de la implementación](deployment-strategy.md)
