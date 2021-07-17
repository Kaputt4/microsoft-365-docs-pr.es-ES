---
title: Pilot Defender for Endpoint evaluation
description: Habilite su laboratorio Microsoft 365 Defender prueba o entorno piloto.
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
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458639"
---
# <a name="pilot-mde-evaluation"></a><span data-ttu-id="d454a-104">Evaluación piloto de MDE</span><span class="sxs-lookup"><span data-stu-id="d454a-104">Pilot MDE Evaluation</span></span>

>[!NOTE]
><span data-ttu-id="d454a-105">Con el fin de guiarlo a través de una implementación típica, este escenario solo abarcará el uso de Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d454a-105">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="d454a-106">Defender for Endpoint admite el uso de otras herramientas de incorporación, pero no cubrirá esos escenarios en la guía de implementación.</span><span class="sxs-lookup"><span data-stu-id="d454a-106">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="d454a-107">Para obtener más información, consulta [Incorporación de dispositivos a Microsoft Defender para Endpoint](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="d454a-107">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="step-1-check-license-state"></a><span data-ttu-id="d454a-108">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="d454a-108">Step 1.</span></span> <span data-ttu-id="d454a-109">Comprobar el estado de la licencia</span><span class="sxs-lookup"><span data-stu-id="d454a-109">Check license state</span></span>

<span data-ttu-id="d454a-110">Comprobar el estado de la licencia y si se aprovisionó correctamente, se puede realizar a través del Centro de administración o a través **del portal Microsoft Azure .**</span><span class="sxs-lookup"><span data-stu-id="d454a-110">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="d454a-111">Para ver las licencias, vaya al **portal de** Microsoft Azure y vaya a la sección Microsoft Azure licencia [del portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="d454a-111">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Imagen de la página licencias de Azure](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="d454a-113">Como alternativa, en el Centro de administración, vaya a **Suscripciones de**  >  **facturación.**</span><span class="sxs-lookup"><span data-stu-id="d454a-113">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="d454a-114">En la pantalla, verá todas las licencias aprovisionadas y su estado **actual.**</span><span class="sxs-lookup"><span data-stu-id="d454a-114">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Imagen de las licencias de facturación](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="d454a-116">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="d454a-116">Step 2.</span></span> <span data-ttu-id="d454a-117">Incorporación de puntos de conexión con cualquiera de las herramientas de administración admitidas</span><span class="sxs-lookup"><span data-stu-id="d454a-117">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="d454a-118">En [el tema Plan deployment](deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d454a-118">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="d454a-119">Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtenga información sobre las herramientas y métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="d454a-119">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

<span data-ttu-id="d454a-120">Después de identificar la arquitectura, deberá decidir qué método de implementación usar.</span><span class="sxs-lookup"><span data-stu-id="d454a-120">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="d454a-121">La herramienta de implementación que elija influye en la forma en que incorpora puntos de conexión al servicio.</span><span class="sxs-lookup"><span data-stu-id="d454a-121">The deployment tool you choose influences how you onboard endpoints to the service.</span></span>

### <a name="onboarding-tool-options"></a><span data-ttu-id="d454a-122">Opciones de la herramienta de incorporación</span><span class="sxs-lookup"><span data-stu-id="d454a-122">Onboarding tool options</span></span>

<span data-ttu-id="d454a-123">En la tabla siguiente se enumeran las herramientas disponibles en función del extremo que necesita incorporar.</span><span class="sxs-lookup"><span data-stu-id="d454a-123">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="d454a-124">Punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d454a-124">Endpoint</span></span>     | <span data-ttu-id="d454a-125">Opciones de herramientas</span><span class="sxs-lookup"><span data-stu-id="d454a-125">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="d454a-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d454a-126">**Windows**</span></span>  |  [<span data-ttu-id="d454a-127">Script local (hasta 10 dispositivos)</span><span class="sxs-lookup"><span data-stu-id="d454a-127">Local script (up to 10 devices)</span></span>](../defender-endpoint/configure-endpoints-script.md) <br> [<span data-ttu-id="d454a-128">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="d454a-128">Group Policy</span></span>](../defender-endpoint/configure-endpoints-gp.md) <br> [<span data-ttu-id="d454a-129">Microsoft Endpoint Manager/ Administrador de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="d454a-129">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](../defender-endpoint/configure-endpoints-mdm.md) <br> [<span data-ttu-id="d454a-130">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d454a-130">Microsoft Endpoint Configuration Manager</span></span>](../defender-endpoint/configure-endpoints-sccm.md) <br> [<span data-ttu-id="d454a-131">Scripts VDI</span><span class="sxs-lookup"><span data-stu-id="d454a-131">VDI scripts</span></span>](../defender-endpoint/configure-endpoints-vdi.md) <br> [<span data-ttu-id="d454a-132">Integración con Azure Defender</span><span class="sxs-lookup"><span data-stu-id="d454a-132">Integration with Azure Defender</span></span>](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="d454a-133">**macOS**</span><span class="sxs-lookup"><span data-stu-id="d454a-133">**macOS**</span></span>    | [<span data-ttu-id="d454a-134">Scripts locales</span><span class="sxs-lookup"><span data-stu-id="d454a-134">Local scripts</span></span>](../defender-endpoint/mac-install-manually.md) <br> [<span data-ttu-id="d454a-135">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d454a-135">Microsoft Endpoint Manager</span></span>](../defender-endpoint/mac-install-with-intune.md) <br> [<span data-ttu-id="d454a-136">Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="d454a-136">JAMF Pro</span></span>](../defender-endpoint/mac-install-with-jamf.md) <br> [<span data-ttu-id="d454a-137">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="d454a-137">Mobile Device Management</span></span>](../defender-endpoint/mac-install-with-other-mdm.md) |
| <span data-ttu-id="d454a-138">**Servidor Linux**</span><span class="sxs-lookup"><span data-stu-id="d454a-138">**Linux Server**</span></span> | [<span data-ttu-id="d454a-139">Script local</span><span class="sxs-lookup"><span data-stu-id="d454a-139">Local script</span></span>](../defender-endpoint/linux-install-manually.md) <br> [<span data-ttu-id="d454a-140">Puppet</span><span class="sxs-lookup"><span data-stu-id="d454a-140">Puppet</span></span>](../defender-endpoint/linux-install-with-puppet.md) <br> [<span data-ttu-id="d454a-141">Ansible</span><span class="sxs-lookup"><span data-stu-id="d454a-141">Ansible</span></span>](../defender-endpoint/linux-install-with-ansible.md)|
| <span data-ttu-id="d454a-142">**iOS**</span><span class="sxs-lookup"><span data-stu-id="d454a-142">**iOS**</span></span>      | [<span data-ttu-id="d454a-143">Basado en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d454a-143">App-based</span></span>](../defender-endpoint/ios-install.md)                                |
| <span data-ttu-id="d454a-144">**Android**</span><span class="sxs-lookup"><span data-stu-id="d454a-144">**Android**</span></span>  | [<span data-ttu-id="d454a-145">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d454a-145">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)               |
