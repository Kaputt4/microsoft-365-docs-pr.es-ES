---
title: Ejecutar el proyecto piloto de Microsoft 365 defender
description: Ejecute el proyecto piloto de Microsoft 365 defender en producción para determinar eficazmente las ventajas y la adopción de Microsoft 365 defender.
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
ms.openlocfilehash: f01e918d35ce77d9239c200355c7b4c48c9e2b84
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659326"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Ejecutar el proyecto piloto de Microsoft 365 defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


Esta guía le ayudará a ejecutar un proyecto piloto proporcionando punteros para garantizar que tiene un plan bien estructurado, que le guiará por el uso de la característica de simulación de ataques y, finalmente, que concluya el piloto con puntos clave para que los refleje y documente los resultados.

![Fases de la ejecución de un piloto de Microsoft 365 defender](../../media/pilotphases.png)


La ejecución de un proyecto piloto ayuda a determinar eficazmente las ventajas de adoptiing Microsoft 365 defender. Antes de habilitar Microsoft 365 defender en su entorno de producción e iniciar los casos de uso, es mejor planear las tareas que se deben realizar para el proyecto piloto y establecer los criterios de éxito. 


## <a name="how-to-use-this-pilot-playbook"></a>Cómo usar esta guía del piloto

En esta guía se proporciona información general sobre Microsoft 365 defender e instrucciones paso a paso sobre cómo configurar el proyecto piloto. 

Microsoft 365 defender es un conjunto unificado de defensa de la empresa, antes y después de la violación, que coordina de forma nativa la protección, la detección, la prevención, la investigación y la respuesta en puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados. Lo hace combinando y orquestando las siguientes capacidades en una sola solución de seguridad:
  - Microsoft defender para extremo, el nuevo nombre para la protección contra amenazas avanzada de Microsoft defender (puntos de conexión)
  - Microsoft defender para Office 365, el nuevo nombre para Office 365 ATP (correo electrónico) 
  - Microsoft defender para identidad, el nuevo nombre de ATP (identidad) de Azure 
  - Microsoft Cloud App Security (aplicaciones)

![Imagen of_Microsoft solución de 365 defender para usuarios, Microsoft defender para identidad, para extremos Microsoft defender para Endpoint, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft defender para Office 365](../../media/mtp/m365pillars.png)

Con la solución integrada Microsoft 365 defender, los profesionales de seguridad pueden combinar las señales de amenaza que Microsoft defender para el punto de conexión, Microsoft defender para Office 365, Microsoft defender para la identidad y la recepción de seguridad de aplicaciones en la nube de Microsoft reciben, y determinar el alcance completo y el impacto de la amenaza, cómo se introdujo en el entorno, cómo se ve afectado y cómo afecta actualmente a Microsoft 365 defender realiza acciones automáticas para evitar o detener el ataque y Autocorregir los buzones de correo, los extremos y las identidades de usuario afectados. Consulte la [información general de Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) para obtener más información.



La siguiente escala de tiempo de ejemplo varía en función de la necesidad de disponer de los recursos adecuados en el entorno. Es posible que algunas detecciones y flujos de trabajo necesiten más tiempo de aprendizaje que los otros.

![Línea de tiempo de ejemplo para ejecutar un piloto de Microsoft 365 defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones piloto de la forma más parecida posible.


### <a name="pilot-playbook-phases"></a>Fases de la guía piloto 

Hay cuatro fases para ejecutar un piloto de Microsoft 365 defender:

|Fase | Description | 
|:-------|:-----|
| [Planeación](mtp-pilot-plan.md)<br> ~ 1 día| Obtenga información sobre lo que debe tener en cuenta antes de ejecutar el proyecto piloto de Microsoft 365 defender: <br><br>-Scope <br> Casos de uso de <br>- Requisitos <br>-Plan de pruebas <br> -Criterios de éxito <br> -Cuadro de mandos 
| [Declaración](mtp-evaluation.md) <br>~ 2 días|  Obtenga acceso al centro de seguridad 365 de Microsoft para configurar su entorno piloto de Microsoft 365 defender. Se le guiará a:<br><br>-Identificar las partes interesadas y buscar la firma para el proyecto piloto <br> Consideraciones del entorno <br>Acceso a <br>-Instalación de Azure Active Directory <br> -Orden de configuración <br> -Inscríbase en la versión de prueba de Microsoft 365 E5 <br> -Configurar dominio <br>-Asignar licencias de Microsoft 365 E5 <br> -Completar el Asistente de configuración en el portal|
| [Simulación de ataques](mtp-pilot-simulate.md) <br>~ 2 días| Para simular un ataque, se le guiará a lo siguiente:<br><br>-Comprobación de los requisitos del entorno de prueba <br>-Ejecutar la simulación <br>-Investigar un incidente <br>-resolver el incidente 
| [Cierre y Resumen](mtp-pilot-close.md) <br>~ 1 día| Cuando haya llegado al final del proceso, se le guiará a lo siguiente:<br><br>-Pase por el resultado final<br>-Presentar la salida a las partes interesadas <br>-Proporcionar comentarios <br>-Realizar los siguientes pasos 

## <a name="next-step"></a>Paso siguiente
|[Fase de planeación](mtp-pilot-plan.md) | Planeación de un proyecto piloto de Microsoft 365 defender 
|:-------|:-----|
