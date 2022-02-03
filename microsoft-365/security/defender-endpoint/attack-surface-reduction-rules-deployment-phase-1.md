---
title: 'Fase 1 de implementación de reglas de ASR: planificar'
description: Proporciona instrucciones para planear la implementación de las reglas de reducción de superficie de ataque.
keywords: Implementación de reglas de reducción de superficie de ataque, implementación de ASR, habilitar reglas asr, configurar ASR, sistema de prevención de intrusiones de host, reglas de protección, reglas contra vulnerabilidades, anti exploit, reglas de vulnerabilidad, reglas de prevención de infecciones, Microsoft Defender para endpoint, configurar reglas ASR
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: m365solution-scenario
ms.date: 1/18/2022
ms.openlocfilehash: ecd582f99dd0dfa9df51ce50651904144dcc8ff8
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321846"
---
# <a name="asr-rules-deployment-phase-1-plan"></a>Fase 1 de implementación de reglas ASR: plan

Empezar a probar las reglas asr implica empezar con la unidad de negocio adecuada. Querrá empezar con un pequeño grupo de personas en una unidad de negocio específica. Puede identificar algunos campeones de ASR dentro de una unidad de negocio determinada que puedan proporcionar un impacto real a las reglas de ASR y ayudarle a ajustar su implementación.

> [!div class="mx-imgBorder"]
> ![Pasos de planeación de reglas de ASR](images/asr-rules-planning-steps.png)

## <a name="start-with-the-right-business-unit"></a>Comience con la unidad de negocio adecuada

La forma de seleccionar la unidad de negocio para implementar la implementación de reglas ASR dependerá de factores como:

- Tamaño de la unidad de negocio
- Disponibilidad de campeones de reglas ASR  
- Distribución y uso de:
  - Software
  - Carpetas compartidas
  - Uso de scripts
  - Office macros
  - Otras entidades afectadas por reglas ASR

Según las necesidades de su empresa, puede decidir incluir varias unidades de negocio para obtener un amplio muestreo de software, carpetas compartidas, scripts, macros, etc. Por el contrario, puede decidir limitar el ámbito de la primera implementación de reglas ASR a una sola unidad de negocio y, a continuación, repetir todo el proceso de implementación de reglas ASR a las demás unidades de negocio, de una en una.

## <a name="identify-asr--rules-champions"></a>Identificar campeones de reglas ASR

Los campeones de reglas ASR son miembros de la organización que ayudarán con el lanzamiento de las reglas ASR iniciales durante las fases preliminares de prueba e implementación. Los campeones suelen ser empleados que son más expertos técnicamente y que no se descarrila por interrupciones intermitentes del flujo de trabajo. La participación de los campeones continuará a lo largo de la expansión más amplia de la implementación de reglas ASR en su organización. Los campeones de reglas ASR serán los primeros en experimentar cada nivel del lanzamiento de reglas ASR.

Es importante proporcionar un canal de comentarios y respuesta para que los campeones de reglas ASR le alerte sobre las interrupciones de trabajo relacionadas con las reglas asr y reciba comunicaciones relacionadas con la implementación de reglas asr.

## <a name="get-inventory-of-line-of-business-apps-and-understand-the-business-unit-processes"></a>Obtener inventario de aplicaciones de línea de negocio y comprender los procesos de la unidad de negocio

Tener una comprensión completa de las aplicaciones y los procesos por unidad empresarial que se usan en toda la organización es fundamental para una implementación correcta de reglas ASR. Además, es imperativo que comprenda cómo se usan esas aplicaciones en las distintas unidades de negocio de su organización.
Para empezar, debes obtener un inventario de las aplicaciones aprobadas para su uso en toda la organización. Puede usar herramientas como el Centro de administración Aplicaciones Microsoft 365 para ayudarle a realizar el inventario de aplicaciones de software. Vea: [Información general sobre el inventario en el centro Aplicaciones Microsoft 365 administración](/deployoffice/admincenter/inventory).

## <a name="define-reporting-and-response-team--roles-and-responsibilities"></a>Definir responsabilidades y roles de equipo de informes y respuesta

La función y responsabilidades claramente articuladas de las personas responsables de supervisar y comunicar el estado y la actividad de las reglas ASR es una actividad principal del mantenimiento de ASR. Por lo tanto, es importante determinar:

- La persona o el equipo responsable de recopilar informes
- Cómo y con quién se comparten los informes
- Cómo se aborda la escalación para amenazas recién identificadas o bloqueos no deseados causados por reglas ASR

Los roles y responsabilidades típicos incluyen:

- Administradores de TI: implementar reglas ASR y administrar exclusiones. Trabajar con diferentes unidades de negocio en aplicaciones y procesos. Ensamblar y compartir informes a las partes interesadas
- Analista del Centro de operaciones de seguridad certificado (CSOC): responsable de invertir procesos bloqueados y de alta prioridad, para determinar si la amenaza es válida o no.
- Director de seguridad de la información (CISO): responsable de la posición general de seguridad y el estado de la organización

## <a name="ring-deployment"></a>Implantación de anillos

Para las grandes empresas, Microsoft recomienda implementar reglas ASR en "anillos". Los anillos son grupos de dispositivos que se representan visualmente como círculos concéntricos que se radian hacia fuera como anillos de árbol no superpuestos. Cuando el anillo más interno se implementa correctamente, puede pasar el siguiente anillo a la fase de prueba. Una evaluación exhaustiva de las unidades de negocio, los campeones de reglas de ASR, las aplicaciones y los procesos es imprescindible para definir los anillos.
En la mayoría de los casos, la organización habrá diseñado anillos de implementación para implementaciones por fases de Windows actualizaciones. Puede usar el diseño de anillo existente para implementar reglas ASR.
Vea: [Crear un plan de implementación para Windows](/windows/deployment/update/create-deployment-plan)

## <a name="additional-topics-in-this-deployment-collection"></a>Temas adicionales de esta colección de implementación

[Introducción a la implementación de reglas de ASR](attack-surface-reduction-rules-deployment.md)

[Fase 2: Probar](attack-surface-reduction-rules-deployment-phase-2.md)

[Fase 3: Implementar](attack-surface-reduction-rules-deployment-phase-3.md)

[Fase 4: Operar](attack-surface-reduction-rules-deployment-phase-4.md)
