---
title: Experiencia Microsoft Defender para punto de conexión a través de ataques simulados
description: Ejecute las simulaciones de escenarios de ataque proporcionadas para experimentar cómo Microsoft Defender para punto de conexión puede detectar, investigar y responder a infracciones.
keywords: prueba, escenario, ataque, simulación, simulado, bricolaje, Microsoft Defender para punto de conexión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.service: microsoft-365-security
ms.subservice: mde
ms.pagetype: security
ms.author: maccruz
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 8e934c166aca10ff7913e4c6bc7bc7ad42f2af11
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67812444"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Experiencia Microsoft Defender para punto de conexión a través de ataques simulados 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-abovefoldlink)

> [!TIP]
>
> - Obtenga información sobre las mejoras más recientes en Microsoft Defender para punto de conexión: [¿Qué hay de nuevo en Defender para punto de conexión?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
> - Defender para punto de conexión demostró las funcionalidades de óptica y detección líderes del sector en la evaluación reciente de MITRE. Lectura: [Insights de la evaluación basada en MITRE ATT&CK](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

Es posible que quiera experimentar Defender para punto de conexión antes de incorporar más de unos pocos dispositivos al servicio. Para ello, puede ejecutar simulaciones de ataque controladas en algunos dispositivos de prueba. Después de ejecutar los ataques simulados, puede revisar cómo Defender for Endpoint expone la actividad malintencionada y explorar cómo permite una respuesta eficaz.

## <a name="before-you-begin"></a>Antes de empezar

Para ejecutar cualquiera de las simulaciones proporcionadas, necesita al menos [un dispositivo incorporado](onboard-configure.md).

Lea el documento del tutorial proporcionado con cada escenario de ataque. Cada documento incluye los requisitos del sistema operativo y de la aplicación, así como instrucciones detalladas específicas de un escenario de ataque.

## <a name="run-a-simulation"></a>Ejecución de una simulación

1. En **Evaluación de puntos** \> de conexión **& tutoriales Tutoriales** \> **& simulaciones**, seleccione cuál de los escenarios de ataque disponibles desea simular:
   - **Escenario 1: El documento coloca la puerta trasera** : simula la entrega de un documento señuelo diseñado socialmente. El documento inicia una puerta trasera especialmente diseñada que proporciona control a los atacantes.
   - **Escenario 2: Script de PowerShell en ataque sin archivos** : simula un ataque sin archivos que se basa en PowerShell, que muestra la reducción de la superficie expuesta a ataques y la detección de aprendizaje de dispositivos de actividad de memoria malintencionada.
   - **Escenario 3: Respuesta a incidentes automatizada:** desencadena una investigación automatizada, que busca y corrige automáticamente los artefactos de infracción para escalar la capacidad de respuesta a incidentes.

2. Descargue y lea el documento de tutorial correspondiente proporcionado con el escenario seleccionado.

3. Descargue el archivo de simulación o copie el script de simulación; para ello, vaya a **Evaluación & tutoriales Tutoriales** \> **& simulaciones**. Puede optar por descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.

4. Ejecute el archivo o script de simulación en el dispositivo de prueba como se indica en el documento del tutorial.

> [!NOTE]
> Los archivos o scripts de simulación imitan la actividad de ataque, pero en realidad son benignos y no dañarán ni pondrán en peligro el dispositivo de prueba.
>
> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados

- [Incorporación de dispositivos](onboard-configure.md)
- [incorporar dispositivos Windows](configure-endpoints.md)
