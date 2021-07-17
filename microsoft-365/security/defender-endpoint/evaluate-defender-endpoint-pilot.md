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
ms.openlocfilehash: 131a048e806976afa3bffbd3f3bce2d61a370225
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458612"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a><span data-ttu-id="e981f-104">Experiencia de Microsoft Defender para endpoint (MDE) a través de ataques simulados</span><span class="sxs-lookup"><span data-stu-id="e981f-104">Experience Microsoft Defender for Endpoint (MDE) through simulated attacks</span></span>

>[!TIP]
>
>- <span data-ttu-id="e981f-105">Obtenga información sobre las mejoras más recientes en Microsoft Defender para endpoint: ¿Qué hay [de nuevo en Defender para endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="e981f-105">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="e981f-106">Defender for Endpoint demostró las capacidades de detección y óptica líderes del sector en la reciente evaluación de MITRE.</span><span class="sxs-lookup"><span data-stu-id="e981f-106">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="e981f-107">Read: [Ideas from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="e981f-107">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="e981f-108">Es posible que quieras experimentar Defender for Endpoint antes de incorporar más de unos pocos dispositivos al servicio.</span><span class="sxs-lookup"><span data-stu-id="e981f-108">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="e981f-109">Para ello, puedes ejecutar simulaciones de ataque controlado en algunos dispositivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="e981f-109">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="e981f-110">Después de ejecutar los ataques simulados, puedes revisar cómo Defender for Endpoint muestra actividad malintencionada y explorar cómo habilita una respuesta eficaz.</span><span class="sxs-lookup"><span data-stu-id="e981f-110">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e981f-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="e981f-111">Before you begin</span></span>

<span data-ttu-id="e981f-112">Para ejecutar cualquiera de las simulaciones proporcionadas, necesita al menos [un dispositivo incorporado](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="e981f-112">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span>

<span data-ttu-id="e981f-113">Lea el documento del tutorial proporcionado con cada escenario de ataque.</span><span class="sxs-lookup"><span data-stu-id="e981f-113">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="e981f-114">Cada documento incluye requisitos de sistema operativo y aplicación, así como instrucciones detalladas específicas para un escenario de ataque.</span><span class="sxs-lookup"><span data-stu-id="e981f-114">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="e981f-115">Ejecutar una simulación</span><span class="sxs-lookup"><span data-stu-id="e981f-115">Run a simulation</span></span>

1. <span data-ttu-id="e981f-116">En **help**  >  **simulations & tutoriales**, seleccione cuál de los escenarios de ataque disponibles desea simular:</span><span class="sxs-lookup"><span data-stu-id="e981f-116">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="e981f-117">**Escenario 1: El documento deja la puerta trasera:** simula la entrega de un documento de señuelo de ingeniería social.</span><span class="sxs-lookup"><span data-stu-id="e981f-117">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="e981f-118">El documento inicia una puerta trasera especialmente diseñada que proporciona control a los atacantes.</span><span class="sxs-lookup"><span data-stu-id="e981f-118">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="e981f-119">**Escenario 2: Script** de PowerShell en ataque sin archivos: simula un ataque sin archivos que se basa en PowerShell, que muestra la reducción de superficie de ataque y la detección de aprendizaje de dispositivos de actividad de memoria malintencionada.</span><span class="sxs-lookup"><span data-stu-id="e981f-119">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="e981f-120">**Escenario 3: Respuesta** automatizada a incidentes: desencadena la investigación automatizada, que busca y corrige automáticamente artefactos de infracción para escalar la capacidad de respuesta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="e981f-120">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="e981f-121">Descargue y lea el documento de tutorial correspondiente proporcionado con el escenario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e981f-121">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="e981f-122">Descargue el archivo de simulación o copie el script de simulación navegando a **Help**  >  **Simulations & tutoriales**.</span><span class="sxs-lookup"><span data-stu-id="e981f-122">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="e981f-123">Puedes elegir descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e981f-123">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="e981f-124">Ejecute el archivo de simulación o el script en el dispositivo de prueba como se indica en el documento del tutorial.</span><span class="sxs-lookup"><span data-stu-id="e981f-124">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="e981f-125">Los archivos de simulación o scripts imitan la actividad de ataque, pero en realidad son benignos y no dañan ni comprometen el dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="e981f-125">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
>

## <a name="alternate-topic-text"></a><span data-ttu-id="e981f-126">TEXTO DE TEMA ALTERNATIVO</span><span class="sxs-lookup"><span data-stu-id="e981f-126">ALTERNATE TOPIC TEXT</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="e981f-127">Simular escenarios de ataque</span><span class="sxs-lookup"><span data-stu-id="e981f-127">Simulate attack scenarios</span></span>

<span data-ttu-id="e981f-128">Usa los dispositivos de prueba para ejecutar tus propias simulaciones de ataque conectándose a ellos.</span><span class="sxs-lookup"><span data-stu-id="e981f-128">Use the test devices to run your own attack simulations by connecting to them.</span></span>

<span data-ttu-id="e981f-129">Puedes simular escenarios de ataque con:</span><span class="sxs-lookup"><span data-stu-id="e981f-129">You can simulate attack scenarios using:</span></span>

- <span data-ttu-id="e981f-130">Escenarios de ataque ["Do It Yourself"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="e981f-130">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="e981f-131">Simuladores de amenazas</span><span class="sxs-lookup"><span data-stu-id="e981f-131">Threat simulators</span></span>

<span data-ttu-id="e981f-132">También puede usar búsqueda avanzada [para consultar](advanced-hunting-overview.md) datos y [análisis de](threat-analytics.md) amenazas para ver informes sobre amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="e981f-132">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="e981f-133">Escenarios de ataque do-it-yourself</span><span class="sxs-lookup"><span data-stu-id="e981f-133">Do-it-yourself attack scenarios</span></span>

<span data-ttu-id="e981f-134">Si está buscando una simulación pre-made, puede usar nuestros escenarios de ataque ["Do It Yourself".](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="e981f-134">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="e981f-135">Estos scripts son seguros, documentados y fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="e981f-135">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="e981f-136">Estos escenarios reflejarán las capacidades de Defender for Endpoint y le ayudarán a través de la experiencia de investigación.</span><span class="sxs-lookup"><span data-stu-id="e981f-136">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

>[!NOTE]
><span data-ttu-id="e981f-137">La conexión a los dispositivos de prueba se realiza con RDP.</span><span class="sxs-lookup"><span data-stu-id="e981f-137">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="e981f-138">Asegúrese de que la configuración del firewall permite conexiones RDP.</span><span class="sxs-lookup"><span data-stu-id="e981f-138">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="e981f-139">Conectar a tu dispositivo y ejecuta una simulación de ataque seleccionando **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="e981f-139">Connect to your device and run an attack simulation by selecting **Connect**.</span></span>

    ![Imagen del botón conectar para dispositivos de prueba](images/test-machine-table.png)

2. <span data-ttu-id="e981f-141">Guarde el archivo RDP e inicielo seleccionando **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="e981f-141">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Imagen de conexión de escritorio remoto](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="e981f-143">Si no tienes una copia de la contraseña guardada durante la configuración inicial, puedes restablecer la contraseña seleccionando **Restablecer** contraseña en el menú: Imagen de la contraseña de ![ restablecimiento](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="e981f-143">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span>
    >
    > <span data-ttu-id="e981f-144">El dispositivo cambiará su estado a "Ejecutar el restablecimiento de contraseña" y, a continuación, se te presentará la nueva contraseña en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="e981f-144">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="e981f-145">Escribe la contraseña que se ha mostrado durante el paso de creación del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e981f-145">Enter the password that was displayed during the device creation step.</span></span>

   ![Imagen de ventana para escribir credenciales](images/enter-password.png)

4. <span data-ttu-id="e981f-147">Ejecuta simulaciones de ataques do-it-yourself en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e981f-147">Run Do-it-yourself attack simulations on the device.</span></span>

### <a name="threat-simulator-scenarios"></a><span data-ttu-id="e981f-148">Escenarios del simulador de amenazas</span><span class="sxs-lookup"><span data-stu-id="e981f-148">Threat simulator scenarios</span></span>

<span data-ttu-id="e981f-149">Si optó por instalar cualquiera de los simuladores de amenazas compatibles durante la configuración del laboratorio, puede ejecutar las simulaciones integradas en los dispositivos de laboratorio de evaluación.</span><span class="sxs-lookup"><span data-stu-id="e981f-149">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span>

<span data-ttu-id="e981f-150">Ejecutar simulaciones de amenazas con plataformas de terceros es una buena manera de evaluar las capacidades de Punto de conexión de Microsoft Defender en los límites de un entorno de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="e981f-150">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
>
><span data-ttu-id="e981f-151">Antes de poder ejecutar simulaciones, asegúrese de que se cumplen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="e981f-151">Before you can run simulations, ensure the following requirements are met:</span></span>

>- <span data-ttu-id="e981f-152">Los dispositivos deben agregarse al laboratorio de evaluación</span><span class="sxs-lookup"><span data-stu-id="e981f-152">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="e981f-153">Los simuladores de amenazas deben instalarse en el laboratorio de evaluación</span><span class="sxs-lookup"><span data-stu-id="e981f-153">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="e981f-154">En el portal, seleccione **Crear simulación**.</span><span class="sxs-lookup"><span data-stu-id="e981f-154">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="e981f-155">Seleccione un simulador de amenazas.</span><span class="sxs-lookup"><span data-stu-id="e981f-155">Select a threat simulator.</span></span>

    ![Imagen de selección del simulador de amenazas](images/select-simulator.png)

3. <span data-ttu-id="e981f-157">Elija una simulación o busque en la galería de simulación para examinar las simulaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="e981f-157">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span>

    <span data-ttu-id="e981f-158">Puede acceder a la galería de simulación desde:</span><span class="sxs-lookup"><span data-stu-id="e981f-158">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="e981f-159">El panel de evaluación principal en el icono de información general de **Simulaciones** o</span><span class="sxs-lookup"><span data-stu-id="e981f-159">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="e981f-160">Al navegar desde el panel de navegación Evaluación y tutoriales De **simulación**&  >  **tutoriales** y, a continuación, seleccione **Catálogo de simulaciones**.</span><span class="sxs-lookup"><span data-stu-id="e981f-160">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="e981f-161">Selecciona los dispositivos en los que quieres ejecutar la simulación.</span><span class="sxs-lookup"><span data-stu-id="e981f-161">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="e981f-162">Seleccione **Crear simulación**.</span><span class="sxs-lookup"><span data-stu-id="e981f-162">Select **Create simulation**.</span></span>

6. <span data-ttu-id="e981f-163">Para ver el progreso de una simulación, seleccione la **pestaña Simulaciones.** Vea el estado de simulación, las alertas activas y otros detalles.</span><span class="sxs-lookup"><span data-stu-id="e981f-163">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span>

    <span data-ttu-id="e981f-164">![Imagen de la pestaña simulaciones](images/simulations-tab.png)
</span><span class="sxs-lookup"><span data-stu-id="e981f-164">![Image of simulations tab](images/simulations-tab.png)
</span></span><br>

<span data-ttu-id="e981f-165">Después de ejecutar las simulaciones, te animamos a recorrer la barra de progreso del laboratorio y explorar Microsoft Defender for Endpoint desencadenando una **investigación y corrección automatizadas.**</span><span class="sxs-lookup"><span data-stu-id="e981f-165">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="e981f-166">Consulte las pruebas recopiladas y analizadas por la característica.</span><span class="sxs-lookup"><span data-stu-id="e981f-166">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="e981f-167">Busca pruebas de ataque mediante la búsqueda avanzada mediante el lenguaje de consulta enriquecido y telemetría sin procesar y echa un vistazo a algunas amenazas de todo el mundo documentadas en análisis de amenazas.</span><span class="sxs-lookup"><span data-stu-id="e981f-167">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>
