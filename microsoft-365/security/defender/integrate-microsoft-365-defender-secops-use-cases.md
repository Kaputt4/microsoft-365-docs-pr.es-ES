---
title: Paso 5. Desarrollar y probar casos de uso
description: Los conceptos básicos de desarrollo y pruebas de casos de uso al integrar Microsoft 365 Defender en las operaciones de seguridad.
keywords: incidentes, alertas, investigación, correlación, ataque, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque, secops, operaciones de seguridad, soc
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c4caee1bd0904cecd941789e891b93a378080eed
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483308"
---
# <a name="step-5-develop-and-test-use-cases"></a>Paso 5. Desarrollar y probar casos de uso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los métodos recomendados para implementar Microsoft 365 Defender en security operations center (SOC) dependerán del conjunto actual de herramientas, procesos y conjuntos de aptitudes del equipo de SOC. Mantener la ciberseguridad en todas las plataformas puede ser difícil debido a la gran cantidad de datos procedentes de docenas o no de cientos de orígenes de seguridad.

Las herramientas de seguridad están interrelacionadas. Activar una característica en una tecnología de seguridad o cambiar un proceso puede, a su vez, interrumpir otra. Por este motivo, Microsoft recomienda que el equipo de SOC formalice un método para definir y priorizar casos de uso. Los casos de uso ayudan a definir los requisitos y los procesos de prueba para las operaciones de SOC en varios equipos. Crea una metodología para capturar métricas con el fin de determinar si los roles adecuados y la combinación de tareas están alineados con el equipo adecuado con los conjuntos de aptitudes adecuados.

## <a name="develop-and-formalize-use-case-process"></a>Desarrollo y formalización del proceso de casos de uso

El SOC debe definir un estándar de alto nivel y un proceso para desarrollar casos de uso, que serían regulados por el equipo de supervisión de SOC. El equipo de supervisión de SOC debe trabajar con su empresa, TI, legal, RR. HH. y otros grupos para dar prioridad a los casos de uso del SOC que finalmente llegarán a los runbooks y cuadernos de estrategias del equipo de SOC. La prioridad de los casos de uso se basa en objetivos, como el cumplimiento o la privacidad.

Las actividades de supervisión de SOC relacionadas con el desarrollo de casos de uso incluyen:

- Requisitos
- Necesidades de personal o formación
- Licencias de software
- Contratación de proveedores
- Administración del plan
- Mantenimiento del registro de casos de uso
- Mantenimiento y actualización de plantillas

Para facilitar los procesos de creación del runbook y del cuaderno de estrategias, cree un árbol de decisión de casos de uso. En esta ilustración se muestra un ejemplo.

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png" alt-text="El proceso de decisión del caso de uso" lightbox="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png":::

Una vez definido y aprobado un estándar de caso de uso de alto nivel, el siguiente paso consiste en crear y probar un caso de uso real. En las secciones siguientes se usan escenarios de detección de amenazas y amenazas y vulnerabilidades como ejemplos.

## <a name="use-case-example-1-new-phishing-variant"></a>Ejemplo de caso de uso 1: Nueva variante de suplantación de identidad

El primer paso para crear un caso de uso es describir el flujo de trabajo mediante un panel de artículos. Este es un ejemplo de un panel de historias de alto nivel para una nueva notificación de vulnerabilidad de suplantación de identidad (phishing) a un equipo de Inteligencia sobre amenazas.

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png" alt-text="El flujo de trabajo de un caso de uso para una campaña contra la suplantación de identidad" lightbox="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png":::

### <a name="invoke-the-use-case-workflow-for-example-1"></a>Invocación del flujo de trabajo de casos de uso por ejemplo 1

Una vez aprobado el panel de artículos, el siguiente paso es invocar el flujo de trabajo de casos de uso. Este es un proceso de ejemplo para una campaña contra la suplantación de identidad (phishing).

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png" alt-text="Un flujo de trabajo detallado de casos de uso para una campaña contra la suplantación de identidad" lightbox="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png":::

## <a name="use-case-example-2-threat-and-vulnerability-scanning"></a>Ejemplo de caso de uso 2: Examen de amenazas y vulnerabilidades

Otro escenario en el que se podría usar un caso de uso es para el examen de amenazas y vulnerabilidades. En este ejemplo, el SOC requiere que las amenazas y vulnerabilidades se corrijan contra los recursos a través de procesos aprobados que incluyen el examen de los recursos.

Este es un guión gráfico de alto nivel de ejemplo para el Administración de vulnerabilidades de Microsoft Defender de recursos.

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png" alt-text="Un flujo de trabajo de caso de uso para Administración de amenazas y vulnerabilidades" lightbox="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png":::

### <a name="invoke-the-use-case-workflow-for-example-2"></a>Invocación del flujo de trabajo de casos de uso, por ejemplo 2

Este es un proceso de ejemplo para el examen de amenazas y vulnerabilidades.

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png" alt-text="Un flujo de trabajo detallado de casos de uso para Administración de amenazas y vulnerabilidades" lightbox="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png":::

### <a name="analyze-the-use-case-output-and-lessons-learned"></a>Análisis de la salida del caso de uso y las lecciones aprendidas

Una vez aprobado y probado un caso de uso, se deben identificar las brechas entre los equipos de seguridad, junto con las personas, los procesos y las tecnologías de Microsoft 365 Defender implicadas. Microsoft 365 Defender tecnologías deben analizarse para determinar si son capaces de lograr los resultados deseados. Se puede realizar un seguimiento de ellos a través de una lista de comprobación o una matriz.

Por ejemplo, en el ejemplo de escenario contra la suplantación de identidad (phishing), los equipos de SOC podrían haber realizado las detecciones en esta tabla.

|Equipo de SOC|Requisito|Personas cumplir los requisitos|Proceso para cumplir los requisitos|Tecnología pertinente|Brecha identificada|Registro de cambios de casos de uso|Exento (Y/N)|
|---|---|---|---|---|---|---|---|
|Equipo de inteligencia y análisis de amenazas|Los orígenes de datos alimentan correctamente los motores de inteligencia sobre amenazas.|Analista/ingeniero de Inteligencia sobre amenazas|Requisitos de fuente de distribución de datos establecidos, desencadenadores de inteligencia sobre amenazas de orígenes aprobados|Microsoft Defender for Identity, Microsoft Defender para punto de conexión|El equipo de Inteligencia sobre amenazas no usó el script de automatización para vincular Microsoft 365 Defender API con motores intel de amenazas|Adición de Microsoft 365 Defender como orígenes de datos a los motores de amenazas <p> Actualización del libro de ejecución de casos de uso|N|
|Equipo de supervisión|Los orígenes de datos alimentan correctamente los paneles de supervisión.|Analista de SOC de nivel 1,2: alertas de & de supervisión|Flujo de trabajo para informar de la puntuación segura del Centro de seguridad & cumplimiento|[Alertas en el Centro de cumplimiento de & de seguridad](/microsoft-365/security/office-365-security/alerts) <p> Supervisión de puntuación segura|No hay ningún mecanismo para que los analistas de SOC notifiquen una nueva detección de variantes de suplantación de identidad correcta para mejorar la puntuación de seguridad <p> [Visualización de informes de seguridad de correo electrónico en el portal de Microsoft 365 Defender](/microsoft-365/security/office-365-security/view-email-security-reports)|Adición de un proceso para realizar un seguimiento de la mejora de puntuación segura en flujos de trabajo de informes|N|
|Equipo de ingeniería y SecOps|Las actualizaciones del control de cambios se realizan en los runbooks de equipo de SOC.|Ingeniero de SOC de nivel 2|Procedimiento de notificación de control de cambios para runbooks de equipo de SOC|Cambios aprobados en dispositivos de seguridad|Los cambios en Microsoft 365 Defender conectividad a la tecnología de seguridad soc requieren aprobación|Agregar Microsoft Defender for Cloud Apps, Defender for Identity, Defender para punto de conexión, Security & Compliance Center a runbooks de SOC|v|

Además, los equipos de SOC podrían haber realizado las detecciones descritas en la tabla siguiente con respecto al escenario de Administración de vulnerabilidades de Defender descrito anteriormente:

|Equipo de SOC|Requisito|Personas cumplir los requisitos|Proceso para cumplir los requisitos|Tecnología pertinente|Brecha identificada|Registro de cambios de casos de uso|Exento (Y/N)|
|---|---|---|---|---|---|---|---|
|Supervisión de SOC|Todos los recursos conectados a redes aprobadas se identifican y clasifican|Supervisión de SOC, propietarios de BU, propietarios de aplicaciones, propietarios de recursos de TI, etc.|Sistema centralizado de administración de recursos para detectar y enumerar la categoría de recursos y los atributos en función del riesgo.|ServiceNow u otros recursos. <br><br>[Inventario de dispositivos de Microsoft 365](/microsoft-365/security/defender-endpoint/device-discovery)|Solo se ha descubierto el 70 % de los recursos. Microsoft 365 Defender seguimiento de corrección solo es efectivo para los recursos conocidos|Servicios de administración del ciclo de vida de activos maduros para garantizar que Microsoft 365 Defender tenga una cobertura del 100 %|N|
|Ingeniería & SecOps Teams|El alto impacto y las vulnerabilidades críticas en los recursos se corrigen según la directiva|Ingenieros de SecOps, analistas de SOC: Cumplimiento de vulnerabilidades &, ingeniería de seguridad|Proceso definido para clasificar vulnerabilidades críticas y de alto riesgo|[Paneles de Administración de vulnerabilidades de Microsoft Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)|Defender para punto de conexión ha identificado dispositivos de alerta alta y de alto impacto sin ningún plan de corrección o implementación de la actividad recomendada por Microsoft.|Agregue un flujo de trabajo para notificar a los propietarios de recursos cuando se requiera la actividad de corrección en un plazo de 30 días por directiva; Implemente un sistema de vales para notificar a los propietarios de recursos los pasos de corrección.|N|
|Supervisión de Teams|El estado de amenazas y vulnerabilidades se notifica a través del portal de intranet de la empresa|Analista de SOC de nivel 2|Informes generados automáticamente a partir de Microsoft 365 Defender que muestran el progreso de corrección de los recursos|[Alertas en el Centro de cumplimiento de & de seguridad](/microsoft-365/security/office-365-security/alerts) <p> Supervisión de puntuación segura|No se comunican vistas ni informes de panel a los propietarios de recursos con respecto al estado de amenaza y vulnerabilidad de los recursos.|Cree un script de automatización para rellenar el estado de la corrección de vulnerabilidad de recursos críticos y de alto riesgo para la organización.|N|

En estos casos de uso de ejemplo, las pruebas revelaron varias lagunas en los requisitos del equipo de SOC que se establecieron como líneas base para las responsabilidades de cada equipo. La lista de comprobación del caso de uso puede ser tan completa como sea necesario para asegurarse de que el equipo de SOC está preparado para la integración Microsoft 365 Defender con los requisitos de SOC nuevos o existentes. Dado que se trata de un proceso iterativo, el proceso de desarrollo de casos de uso y el contenido de salida del caso de uso servirán naturalmente para actualizar y madurar los runbooks del SOC con lecciones aprendidas.

## <a name="update-production-runbooks-and-playbooks"></a>Actualización de runbooks y cuadernos de estrategias de producción

Una vez que las pruebas de casos de uso se han corregido para todas las lagunas, las lecciones aprendidas y las métricas recopiladas en ellas se pueden incorporar en los runbooks de producción (procesos operativos) y cuadernos de estrategias del equipo de SOC (respuestas a incidentes y procedimientos de escalado).

El mantenimiento de los runbooks y cuadernos de estrategias del equipo de SOC se puede organizar de varias maneras. Cada equipo de SOC puede ser responsable de los suyos propios o puede haber una única versión centralizada para que todos los equipos compartan en un repositorio central. La administración de runbooks y cuadernos de estrategias para organizaciones individuales se basa en el tamaño, los conjuntos de aptitudes, los roles y la segregación de tareas. Una vez actualizado un runbook, debe seguir el proceso de actualización del cuaderno de estrategias.

## <a name="use-a-standard-framework-for-escalation"></a>Uso de un marco estándar para la escalación

Los cuadernos de estrategias son los pasos que los equipos de SOC necesitarán seguir cuando se produzca un evento real, en función de la integración y prueba correctas del caso de uso. Por lo tanto, es imperativo que el SOC siga un enfoque formalizado para la respuesta a incidentes, como el [Estándar de respuesta a incidentes de NIST](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) que se ha convertido en uno de los estándares líderes del sector para la respuesta a incidentes.

El proceso de respuesta a incidentes de cuatro pasos de NIST incluye cuatro fases:

1. Preparación
2. Detección y análisis
3. Contención, restablecimiento y recuperación
4. Actividad posterior al incidente

### <a name="example-tracking-preparation-phase-activity"></a>Ejemplo: Seguimiento de la actividad de la fase de preparación

Uno de los fundamentos básicos de un cuaderno de estrategias de escalación es asegurarse de que hay poca ambigüedad en cuanto a lo que se supone que cada equipo de SOC debe hacer antes, durante y después de un evento o incidente. Por lo tanto, es recomendable enumerar las instrucciones paso a paso.

Por ejemplo, la fase de preparación podría incluir una matriz if/then o XoR de tareas. En el caso del nuevo caso de uso de ejemplo de variante de suplantación de identidad (phishing), esta matriz podría tener este aspecto:

|¿Por qué se garantiza la escalación?|Paso siguiente|
|---|---|
|Alerta en supervisión de SOC clasificada como **crítica** desencadenada > **500/hora**|Vaya al Cuaderno de estrategias A, Sección 2, Actividad 5 (con un vínculo a la sección del cuaderno de estrategias)|
|Comercio electrónico informó de un posible ataque DDoS|Invocar cuaderno de estrategias B-Sección C, Actividad 19 (con un vínculo a la sección del cuaderno de estrategias)|
|El ejecutivo informó de un correo electrónico sospechoso como intento de suplantación de identidad (phishing)|Vaya al Cuaderno de estrategias 5, Sección 2, Actividad 5 (con un vínculo a la sección del cuaderno de estrategias)|

Después de ejecutar la fase de preparación, las organizaciones deben invocar las fases restantes tal como se describe en NIST:

- Detección y análisis
- Contención, restablecimiento y recuperación
- Actividad posterior al incidente

## <a name="next-step"></a>Paso siguiente

[Paso 6. Identificación de tareas de mantenimiento de SOC](integrate-microsoft-365-defender-secops-tasks.md)
