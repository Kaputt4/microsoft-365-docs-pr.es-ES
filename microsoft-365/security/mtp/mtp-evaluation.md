---
title: Evalúe Microsoft 365 defender
description: Configure el entorno piloto o el laboratorio de prueba de Microsoft 365 defender para probar y experimentar la solución de seguridad diseñada para proteger los dispositivos, la identidad, los datos y las aplicaciones de su organización.
keywords: Microsoft Threat Protection Trial, pruebe Microsoft Threat Protection, evalúe Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, Microsoft Threat Protection Pilot, Cyber Security, seguridad persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130887"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Crear un entorno piloto o un laboratorio de prueba de Microsoft 365 defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La finalidad de crear este entorno de prueba o un entorno piloto es ilustrar las capacidades completas e integradas de Microsoft 365 defender. Experimente cómo esta solución de seguridad inteligente detecta, evita, investiga automáticamente y responde a las amenazas avanzadas de su organización. 

Esta guía le guiará por los pasos para iniciar la evaluación de Microsoft 365 defender en función de las rutas de implementación recomendadas. El objetivo es ayudarle a configurar la solución de seguridad, ya sea en un entorno de laboratorio con una cuenta de prueba o en un entorno piloto en producción con una licencia completa. La preparación del entorno piloto o del laboratorio de pruebas puede ayudarle a presentar los casos de uso de la operación de seguridad a los responsables de la toma de decisiones de la organización. Cuando haya terminado de ejecutar las simulaciones de ataque y esté satisfecho con los resultados, puede implementar y descargar por completo en su organización con la ayuda de profesionales de ventas técnicos de Microsoft o expertos de su organización. 

Esta guía le ayudará a:
- Configurar el servidor y los equipos del laboratorio
- Configuración de Active Directory con usuarios y grupos
- Instalación y configuración de Microsoft defender para identidad, Microsoft defender para Office 365, Microsoft defender para el Endpoint y Microsoft Cloud App Security
- Configurar directivas locales para el servidor y los equipos
- Imitar un ataque de amenaza para generar una alerta o incidente de prueba en Microsoft 365 defender

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio tan cerca como sea posible.


## <a name="deployment-phases"></a>Fases de implementación

Hay tres fases para crear un entorno de laboratorio de prueba de Microsoft 365 defender e implementarlo:

![Fases de implementación: preparación, configuración, incorporación](../../media/phase-diagrams/deployment-phases.png)

|Fase | Descripción | 
|:-------|:-----|
|[Fase 1: preparación](prepare-mtpeval.md)| Obtenga información sobre lo que debe tener en cuenta al implementar Microsoft 365 defender en un laboratorio de pruebas o un entorno piloto: <br><br>-Partes interesadas y la firma <br> Consideraciones del entorno <br>Acceso a <br>-Instalación de Azure Active Directory <br> -Orden de configuración
|[Fase 2: configuración](setup-mtpeval.md)|  Siga los pasos iniciales para acceder al centro de seguridad de Microsoft 365 para configurar el entorno piloto o el laboratorio de pruebas de Microsoft 365 defender. Se le guiará a:<br><br>-Inscríbase en la versión de prueba de Microsoft 365 E5 <br>  -Configurar dominio<br>-Asignar licencias de Microsoft 365 E5<br>-Completar el Asistente de configuración en el portal|
|[Fase 3: configurar & incorporado](config-mtpeval.md) | Configure cada uno de los puntos de conexión y los pilares de 365 defender de Microsoft. Se le guiará a:<br><br>-Configurar Microsoft defender para Office 365<br>-Configurar Microsoft Cloud App Security<br>-Configurar Microsoft defender para identidad<br>-Configurar Microsoft defender para el punto de conexión


## <a name="in-scope"></a>En el ámbito

Las siguientes tareas se encuentran en el ámbito de esta guía:
-   Configurar Azure Active Directory
-   Configurar Microsoft 365 defender
    -   Regístrese en la versión de prueba de Microsoft 365 E5 o use su licencia completa si está ejecutando un piloto
    -   Configurar dominio
    -   Asignar licencias de Microsoft 365 E5
    -   Finalización del Asistente para la instalación en el portal
-   Configurar todos los pilares de 365 defender de Microsoft según los procedimientos recomendados
    -   Microsoft Defender para Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender para punto de conexión

## <a name="out-of-scope"></a>Fuera de ámbito

Las siguientes opciones están fuera del ámbito de esta guía de implementación:

-   Configuración de soluciones de terceros que pueden integrarse con Microsoft 365 defender
-   Pruebas de penetración en el entorno de producción

## <a name="next-step"></a>Paso siguiente
[Fase 1: preparación](prepare-mtpeval.md) 
<br> Preparar el entorno piloto o el laboratorio de prueba de Microsoft 365 defender
