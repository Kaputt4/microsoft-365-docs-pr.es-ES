---
title: Ejecutar el proyecto piloto de Microsoft 365 Defender
description: Ejecute el proyecto piloto de Microsoft 365 Defender en producción para determinar eficazmente los beneficios y la adopción de Microsoft 365 Defender.
keywords: Piloto de Protección contra amenazas de Microsoft, ejecutar proyecto piloto de Protección contra amenazas de Microsoft, evaluar la Protección contra amenazas de Microsoft en producción, proyecto piloto de Protección contra amenazas de Microsoft, seguridad cibernética, amenaza persistente avanzada, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizada, búsqueda avanzada
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933035"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Ejecutar el proyecto piloto de Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


Esta guía le ayuda a ejecutar un proyecto piloto proporcionando punteros para asegurarse de que tiene un plan bien estructurado, guiándolo a través del uso de la característica de simulación de ataques y, por último, concluyendo el piloto con puntos clave para que se reflejen y documenten los resultados.

![Fases en la ejecución de un piloto de Microsoft 365 Defender](../../media/pilotphases.png)


La ejecución de un piloto le ayuda a determinar eficazmente las ventajas de adoptar Microsoft 365 Defender. Antes de habilitar Microsoft 365 Defender en su entorno de producción e iniciar los casos de uso, es mejor planear determinar las tareas que se deben realizar para el proyecto piloto y establecer los criterios de éxito. 


## <a name="how-to-use-this-pilot-playbook"></a>Cómo usar este libro de juegos piloto

En esta guía se proporciona información general sobre Microsoft 365 Defender e instrucciones paso a paso sobre cómo configurar el proyecto piloto. 

Microsoft 365 Defender es un conjunto unificado de defensa empresarial anterior y posterior a la infracción que coordina de forma nativa la protección, la detección, la prevención, la investigación y la respuesta entre puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar protección integrada contra ataques sofisticados. Para ello, combina y orquesta las siguientes funcionalidades en una única solución de seguridad:
  - Microsoft Defender para Endpoint, el nuevo nombre de Protección contra amenazas avanzada de Microsoft Defender (puntos de conexión)
  - Microsoft Defender para Office 365, el nuevo nombre de ATP de Office 365 (correo electrónico) 
  - Microsoft Defender for Identity, el nuevo nombre de Azure ATP (identidad) 
  - Microsoft Cloud App Security (aplicaciones)

![Imagen of_Microsoft solución de Defender 365 para usuarios, Microsoft Defender para Identidad, para puntos de conexión de Microsoft Defender para puntos de conexión, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

Con la solución integrada de Microsoft 365 Defender, los profesionales de seguridad pueden unir las señales de amenaza que Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Defender para Identity y Microsoft Cloud App Security reciben, y determinar el alcance completo y el impacto de la amenaza, cómo entra en el entorno, qué se ve afectado y cómo afecta actualmente a la organización. Microsoft 365 Defender toma medidas automáticas para evitar o detener el ataque y sanar automáticamente los buzones de correo, los puntos de conexión y las identidades de usuario afectados. Consulte la introducción [a Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) para obtener más información.



La siguiente escala de tiempo de ejemplo varía en función de tener los recursos adecuados en su entorno. Es posible que algunas detecciones y flujos de trabajo necesiten más tiempo de aprendizaje que las otras.

![Escala de tiempo de ejemplo en la ejecución de un piloto de Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Para obtener resultados óptimos, siga las instrucciones piloto lo más cerca posible.


### <a name="pilot-playbook-phases"></a>Fases del libro de juegos piloto 

Hay cuatro fases para ejecutar una prueba piloto de Microsoft 365 Defender:

|Fase | Descripción | 
|:-------|:-----|
| [Planeación](mtp-pilot-plan.md)<br> ~ 1 día| Obtenga información sobre lo que necesita tener en cuenta antes de ejecutar el proyecto piloto de Microsoft 365 Defender: <br><br>- Ámbito <br> - Casos de uso <br>- Requisitos <br>- Plan de prueba <br> - Criterios de éxito <br> - Cuadro de mandos 
| [Preparación](mtp-evaluation.md) <br>~2 días|  Acceda al Centro de seguridad de Microsoft 365 para configurar su entorno piloto de Microsoft 365 Defender. Se le guiará a:<br><br>- Identificar a las partes interesadas y buscar el inicio de sesión para el piloto <br> - Consideraciones de entorno <br>- Acceso <br>- Configuración de Azure Active Directory <br> - Orden de configuración <br> - Registrarse para la prueba de Microsoft 365 E5 <br> - Configurar dominio <br>- Asignar licencias de Microsoft 365 E5 <br> - Completar el asistente de configuración en el portal|
| [Simulación de ataques](mtp-pilot-simulate.md) <br>~2 días| Para simular un ataque, se te guiará a:<br><br>- Comprobar los requisitos del entorno de prueba <br>- Ejecutar la simulación <br>- Investigar un incidente <br>- resolver el incidente 
| [Cierre y resumen](mtp-pilot-close.md) <br>~ 1 día| Cuando haya llegado al final del proceso, se le guiará a:<br><br>- Ir a través de la salida final<br>- Presentar los resultados a las partes interesadas <br>- Proporcionar comentarios <br>- Siga los pasos siguientes 

## <a name="next-step"></a>Paso siguiente
|[Fase de planeación](mtp-pilot-plan.md) | Planear el proyecto piloto de Microsoft 365 Defender 
|:-------|:-----|
