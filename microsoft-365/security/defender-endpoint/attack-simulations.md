---
title: Experiencia de Microsoft Defender para endpoint a través de ataques simulados
description: Ejecute las simulaciones de escenario de ataque proporcionadas para experimentar cómo Microsoft Defender para Endpoint puede detectar, investigar y responder a infracciones.
keywords: prueba, escenario, ataque, simulación, simulación, simulación, bricolaje, Microsoft Defender para endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 73a226d83e46cf06aa9d3cceb903a2b142604179
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213162"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Experiencia de Microsoft Defender para endpoint a través de ataques simulados 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-abovefoldlink)

> [!TIP]
>
> - Obtenga información sobre las mejoras más recientes en Microsoft Defender para endpoint: ¿Qué hay [de nuevo en Defender para endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
> - Defender for Endpoint demostró las capacidades de detección y óptica líderes del sector en la reciente evaluación de MITRE. Lectura: [Insights de la evaluación basada en MITRE ATT&CK](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

Es posible que quieras experimentar Defender for Endpoint antes de incorporar más de unos pocos dispositivos al servicio. Para ello, puedes ejecutar simulaciones de ataque controlado en algunos dispositivos de prueba. Después de ejecutar los ataques simulados, puedes revisar cómo Defender for Endpoint muestra actividad malintencionada y explorar cómo habilita una respuesta eficaz.

## <a name="before-you-begin"></a>Antes de empezar

Para ejecutar cualquiera de las simulaciones proporcionadas, necesita al menos [un dispositivo incorporado](onboard-configure.md).

Lea el documento del tutorial proporcionado con cada escenario de ataque. Cada documento incluye requisitos de sistema operativo y aplicación, así como instrucciones detalladas específicas para un escenario de ataque.

## <a name="run-a-simulation"></a>Ejecutar una simulación

1. En **Endpoints** \> **Evaluation &** \> **tutoriales & simulaciones**, seleccione cuál de los escenarios de ataque disponibles desea simular:
   - **Escenario 1: El documento deja la puerta trasera:** simula la entrega de un documento de señuelo de ingeniería social. El documento inicia una puerta trasera especialmente diseñada que proporciona control a los atacantes.
   - **Escenario 2: Script** de PowerShell en ataque sin archivos: simula un ataque sin archivos que se basa en PowerShell, que muestra la reducción de superficie de ataque y la detección de aprendizaje de dispositivos de actividad de memoria malintencionada.
   - **Escenario 3: Respuesta** automatizada a incidentes: desencadena la investigación automatizada, que busca y corrige automáticamente artefactos de infracción para escalar la capacidad de respuesta a incidentes.

2. Descargue y lea el documento de tutorial correspondiente proporcionado con el escenario seleccionado.

3. Para descargar el archivo de simulación o copiar el script de simulación, vaya a Tutoriales de evaluación **&** \> **tutoriales & simulaciones**. Puedes elegir descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.

4. Ejecute el archivo de simulación o el script en el dispositivo de prueba como se indica en el documento del tutorial.

> [!NOTE]
> Los archivos de simulación o scripts imitan la actividad de ataque, pero en realidad son benignos y no dañan ni comprometen el dispositivo de prueba.
>
> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados

- [Incorporar dispositivos](onboard-configure.md)
- [incorporar dispositivos Windows](configure-endpoints.md)
