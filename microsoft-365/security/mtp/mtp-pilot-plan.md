---
title: Planeación del proyecto piloto de Microsoft Threat Protection
description: Planifique el proyecto piloto de Microsoft Threat Protection con las partes interesadas para administrar las expectativas y garantizar un resultado correcto.
keywords: Microsoft Threat Protection Pilot, plan Pilot proyecto de protección contra amenazas de Microsoft, evaluación de la protección contra amenazas de Microsoft en producción, Microsoft Threat Protection Pilot Project, Cyber Security, prevención persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: e62b4ec0ee6c9d05321accf269406e8127019f5b
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418114"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a>Planeación del proyecto piloto de Microsoft Threat Protection 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Planear el proyecto piloto de Microsoft Threat Protection" />
      <br/>Planear</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparar el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection" />
      <br/>Preparación</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Ejecutar las simulaciones de ataque de la protección contra amenazas de Microsoft" />
     <br/>Simular ataque</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Cierre y resuma el piloto de Microsoft Threat Protection" />
     <br/>Cerrar y resumir</a><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

Actualmente está en la fase de planeación.

Para asegurarse de que el proyecto piloto es un éxito, es esencial que se planee minuciosamente y obtenga aprobaciones de las partes interesadas desde el principio. Los elementos de planeación incluyen el ámbito de identificación, los casos de uso, los requisitos y los criterios de éxito.

En esta guía se explica cómo planear el proyecto piloto. 

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones piloto de la forma más parecida posible.


## <a name="scope"></a>Ámbito

El ámbito del proyecto piloto determinará la amplitud de la prueba, en función de su entorno y de métodos de prueba aceptables. Estos son algunos de los ámbitos de ejemplo que se deben tener en cuenta:
- Entorno de desarrollo o prueba que incluye extremos, servidores y controladores de dominio.
- Entorno de producción con Microsoft 365, Azure, servicios de Active Directory, extremos y servidores

>[!NOTE]
>Si aún no dispone de licencias completas, puede obtener licencias de prueba para [evaluar Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) : planear, preparar, instalar, configurar y ejecutar el proyecto piloto. Las partes interesadas desempeñarán un papel importante en ayudar a facilitar el proceso desde el principio hasta el final.

Los tipos de sistemas operativos que se van a evaluar también deben definirse en función de la estructura organizativa. Esto puede incluir lo siguiente: [extremos Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [servidores Linux](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [puntos de conexión windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Casos de uso

Los casos de uso representan instrucciones sobre cómo la herramienta que se está probando va a ser consumida por los usuarios previstos. Se pueden formular como casos de usuario desde el punto de vista de un rol en particular, como un analista de SOC. Por ejemplo:
- Como Analista de SOC, necesito ver, correlacionar, evaluar y administrar alertas y eventos a través de dispositivos, usuarios y buzones de correo en mi red. [Administración de incidentes]
- Como Analista de SOC, debo tener la herramienta y el proceso para investigar y responder automáticamente a eventos malintencionados en mi red. [Auto IR]
- Como Analista de SOC, debo buscar datos de mi entorno para encontrar amenazas conocidas y potenciales, así como actividades sospechosas. [Caza avanzado]

Tenga en cuenta que estos casos de uso deben crearse dentro de los parámetros del ámbito definido. Si, por ejemplo, el ámbito de las pruebas no incluye una evaluación de herramientas como Microsoft Cloud App Security, use casos que dependan de esto como no se debe crear un origen de datos.

## <a name="requirements"></a>Requirements

En la lista de casos de uso, puede empezar a crear requisitos. Los requisitos incluyen características que una herramienta debe tener para satisfacer los casos de uso. Estos requisitos pueden dividirse en categorías como la configuración y el mantenimiento, la compatibilidad con las integraciones y los requisitos específicos de características, como la capacidad de búsqueda y la capacidad de crear alertas personalizadas.

## <a name="test-plan"></a>Plan de pruebas

Según los requisitos, los distintos métodos de prueba pueden ser apropiados. Por ejemplo, si el requisito es evaluar la eficacia de la corrección automatizada, el plan de pruebas debe incluir pasos para generar los comportamientos que activarían una acción de corrección automatizada dentro de la protección contra amenazas de Microsoft. Si el requisito es detectar un comportamiento o ataque en particular, la prueba puede implicar más pasos. El punto es disponer de un plan para realizar pruebas con precisión de los requisitos.

## <a name="success-criteria"></a>Criterios de éxito

Los criterios de éxito son en última instancia la barra que se debe medir con respecto a lo que se está probando. Tanto si va a probar la protección contra amenazas de Microsoft (o cualquier otra tecnología en la materia) con otras herramientas como si por sí misma, debe haber algunos criterios cuantificables para determinar el valor que proporciona la herramienta. Según el ámbito, los requisitos y el plan de pruebas, los criterios de éxito determinarán cómo puntuar la prueba. Debe ser inferior a pass o Fail y más de una puntuación ponderada según sus necesidades. Por ejemplo, para que funcione correctamente, es posible que una herramienta necesite puntuar por encima del 80% en determinadas áreas críticas que identifique.

## <a name="scorecard"></a>Puntua

Una forma de llevar a cabo juntos todos los elementos del plan puede ser crear un cuadro de mandos. Vea un cuadro de mandos de muestra a continuación:

| Caso de uso | Requirements | Requisitos de configuración | Plan de pruebas | Resultado previsto | Estado de la prueba | Puntuación | Notas |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Administración de incidentes|-Protección contra amenazas de Microsoft </br></br>-ATP de Azure </br></br>-ATP de Microsoft defender </br></br>-Microsoft Cloud App Security (opcional)|Vea los [requisitos previos](https://aka.ms/mtp-trial-lab) para la preparación, configuración y configuración para obtener más información. |[Simular ataque](mtp-pilot-simulate.md) <br></br>[Investigar el incidente](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |Los investigadores pueden comprender el alcance y el impacto del incidente y administrar el incidente.||||
|AutoIR|-Protección contra amenazas de Microsoft </br></br>-ATP de Azure </br></br>-ATP de Microsoft defender |Vea los [requisitos previos](https://aka.ms/mtp-trial-lab) para la preparación, configuración y configuración para obtener más información. <br>Habilitar AutoIR  |[Simular ataque](mtp-pilot-simulate.md) <br></br>[Investigación automatizada](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |La protección contra amenazas de Microsoft corrige automáticamente las alertas y los incidentes||||
|Búsqueda avanzada|-Protección contra amenazas de Microsoft </br></br>-ATP de Microsoft defender </br></br>-Office 365 ATP   |Vea los [requisitos previos](https://aka.ms/mtp-trial-lab) para la preparación, configuración y configuración para obtener más información.|[Escenario de caza avanzado](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |Los investigadores pueden encontrar datos a través de la búsqueda avanzada, dinamizar las entidades afectadas y crear detecciones personalizadas.||||



## <a name="next-step"></a>Paso siguiente
|![Fase de preparación](../../media/mtp/prep.png) <br>[Fase de preparación](prepare-mtpeval.md) | Preparar el entorno piloto de Microsoft Threat Protection
|:-------|:-----|
