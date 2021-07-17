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
# <a name="pilot-microsoft-defender-for-endpoint"></a><span data-ttu-id="34e60-103">Piloto de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="34e60-103">Pilot Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="34e60-104">Este artículo le guiará en el proceso de ejecución de un piloto para Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="34e60-104">This article will guide you in the process of running a pilot for Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="34e60-105">Siga estos pasos para configurar y configurar el piloto de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="34e60-105">Use the following steps to setup and configure the pilot for Microsoft Defender for Endpoint.</span></span> 

![Pasos para agregar Microsoft Defender for Identity al entorno de evaluación de Defender](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- <span data-ttu-id="34e60-107">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="34e60-107">Step 1.</span></span> <span data-ttu-id="34e60-108">Comprobar grupo piloto</span><span class="sxs-lookup"><span data-stu-id="34e60-108">Verify pilot group</span></span>
- <span data-ttu-id="34e60-109">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="34e60-109">Step 2.</span></span> <span data-ttu-id="34e60-110">Probar funcionalidades</span><span class="sxs-lookup"><span data-stu-id="34e60-110">Try out capabilities</span></span>

<span data-ttu-id="34e60-111">Cuando pilote Microsoft Defender para Endpoint, puede optar por incorporar algunos dispositivos al servicio antes de incorporar toda la organización.</span><span class="sxs-lookup"><span data-stu-id="34e60-111">When you pilot Microsoft Defender for Endpoint, you may choose to onboard a few devices to the service before onboarding your entire organization.</span></span>  

<span data-ttu-id="34e60-112">A continuación, puedes probar las funcionalidades disponibles, como ejecutar simulaciones de ataques y ver cómo Defender for Endpoint muestra actividades malintencionadas y te permite llevar a cabo una respuesta eficaz.</span><span class="sxs-lookup"><span data-stu-id="34e60-112">You can then try out capabilities that are available such as running attack simulations and seeing how Defender for Endpoint surfaces malicious activities and enables you to conduct an efficient response.</span></span> 

## <a name="step-1-verify-pilot-group"></a><span data-ttu-id="34e60-113">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="34e60-113">Step 1.</span></span> <span data-ttu-id="34e60-114">Comprobar grupo piloto</span><span class="sxs-lookup"><span data-stu-id="34e60-114">Verify pilot group</span></span>
<span data-ttu-id="34e60-115">Después de completar los pasos de [](eval-defender-endpoint-enable-eval.md) incorporación descritos en la sección Habilitar evaluación, debes ver los dispositivos en la lista inventario de dispositivos aproximadamente después de una hora.</span><span class="sxs-lookup"><span data-stu-id="34e60-115">After completing the onboarding steps outlined in the [Enable evaluation](eval-defender-endpoint-enable-eval.md) section, you should see the devices in the Device inventory list approximately after an hour.</span></span> 

<span data-ttu-id="34e60-116">Cuando veas los dispositivos incorporados, puedes continuar con las funciones de probar.</span><span class="sxs-lookup"><span data-stu-id="34e60-116">When you see your onboarded devices you can then proceed with trying out capabilities.</span></span> 

## <a name="step-2-try-out-capabilities"></a><span data-ttu-id="34e60-117">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="34e60-117">Step 2.</span></span> <span data-ttu-id="34e60-118">Probar funcionalidades</span><span class="sxs-lookup"><span data-stu-id="34e60-118">Try out capabilities</span></span>
<span data-ttu-id="34e60-119">Ahora que ha completado la incorporación de algunos dispositivos y ha comprobado que están informando al servicio, familiarícese con el producto probando las funciones eficaces que están disponibles desde el primer momento.</span><span class="sxs-lookup"><span data-stu-id="34e60-119">Now that you've completed onboarding some devices and verified that they are reporting to the service, familiarize yourself with the product by trying out the powerful capabilities that are available right out of the box.</span></span>

<span data-ttu-id="34e60-120">Durante el piloto, puede empezar fácilmente a probar algunas de las características para ver el producto en acción sin pasar por pasos complejos de configuración.</span><span class="sxs-lookup"><span data-stu-id="34e60-120">During the pilot, you can easily get started with trying out some of the features to see the product in action without going through complex configuration steps.</span></span>

<span data-ttu-id="34e60-121">Empecemos por echar un vistazo a los paneles.</span><span class="sxs-lookup"><span data-stu-id="34e60-121">Let's start by checking out the dashboards.</span></span>

### <a name="view-the-device-inventory"></a><span data-ttu-id="34e60-122">Ver el inventario de dispositivos</span><span class="sxs-lookup"><span data-stu-id="34e60-122">View the device inventory</span></span>
<span data-ttu-id="34e60-123">El inventario de dispositivos es donde verá la lista de puntos de conexión, dispositivos de red y dispositivos IoT de la red.</span><span class="sxs-lookup"><span data-stu-id="34e60-123">The device inventory is where you'll see the list of endpoints, network devices, and IoT devices in your network.</span></span> <span data-ttu-id="34e60-124">No solo proporciona una vista de los dispositivos de la red, sino que también proporciona información detallada sobre ellos, como dominio, nivel de riesgo, plataforma del sistema operativo y otros detalles para facilitar la identificación de los dispositivos más en riesgo.</span><span class="sxs-lookup"><span data-stu-id="34e60-124">Not only does it provide you with a view of the devices in your network, but it also gives your in-depth information about them such as  domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="34e60-125">Ver el panel amenazas y administración de vulnerabilidades panel</span><span class="sxs-lookup"><span data-stu-id="34e60-125">View the Threat and vulnerability management dashboard</span></span> 
<span data-ttu-id="34e60-126">La amenaza administración de vulnerabilidades ayuda a centrarse en las debilidades que representan el riesgo más urgente y más alto para la organización.</span><span class="sxs-lookup"><span data-stu-id="34e60-126">Threat and vulnerability management helps you focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="34e60-127">Desde el panel, obtenga una vista de alto nivel de la puntuación de exposición de la organización, puntuación segura de Microsoft para dispositivos, distribución de exposición de dispositivos, recomendaciones de seguridad superiores, software vulnerable superior, actividades de corrección superior y datos de dispositivos expuestos superiores.</span><span class="sxs-lookup"><span data-stu-id="34e60-127">From the dashboard, get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span> 

### <a name="run-a-simulation"></a><span data-ttu-id="34e60-128">Ejecutar una simulación</span><span class="sxs-lookup"><span data-stu-id="34e60-128">Run a simulation</span></span>
<span data-ttu-id="34e60-129">Microsoft Defender para endpoint viene con escenarios de ataque ["Do It Yourself"](https://securitycenter.windows.com/tutorials) que puedes ejecutar en tus dispositivos piloto.</span><span class="sxs-lookup"><span data-stu-id="34e60-129">Microsoft Defender for Endpoint comes with ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials) that you can run on your pilot devices.</span></span>  <span data-ttu-id="34e60-130">Cada documento incluye requisitos de sistema operativo y aplicación, así como instrucciones detalladas específicas para un escenario de ataque.</span><span class="sxs-lookup"><span data-stu-id="34e60-130">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span> <span data-ttu-id="34e60-131">Estos scripts son seguros, documentados y fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="34e60-131">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="34e60-132">Estos escenarios reflejarán las capacidades de Defender for Endpoint y le ayudarán a través de la experiencia de investigación.</span><span class="sxs-lookup"><span data-stu-id="34e60-132">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

<span data-ttu-id="34e60-133">Para ejecutar cualquiera de las simulaciones proporcionadas, necesita al menos [un dispositivo incorporado](../defender-endpoint/onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="34e60-133">To run any of the provided simulations, you need at least [one onboarded device](../defender-endpoint/onboard-configure.md).</span></span>

1. <span data-ttu-id="34e60-134">En **help**  >  **simulations & tutoriales**, seleccione cuál de los escenarios de ataque disponibles desea simular:</span><span class="sxs-lookup"><span data-stu-id="34e60-134">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="34e60-135">**Escenario 1: El documento deja la puerta trasera:** simula la entrega de un documento de señuelo de ingeniería social.</span><span class="sxs-lookup"><span data-stu-id="34e60-135">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="34e60-136">El documento inicia una puerta trasera especialmente diseñada que proporciona control a los atacantes.</span><span class="sxs-lookup"><span data-stu-id="34e60-136">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="34e60-137">**Escenario 2: Script** de PowerShell en ataque sin archivos: simula un ataque sin archivos que se basa en PowerShell, que muestra la reducción de superficie de ataque y la detección de aprendizaje de dispositivos de actividad de memoria malintencionada.</span><span class="sxs-lookup"><span data-stu-id="34e60-137">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="34e60-138">**Escenario 3: Respuesta** automatizada a incidentes: desencadena la investigación automatizada, que busca y corrige automáticamente artefactos de infracción para escalar la capacidad de respuesta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="34e60-138">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="34e60-139">Descargue y lea el documento de tutorial correspondiente proporcionado con el escenario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="34e60-139">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="34e60-140">Descargue el archivo de simulación o copie el script de simulación navegando a **Help**  >  **Simulations & tutoriales**.</span><span class="sxs-lookup"><span data-stu-id="34e60-140">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="34e60-141">Puedes elegir descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="34e60-141">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="34e60-142">Ejecute el archivo de simulación o el script en el dispositivo de prueba como se indica en el documento del tutorial.</span><span class="sxs-lookup"><span data-stu-id="34e60-142">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="34e60-143">Los archivos de simulación o scripts imitan la actividad de ataque, pero en realidad son benignos y no dañan ni comprometen el dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="34e60-143">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>

## <a name="next-steps"></a><span data-ttu-id="34e60-144">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="34e60-144">Next steps</span></span>
[<span data-ttu-id="34e60-145">Evaluar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="34e60-145">Evaluate Microsoft Cloud App Security</span></span>](eval-defender-mcas-overview.md)

<span data-ttu-id="34e60-146">Vuelva a la introducción a [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="34e60-146">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="34e60-147">Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="34e60-147">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>