---
title: Experiencia de ATP de Microsoft Defender a través de ataques simulados
description: Ejecute las simulaciones de escenario de ataque proporcionadas para experimentar cómo ATP de Microsoft Defender puede detectar, investigar y responder a infracciones.
keywords: wdatp, test, scenario, attack, simulation, simulated, diy, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 25538e1866db8f4a7bff24ac336005bf2e1ce78b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073051"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Experiencia de Microsoft Defender para endpoint a través de ataques simulados 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- Obtenga información sobre las últimas mejoras en ATP de Microsoft Defender: ¿Qué hay [de nuevo en Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
>- Defender for Endpoint demostró las capacidades de detección y óptica líderes del sector en la reciente evaluación de MITRE. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

Es posible que quieras experimentar Defender for Endpoint antes de incorporar más de unos pocos dispositivos al servicio. Para ello, puedes ejecutar simulaciones de ataque controlado en algunos dispositivos de prueba. Después de ejecutar los ataques simulados, puedes revisar cómo Defender for Endpoint muestra actividad malintencionada y explorar cómo habilita una respuesta eficaz.

## <a name="before-you-begin"></a>Antes de empezar

Para ejecutar cualquiera de las simulaciones proporcionadas, necesita al menos [un dispositivo incorporado](onboard-configure.md). 

Lea el documento del tutorial proporcionado con cada escenario de ataque. Cada documento incluye requisitos de sistema operativo y aplicación, así como instrucciones detalladas específicas para un escenario de ataque.

## <a name="run-a-simulation"></a>Ejecutar una simulación

1. En **help**  >  **simulations & tutoriales**, seleccione cuál de los escenarios de ataque disponibles desea simular:

   - **Escenario 1: El documento deja la puerta trasera:** simula la entrega de un documento de señuelo de ingeniería social. El documento inicia una puerta trasera especialmente diseñada que proporciona control a los atacantes.

   - **Escenario 2: Script** de PowerShell en ataque sin archivos: simula un ataque sin archivos que se basa en PowerShell, que muestra la reducción de superficie de ataque y la detección de aprendizaje de dispositivos de actividad de memoria malintencionada.
    
   - **Escenario 3: Respuesta** automatizada a incidentes: desencadena la investigación automatizada, que busca y corrige automáticamente artefactos de infracción para escalar la capacidad de respuesta a incidentes.

2. Descargue y lea el documento de tutorial correspondiente proporcionado con el escenario seleccionado.

3. Descargue el archivo de simulación o copie el script de simulación navegando a **Help**  >  **Simulations & tutoriales**. Puedes elegir descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.

4. Ejecute el archivo de simulación o el script en el dispositivo de prueba como se indica en el documento del tutorial.

> [!NOTE]
> Los archivos de simulación o scripts imitan la actividad de ataque, pero en realidad son benignos y no dañan ni comprometen el dispositivo de prueba.
> 
> 
> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a>Temas relacionados

- [Dispositivos integrados](onboard-configure.md)
- [Incorporación de dispositivos Windows 10](configure-endpoints.md)
