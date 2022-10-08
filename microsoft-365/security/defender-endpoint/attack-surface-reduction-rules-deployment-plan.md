---
title: Planear la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)
description: Proporciona instrucciones para planear la implementación de reglas de reducción de la superficie expuesta a ataques (ASR).
keywords: Implementación de reglas de reducción de superficie expuesta a ataques, implementación de ASR de Microsoft Defender para punto de conexión (MDE), reglas de ASR de Defender, habilitación de reglas de asr, configuración de ASR, sistema de prevención de intrusiones de host, reglas de protección, reglas contra vulnerabilidades de seguridad, reglas contra vulnerabilidades de seguridad, reglas de prevención de infecciones, Microsoft Defender para punto de conexión, configurar reglas ASR
search.product: eADQiWindows 10XVcnh
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.topic: article
ms.collection:
- m365-security
- m365solution-asr-rules
- highpri
- tier1
ms.date: 1/18/2022
search.appverid: met150
ms.openlocfilehash: ecd5b5cc93d1068ce42ba4f7ca6b5a33748b2a18
ms.sourcegitcommit: 7828a1e78c3e6bd8d10289f1ad6c8b6769da0966
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2022
ms.locfileid: "68495087"
---
# <a name="plan-attack-surface-reduction-asr-rules-deployment"></a>Planear la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)

Antes de probar o habilitar las reglas de reducción de superficie expuesta a ataques (ASR) de Microsoft Defender para punto de conexión (MDE), debe planear cómo implementará la implementación. Un planeamiento cuidadoso no solo ayudará a probar y habilitar la implementación de reglas de ASR, sino que también será útil al configurar excepciones de reglas de ASR. Al planear probar o habilitar reglas de reducción de la superficie expuesta a ataques (ASR), es importante empezar con la unidad de negocio adecuada. Querrá empezar con un pequeño grupo de personas en una unidad de negocio específica. Puede identificar a algunos campeones de ASR dentro de una unidad de negocio determinada que pueden proporcionar un impacto real sobre las reglas de ASR y ayudarle a ajustar la implementación.

> :::image type="content" source="images/asr-rules-planning-steps.png" alt-text="Pasos de planeamiento de reglas de ASR. Preparación antes de probar las reglas ASR de Microsoft Defender para punto de conexión (MDE) o habilitar las reglas de ASR de MDE." lightbox="images/asr-rules-planning-steps.png":::

> [!IMPORTANT]
>
> Mientras pasa por el proceso de planeamiento, auditoría y habilitación de reglas asr, se recomienda habilitar las tres _reglas de protección estándar_ siguientes. Consulta [Reglas de reducción de superficie expuesta a ataques por tipo](attack-surface-reduction-rules-reference.md#attack-surface-reduction-rules-by-type) para obtener detalles importantes sobre los dos tipos de reglas de ASR.
>
> - [Bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows (lsass.exe)](attack-surface-reduction-rules-reference.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem)
> - [Bloquear el abuso de controladores firmados vulnerables explotados](attack-surface-reduction-rules-reference.md#block-abuse-of-exploited-vulnerable-signed-drivers)
> - [Bloquear la persistencia a través de la suscripción de eventos de Instrumental de administración de Windows (WMI)](attack-surface-reduction-rules-reference.md#block-persistence-through-wmi-event-subscription)
>
> Normalmente, puede habilitar las reglas de protección estándar con un impacto mínimo notable para el usuario final. Para obtener un método sencillo para habilitar las reglas de protección estándar, consulte: [Opción de protección estándar simplificada](attack-surface-reduction-rules-report.md#simplified-standard-protection-option).

## <a name="start-your-asr-rules-deployment-with-the-right-business-unit"></a>Inicio de la implementación de reglas de ASR con la unidad de negocio adecuada

La forma en que seleccione la unidad de negocio para implementar la implementación de reglas de ASR dependerá de factores como:

- Tamaño de la unidad de negocio
- Disponibilidad de los campeones de reglas de ASR  
- Distribución y uso de:
  - Software
  - Carpetas compartidas
  - Uso de scripts
  - Macros de Office
  - Otras entidades afectadas por las reglas de ASR

En función de sus necesidades empresariales, puede decidir incluir varias unidades de negocio para obtener un amplio muestreo de software, carpetas compartidas, scripts, macros, etc. Por el contrario, puede decidir limitar el ámbito de la primera implementación de reglas de ASR a una sola unidad de negocio y, a continuación, repetir todo el proceso de implementación de reglas de ASR a las otras unidades de negocio, de una en una.

## <a name="identify-asr-rules-champions"></a>Identificación de los campeones de reglas de ASR

Los campeones de reglas de ASR son miembros de su organización que le ayudarán con el lanzamiento inicial de reglas de ASR durante las fases preliminares de implementación y pruebas. Los campeones suelen ser empleados más expertos técnicamente y que no se ven afectados por interrupciones intermitentes del flujo de trabajo. La participación de los campeones continuará a lo largo de la expansión más amplia de la implementación de reglas de ASR en su organización. Los campeones de reglas de ASR serán los primeros en experimentar cada nivel del lanzamiento de reglas de ASR.

Es importante proporcionar un canal de comentarios y respuesta para que los expertos en reglas de ASR le alerten sobre las interrupciones del trabajo relacionadas con las reglas de ASR y reciban comunicaciones relacionadas con el lanzamiento de reglas de ASR.

## <a name="get-inventory-of-line-of-business-apps-and-understand-the-business-unit-processes"></a>Obtención del inventario de aplicaciones de línea de negocio y comprensión de los procesos de la unidad de negocio

Tener un conocimiento completo de las aplicaciones y los procesos por unidad de negocio que se usan en toda la organización es fundamental para una implementación correcta de reglas de ASR. Además, es imperativo que comprenda cómo se usan esas aplicaciones dentro de las distintas unidades de negocio de su organización.
Para empezar, debe obtener un inventario de las aplicaciones aprobadas para su uso en toda la organización. Puede usar herramientas como el centro de administración de Aplicaciones Microsoft 365 para ayudarle a realizar un inventario de aplicaciones de software. Consulte: [Introducción al inventario en el centro de administración de Aplicaciones Microsoft 365](/deployoffice/admincenter/inventory).

## <a name="define-reporting-and-response-asr-rules-team-roles-and-responsibilities"></a>Definición de roles y responsabilidades del equipo de reglas de ASR de informes y respuesta

La articulación clara de roles y responsabilidades de las personas responsables de supervisar y comunicar el estado y la actividad de las reglas de ASR es una actividad fundamental del mantenimiento de ASR. Por lo tanto, es importante determinar:

- La persona o el equipo responsable de recopilar informes
- Cómo y con quién se comparten los informes
- Cómo se aborda la escalación de amenazas recién identificadas o bloqueos no deseados causados por reglas de ASR

Entre los roles y responsabilidades típicos se incluyen:

- Administradores de TI: implemente reglas ASR y administre exclusiones. Trabaje con diferentes unidades de negocio en aplicaciones y procesos. Ensamblar y compartir informes con las partes interesadas
- Analista certificado del Centro de operaciones de seguridad (CSOC): responsable de invertir procesos bloqueados y de alta prioridad, para determinar que la amenaza es válida o no
- Director de seguridad de la información (CISO): responsable de la posición de seguridad general y el estado de la organización

## <a name="asr-rules-ring-deployment"></a>Implementación en anillo de reglas de ASR

Para grandes empresas, Microsoft recomienda implementar reglas ASR en "anillos". Los anillos son grupos de dispositivos que se representan visualmente como círculos concéntricos que irradian hacia afuera, como anillos de árbol no superpuestos. Cuando el anillo más interno se implementa correctamente, puede realizar la transición del siguiente anillo a la fase de prueba. La evaluación exhaustiva de las unidades de negocio, los campeones de reglas de ASR, las aplicaciones y los procesos es imprescindible para definir los anillos.
En la mayoría de los casos, la organización habrá diseñado anillos de implementación para implementaciones por fases de actualizaciones de Windows. Puede usar el diseño de anillo existente para implementar reglas ASR.
Consulte: [Creación de un plan de implementación para Windows](/windows/deployment/update/create-deployment-plan)

## <a name="additional-topics-in-this-deployment-collection"></a>Temas adicionales de esta colección de implementación

[Introducción a la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment.md)

[Probar las reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-test.md)

[Habilitar reglas de la reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-implement.md)

[Operacionar reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-operationalize.md)

[Referencia de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-reference.md)
