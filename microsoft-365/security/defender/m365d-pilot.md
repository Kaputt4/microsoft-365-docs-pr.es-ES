---
title: Ejecutar el proyecto piloto Microsoft 365 Defender
description: Ejecute el proyecto piloto Microsoft 365 Defender en producción para determinar eficazmente los beneficios y la adopción de Microsoft 365 Defender.
keywords: Microsoft 365 Piloto de Defender, ejecutar proyecto piloto de Microsoft 365 Defender, evaluar Microsoft 365 Defender en producción, proyecto piloto de Microsoft 365 Defender, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizadas, búsqueda avanzada
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
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b1616b39597a90ff8e8f7b4c92f29f75c62fea18
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934434"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Ejecutar el proyecto piloto Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


Esta guía te ayuda a ejecutar un proyecto piloto proporcionando punteros para asegurarte de que tienes un plan bien estructurado, guiándolo a través del uso de la característica de simulación de ataques y, por último, concluyendo el piloto con claves para que reflexiones y documentes los resultados.

![Fases en la ejecución de un piloto Microsoft 365 Defender](../../media/pilotphases.png)


Ejecutar un piloto le ayuda a determinar eficazmente las ventajas de adoptar Microsoft 365 Defender. Antes de habilitar Microsoft 365 Defender en el entorno de producción e iniciar los casos de uso, lo mejor es planear determinar las tareas que se deben realizar para el proyecto piloto y establecer los criterios de éxito. 


## <a name="how-to-use-this-pilot-playbook"></a>Cómo usar este libro de juegos piloto

Esta guía proporciona información general sobre Microsoft 365 Defender e instrucciones paso a paso sobre cómo configurar el proyecto piloto. 

Microsoft 365 Defender es un conjunto unificado de defensa empresarial anterior y posterior a la infracción que coordina de forma nativa la protección, la detección, la prevención, la investigación y la respuesta entre puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados. Lo hace combinando y orquestando las siguientes funcionalidades en una única solución de seguridad:
  - Microsoft Defender para el extremo (puntos de conexión)
  - Microsoft Defender para Office 365 (correo electrónico) 
  - Microsoft Defender para identidad (identidad) 
  - Microsoft Cloud App Security (aplicaciones)

![Imagen of_Microsoft solución de 365 Defender para usuarios, Microsoft Defender para identidad, para puntos de conexión de Microsoft Defender para endpoint, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

Con la solución integrada de Microsoft 365 Defender, los profesionales de seguridad pueden unir las señales de amenaza que Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Defender para Identity y Microsoft Cloud App Security reciben y determinar el alcance completo y el impacto de la amenaza, cómo entró en el entorno, qué está afectado y cómo afecta actualmente a la organización. Microsoft 365 Defender realiza acciones automáticas para evitar o detener el ataque y auto sanar los buzones, puntos de conexión e identidades de usuario afectados. Consulta la [información general Microsoft 365 Defender para](microsoft-365-defender.md) obtener más información.



La escala de tiempo de ejemplo siguiente varía en función de tener los recursos adecuados en el entorno. Es posible que algunas detecciones y flujos de trabajo necesiten más tiempo de aprendizaje que los demás.

![Escala de tiempo de ejemplo en la ejecución de un piloto Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones piloto lo más cerca posible.


### <a name="pilot-playbook-phases"></a>Fases piloto del libro de juegos 

Hay cuatro fases en la ejecución de un piloto de Microsoft 365 Defender:

|Fase | Descripción | 
|:-------|:-----|
| [Planeación](m365d-pilot-plan.md)<br> ~ 1 día| Obtenga información sobre lo que debe tener en cuenta antes de ejecutar el proyecto piloto de Microsoft 365 Defender: <br><br>- Ámbito <br> - Casos de uso <br>- Requisitos <br>- Plan de prueba <br> - Criterios de éxito <br> - Cuadro de mandos 
| [Preparación](m365d-evaluation.md) <br>~2 días|  Acceda Microsoft 365 Security Center para configurar el entorno piloto de Microsoft 365 Defender. Se le guiará a:<br><br>- Identificar partes interesadas y buscar el inicio de sesión para el piloto <br> - Consideraciones sobre el entorno <br>- Access <br>- Azure Active Directory configuración <br> - Orden de configuración <br> - Registrarse para la Microsoft 365 E5 prueba <br> - Configurar dominio <br>- Asignar Microsoft 365 E5 licencias <br> - Completar el asistente de configuración en el portal|
| [Simulación de ataque](m365d-pilot-simulate.md) <br>~2 días| Para simular un ataque, se te guiará a:<br><br>- Comprobar los requisitos del entorno de prueba <br>- Ejecutar la simulación <br>- Investigar un incidente <br>- resolver el incidente 
| [Cierre y resumen](m365d-pilot-close.md) <br>~ 1 día| Cuando haya llegado al final del proceso, se le guiará a:<br><br>- Ir a través de la salida final<br>- Presentar los resultados a las partes interesadas <br>- Proporcionar comentarios <br>- Siga los pasos siguientes 

## <a name="next-step"></a>Paso siguiente
|[Fase de planeación](m365d-pilot-plan.md) | Planear el proyecto piloto Microsoft 365 Defender 
|:-------|:-----|
