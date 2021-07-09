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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 9a56167f0025ec42f4fd441886f83026c1bf23d6
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339543"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="d9a33-104">Experiencia de Microsoft Defender para endpoint a través de ataques simulados</span><span class="sxs-lookup"><span data-stu-id="d9a33-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d9a33-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d9a33-105">**Applies to:**</span></span>
- [<span data-ttu-id="d9a33-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d9a33-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d9a33-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9a33-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="d9a33-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d9a33-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d9a33-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d9a33-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="d9a33-110">Obtenga información sobre las mejoras más recientes en Microsoft Defender para endpoint: ¿Qué hay [de nuevo en Defender para endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="d9a33-110">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="d9a33-111">Defender for Endpoint demostró las capacidades de detección y óptica líderes del sector en la reciente evaluación de MITRE.</span><span class="sxs-lookup"><span data-stu-id="d9a33-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="d9a33-112">Read: [Ideas from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="d9a33-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="d9a33-113">Es posible que quieras experimentar Defender for Endpoint antes de incorporar más de unos pocos dispositivos al servicio.</span><span class="sxs-lookup"><span data-stu-id="d9a33-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="d9a33-114">Para ello, puedes ejecutar simulaciones de ataque controlado en algunos dispositivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="d9a33-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="d9a33-115">Después de ejecutar los ataques simulados, puedes revisar cómo Defender for Endpoint muestra actividad malintencionada y explorar cómo habilita una respuesta eficaz.</span><span class="sxs-lookup"><span data-stu-id="d9a33-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d9a33-116">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="d9a33-116">Before you begin</span></span>

<span data-ttu-id="d9a33-117">Para ejecutar cualquiera de las simulaciones proporcionadas, necesita al menos [un dispositivo incorporado](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="d9a33-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="d9a33-118">Lea el documento del tutorial proporcionado con cada escenario de ataque.</span><span class="sxs-lookup"><span data-stu-id="d9a33-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="d9a33-119">Cada documento incluye requisitos de sistema operativo y aplicación, así como instrucciones detalladas específicas para un escenario de ataque.</span><span class="sxs-lookup"><span data-stu-id="d9a33-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="d9a33-120">Ejecutar una simulación</span><span class="sxs-lookup"><span data-stu-id="d9a33-120">Run a simulation</span></span>

1. <span data-ttu-id="d9a33-121">En **Endpoints**  >  **Evaluation &**  >  **tutoriales & simulaciones**, seleccione cuál de los escenarios de ataque disponibles desea simular:</span><span class="sxs-lookup"><span data-stu-id="d9a33-121">In **Endpoints** > **Evaluation & tutorials** > **Tutorials & simulations**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="d9a33-122">**Escenario 1: El documento deja la puerta trasera:** simula la entrega de un documento de señuelo de ingeniería social.</span><span class="sxs-lookup"><span data-stu-id="d9a33-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="d9a33-123">El documento inicia una puerta trasera especialmente diseñada que proporciona control a los atacantes.</span><span class="sxs-lookup"><span data-stu-id="d9a33-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="d9a33-124">**Escenario 2: Script** de PowerShell en ataque sin archivos: simula un ataque sin archivos que se basa en PowerShell, que muestra la reducción de superficie de ataque y la detección de aprendizaje de dispositivos de actividad de memoria malintencionada.</span><span class="sxs-lookup"><span data-stu-id="d9a33-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="d9a33-125">**Escenario 3: Respuesta** automatizada a incidentes: desencadena la investigación automatizada, que busca y corrige automáticamente artefactos de infracción para escalar la capacidad de respuesta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="d9a33-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="d9a33-126">Descargue y lea el documento de tutorial correspondiente proporcionado con el escenario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d9a33-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="d9a33-127">Descargue el archivo de simulación o copie el script de simulación navegando a **Help**  >  **Simulations & tutoriales**.</span><span class="sxs-lookup"><span data-stu-id="d9a33-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="d9a33-128">Puedes elegir descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d9a33-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="d9a33-129">Ejecute el archivo de simulación o el script en el dispositivo de prueba como se indica en el documento del tutorial.</span><span class="sxs-lookup"><span data-stu-id="d9a33-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="d9a33-130">Los archivos de simulación o scripts imitan la actividad de ataque, pero en realidad son benignos y no dañan ni comprometen el dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="d9a33-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="d9a33-131">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d9a33-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d9a33-132">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d9a33-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="d9a33-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d9a33-133">Related topics</span></span>

- [<span data-ttu-id="d9a33-134">Incorporar dispositivos</span><span class="sxs-lookup"><span data-stu-id="d9a33-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="d9a33-135">Incorporar dispositivos Windows 10 mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="d9a33-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
