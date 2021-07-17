---
title: Pilot Microsoft Defender for Endpoint, set up a pilot, test capabilities in evaluation
description: Obtenga información sobre cómo ejecutar un piloto para Microsoft Defender para Endpoint(MDE), incluida la comprobación del grupo piloto y las capacidades de prueba.
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d1efc37bd6412e441593dc9cf81296162f7fa754
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458513"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a>Piloto de Microsoft Defender para punto de conexión

Este artículo le guiará en el proceso de ejecución de un piloto para Microsoft Defender para Endpoint. 

Siga estos pasos para configurar y configurar el piloto de Microsoft Defender para endpoint. 

![Pasos para agregar Microsoft Defender for Identity al entorno de evaluación de Defender](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- Paso 1. Comprobar grupo piloto
- Paso 2. Probar funcionalidades

Cuando pilote Microsoft Defender para Endpoint, puede optar por incorporar algunos dispositivos al servicio antes de incorporar toda la organización.  

A continuación, puedes probar las funcionalidades disponibles, como ejecutar simulaciones de ataques y ver cómo Defender for Endpoint muestra actividades malintencionadas y te permite llevar a cabo una respuesta eficaz. 

## <a name="step-1-verify-pilot-group"></a>Paso 1. Comprobar grupo piloto
Después de completar los pasos de [](eval-defender-endpoint-enable-eval.md) incorporación descritos en la sección Habilitar evaluación, debes ver los dispositivos en la lista inventario de dispositivos aproximadamente después de una hora. 

Cuando veas los dispositivos incorporados, puedes continuar con las funciones de probar. 

## <a name="step-2-try-out-capabilities"></a>Paso 2. Probar funcionalidades
Ahora que ha completado la incorporación de algunos dispositivos y ha comprobado que están informando al servicio, familiarícese con el producto probando las funciones eficaces que están disponibles desde el primer momento.

Durante el piloto, puede empezar fácilmente a probar algunas de las características para ver el producto en acción sin pasar por pasos complejos de configuración.

Empecemos por echar un vistazo a los paneles.

### <a name="view-the-device-inventory"></a>Ver el inventario de dispositivos
El inventario de dispositivos es donde verá la lista de puntos de conexión, dispositivos de red y dispositivos IoT de la red. No solo proporciona una vista de los dispositivos de la red, sino que también proporciona información detallada sobre ellos, como dominio, nivel de riesgo, plataforma del sistema operativo y otros detalles para facilitar la identificación de los dispositivos más en riesgo.

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a>Ver el panel amenazas y administración de vulnerabilidades panel 
La amenaza administración de vulnerabilidades ayuda a centrarse en las debilidades que representan el riesgo más urgente y más alto para la organización. Desde el panel, obtenga una vista de alto nivel de la puntuación de exposición de la organización, puntuación segura de Microsoft para dispositivos, distribución de exposición de dispositivos, recomendaciones de seguridad superiores, software vulnerable superior, actividades de corrección superior y datos de dispositivos expuestos superiores. 

### <a name="run-a-simulation"></a>Ejecutar una simulación
Microsoft Defender para endpoint viene con escenarios de ataque ["Do It Yourself"](https://securitycenter.windows.com/tutorials) que puedes ejecutar en tus dispositivos piloto.  Cada documento incluye requisitos de sistema operativo y aplicación, así como instrucciones detalladas específicas para un escenario de ataque. Estos scripts son seguros, documentados y fáciles de usar. Estos escenarios reflejarán las capacidades de Defender for Endpoint y le ayudarán a través de la experiencia de investigación.

Para ejecutar cualquiera de las simulaciones proporcionadas, necesita al menos [un dispositivo incorporado](../defender-endpoint/onboard-configure.md).

1. En **help**  >  **simulations & tutoriales**, seleccione cuál de los escenarios de ataque disponibles desea simular:

   - **Escenario 1: El documento deja la puerta trasera:** simula la entrega de un documento de señuelo de ingeniería social. El documento inicia una puerta trasera especialmente diseñada que proporciona control a los atacantes.

   - **Escenario 2: Script** de PowerShell en ataque sin archivos: simula un ataque sin archivos que se basa en PowerShell, que muestra la reducción de superficie de ataque y la detección de aprendizaje de dispositivos de actividad de memoria malintencionada.

   - **Escenario 3: Respuesta** automatizada a incidentes: desencadena la investigación automatizada, que busca y corrige automáticamente artefactos de infracción para escalar la capacidad de respuesta a incidentes.

2. Descargue y lea el documento de tutorial correspondiente proporcionado con el escenario seleccionado.

3. Descargue el archivo de simulación o copie el script de simulación navegando a **Help**  >  **Simulations & tutoriales**. Puedes elegir descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.

4. Ejecute el archivo de simulación o el script en el dispositivo de prueba como se indica en el documento del tutorial.

> [!NOTE]
> Los archivos de simulación o scripts imitan la actividad de ataque, pero en realidad son benignos y no dañan ni comprometen el dispositivo de prueba.

## <a name="next-steps"></a>Pasos siguientes
[Evaluar Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Vuelva a la introducción a [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)