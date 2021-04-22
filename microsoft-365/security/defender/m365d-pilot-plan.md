---
title: Planeación del proyecto piloto de Microsoft 365 Defender
description: Planee su proyecto piloto de Microsoft 365 Defender con las partes interesadas para administrar las expectativas y garantizar un resultado correcto.
keywords: Piloto de Microsoft 365 Defender, proyecto piloto de Microsoft 365 Defender, evaluación de Microsoft 365 Defender en producción, proyecto piloto de Microsoft 365 Defender, ciberseguridad, amenaza persistente avanzada, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 98f0c91a51cc2b73cc26e6fb53143a417a7a147e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932552"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Planeación del proyecto piloto de Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

|![Planificación](../../media/phase-diagrams/1-planning.png)<br/>Planificación|[![Preparación](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[Preparación](prepare-m365d-eval.md) | [![Simular ataque](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[Simular ataque](m365d-pilot-simulate.md) | [![Cerrar y resumir](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[Cerrar y resumir](m365d-pilot-close.md)|
|--|--|--|--|
|*¡Estás aquí!*| | | |

Actualmente está en la fase de planeación.

Para asegurarse de que el proyecto piloto es un éxito, es esencial planear exhaustivamente y obtener aprobaciones de las partes interesadas al principio. Los elementos de planeación incluyen identificar el ámbito, los casos de uso, los requisitos y los criterios de éxito.

Esta guía le guiará a través de cómo planear el proyecto piloto. 

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones piloto lo más cerca posible.


## <a name="scope"></a>Ámbito

El ámbito del piloto determinará la amplitud de la prueba, en función del entorno y de los métodos de prueba aceptables. Estos son algunos ámbitos de ejemplo a tener en cuenta:
- Entorno de desarrollo o prueba que incluye puntos de conexión, servidores, controladores de dominio.
- Entorno de producción con Microsoft 365, Azure, servicios de Active Directory, puntos de conexión y servidores

>[!NOTE]
>Si aún no tiene las licencias completa, puede obtener licencias de prueba para evaluar [Microsoft 365 Defender:](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) planee, prepare, configure, configure y ejecute el proyecto piloto. Las partes interesadas desempeñarán un papel importante en ayudar a facilitar el proceso de principio a fin.

Los tipos de sistemas operativos que se deben evaluar también deben definirse en función de la composición de la organización. Esto puede incluir lo siguiente: [puntos de conexión de Mac](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), Servidores [Linux](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), puntos de conexión de [Windows 10](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Casos de uso

Los casos de uso representan instrucciones de cómo la herramienta que se está probando está destinada a ser consumida por los usuarios previstos. Se pueden formular como historias de usuario desde el punto de vista de una persona determinada, como un analista de SOC. Por ejemplo:
- Como analista de SOC, necesito ver, correlacionar, evaluar y administrar alertas y eventos en dispositivos, usuarios y buzones de mi red. [Administración de incidentes]
- Como analista de SOC, debo tener la herramienta y el proceso para investigar y responder automáticamente a eventos malintencionados en mi red. [Ir automático]
- Como analista de SOC, debo buscar datos de mi entorno para encontrar amenazas conocidas y potenciales, y actividades sospechosas. [Búsqueda avanzada]

Tenga en cuenta que estos casos de uso deben crearse dentro de los parámetros del ámbito definido. Si, por ejemplo, el ámbito de las pruebas no incluye una evaluación de herramientas como Microsoft Cloud App Security, no se deben crear casos que se basen en esto como origen de datos.

## <a name="requirements"></a>Requisitos

En la lista de casos de uso, puede empezar a crear requisitos. Entre los requisitos se incluyen las características que una herramienta debe tener para satisfacer los casos de uso. Estos requisitos se pueden dividir en categorías como configuración y mantenimiento, compatibilidad con integraciones y requisitos específicos de características, como la capacidad de búsqueda y la capacidad de crear alertas personalizadas.

## <a name="test-plan"></a>Plan de pruebas

Según los requisitos, pueden ser apropiados distintos métodos de prueba. Por ejemplo, si el requisito es evaluar la eficacia de la corrección automatizada, el plan de prueba debe incluir pasos para generar los comportamientos que desencadenarían una acción de corrección automatizada en Microsoft 365 Defender. Si el requisito es detectar un comportamiento o ataque en particular, la prueba puede implicar más pasos. El punto es tener un plan en marcha para probar con precisión sus requisitos.

## <a name="success-criteria"></a>Criterios de éxito

Los criterios de éxito son, en última instancia, la barra establecida para medir con respecto a lo que está probando. Tanto si está probando Microsoft 365 Defender (o cualquier otra tecnología en ese caso) con otras herramientas o por sí mismo, debe haber algunos criterios cuantificables para determinar el valor que proporciona la herramienta. En función del ámbito, los requisitos y el plan de pruebas, los criterios de éxito determinarán cómo puntuar la prueba. Esto debe ser menos de un pase o error y más de una puntuación ponderada en función de sus necesidades. Por ejemplo, para ser correcta, es posible que una herramienta necesite obtener una puntuación superior al 80 % en determinadas áreas críticas que identifique.

## <a name="scorecard"></a>Cuadro de mandos

Una forma de unir todos los elementos del plan puede ser crear un cuadro de mandos. Vea un cuadro de mandos de ejemplo a continuación:

| Caso de uso | Requisitos | Requisitos de configuración | Plan de pruebas | Resultado previsto | Estado de la prueba | Puntuación | Notas |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Administración de incidencias|- Microsoft 365 Defender  </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender para endpoint </br></br>- Microsoft Cloud App Security (opcional)|Vea los [requisitos previos](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) para la preparación, la configuración y la configuración para obtener más información |[Simular ataque](m365d-pilot-simulate.md) <br></br>[Investigar el incidente](./m365d-pilot-simulate.md#investigate-an-incident) |Los investigadores pueden comprender el alcance y el impacto del incidente y administrar el incidente||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender para endpoint |Vea los [requisitos previos](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) para la preparación, la configuración y la configuración para obtener más información <br>Habilitar AutoIR  |[Simular ataque](m365d-pilot-simulate.md) <br></br>[Investigación automatizada](m365d-pilot-simulate.md#automated-investigation-and-remediation) |Microsoft 365 Defender corrige automáticamente las alertas e incidentes||||
|Búsqueda avanzada|- Microsoft 365 Defender </br></br>- Microsoft Defender para endpoint </br></br>-Microsoft Defender para Office 365 |Vea los [requisitos previos](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) para la preparación, la configuración y la configuración para obtener más información|[Escenario de búsqueda avanzada](./m365d-pilot-simulate.md#advanced-hunting-scenario) |Los investigadores pueden encontrar datos a través de búsquedas avanzadas, pivotando en entidades afectadas y creando detecciones personalizadas||||



## <a name="next-step"></a>Paso siguiente
|![Fase de preparación](../../media/mtp/prep.png) <br>[Fase de preparación](prepare-m365d-eval.md) | Preparar el entorno piloto de Microsoft 365 Defender
|:-------|:-----|
