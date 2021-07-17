---
title: Habilitar Microsoft Defender para la evaluación de extremo, activar la evaluación para MDE
description: Habilitar el entorno Microsoft 365 Defender prueba o piloto, incluida la comprobación del estado de la licencia y los puntos de incorporación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458582"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a><span data-ttu-id="19a62-103">Habilitar el entorno de evaluación de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="19a62-103">Enable Microsoft Defender for Endpoint evaluation environment</span></span>


<span data-ttu-id="19a62-104">Este artículo le guiará a través de los pasos para configurar el entorno de evaluación de Microsoft Defender para endpoint mediante dispositivos de producción.</span><span class="sxs-lookup"><span data-stu-id="19a62-104">This article will guide you through the steps on setting up the evaluation environment for Microsoft Defender for Endpoint using production devices.</span></span> 


>[!TIP]
><span data-ttu-id="19a62-105">Microsoft Defender para endpoint también incluye un laboratorio de evaluación del producto donde puede agregar dispositivos preconfigurados y ejecutar simulaciones para evaluar las capacidades de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="19a62-105">Microsoft Defender for Endpoint also comes with an in-product evaluation lab where you can add pre-configured devices and run simulations to evaluate the capabilities of the platform.</span></span> <span data-ttu-id="19a62-106">El laboratorio viene con una experiencia de configuración simplificada que puede ayudar a demostrar rápidamente el valor de Microsoft Defender para Enpdoint, que incluye instrucciones para muchas características como la búsqueda avanzada y el análisis de amenazas.</span><span class="sxs-lookup"><span data-stu-id="19a62-106">The lab comes with a simplified set-up experience that can help quickly demonstrate the value of Microsoft Defender for Enpdoint including guidance for many features like advanced hunting and threat analytics.</span></span> <span data-ttu-id="19a62-107">Para obtener más información, vea [Evaluate capabilities](/defender-endpoint/evaluation-lab.md).</span><span class="sxs-lookup"><span data-stu-id="19a62-107">For more information, see [Evaluate capabilities](/defender-endpoint/evaluation-lab.md).</span></span> <br> <span data-ttu-id="19a62-108">La principal diferencia entre las instrucciones proporcionadas en este artículo y el laboratorio de evaluación es que el entorno de evaluación usa dispositivos de producción, mientras que el laboratorio de evaluación usa dispositivos que no son de producción.</span><span class="sxs-lookup"><span data-stu-id="19a62-108">The main difference between the guidance provided in this article and the evaluation lab is the evaluation environment uses production devices whereas the evaluation lab uses non-production devices.</span></span> 

<span data-ttu-id="19a62-109">Siga estos pasos para habilitar la evaluación de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="19a62-109">Use the following steps to enable the evaluation for Microsoft Defender for Endpoint.</span></span>

![Pasos para habilitar Microsoft Defender para endpoint en el entorno de evaluación de Microsoft Defender](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [<span data-ttu-id="19a62-111">Paso 1. Comprobar el estado de la licencia</span><span class="sxs-lookup"><span data-stu-id="19a62-111">Step 1. Check license state</span></span>](#step-1-check-license-state)
- [<span data-ttu-id="19a62-112">Paso 2. Puntos de conexión integrados</span><span class="sxs-lookup"><span data-stu-id="19a62-112">Step 2. Onboard endpoints</span></span>](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a><span data-ttu-id="19a62-113">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="19a62-113">Step 1.</span></span> <span data-ttu-id="19a62-114">Comprobar el estado de la licencia</span><span class="sxs-lookup"><span data-stu-id="19a62-114">Check license state</span></span>

<span data-ttu-id="19a62-115">Primero tendrá que comprobar el estado de la licencia para comprobar que se aprovisionó correctamente.</span><span class="sxs-lookup"><span data-stu-id="19a62-115">You'll first need to check the license state to verify that it was properly provisioned.</span></span> <span data-ttu-id="19a62-116">Puede hacerlo a través del Centro de administración o a través **del portal Microsoft Azure .**</span><span class="sxs-lookup"><span data-stu-id="19a62-116">You can do this through the admin center or through the **Microsoft Azure portal**.</span></span>


1. <span data-ttu-id="19a62-117">Para ver las licencias, vaya al **portal de** Microsoft Azure y vaya a la sección Microsoft Azure licencia [del portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="19a62-117">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Imagen de la página licencias de Azure](../../media/defender/atp-licensing-azure-portal.png)

1. <span data-ttu-id="19a62-119">Como alternativa, en el Centro de administración, vaya a **Suscripciones de**  >  **facturación.**</span><span class="sxs-lookup"><span data-stu-id="19a62-119">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="19a62-120">En la pantalla, verá todas las licencias aprovisionadas y su estado **actual.**</span><span class="sxs-lookup"><span data-stu-id="19a62-120">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Imagen de las licencias de facturación](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="19a62-122">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="19a62-122">Step 2.</span></span> <span data-ttu-id="19a62-123">Incorporación de puntos de conexión con cualquiera de las herramientas de administración admitidas</span><span class="sxs-lookup"><span data-stu-id="19a62-123">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="19a62-124">Después de comprobar que el estado de la licencia se ha aprovisionado correctamente, puede iniciar la incorporación de dispositivos al servicio.</span><span class="sxs-lookup"><span data-stu-id="19a62-124">After verifying that the license state has been provisioned properly, you can start onboarding devices to the service.</span></span> 

<span data-ttu-id="19a62-125">Con el fin de evaluar Microsoft Defender para Endpoint, recomendamos elegir un par de dispositivos Windows 10 para realizar la evaluación.</span><span class="sxs-lookup"><span data-stu-id="19a62-125">For the purpose of evaluating Microsoft Defender for Endpoint, we recommend choosing a couple of Windows 10 devices to conduct the evaluation on.</span></span> 

<span data-ttu-id="19a62-126">En [el tema Plan deployment](../defender-endpoint/deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="19a62-126">The [Plan deployment](../defender-endpoint/deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="19a62-127">Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtenga información sobre las herramientas y métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="19a62-127">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a><span data-ttu-id="19a62-128">Opciones de la herramienta de incorporación</span><span class="sxs-lookup"><span data-stu-id="19a62-128">Onboarding tool options</span></span>

<span data-ttu-id="19a62-129">En la tabla siguiente se enumeran las herramientas disponibles en función del extremo que necesita incorporar.</span><span class="sxs-lookup"><span data-stu-id="19a62-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

<span data-ttu-id="19a62-130">Punto de conexión</span><span class="sxs-lookup"><span data-stu-id="19a62-130">Endpoint</span></span> | <span data-ttu-id="19a62-131">Opciones de herramientas</span><span class="sxs-lookup"><span data-stu-id="19a62-131">Tool options</span></span>
:---|:---
<span data-ttu-id="19a62-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="19a62-132">**Windows**</span></span> | <span data-ttu-id="19a62-133">[Script local (hasta 10 dispositivos),](../defender-endpoint/configure-endpoints-script.md)Directiva de grupo [,](../defender-endpoint/configure-endpoints-gp.md) [Microsoft Endpoint Manager/ Administrador](../defender-endpoint/configure-endpoints-mdm.md)de dispositivos móviles , [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md), [scripts VDI](../defender-endpoint/configure-endpoints-vdi.md), [Integración con Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span><span class="sxs-lookup"><span data-stu-id="19a62-133">[Local script (up to 10 devices)](../defender-endpoint/configure-endpoints-script.md),  [Group Policy](../defender-endpoint/configure-endpoints-gp.md),  [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md),  [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md),  [VDI scripts](../defender-endpoint/configure-endpoints-vdi.md),  [Integration with Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span></span>
<span data-ttu-id="19a62-134">**macOS**</span><span class="sxs-lookup"><span data-stu-id="19a62-134">**macOS**</span></span> | <span data-ttu-id="19a62-135">[Scripts locales](../defender-endpoint/mac-install-manually.md), [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md), [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md), Administración [de dispositivos móviles](../defender-endpoint/mac-install-with-other-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="19a62-135">[Local scripts](../defender-endpoint/mac-install-manually.md),  [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md),  [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md),  [Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md)</span></span>
<span data-ttu-id="19a62-136">**Servidor Linux**</span><span class="sxs-lookup"><span data-stu-id="19a62-136">**Linux Server**</span></span> | <span data-ttu-id="19a62-137">[Script local](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span><span class="sxs-lookup"><span data-stu-id="19a62-137">[Local script](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span></span>
<span data-ttu-id="19a62-138">**iOS**</span><span class="sxs-lookup"><span data-stu-id="19a62-138">**iOS**</span></span> | [<span data-ttu-id="19a62-139">Basado en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="19a62-139">App-based</span></span>](../defender-endpoint/ios-install.md)
<span data-ttu-id="19a62-140">**Android**</span><span class="sxs-lookup"><span data-stu-id="19a62-140">**Android**</span></span> | [<span data-ttu-id="19a62-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="19a62-141">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)



## <a name="next-step"></a><span data-ttu-id="19a62-142">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="19a62-142">Next step</span></span>
[<span data-ttu-id="19a62-143">Configurar el piloto de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="19a62-143">Setup the pilot for Microsoft Defender for Endpoint</span></span>](eval-defender-endpoint-pilot.md)
 
<span data-ttu-id="19a62-144">Vuelva a la introducción a [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="19a62-144">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="19a62-145">Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="19a62-145">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>