---
title: Microsoft Defender para punto de conexión piloto
description: Obtenga información sobre cómo ejecutar un piloto para Microsoft Defender para punto de conexión (MDE), incluida la comprobación del grupo piloto y la prueba de funcionalidades.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 44e6e341bd47dfb4d0debe1975c79f00cdb5a1da
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328967"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión piloto

Este artículo le guiará en el proceso de ejecución de un piloto para Microsoft Defender para punto de conexión. 

Siga estos pasos para configurar y configurar el piloto para Microsoft Defender para punto de conexión. 

:::image type="content" source="../../media/defender/m365-defender-endpoint-pilot-steps.png" alt-text="Los pasos para agregar Microsoft Defender for Identity al entorno de evaluación de Microsoft Defender" lightbox="../../media/defender/m365-defender-endpoint-pilot-steps.png":::

- Paso 1. Comprobación del grupo piloto
- Paso 2. Probar las funcionalidades

Al pilotar Microsoft Defender para punto de conexión, puede optar por incorporar algunos dispositivos al servicio antes de incorporar toda la organización.  

A continuación, puede probar las funcionalidades que están disponibles, como ejecutar simulaciones de ataque y ver cómo Defender for Endpoint expone actividades malintencionadas y le permite realizar una respuesta eficaz. 

## <a name="step-1-verify-pilot-group"></a>Paso 1. Comprobación del grupo piloto
Después de completar los pasos de incorporación descritos en la sección [Habilitar evaluación](eval-defender-endpoint-enable-eval.md) , debería ver los dispositivos en la lista Inventario de dispositivos aproximadamente después de una hora. 

Cuando vea los dispositivos incorporados, puede continuar con la prueba de funcionalidades. 

## <a name="step-2-try-out-capabilities"></a>Paso 2. Probar las funcionalidades
Ahora que ha completado la incorporación de algunos dispositivos y ha comprobado que están informando al servicio, familiarícese con el producto probando las eficaces funcionalidades que están disponibles inmediatamente.

Durante el piloto, puede empezar a probar fácilmente algunas de las características para ver el producto en acción sin pasar por pasos de configuración complejos.

Comencemos por la desprotejación de los paneles.

### <a name="view-the-device-inventory"></a>Visualización del inventario de dispositivos
El inventario de dispositivos es donde verá la lista de puntos de conexión, dispositivos de red y dispositivos IoT en la red. No solo proporciona una vista de los dispositivos de la red, sino que también proporciona información detallada sobre ellos, como el dominio, el nivel de riesgo, la plataforma del sistema operativo y otros detalles para facilitar la identificación de los dispositivos más en riesgo.

### <a name="view-the-microsoft-defender-vulnerability-management-dashboard"></a>Ver el panel de Administración de vulnerabilidades de Microsoft Defender 
La administración de La administración de vulnerabilidades de Defender le ayuda a centrarse en las debilidades que suponen el riesgo más urgente y el más alto para la organización. En el panel, obtenga una vista de alto nivel de la puntuación de exposición de la organización, puntuación segura de Microsoft para dispositivos, distribución de la exposición de dispositivos, recomendaciones de seguridad principales, software vulnerable superior, principales actividades de corrección y datos de dispositivo expuestos. 

### <a name="run-a-simulation"></a>Ejecución de una simulación
Microsoft Defender para punto de conexión incluye [escenarios de ataque "Do It Yourself"](https://securitycenter.windows.com/tutorials) que puede ejecutar en los dispositivos piloto.  Cada documento incluye los requisitos del sistema operativo y de la aplicación, así como instrucciones detalladas específicas de un escenario de ataque. Estos scripts son seguros, documentados y fáciles de usar. Estos escenarios reflejarán las funcionalidades de Defender para punto de conexión y le guiarán por la experiencia de investigación.

Para ejecutar cualquiera de las simulaciones proporcionadas, necesita al menos [un dispositivo incorporado](../defender-endpoint/onboard-configure.md).

1. En Simulaciones de **ayuda** > **& tutoriales**, seleccione cuál de los escenarios de ataque disponibles desea simular:

   - **Escenario 1: El documento coloca la puerta trasera** : simula la entrega de un documento señuelo diseñado socialmente. El documento inicia una puerta trasera especialmente diseñada que proporciona control a los atacantes.

   - **Escenario 2: Script de PowerShell en ataque sin archivos** : simula un ataque sin archivos que se basa en PowerShell, que muestra la reducción de la superficie expuesta a ataques y la detección de aprendizaje de dispositivos de actividad de memoria malintencionada.

   - **Escenario 3: Respuesta a incidentes automatizada:** desencadena una investigación automatizada, que busca y corrige automáticamente los artefactos de infracción para escalar la capacidad de respuesta a incidentes.

2. Descargue y lea el documento de tutorial correspondiente proporcionado con el escenario seleccionado.

3. Descargue el archivo de simulación o copie el script de simulación; para ello, vaya a Simulaciones de **ayuda** > **& tutoriales**. Puede optar por descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.

4. Ejecute el archivo o script de simulación en el dispositivo de prueba como se indica en el documento del tutorial.

> [!NOTE]
> Los archivos o scripts de simulación imitan la actividad de ataque, pero en realidad son benignos y no dañarán ni pondrán en peligro el dispositivo de prueba.

## <a name="next-steps"></a>Siguientes pasos
[Evaluar Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)

Vuelva a la introducción para [Evaluar Microsoft Defender para punto de conexión](eval-defender-endpoint-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
