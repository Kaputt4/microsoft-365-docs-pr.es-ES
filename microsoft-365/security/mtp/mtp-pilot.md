---
title: Ejecutar el proyecto piloto de Microsoft Threat Protection
description: Ejecute el proyecto piloto de Microsoft Threat Protection en producción para determinar de forma eficaz las ventajas y la adopción de la protección contra amenazas de Microsoft (MTP).
keywords: Microsoft Threat Protection Pilot, ejecute piloto proyecto de Microsoft Threat Protection, evaluación de la protección contra amenazas de Microsoft en producción, Microsoft Threat Protection Pilot Project, Cyber Security, prevención persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: f49f1afe5461a4f2eff0a3049f1d14d1892f70ce
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477031"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a>Ejecutar el proyecto piloto de Microsoft Threat Protection 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

Para determinar con eficacia el beneficio y la adopción de la protección contra amenazas de Microsoft (MTP), puede ejecutar un proyecto piloto. Antes de habilitar la protección contra amenazas de Microsoft en el entorno de producción e iniciar los casos de uso, es mejor planear la determinación de las tareas que se deben realizar para el proyecto piloto y establecer los criterios de éxito. 


## <a name="how-to-use-this-pilot-playbook"></a>Cómo usar esta guía del piloto

En esta guía se proporciona información general sobre la protección contra amenazas de Microsoft e instrucciones paso a paso sobre cómo configurar el proyecto piloto. 

La protección contra amenazas de Microsoft es un conjunto de aplicaciones de defensa de la empresa, antes y después de la violación, que coordina de forma nativa la protección, la detección, la prevención, la investigación y la respuesta en puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados. Lo hace combinando y orquestando las siguientes capacidades en una sola solución de seguridad:
  - Microsoft defender para extremo, el nuevo nombre para la protección contra amenazas avanzada de Microsoft defender (puntos de conexión)
  - Microsoft defender para Office 365, el nuevo nombre para Office 365 ATP (correo electrónico) 
  - Microsoft defender para identidad, el nuevo nombre de ATP (identidad) de Azure 
  - Microsoft Cloud App Security (aplicaciones)

![Solución de protección contra amenazas of_Microsoft de imágenes para los usuarios, la protección contra amenazas avanzada de Azure, para extremos protección contra amenazas avanzada de Microsoft defender, para aplicaciones en la nube, seguridad de aplicación en la nube de Microsoft y para datos, protección contra amenazas avanzada de Office 365  ](../../media/mtp/m365pillars.png)

Con la solución integrada de protección contra amenazas de Microsoft, los profesionales de seguridad pueden combinar las señales de amenaza que la protección contra amenazas avanzada de Microsoft defender, Office 365 ATP, Azure ATP y la seguridad de aplicaciones en la nube de Microsoft reciben, y determinar el ámbito completo y el impacto de la amenaza, cómo se ha entrado en el entorno, lo que se ve afectado y cómo afecta actualmente a la Microsoft Threat Protection realiza acciones automáticas para impedir o detener el ataque y Autocorregir los buzones de correo, los extremos y las identidades de usuario afectados. Consulte [información general de Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) para obtener más información.

![Fases de la ejecución de un programa piloto de Microsoft Threat Protection](../../media/pilotphases.png)

La siguiente escala de tiempo de ejemplo varía en función de la necesidad de disponer de los recursos adecuados en el entorno. Es posible que algunas detecciones y flujos de trabajo necesiten más tiempo de aprendizaje que los otros.

![Línea de tiempo de ejemplo para ejecutar una prueba piloto de Microsoft Threat Protection](../../media/pilotimeline.png)

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones piloto de la forma más parecida posible.


### <a name="pilot-playbook-phases"></a>Fases de la guía piloto 

Hay cuatro fases para ejecutar un piloto de Microsoft Threat Protection:

|Fase | Descripción | 
|:-------|:-----|
| ![Planificación](../../media/mtp/plan.png)<br>[Planificación](mtp-pilot-plan.md)| Obtenga información sobre lo que debe tener en cuenta antes de ejecutar el proyecto piloto de Microsoft Threat Protection: <br><br>-Scope <br> Casos de uso de <br>- Requisitos <br>-Plan de pruebas <br> -Criterios de éxito <br> -Cuadro de mandos 
| ![Declaración](../../media/mtp/prep.png) <br>[Declaración](mtp-evaluation.md)|  Obtenga acceso al centro de seguridad de Microsoft 365 para configurar su entorno piloto de Microsoft Threat Protection. Se le guiará a:<br><br>-Identificar las partes interesadas y buscar la firma para el proyecto piloto <br> Consideraciones del entorno <br>Acceso a <br>-Instalación de Azure Active Directory <br> -Orden de configuración <br> -Inscríbase en la versión de prueba de Microsoft 365 E5 <br> -Configurar dominio <br>-Asignar licencias de Microsoft 365 E5 <br> -Completar el Asistente de configuración en el portal|
| ![Simulación de ataques](../../media/mtp/run-sim.png) <br>[Simulación de ataques](mtp-pilot-simulate.md) | Para simular un ataque, se le guiará a lo siguiente:<br><br>-Comprobación de los requisitos del entorno de prueba <br>-Ejecutar la simulación <br>-Investigar un incidente <br>-resolver el incidente 
| ![Cierre y Resumen](../../media/mtp/close.png) <br>[Cierre y Resumen](mtp-pilot-close.md) | Cuando haya llegado al final del proceso, se le guiará a lo siguiente:<br><br>-Pase por el resultado final<br>-Presentar la salida a las partes interesadas <br>-Proporcionar comentarios <br>-Realizar los siguientes pasos 

## <a name="next-step"></a>Paso siguiente
|![Fase de planeación](../../media/mtp/plan.png) <br>[Fase de planeación](mtp-pilot-plan.md) | Planeación de un proyecto piloto de Microsoft Threat Protection 
|:-------|:-----|
