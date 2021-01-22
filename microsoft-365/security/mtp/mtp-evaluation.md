---
title: Evaluación de Microsoft 365 Defender
description: Configure el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender para probar y experimentar la solución de seguridad diseñada para proteger dispositivos, identidades, datos y aplicaciones de su organización.
keywords: Prueba de Protección contra amenazas de Microsoft, pruebe la Protección contra amenazas de Microsoft, evalúe la Protección contra amenazas de Microsoft, el laboratorio de evaluación de protección contra amenazas de Microsoft, el piloto de Protección contra amenazas de Microsoft, la seguridad cibernética, la amenaza persistente avanzada, la seguridad empresarial, los dispositivos, el dispositivo, la identidad, los usuarios, los datos, las aplicaciones, los incidentes, la investigación y corrección automatizada, la búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930215"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Crear un entorno piloto o laboratorio de prueba de Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


Esta guía le ayuda a trabajar en la configuración de un entorno de laboratorio con usuarios y grupos y, a continuación, le guiará a través de la configuración de las capacidades de Microsoft 365 Defender para que pueda imitar un ataque de amenazas y obtener un resultado de prueba significativo. 

El propósito de crear este entorno de prueba o piloto es ilustrar las capacidades completas e integradas de Microsoft 365 Defender. Experimente cómo esta solución de seguridad inteligente detecta, impide, investiga automáticamente y responde a amenazas avanzadas de su organización. 


Se le guiará por los pasos para iniciar la evaluación de Microsoft 365 Defender en función de las rutas de implementación recomendadas. El objetivo es ayudarle a configurar la solución de seguridad en un entorno de laboratorio con una cuenta de prueba o en un entorno piloto en producción con una licencia completa. Preparar el entorno de prueba o piloto puede ayudarle a presentar casos de uso de operaciones de seguridad a los responsables de la toma de decisiones de su organización. Cuando haya terminado de ejecutar las simulaciones de ataque y esté satisfecho con los resultados, puede implementarlo y operarlo completamente en su organización con la ayuda de profesionales de ventas técnicas de Microsoft o expertos de su organización. 

Esta guía le ayudará a:
- Configurar el servidor de laboratorio y los equipos
- Configurar Active Directory con usuarios y grupos
- Configurar Microsoft Defender para Identity, Microsoft Defender para Office 365, Microsoft Defender para Endpoint y Microsoft Cloud App Security
- Configurar directivas locales para el servidor y los equipos
- Imitar un ataque de amenaza para generar un incidente de prueba o alerta en Microsoft 365 Defender

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio lo más cerca posible.


## <a name="deployment-phases"></a>Fases de implementación

Hay tres fases para crear un entorno de laboratorio de prueba de Microsoft 365 Defender.

![Fases de implementación: preparar, configurar, incorporar](../../media/evaluation-guide-phases.png)

|Fase | Descripción | 
|:-------|:-----|
|[Fase 1: Preparar](prepare-mtpeval.md)| Obtenga información sobre lo que necesita tener en cuenta al implementar Microsoft 365 Defender en un entorno piloto o laboratorio de prueba: <br><br>- Partes interesadas y cerrar sesión <br> - Consideraciones de entorno <br>- Acceso <br>- Configuración de Azure Active Directory <br> - Orden de configuración
|[Fase 2: Instalación](setup-mtpeval.md)|  Siga los pasos iniciales para acceder al Centro de seguridad de Microsoft 365 para configurar su entorno piloto o laboratorio de prueba de Microsoft 365 Defender. Se le guiará a:<br><br>- Registrarse para la prueba de Microsoft 365 E5 <br>  - Configurar dominio<br>- Asignar licencias de Microsoft 365 E5<br>- Completar el asistente de configuración en el portal|
|[Fase 3: Configurar & incorporación](config-mtpeval.md) | Configurar cada columna de Microsoft 365 Defender y incorporar puntos de conexión. Se le guiará a:<br><br>- Configurar Microsoft Defender para Office 365<br>- Configurar Microsoft Cloud App Security<br>- Configurar Microsoft Defender para la identidad<br>- Configurar Microsoft Defender para endpoint


Después de completar esta guía, habrá identificado a las partes interesadas implicadas y las aprobaciones necesarias, tiene los permisos de acceso adecuados, se ha registrado para la prueba, los dominios configurados y cada uno de los pilares de Microsoft 365 Defender, y los puntos de conexión se incorporarán al servicio.

## <a name="key-capabilities"></a>Principales funcionalidades

Aunque Microsoft 365 Defender proporciona muchas funcionalidades, el propósito principal de esta guía de implementación es empezar a incorporar dispositivos. Además de la incorporación, estas instrucciones te ayudarán a empezar con las siguientes funcionalidades.


Funcionalidad | Descripción 
:---|:---
Microsoft Defender para Office 365 | Ayuda a proteger todo el aislamiento de Office 365 de las amenazas actuales
Microsoft Defender for Identity | Identifica y detecta amenazas en identidades comprometidas y acciones internas malintencionadas.
Microsoft Cloud App Security | Proporciona una visibilidad enriquecida, controla los viajes de datos y detecta ciberamenazas en los servicios en la nube.
Microsoft Defender para punto de conexión | Impide, detecta y proporciona capacidades de respuesta a amenazas avanzadas con seguridad completa de los puntos de conexión.


## <a name="in-scope"></a>En el ámbito

Las siguientes tareas están en el ámbito de esta guía:
-   Configurar Azure Active Directory
-   Configurar Microsoft 365 Defender
    -   Registrarse en la prueba de Microsoft 365 E5 o usar la licencia completa si está ejecutando un piloto
    -   Configurar dominio
    -   Asignar licencias de Microsoft 365 E5
    -   Finalización del asistente para instalación en el portal
-   Configurar todos los pilares de Microsoft 365 Defender en función de los procedimientos recomendados
    -   Microsoft Defender para Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender para punto de conexión

## <a name="out-of-scope"></a>Fuera de ámbito

Los siguientes elementos están fuera del ámbito de esta guía de implementación:

-   Configuración de soluciones de terceros que podrían integrarse con Microsoft 365 Defender
-   Pruebas de penetración en entornos de producción

## <a name="next-step"></a>Paso siguiente
[Fase 1: Preparar](prepare-mtpeval.md) 
<br> Preparar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender
