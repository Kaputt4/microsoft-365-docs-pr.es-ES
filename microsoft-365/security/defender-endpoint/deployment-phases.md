---
title: Fases de implementación
description: Obtenga información sobre cómo implementar Microsoft Defender para endpoint mediante la preparación, configuración e incorporación de puntos de conexión a ese servicio
keywords: implementar, preparar, configurar, incorporar, fase, implementación, implementación, adopción, configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165170"
---
# <a name="deployment-phases"></a>Fases de implementación

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Obtenga información sobre cómo implementar Microsoft Defender para endpoint para que su empresa pueda aprovechar la protección preventiva, la detección posterior a la infracción, la investigación automatizada y la respuesta. 


Esta guía le ayuda a trabajar entre partes interesadas para preparar su entorno y, a continuación, incorporar dispositivos de forma metórica, pasando de la evaluación a un piloto significativo, a una implementación completa.

Cada sección corresponde a un artículo independiente de esta solución.

![Imagen de las fases de implementación con detalles de la tabla](images/deployment-guide-phases.png)


![Resumen de las fases de implementación: preparar, configurar, incorporar](images/phase-diagrams/deployment-phases.png)

|Fase | Descripción | 
|:-------|:-----|
| [Fase 1: Preparar](prepare-deployment.md)| Obtenga información sobre lo que debe tener en cuenta al implementar Defender for Endpoint, como aprobaciones de partes interesadas, consideraciones del entorno, permisos de acceso y orden de adopción de capacidades. 
| [Fase 2: Configuración](production-deployment.md)|  Obtenga instrucciones sobre los pasos iniciales que debe seguir para tener acceso al portal, como validar licencias, completar el asistente de instalación y configuración de red. 
| [Fase 3: Incorporación](onboarding.md) | Obtenga información sobre cómo usar anillos de implementación, herramientas de incorporación compatibles basadas en el tipo de extremo y cómo configurar las capacidades disponibles. 


Después de completar esta guía, se configurará con los permisos de acceso adecuados, los puntos de conexión se incorporarán e informarán de los datos del sensor al servicio, y se instalarán funcionalidades como la protección de última generación y la reducción de superficie de ataque.



Independientemente de la arquitectura del entorno y el método de implementación que elija en la [guía de](deployment-strategy.md) planeación de implementación, esta guía le admitirá en los puntos de conexión de incorporación. 








## <a name="key-capabilities"></a>Principales funcionalidades

Aunque Microsoft Defender para endpoint proporciona muchas funcionalidades, el objetivo principal de esta guía de implementación es empezar por la incorporación de dispositivos. Además de la incorporación, esta guía le permite empezar con las siguientes funcionalidades.



Funcionalidad | Descripción 
:---|:---
Detección y respuesta de puntos de conexión. | Las capacidades de detección y respuesta de puntos de conexión se ponen en marcha para detectar, investigar y responder a intentos de intrusión e infracciones activas.
Protección de última generación | Para reforzar aún más el perímetro de seguridad de la red, Microsoft Defender para endpoint usa la protección de última generación diseñada para detectar todo tipo de amenazas emergentes.
Reducción de la superficie expuesta a ataques |  Proporcione la primera línea de defensa en la pila. Al garantizar que las opciones de configuración se establecen correctamente y se aplican técnicas de mitigación de vulnerabilidades, este conjunto de capacidades resiste los ataques y la explotación.

Todas estas funcionalidades están disponibles para microsoft defender para los titulares de licencias de extremo. Para obtener más información, vea [Requisitos de licencias](minimum-requirements.md#licensing-requirements).

## <a name="scope"></a>Ámbito

### <a name="in-scope"></a>En el ámbito

-   Uso de Microsoft Endpoint Manager y Microsoft Endpoint Manager para incorporar puntos de conexión en el servicio y configurar funcionalidades

-   Habilitar las capacidades de detección y respuesta de puntos de conexión (EDR) de Defender para endpoints

-   Habilitar las capacidades de defender para la plataforma de protección de puntos de conexión (EPP)

    -   Protección de última generación

    -   Reducción de la superficie expuesta a ataques


### <a name="out-of-scope"></a>Fuera de ámbito

Los siguientes están fuera del ámbito de esta guía de implementación:

-   Configuración de soluciones de terceros que podrían integrarse con Defender for Endpoint

-   Pruebas de penetración en entornos de producción




## <a name="see-also"></a>Ver también
- [Fase 1: Preparar](prepare-deployment.md)
- [Fase 2: Configurar](production-deployment.md)
- [Fase 3: Incorporación](onboarding.md)
- [Planeación de la implementación](deployment-strategy.md)