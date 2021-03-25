---
title: Evaluación de Microsoft 365 Defender
description: Configure el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender para probar y experimentar la solución de seguridad diseñada para proteger los dispositivos, la identidad, los datos y las aplicaciones de su organización.
keywords: Prueba de Protección contra amenazas de Microsoft, prueba Microsoft Threat Protection, evalúa Microsoft Threat Protection, Microsoft Threat Protection evaluation lab, Microsoft Threat Protection pilot, cyber security, advanced persistent threat, enterprise security, devices, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting, advanced hunting
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2ea829e0e2697facd2522dbf16ced7d620662eee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076656"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Crear un entorno piloto o un laboratorio de prueba de Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


Esta guía le ayuda a trabajar en la configuración de un entorno de laboratorio con usuarios y grupos y, a continuación, le guía a través de la configuración de las capacidades de Microsoft 365 Defender para que pueda imitar un ataque de amenazas y obtener un resultado de prueba significativo. 

El propósito de crear este entorno piloto o laboratorio de prueba es ilustrar las capacidades completas e integradas de Microsoft 365 Defender. Experimente cómo esta solución de seguridad inteligente detecta, evita, investiga automáticamente y responde a amenazas avanzadas de su organización. 


Se le guiará por los pasos para iniciar la evaluación de Microsoft 365 Defender en función de las rutas de implementación recomendadas. El objetivo es ayudarle a configurar la solución de seguridad en un entorno de laboratorio con una cuenta de prueba o en un entorno piloto en producción con una licencia completa. Preparar el entorno piloto o de laboratorio de prueba puede ayudarle a presentar casos de uso de la operación de seguridad a los responsables de la toma de decisiones de su organización. Cuando haya terminado de ejecutar las simulaciones de ataque y esté satisfecho con los resultados, puede implementarlo y operarlo completamente en su organización con la ayuda de profesionales de ventas técnicas de Microsoft o expertos en su organización. 

Esta guía le ayudará a:
- Configurar el servidor de laboratorio y los equipos
- Configurar Active Directory con usuarios y grupos
- Configurar y configurar Microsoft Defender para Identity, Microsoft Defender para Office 365, Microsoft Defender para Endpoint y Microsoft Cloud App Security
- Configurar directivas locales para el servidor y los equipos
- Imitar un ataque de amenaza para generar una alerta o un incidente de prueba en Microsoft 365 Defender

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio lo más de cerca posible.


## <a name="deployment-phases"></a>Fases de implementación

Hay tres fases en la creación de un entorno de laboratorio de prueba de Microsoft 365 Defender.

![Fases de implementación: preparar, configurar, incorporar](../../media/evaluation-guide-phases.png)

|Fase | Descripción | 
|:-------|:-----|
|[Fase 1: Preparar](prepare-m365d-eval.md)| Obtenga información sobre lo que debe tener en cuenta al implementar Microsoft 365 Defender en un entorno piloto o de laboratorio de prueba: <br><br>- Partes interesadas y inicio de sesión <br> - Consideraciones sobre el entorno <br>- Access <br>- Configuración de Azure Active Directory <br> - Orden de configuración
|[Fase 2: Configuración](setup-m365deval.md)|  Siga los pasos iniciales para acceder al Centro de seguridad de Microsoft 365 para configurar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender. Se le guiará a:<br><br>- Registrarse para la versión de prueba de Microsoft 365 E5 <br>  - Configurar dominio<br>- Asignar licencias de Microsoft 365 E5<br>- Completar el asistente de configuración en el portal|
|[Fase 3: Configurar & incorporación](config-m365d-eval.md) | Configure cada pilar de Microsoft 365 Defender y los puntos de conexión integrados. Se le guiará a:<br><br>- Configurar Microsoft Defender para Office 365<br>- Configurar Microsoft Cloud App Security<br>- Configurar Microsoft Defender para la identidad<br>- Configurar Microsoft Defender para el punto de conexión


Después de completar esta guía, habría identificado las partes interesadas implicadas y las aprobaciones necesarias, tiene los permisos de acceso adecuados, se ha registrado para la prueba, los dominios configurados y cada uno de los pilares de Microsoft 365 Defender y los puntos de conexión se incorporarán al servicio.

## <a name="key-capabilities"></a>Principales funcionalidades

Aunque Microsoft 365 Defender proporciona muchas funcionalidades, el objetivo principal de esta guía de implementación es empezar a incorporar dispositivos. Además de la incorporación, esta guía le permite empezar con las siguientes funcionalidades.


Funcionalidad | Descripción 
:---|:---
Microsoft Defender para Office 365 | Ayuda a proteger todo el envrionment de Office 365 de las amenazas actuales
Microsoft Defender for Identity | Identifica y detecta amenazas en identidades comprometidas y acciones internas malintencionadas.
Microsoft Cloud App Security | Proporciona una visibilidad enriquecida, controla los viajes de datos y detecta ciberamenazas en los servicios en la nube.
Microsoft Defender para punto de conexión | Impide, detecta y proporciona capacidades de respuesta a amenazas avanzadas con una seguridad de extremo completa.


## <a name="in-scope"></a>En el ámbito

Las siguientes tareas están en el ámbito de esta guía:
-   Configurar Azure Active Directory
-   Configurar Microsoft 365 Defender
    -   Regístrate en prueba de Microsoft 365 E5 o usa la licencia completa si estás ejecutando un piloto
    -   Configurar dominio
    -   Asignar licencias de Microsoft 365 E5
    -   Completar el asistente de configuración en el portal
-   Configurar todos los pilares de Microsoft 365 Defender en función de los procedimientos recomendados
    -   Microsoft Defender para Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender para punto de conexión

## <a name="out-of-scope"></a>Fuera de ámbito

Los siguientes están fuera del ámbito de esta guía de implementación:

-   Configuración de soluciones de terceros que podrían integrarse con Microsoft 365 Defender
-   Pruebas de penetración en entornos de producción

## <a name="next-step"></a>Paso siguiente
[Fase 1: Preparar](prepare-m365d-eval.md) 
<br> Preparar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender
