---
title: Evaluación de la protección contra amenazas de Microsoft
description: Configure el entorno de prueba de la protección contra amenazas de Microsoft para probar cómo la solución coordinada de protección contra amenazas diseñada para proteger dispositivos, identidades, datos y aplicaciones puede ayudar a su organización
keywords: Microsoft Threat Protection Trial, pruebe la protección contra amenazas de Microsoft, evalúe Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, Cyber Security, la seguridad persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049644"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a>Crear un entorno de laboratorio de prueba de Microsoft Threat Protection 

**Se aplica a:**
- Protección contra amenazas de Microsoft

El propósito de crear este entorno de laboratorio de prueba es ilustrar las capacidades completas, integradas e inteligentes de la protección contra amenazas de Microsoft en detección, prevención, investigación y respuesta que puede usar en su organización. 

Esta guía le guiará por los pasos necesarios para iniciar la evaluación de Microsoft Threat Protection en función de las rutas de implementación recomendadas. El objetivo es ayudarle a configurar los servicios integrados de protección contra amenazas de Microsoft en un entorno de laboratorio o como una prueba de concepto (POC) cuando se presentan a los responsables de las decisiones de las soluciones de seguridad de la organización. Cuando haya terminado de ejecutar las simulaciones de ataque, la investigación y la respuesta automatizadas, y que estén satisfechos con los resultados, puede implementarla en su entorno de producción con la ayuda de profesionales de ventas técnicos de Microsoft o expertos de su organización. 

Esta guía le ayudará a:
- Configurar el servidor y los equipos del laboratorio
- Configuración de Active Directory con usuarios y grupos
- Configurar y configurar ATP de Azure, ATP de Office, ATP de Microsoft defender y Microsoft Cloud App Security
- Configurar directivas locales para el servidor y los equipos
- Imitar un ataque de amenaza para generar una alerta o incidente de prueba en la protección contra amenazas de Microsoft

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio tan cerca como sea posible.


## <a name="deployment-phases"></a>Fases de implementación

Hay tres fases para la creación de un entorno de laboratorio de prueba de Microsoft Threat Protection y su implementación:

|Fase | Descripción | 
|:-------|:-----|
| ![Fase 1: preparación](../../media/prepare.png)<br>[Fase 1: preparación](prepare-mtpeval.md)| Obtenga información sobre lo que debe tener en cuenta al implementar la protección contra amenazas de Microsoft en un entorno de prueba de pruebas: <br><br>-Partes interesadas y la firma <br> Consideraciones del entorno <br>Acceso a <br>-Instalación de Azure Active Directory <br> -Orden de configuración
|  ![Fase 2: configuración](../../media/setup.png) <br>[Fase 2: configuración](setup-mtpeval.md)|  Siga los pasos iniciales para acceder al centro de seguridad de Microsoft 365 para configurar el entorno de laboratorio de prueba de Microsoft Threat Protection. Se le guiará para:<br><br>-Inscríbase en la versión de prueba de Microsoft 365 E5 <br>  -Configurar dominio<br>-Asignar licencias de Microsoft 365 E5<br>-Completar el Asistente de configuración en el portal|
|  ![Fase 3: configurar & incorporado](../../media/config-onboard.png) <br>[Fase 3: configurar & incorporado](config-mtpeval.md) | Configure cada uno de los extremos incorporados y de la protección contra amenazas de Microsoft. Se le guiará para:<br><br>-Configurar la protección contra amenazas avanzada de Office 365<br>-Configurar Microsoft Cloud App Security<br>-Configurar la protección contra amenazas avanzada de Azure<br>-Configurar la protección contra amenazas avanzada de Microsoft defender 


## <a name="in-scope"></a>En el ámbito

A continuación se encuentra en el ámbito de esta guía del entorno de laboratorio de prueba:
-   Configurar Azure Active Directory
-   Configuración de la protección contra amenazas de Microsoft
    -   Inscríbase en la versión de prueba de Microsoft 365 E5
    -   Configurar dominio
    -   Asignar licencias de Microsoft 365 E5
    -   Finalización del Asistente para la instalación en el portal
-   Configurar todos los pilares de la protección contra amenazas de Microsoft según los procedimientos recomendados
    -   Protección contra amenazas avanzada de Office 365
    -   Azure Advanced Threat Protection
    -   Microsoft Cloud App Security
    -   Protección contra amenazas avanzada de Microsoft Defender

## <a name="out-of-scope"></a>Fuera de ámbito

Las siguientes opciones están fuera del ámbito de esta guía de implementación:

-   Configuración de soluciones de terceros que pueden integrarse con ATP de Microsoft defender
-   Pruebas de penetración en el entorno de producción

## <a name="next-step"></a>Paso siguiente
|||
|:-------|:-----|
|![Fase 1: preparación](../../media/prepare.png) <br>[Fase 1: preparación](prepare-mtpeval.md) | Preparar el entorno de laboratorio de evaluación de Microsoft Threat Protection
