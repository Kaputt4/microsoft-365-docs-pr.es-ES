---
title: Experiencia de Microsoft Defender para endpoint (MDE) a través de ataques simulados
description: Pilote su Microsoft 365 Defender de prueba o entorno piloto.
keywords: Microsoft 365 Defender prueba, pruebe Microsoft 365 Defender, evalúe Microsoft 365 Defender, laboratorio de evaluación de Microsoft 365 Defender Microsoft 365 Defender, piloto, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizadas, búsqueda avanzada
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e06d3c436c01d7d88abca65819493902c2a5ab20
ms.sourcegitcommit: 87d994407fb69a747239b8589ad11ddf9b47e527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2021
ms.locfileid: "53594903"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a>Experiencia de Microsoft Defender para endpoint (MDE) a través de ataques simulados

>[!TIP]
>
>- Obtenga información sobre las mejoras más recientes en Microsoft Defender para endpoint: ¿Qué hay [de nuevo en Defender para endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
>- Defender for Endpoint demostró las capacidades de detección y óptica líderes del sector en la reciente evaluación de MITRE. Lectura: [Insights de la evaluación basada en MITRE ATT&CK](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

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

## <a name="alternate-topic-text"></a>TEXTO DE TEMA ALTERNATIVO

## <a name="simulate-attack-scenarios"></a>Simular escenarios de ataque

Usa los dispositivos de prueba para ejecutar tus propias simulaciones de ataque conectándose a ellos.

Puedes simular escenarios de ataque con:

- Escenarios de ataque ["Do It Yourself"](https://securitycenter.windows.com/tutorials)
- Simuladores de amenazas

También puede usar búsqueda avanzada [para consultar](advanced-hunting-overview.md) datos y [análisis de](threat-analytics.md) amenazas para ver informes sobre amenazas emergentes.

### <a name="do-it-yourself-attack-scenarios"></a>Escenarios de ataque do-it-yourself

Si está buscando una simulación pre-made, puede usar nuestros escenarios de ataque ["Do It Yourself".](https://securitycenter.windows.com/tutorials) Estos scripts son seguros, documentados y fáciles de usar. Estos escenarios reflejarán las capacidades de Defender for Endpoint y le ayudarán a través de la experiencia de investigación.

>[!NOTE]
>La conexión a los dispositivos de prueba se realiza con RDP. Asegúrese de que la configuración del firewall permite conexiones RDP.

1. Conectar a tu dispositivo y ejecuta una simulación de ataque seleccionando **Conectar**.

    ![Imagen del botón conectar para dispositivos de prueba](images/test-machine-table.png)

2. Guarde el archivo RDP e inicielo seleccionando **Conectar**.

    ![Imagen de conexión de escritorio remoto](images/remote-connection.png)

    >[!NOTE]
    >Si no tienes una copia de la contraseña guardada durante la configuración inicial, puedes restablecer la contraseña seleccionando **Restablecer** contraseña en el menú: Imagen de la contraseña de ![ restablecimiento](images/reset-password-test-machine.png)
    >
    > El dispositivo cambiará su estado a "Ejecutar el restablecimiento de contraseña" y, a continuación, se te presentará la nueva contraseña en unos minutos.

3. Escribe la contraseña que se ha mostrado durante el paso de creación del dispositivo.

   ![Imagen de ventana para escribir credenciales](images/enter-password.png)

4. Ejecuta simulaciones de ataques do-it-yourself en el dispositivo.

### <a name="threat-simulator-scenarios"></a>Escenarios del simulador de amenazas

Si optó por instalar cualquiera de los simuladores de amenazas compatibles durante la configuración del laboratorio, puede ejecutar las simulaciones integradas en los dispositivos de laboratorio de evaluación.

Ejecutar simulaciones de amenazas con plataformas de terceros es una buena manera de evaluar las capacidades de Punto de conexión de Microsoft Defender en los límites de un entorno de laboratorio.

>[!NOTE]
>
>Antes de poder ejecutar simulaciones, asegúrese de que se cumplen los siguientes requisitos:

>- Los dispositivos deben agregarse al laboratorio de evaluación
>- Los simuladores de amenazas deben instalarse en el laboratorio de evaluación

1. En el portal, seleccione **Crear simulación**.

2. Seleccione un simulador de amenazas.

    ![Imagen de selección del simulador de amenazas](images/select-simulator.png)

3. Elija una simulación o busque en la galería de simulación para examinar las simulaciones disponibles.

    Puede acceder a la galería de simulación desde:
    - El panel de evaluación principal en el icono de información general de **Simulaciones** o
    - Al navegar desde el panel de navegación Evaluación y tutoriales De **simulación**&  >  **tutoriales** y, a continuación, seleccione **Catálogo de simulaciones**.

4. Selecciona los dispositivos en los que quieres ejecutar la simulación.

5. Seleccione **Crear simulación**.

6. Para ver el progreso de una simulación, seleccione la **pestaña Simulaciones.** Vea el estado de simulación, las alertas activas y otros detalles.

    ![Imagen de la pestaña simulaciones](images/simulations-tab.png)
<br>

Después de ejecutar las simulaciones, te animamos a recorrer la barra de progreso del laboratorio y explorar Microsoft Defender for Endpoint desencadenando una **investigación y corrección automatizadas.** Consulte las pruebas recopiladas y analizadas por la característica.

Busca pruebas de ataque mediante la búsqueda avanzada mediante el lenguaje de consulta enriquecido y telemetría sin procesar y echa un vistazo a algunas amenazas de todo el mundo documentadas en análisis de amenazas.
