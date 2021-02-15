---
title: Planeación del proyecto piloto de Microsoft 365 Defender
description: Planee su proyecto piloto de Microsoft 365 Defender con las partes interesadas para administrar las expectativas y garantizar un resultado correcto.
keywords: Piloto de Protección contra amenazas de Microsoft, plan piloto de Protección contra amenazas de Microsoft, evaluar protección contra amenazas de Microsoft en producción, proyecto piloto de Protección contra amenazas de Microsoft, seguridad cibernética, amenaza persistente avanzada, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizada, búsqueda avanzada
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8037b71fc41fb7fb0bdbfc829bad2ece1de6849b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930179"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Planeación del proyecto piloto de Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

|![Planificación](../../media/phase-diagrams/1-planning.png)<br/>Planificación|[![Preparación](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[Preparación](prepare-mtpeval.md) | [![Simular ataque](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[Simular ataque](mtp-pilot-simulate.md) | [![Cerrar y resumir](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[Cerrar y resumir](mtp-pilot-close.md)|
|--|--|--|--|
|*¡Estás aquí!*| | | |

Actualmente se encuentra en la fase de planeación.

Para asegurarse de que el proyecto piloto sea un éxito, es esencial planear exhaustivamente y obtener las aprobaciones de las partes interesadas al principio. Entre los elementos de planeación se incluyen la identificación del ámbito, los casos de uso, los requisitos y los criterios de éxito.

Esta guía le guiará a través de cómo planear el proyecto piloto. 

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones piloto lo más cerca posible.


## <a name="scope"></a>Ámbito

El ámbito del piloto determinará la amplitud de la prueba, en función de su entorno y de los métodos de prueba aceptables. Estos son algunos ámbitos de ejemplo que se deben tener en cuenta:
- Entorno de desarrollo o prueba que incluye puntos de conexión, servidores y controladores de dominio.
- Entorno de producción con Microsoft 365, Azure, servicios de Active Directory, puntos de conexión y servidores

>[!NOTE]
>Si aún no tiene las licencias completa, puede obtener licencias de prueba para evaluar [Microsoft 365 Defender:](https://aka.ms/mtp-trial-lab) planear, preparar, configurar, configurar y ejecutar el proyecto piloto. Las partes interesadas desempeñarán un papel importante a la hora de facilitar el proceso de principio a fin.

Los tipos de sistemas operativos que se evaluarán también deben definirse en función de la estructura organizativa. Esto puede incluir lo siguiente: puntos de [conexión de Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), servidores [Linux](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), puntos de conexión de [Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), Windows Server [2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Casos de uso

Los casos de uso representan instrucciones de cómo la herramienta que se está probando está pensada para que la usen sus usuarios previstos. Se pueden formular como casos de usuario desde el punto de vista de un rol en particular, como un analista de SOC. Por ejemplo:
- Como analista de SOC, necesito ver, correlacionar, evaluar y administrar alertas y eventos en dispositivos, usuarios y buzones de mi red. [Administración de incidentes]
- Como analista de SOC, necesito tener la herramienta y el proceso para investigar y responder automáticamente a eventos malintencionados en mi red. [IR automática]
- Como analista de SOC, debo buscar datos de mi entorno para encontrar amenazas conocidas y potenciales, y actividades sospechosas. [Búsqueda avanzada]

Tenga en cuenta que estos casos de uso deben crearse dentro de los parámetros del ámbito definido. Si, por ejemplo, el ámbito de las pruebas no incluye una evaluación de herramientas como Microsoft Cloud App Security, no se deben crear casos que se basen en esto como origen de datos.

## <a name="requirements"></a>Requirements

En la lista de casos de uso, puede empezar a crear requisitos. Entre los requisitos se incluyen las características que debe tener una herramienta para satisfacer los casos de uso. Estos requisitos se pueden dividir en categorías como configuración y mantenimiento, compatibilidad con integraciones y requisitos específicos de características, como la capacidad de búsqueda y la capacidad de crear alertas personalizadas.

## <a name="test-plan"></a>Plan de pruebas

Según los requisitos, pueden ser adecuados distintos métodos de prueba. Por ejemplo, si el requisito es evaluar la eficacia de la corrección automatizada, el plan de prueba debe incluir pasos para generar los comportamientos que desencadenarían una acción de corrección automatizada en Microsoft 365 Defender. Si el requisito es detectar un comportamiento o ataque en particular, la prueba puede implicar más pasos. El punto es tener un plan para probar con precisión los requisitos.

## <a name="success-criteria"></a>Criterios de éxito

Los criterios de éxito son, en última instancia, la barra establecida para medir con respecto a lo que se está probando. Tanto si está probando Microsoft 365 Defender (o cualquier otra tecnología en ese caso) con otras herramientas o por sí mismo, debe haber algunos criterios cuantificables para determinar el valor que proporciona la herramienta. En función del ámbito, los requisitos y el plan de pruebas, los criterios de éxito determinarán cómo puntuar la prueba. Esto debería ser menos de un pase o un error y más de una puntuación ponderada en función de tus necesidades. Por ejemplo, para ser correcta, es posible que una herramienta deba puntuar por encima del 80 % en determinadas áreas críticas que identifique.

## <a name="scorecard"></a>Cuadro de mandos

Una forma de reunir todos los elementos de su plan puede ser crear un cuadro de mandos. Consulta un cuadro de mandos de ejemplo a continuación:

| Caso de uso | Requirements | Requisitos de configuración | Plan de pruebas | Resultado previsto | Estado de la prueba | Puntuación | Notas |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Administración de incidencias|- Microsoft 365 Defender  </br></br>- Microsoft Defender para identidad </br></br>- Microsoft Defender para punto de conexión </br></br>- Microsoft Cloud App Security (opcional)|Consulte los [requisitos previos](https://aka.ms/mtp-trial-lab) para la preparación, la configuración y la configuración para obtener más información |[Simular ataque](mtp-pilot-simulate.md) <br></br>[Investigar el incidente](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |Los investigadores pueden comprender el alcance y el impacto del incidente y administrar el incidente||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender para identidad </br></br>- Microsoft Defender para punto de conexión |Consulte los [requisitos previos](https://aka.ms/mtp-trial-lab) para la preparación, la configuración y la configuración para obtener más información <br>Habilitar AutoIR  |[Simular ataque](mtp-pilot-simulate.md) <br></br>[Investigación automatizada](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#automated-investigation-and-remediation) |Microsoft 365 Defender corrige automáticamente las alertas e incidentes||||
|Búsqueda avanzada|- Microsoft 365 Defender </br></br>- Microsoft Defender para punto de conexión </br></br>-Microsoft Defender para Office 365 |Consulte los [requisitos previos](https://aka.ms/mtp-trial-lab) para la preparación, la configuración y la configuración para obtener más información|[Escenario de búsqueda avanzada](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#advanced-hunting-scenario) |Los investigadores pueden encontrar datos a través de la búsqueda avanzada, el control dinámico a las entidades afectadas y la creación de detecciones personalizadas||||



## <a name="next-step"></a>Paso siguiente
|![Fase de preparación](../../media/mtp/prep.png) <br>[Fase de preparación](prepare-mtpeval.md) | Preparar el entorno piloto de Microsoft 365 Defender
|:-------|:-----|
