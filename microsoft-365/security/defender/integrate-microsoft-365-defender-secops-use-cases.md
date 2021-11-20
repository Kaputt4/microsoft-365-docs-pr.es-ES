---
title: Paso 5. Desarrollar y probar casos de uso
description: Los conceptos básicos de desarrollar y probar casos de uso al integrar Microsoft 365 Defender en las operaciones de seguridad.
keywords: incidentes, alertas, investigar, correlación, ataque, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque, secops, operaciones de seguridad, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 52579cbe5ff3a40e402a116368b607f2381062ce
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61122122"
---
# <a name="step-5-develop-and-test-use-cases"></a>Paso 5. Desarrollar y probar casos de uso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los métodos recomendados para implementar Microsoft 365 Defender en el Centro de operaciones de seguridad (SOC) dependerán del conjunto actual de herramientas, procesos y conjuntos de aptitudes del equipo soc. Mantener la higiene cibernética en todas las plataformas puede ser difícil debido a la gran cantidad de datos procedentes de decenas de orígenes de seguridad, si no cientos. 

Las herramientas de seguridad están interrelacionadas. Activar una característica en una tecnología de seguridad o cambiar un proceso puede, a su vez, interrumpir otra. Por este motivo, Microsoft recomienda que el equipo de SOC formalice un método para definir y priorizar los casos de uso. Los casos de uso ayudan a definir los requisitos y los procesos de prueba para las operaciones SOC en varios equipos. Crea una metodología para capturar métricas para determinar si los roles adecuados y la combinación de tareas están alineados con el equipo adecuado con los conjuntos de aptitudes adecuados. 

## <a name="develop-and-formalize-use-case-process"></a>Desarrollar y formalizar el proceso de caso de uso

El SOC debe definir un estándar de alto nivel y un proceso para desarrollar casos de uso, que estaría regulado por el equipo de supervisión del SOC. El equipo de supervisión de SOC debe trabajar con su empresa, TI, legales, recursos humanos y otros grupos para priorizar los casos de uso para el SOC que finalmente se abrirán paso en los runbooks y los libros de juegos del equipo de SOC. Los casos de prioridad de uso se basan en objetivos, como el cumplimiento o la privacidad.

Las actividades de supervisión de SOC relacionadas con el desarrollo de casos de uso incluyen: 

- Requisitos
- Necesidades de personal o formación
- Licencias de software
- Contratación de proveedores
- Plan de administración
- Mantenimiento del registro de casos de uso
- Mantenimiento y actualización de plantillas

Para facilitar los procesos de creación del runbook y del libro de juegos, cree un árbol de decisión de casos de uso. En esta figura se muestra un ejemplo.

:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png" alt-text="Proceso de decisión de caso de uso." lightbox="../../media/integrate-microsoft-365-defender-secops/use-case-decision-process.png":::

Una vez definido y aprobado un estándar de caso de uso de alto nivel, el siguiente paso es crear y probar un caso de uso real. En las secciones siguientes se usan escenarios de análisis de vulnerabilidades y amenazas y contra suplantación de identidad como ejemplos.

## <a name="use-case-example-1-new-phishing-variant"></a>Ejemplo de caso de uso 1: Nueva variante de suplantación de identidad

El primer paso para crear un caso de uso es describir el flujo de trabajo mediante un story board. Este es un ejemplo de un panel de artículos de alto nivel para una nueva notificación de vulnerabilidad de suplantación de identidad (phishing) a un equipo de inteligencia de amenazas.
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png" alt-text="Un ejemplo de flujo de trabajo de casos de uso para una campaña contra la suplantación de identidad." lightbox="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-phishing.png":::

### <a name="invoke-the-use-case-workflow-for-example-1"></a>Invocar el flujo de trabajo de casos de uso por ejemplo 1

Una vez aprobado el story board, el siguiente paso es invocar el flujo de trabajo de casos de uso. Este es un proceso de ejemplo para una campaña contra el phishing. 
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png" alt-text="Un ejemplo de flujo de trabajo de casos de uso detallado para una campaña contra la suplantación de identidad." lightbox="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-phishing.png":::

## <a name="use-case-example-2-threat-and-vulnerability-scanning"></a>Ejemplo de caso de uso 2: Análisis de amenazas y vulnerabilidades

Otro escenario en el que se podría usar un caso de uso es para el examen de amenazas y vulnerabilidades. En este ejemplo, el SOC requiere que se corrijan las amenazas y vulnerabilidades de los activos a través de procesos aprobados que incluyen el examen de activos. 

Este es un guión gráfico de alto nivel de ejemplo para el Administración de amenazas y vulnerabilidades de activos.
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png" alt-text="Un ejemplo de flujo de trabajo de casos de Administración de amenazas y vulnerabilidades." lightbox="../../media/integrate-microsoft-365-defender-secops/example-use-case-workflow-storyboard-tvm.png":::

### <a name="invoke-the-use-case-workflow-for-example-2"></a>Invocar el flujo de trabajo de casos de uso por ejemplo 2

Este es un proceso de ejemplo para el examen de amenazas y vulnerabilidades.
 
:::image type="content" source="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png" alt-text="Un ejemplo de flujo de trabajo de casos de uso detallado para Administración de amenazas y vulnerabilidades." lightbox="../../media/integrate-microsoft-365-defender-secops/example-detailed-use-case-workflow-tvm.png":::
 
### <a name="analyze-the-use-case-output-and-lessons-learned"></a>Analizar el resultado del caso de uso y las lecciones aprendidas

Una vez aprobado y probado un caso de uso, se deben identificar las diferencias entre los equipos de seguridad, junto con las personas, los procesos y las Microsoft 365 Defender tecnologías implicadas. Microsoft 365 Defender tecnologías deben analizarse para determinar si son capaces de lograr los resultados deseados. Estos se pueden realizar mediante una lista de comprobación o una matriz. 

Por ejemplo, en el ejemplo de escenario anti phishing, los equipos soc podrían haber realizado los descubrimientos en esta tabla.


| Equipo de SOC | Requisito | Personas para cumplir requisitos | Proceso para cumplir requisitos | Tecnología relevante | Gap identified | Usar registro de cambio de casos | Exempt (Y/N) |
|:-------|:-----|:-------|:-------|:-------|:-----|:-------|:-------|
| Equipo de inteligencia y análisis de amenazas | Los orígenes de datos están alimentando correctamente los motores de inteligencia de amenazas. | Analista/ingeniero de inteligencia de amenazas | Requisitos de fuente de datos establecidos, desencadenadores de inteligencia de amenazas de orígenes aprobados | Microsoft Defender para identity, Microsoft Defender para endpoint | El equipo de inteligencia de amenazas no usaba script de automatización para vincular Microsoft 365 Defender API con motores intel de amenazas | Agregar Microsoft 365 Defender como orígenes de datos a motores de amenazas <BR> <BR> Actualizar la libreta de casos de uso | N |
| Equipo de supervisión | Los orígenes de datos están alimentando correctamente los paneles de supervisión | Alertas de supervisión y supervisión de SO & C de nivel 1,2 | Flujo de trabajo para informar sobre la puntuación & seguridad del Centro de cumplimiento | [Alertas en el Centro de & seguridad](/microsoft-365/security/office-365-security/alerts)  <br><br> Supervisión de puntuación segura  | Ningún mecanismo para que los analistas de SOC informen sobre la detección correcta de nuevas variantes de suplantación de identidad (phishing) para mejorar la puntuación segura <br><br> [Informes en el Centro de & seguridad](/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)| Agregar un proceso para realizar un seguimiento de la mejora de puntuación segura en los flujos de trabajo de informes | N | 
| Equipo de Ingeniería y SecOps | Las actualizaciones de control de cambios se realizan en los runbooks de equipo soc | Ingeniero soc de nivel 2 | Procedimiento de notificación de control de cambios para runbooks de equipo SOC | Cambios aprobados en dispositivos de seguridad | Los cambios en Microsoft 365 Defender conectividad a la tecnología de seguridad SOC requieren aprobación | Agregar Microsoft Defender para aplicaciones en la nube, Defender for Identity, Defender para endpoint, Security & Compliance Center a runbooks soc | v |
|||||||||

Además, los equipos SOC podrían haber realizado los descubrimientos descritos en la tabla siguiente con respecto al escenario Administración de amenazas y vulnerabilidades descrito anteriormente:

| Equipo de SOC | Requisito | Personas para cumplir requisitos | Proceso para cumplir requisitos | Tecnología relevante | Gap identified | Usar registro de cambio de casos | Exempt (Y/N) |
|:-------|:-----|:-------|:-------|:-------|:-----|:-------|:-------|
| Supervisión de SOC | Todos los activos conectados a redes aprobadas se identifican y clasifican | Supervisión de SOC, propietarios de BU, propietarios de aplicaciones, propietarios de activos de IT, etc. | Sistema de administración de activos centralizado para detectar y enumerar la categoría de activos y los atributos en función del riesgo. | ServiceNow u otros activos. <br><br>[Microsoft 365 inventario de dispositivos](/security/defender-endpoint/device-discovery) | Solo se ha detectado el 70 % de los activos. Microsoft 365 Defender de corrección solo efectivo para activos conocidos | Servicios de administración del ciclo de vida de activos maduros para Microsoft 365 Defender una cobertura del 100 % | N |
| Ingeniería & SecOps Teams | El alto impacto y las vulnerabilidades críticas en los activos se corrigen según la directiva | Ingenieros de SecOps, analistas de SOC: Vulnerabilidad & cumplimiento, Ingeniería de seguridad | Proceso definido para categorizar vulnerabilidades críticas y de alto riesgo | [Paneles de administración de amenazas y vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Defender for Endpoint ha identificado dispositivos de alto impacto y alerta alta sin plan de corrección ni implementación de la actividad recomendada por Microsoft | Agregar un flujo de trabajo para notificar a los propietarios de activos cuando se requiera una actividad de corrección en un plazo de 30 días por directiva; Implementar un sistema de vales para notificar a los propietarios de activos los pasos de corrección. | N |
| Supervisión Teams | El estado de amenaza y vulnerabilidad se notifica a través del portal de intranet de la empresa | Analista de SOC de nivel 2 | Informes generados automáticamente desde Microsoft 365 Defender que muestran el progreso de corrección de los activos | [Alertas en el Centro de & seguridad](/microsoft-365/security/office-365-security/alerts) <br><br> Supervisión de puntuación segura | No se comunican vistas ni informes de panel a los propietarios de activos sobre la amenaza y el estado de vulnerabilidad de los activos. | Cree un script de automatización para rellenar el estado de corrección de vulnerabilidad de activos críticos y de alto riesgo para la organización. | N |
|||||||||

En estos casos de uso de ejemplo, las pruebas revelaron varias diferencias en los requisitos del equipo SOC que se establecieron como líneas base para las responsabilidades de cada equipo. La lista de comprobación de casos de uso puede ser tan completa como sea necesario para garantizar que el equipo de SOC esté preparado para la integración Microsoft 365 Defender con los requisitos de SOC nuevos o existentes. Dado que se trata de un proceso iterativo, el proceso de desarrollo de casos de uso y el contenido de salida de casos de uso servirán de forma natural para actualizar y madurar los runbooks del SOC con las lecciones aprendidas.

## <a name="update-production-runbooks-and-playbooks"></a>Actualizar runbooks de producción y playbooks

Una vez que se hayan corregido todas las diferencias en las pruebas de casos de uso, las lecciones aprendidas y las métricas recopiladas en ellas se pueden incorporar a los runbooks de producción (procesos operativos) y a los libros de reproducción (respuestas a incidentes y procedimientos de escalación). 

El mantenimiento de los runbooks y los libros de juegos del equipo SOC se puede organizar de varias maneras. Cada equipo SOC puede ser responsable de los suyos propios o puede haber una única versión centralizada para que todos los equipos compartan en un repositorio central. La administración de runbooks y libros de juegos para organizaciones individuales se basa en el tamaño, los conjuntos de aptitudes, los roles y la segregación de tareas. Una vez que se ha actualizado un runbook, debe seguirse el proceso de actualización del libro de reproducción. 

## <a name="use-a-standard-framework-for-escalation"></a>Usar un marco estándar para la escalación

Los libros de reproducción son los pasos que los equipos SOC tendrán que seguir cuando se produzca un evento real, en función de la integración correcta y la prueba del caso de uso. Por lo tanto, es imperativo que el SOC siga un enfoque formalizado para la respuesta a incidentes, como el Estándar de respuesta a incidentes [nist](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) que se ha convertido en uno de los estándares líderes del sector para la respuesta a incidentes.

El proceso de respuesta a incidentes de cuatro pasos de NIST incluye cuatro fases:

1.  Preparación
2.  Detección y análisis
3.  Contención, restablecimiento y recuperación
4.  Actividad posterior al incidente

### <a name="example-tracking-preparation-phase-activity"></a>Ejemplo: Seguimiento de la actividad de fase de preparación

Uno de los fundamentos básicos de un libro de juegos de escalación es asegurarse de que hay poca ambigüedad en cuanto a lo que se supone que debe hacer cada equipo de SOC antes, durante y después de un evento o incidente. Por lo tanto, es una buena práctica enumerar instrucciones paso a paso. 

Por ejemplo, la fase de preparación podría incluir una matriz if/then o XoR de tareas. En el caso del caso de uso de la nueva variante de suplantación de identidad, esta matriz podría tener este aspecto:

| ¿Por qué se garantiza la escalación? | Paso siguiente |
|:-------|:-----|
| Alerta en la supervisión SOC clasificada como **desencadenada** crítica > **500/hora** | Vaya a Playbook A, Section 2, Activity 5 (con un vínculo a la sección playbook) |
| eCommerce reported potential DDoS attack | Invocar Playbook B-Section C, Actividad 19 (con un vínculo a la sección del libro de reproducción) |
| El ejecutivo informó de un correo electrónico sospechoso como intento de suplantación de identidad | Vaya a Playbook 5, Section 2, Activity 5 (con un vínculo a la sección de playbook) |
|||

Después de ejecutar la fase de preparación, las organizaciones deben invocar las fases restantes como se describe en NIST:

- Detección y análisis
- Contención, restablecimiento y recuperación
- Actividad posterior al incidente 

## <a name="next-step"></a>Paso siguiente

[Paso 6. Identificar tareas de mantenimiento soc](integrate-microsoft-365-defender-secops-tasks.md)
