---
title: Habilitar el entorno de evaluación de Microsoft Defender para Identity, configurar la instancia MDI, instalar y configurar el sensor MDI, permitir que el sensor MDI detecte administradores locales
description: Configure Microsoft Defender for Identity en un entorno piloto Microsoft 365 Defender de prueba mediante la instalación de & la configuración del sensor y la descubriendo administradores locales en otros equipos.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458564"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a><span data-ttu-id="a93a9-103">Habilitar el entorno de evaluación para Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="a93a9-103">Enable the evaluation environment for Microsoft Defender for Identity</span></span>

<span data-ttu-id="a93a9-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a93a9-104">**Applies to:**</span></span>
- <span data-ttu-id="a93a9-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a93a9-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="a93a9-106">Este artículo es [el paso 2 de 2](eval-defender-identity-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="a93a9-106">This article is [Step 2 of 2](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="a93a9-107">Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-identity-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a93a9-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="a93a9-108">Siga estos pasos para configurar el entorno de Microsoft Defender para Identity.</span><span class="sxs-lookup"><span data-stu-id="a93a9-108">Use the following steps to set up your Microsoft Defender for Identity environment.</span></span> 

![Pasos para habilitar Microsoft Defender for Identity en el entorno de evaluación de Microsoft Defender](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [<span data-ttu-id="a93a9-110">Paso 1. Configurar la instancia de Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="a93a9-110">Step 1. Set up the Defender for Identity Instance</span></span>](#step-1-set-up-the-defender-for-identity-instance)
- [<span data-ttu-id="a93a9-111">Paso 2. Instalar y configurar el sensor</span><span class="sxs-lookup"><span data-stu-id="a93a9-111">Step 2. Install and configure the sensor</span></span>](#step-2-install-and-configure-the-sensor)
- [<span data-ttu-id="a93a9-112">Paso 3. Configurar la configuración de proxy y registro de eventos en máquinas con el sensor</span><span class="sxs-lookup"><span data-stu-id="a93a9-112">Step 3. Configure event log and proxy settings on machines with the sensor</span></span>](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [<span data-ttu-id="a93a9-113">Paso 4. Permitir que Defender for Identity identifique administradores locales en otros equipos</span><span class="sxs-lookup"><span data-stu-id="a93a9-113">Step 4. Allow Defender for Identity to identify local admins on other computers</span></span>](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a><span data-ttu-id="a93a9-114">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="a93a9-114">Step 1.</span></span> <span data-ttu-id="a93a9-115">Configurar la instancia de Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="a93a9-115">Set up the Defender for Identity Instance</span></span>

<span data-ttu-id="a93a9-116">Inicie sesión en el portal de Defender for Identity para crear la instancia y, a continuación, conecte esta instancia al entorno de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a93a9-116">Sign in to the Defender for Identity portal to create your instance and then connect this instance to your Active Directory environment.</span></span> 

|  |<span data-ttu-id="a93a9-117">Paso</span><span class="sxs-lookup"><span data-stu-id="a93a9-117">Step</span></span>     |<span data-ttu-id="a93a9-118">Más información</span><span class="sxs-lookup"><span data-stu-id="a93a9-118">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a93a9-119">1</span><span class="sxs-lookup"><span data-stu-id="a93a9-119">1</span></span>     | <span data-ttu-id="a93a9-120">Crear la instancia de Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="a93a9-120">Create the Defender for Identity instance</span></span>        | [<span data-ttu-id="a93a9-121">Inicio rápido: crear la instancia de Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="a93a9-121">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/defender-for-identity/install-step1)        |
|<span data-ttu-id="a93a9-122">2</span><span class="sxs-lookup"><span data-stu-id="a93a9-122">2</span></span>     | <span data-ttu-id="a93a9-123">Conectar la instancia de Defender for Identity al bosque de Active Directory</span><span class="sxs-lookup"><span data-stu-id="a93a9-123">Connect the Defender for Identity instance to your Active Directory forest</span></span>   | [<span data-ttu-id="a93a9-124">Inicio rápido: Conectar al bosque de Active Directory</span><span class="sxs-lookup"><span data-stu-id="a93a9-124">Quickstart: Connect to your Active Directory Forest</span></span>](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a><span data-ttu-id="a93a9-125">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="a93a9-125">Step 2.</span></span> <span data-ttu-id="a93a9-126">Instalar y configurar el sensor</span><span class="sxs-lookup"><span data-stu-id="a93a9-126">Install and configure the sensor</span></span>

<span data-ttu-id="a93a9-127">A continuación, descargue, instale y configure el sensor Defender for Identity en los controladores de dominio y los servidores de AD FS en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="a93a9-127">Next, download, install, and configure the Defender for Identity sensor on the domain controllers and AD FS servers in your on-premises environment.</span></span>

|  |<span data-ttu-id="a93a9-128">Paso</span><span class="sxs-lookup"><span data-stu-id="a93a9-128">Step</span></span>     |<span data-ttu-id="a93a9-129">Más información</span><span class="sxs-lookup"><span data-stu-id="a93a9-129">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a93a9-130">1</span><span class="sxs-lookup"><span data-stu-id="a93a9-130">1</span></span>     | <span data-ttu-id="a93a9-131">Determine cuántos sensores de Microsoft Defender para Identidad necesita.</span><span class="sxs-lookup"><span data-stu-id="a93a9-131">Determine how many Microsoft Defender for Identity sensors you need.</span></span>        | [<span data-ttu-id="a93a9-132">Planear la capacidad de Microsoft Defender para Identity</span><span class="sxs-lookup"><span data-stu-id="a93a9-132">Plan capacity for Microsoft Defender for Identity</span></span>](/defender-for-identity/capacity-planning)   |
|<span data-ttu-id="a93a9-133">2</span><span class="sxs-lookup"><span data-stu-id="a93a9-133">2</span></span>     | <span data-ttu-id="a93a9-134">Descargar el paquete de instalación del sensor</span><span class="sxs-lookup"><span data-stu-id="a93a9-134">Download the sensor setup package</span></span>  |  [<span data-ttu-id="a93a9-135">Inicio rápido: descargar el paquete de instalación del sensor de Microsoft Defender para identidad</span><span class="sxs-lookup"><span data-stu-id="a93a9-135">Quickstart: Download the Microsoft Defender for Identity sensor setup package</span></span>](/defender-for-identity/install-step3)   |
|<span data-ttu-id="a93a9-136">3</span><span class="sxs-lookup"><span data-stu-id="a93a9-136">3</span></span>     | <span data-ttu-id="a93a9-137">Instalar el sensor Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="a93a9-137">Install the Defender for Identity sensor</span></span>    |  [<span data-ttu-id="a93a9-138">Inicio rápido: instalar el sensor de Microsoft Defender para identidad</span><span class="sxs-lookup"><span data-stu-id="a93a9-138">Quickstart: Install the Microsoft Defender for Identity sensor</span></span>](/defender-for-identity/install-step4)       |
|<span data-ttu-id="a93a9-139">4 </span><span class="sxs-lookup"><span data-stu-id="a93a9-139">4</span></span>     | <span data-ttu-id="a93a9-140">Configurar el sensor</span><span class="sxs-lookup"><span data-stu-id="a93a9-140">Configure the sensor</span></span>       |  [<span data-ttu-id="a93a9-141">Configuración de Microsoft Defender para la configuración del sensor de identidad </span><span class="sxs-lookup"><span data-stu-id="a93a9-141">Configure Microsoft Defender for Identity sensor settings </span></span>](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a><span data-ttu-id="a93a9-142">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="a93a9-142">Step 3.</span></span> <span data-ttu-id="a93a9-143">Configurar la configuración de proxy y registro de eventos en máquinas con el sensor</span><span class="sxs-lookup"><span data-stu-id="a93a9-143">Configure event log and proxy settings on machines with the sensor</span></span>

<span data-ttu-id="a93a9-144">En las máquinas en las que instaló el sensor, configure la colección Windows de registros de eventos y la configuración de proxy de Internet para habilitar y mejorar las capacidades de detección.</span><span class="sxs-lookup"><span data-stu-id="a93a9-144">On the machines that you installed the sensor on, configure Windows event log collection and Internet proxy settings to enable and enhance detection capabilities.</span></span>

|  |<span data-ttu-id="a93a9-145">Paso</span><span class="sxs-lookup"><span data-stu-id="a93a9-145">Step</span></span>     |<span data-ttu-id="a93a9-146">Más información</span><span class="sxs-lookup"><span data-stu-id="a93a9-146">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a93a9-147">1</span><span class="sxs-lookup"><span data-stu-id="a93a9-147">1</span></span>     | <span data-ttu-id="a93a9-148">Configurar Windows de registro de eventos</span><span class="sxs-lookup"><span data-stu-id="a93a9-148">Configure Windows event log collection</span></span>         | [<span data-ttu-id="a93a9-149">Configurar Windows event (colección)</span><span class="sxs-lookup"><span data-stu-id="a93a9-149">Configure Windows Event collection</span></span>](/defender-for-identity/configure-windows-event-collection)        |
|<span data-ttu-id="a93a9-150">2</span><span class="sxs-lookup"><span data-stu-id="a93a9-150">2</span></span>     | <span data-ttu-id="a93a9-151">Configurar la configuración de proxy de Internet</span><span class="sxs-lookup"><span data-stu-id="a93a9-151">Configure Internet proxy settings</span></span>        | [<span data-ttu-id="a93a9-152">Configurar el proxy de extremo y la configuración de conectividad a Internet para el Sensor de identidad de Microsoft Defender para</span><span class="sxs-lookup"><span data-stu-id="a93a9-152">Configure endpoint proxy and Internet connectivity settings for your Microsoft Defender for Identity Sensor</span></span>](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a><span data-ttu-id="a93a9-153">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="a93a9-153">Step 4.</span></span> <span data-ttu-id="a93a9-154">Permitir que Defender for Identity identifique administradores locales en otros equipos</span><span class="sxs-lookup"><span data-stu-id="a93a9-154">Allow Defender for Identity to identify local admins on other computers</span></span>

<span data-ttu-id="a93a9-155">La detección de rutas de movimiento lateral de Microsoft Defender para identidad se basa en consultas que identifican a los administradores locales en máquinas específicas.</span><span class="sxs-lookup"><span data-stu-id="a93a9-155">Microsoft Defender for Identity lateral movement path detection relies on queries that identify local admins on specific machines.</span></span> <span data-ttu-id="a93a9-156">Estas consultas se realizan con el protocolo SAM-R, mediante la cuenta defender para el servicio de identidad.</span><span class="sxs-lookup"><span data-stu-id="a93a9-156">These queries are performed with the SAM-R protocol, using the Defender for Identity Service account.</span></span> 

<span data-ttu-id="a93a9-157">Para asegurarse de que Windows clientes y servidores permiten que la cuenta de Defender for Identity realice SAM-R, se debe realizar una modificación en la directiva de grupo para agregar la cuenta de servicio Defender for Identity además de las cuentas configuradas que aparecen en la directiva de acceso a la red.</span><span class="sxs-lookup"><span data-stu-id="a93a9-157">To ensure Windows clients and servers allow your Defender for Identity account to perform SAM-R, a modification to Group Policy must be made to add the Defender for Identity service account in addition to the configured accounts listed in the Network access policy.</span></span> <span data-ttu-id="a93a9-158">Asegúrese de aplicar directivas de grupo a todos los equipos **excepto a los controladores de dominio**.</span><span class="sxs-lookup"><span data-stu-id="a93a9-158">Make sure to apply group policies to all computers **except domain controllers**.</span></span>

<span data-ttu-id="a93a9-159">Para obtener instrucciones sobre cómo hacerlo, consulte [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr).</span><span class="sxs-lookup"><span data-stu-id="a93a9-159">For instructions on how to do this, see [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a93a9-160">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a93a9-160">Next steps</span></span>

<span data-ttu-id="a93a9-161">Paso 3 de 3: [Piloto de Microsoft Defender para identidad](eval-defender-identity-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="a93a9-161">Step 3 of 3: [Pilot Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span></span>

<span data-ttu-id="a93a9-162">Vuelva a la introducción a [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a93a9-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="a93a9-163">Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a93a9-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>