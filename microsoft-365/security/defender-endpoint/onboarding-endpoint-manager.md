---
title: Incorporación con Microsoft Endpoint Manager
description: Obtenga información sobre cómo incorporarse a Microsoft Defender para endpoint con Microsoft Endpoint Manager
keywords: incorporación, configuración, implementación, implementación, administrador de puntos de conexión, Microsoft Defender para endpoint, creación de colecciones, respuesta de detección de puntos de conexión, protección de próxima generación, reducción de superficie de ataque, administrador de puntos de conexión de Microsoft
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e744262cfd63383e69abf02be9fbf91d2d229db2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935262"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="5d1d9-104">Incorporación con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5d1d9-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d1d9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5d1d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="5d1d9-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5d1d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5d1d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d1d9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="5d1d9-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="5d1d9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5d1d9-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5d1d9-110">Este artículo forma parte de la guía de implementación y actúa como un método de incorporación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="5d1d9-111">En el [tema Planeación,](deployment-strategy.md) se proporcionaron varios métodos para incorporar dispositivos al servicio.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="5d1d9-112">En este tema se trata la arquitectura nativa de la nube.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="5d1d9-113">![Imagen de arquitectura nativa de la nube ](images/cloud-native-architecture.png)
 *Diagrama de arquitecturas de entorno*</span><span class="sxs-lookup"><span data-stu-id="5d1d9-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="5d1d9-114">Aunque Defender para endpoint admite la incorporación de varios puntos de conexión y herramientas, este artículo no los cubre.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="5d1d9-115">Para obtener información sobre la incorporación general con otras herramientas y métodos de implementación compatibles, vea [Onboarding overview](onboarding.md).</span><span class="sxs-lookup"><span data-stu-id="5d1d9-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="5d1d9-116">[Microsoft Endpoint Manager es](https://docs.microsoft.com/mem/endpoint-manager-overview) una plataforma de soluciones que unifica varios servicios.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="5d1d9-117">Incluye [Microsoft Intune para](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) la administración de dispositivos basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-117">It includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="5d1d9-118">En este tema se guía a los usuarios en:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-118">This topic guides users in:</span></span>
- <span data-ttu-id="5d1d9-119">Paso 1: Incorporación de dispositivos al servicio mediante la creación de un grupo en Microsoft Endpoint Manager (MEM) para asignar configuraciones en</span><span class="sxs-lookup"><span data-stu-id="5d1d9-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="5d1d9-120">Paso 2: Configuración de las capacidades de Defender para endpoints con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5d1d9-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="5d1d9-121">Esta guía de incorporación le ayudará a seguir los siguientes pasos básicos que debe seguir al usar Microsoft Endpoint Manager:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="5d1d9-122">Identificación de dispositivos o usuarios de destino</span><span class="sxs-lookup"><span data-stu-id="5d1d9-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="5d1d9-123">Creación de un grupo de Azure Active Directory (usuario o dispositivo)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="5d1d9-124">Creación de un perfil de configuración</span><span class="sxs-lookup"><span data-stu-id="5d1d9-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="5d1d9-125">En Microsoft Endpoint Manager, le guiaremos en la creación de una directiva independiente para cada funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="5d1d9-126">Recursos</span><span class="sxs-lookup"><span data-stu-id="5d1d9-126">Resources</span></span>


<span data-ttu-id="5d1d9-127">Estos son los vínculos que necesitará para el resto del proceso:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="5d1d9-128">Portal MEM</span><span class="sxs-lookup"><span data-stu-id="5d1d9-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="5d1d9-129">Centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="5d1d9-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="5d1d9-130">Líneas base de seguridad de Intune</span><span class="sxs-lookup"><span data-stu-id="5d1d9-130">Intune Security baselines</span></span>](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="5d1d9-131">Para obtener más información acerca de Microsoft Endpoint Manager, consulte estos recursos:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- [<span data-ttu-id="5d1d9-132">Página de Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5d1d9-132">Microsoft Endpoint Manager page</span></span>](https://docs.microsoft.com/mem/)
- [<span data-ttu-id="5d1d9-133">Entrada de blog sobre la convergencia de Intune y ConfigMgr</span><span class="sxs-lookup"><span data-stu-id="5d1d9-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="5d1d9-134">Vídeo de introducción en MEM</span><span class="sxs-lookup"><span data-stu-id="5d1d9-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="5d1d9-135">Paso 1: Incorporar dispositivos mediante la creación de un grupo en MEM para asignar configuraciones en</span><span class="sxs-lookup"><span data-stu-id="5d1d9-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="5d1d9-136">Identificar dispositivos o usuarios de destino</span><span class="sxs-lookup"><span data-stu-id="5d1d9-136">Identify target devices or users</span></span>
<span data-ttu-id="5d1d9-137">En esta sección, crearemos un grupo de prueba para asignar las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="5d1d9-138">Intune usa grupos de Azure Active Directory (Azure AD) para administrar dispositivos y usuarios.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="5d1d9-139">Como administrador de Intune, puede configurar grupos que se adapten a sus necesidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="5d1d9-140">Para obtener más información, consulta [Agregar grupos para organizar usuarios y dispositivos.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-140">For more information, see [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="5d1d9-141">Crear un grupo</span><span class="sxs-lookup"><span data-stu-id="5d1d9-141">Create a group</span></span>

1.  <span data-ttu-id="5d1d9-142">Abra el portal de MEM.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5d1d9-143">Abra **Grupos > Nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-144">![Imagen del portal de Microsoft Endpoint Manager1](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="5d1d9-145">Escriba los detalles y cree un nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-146">![Imagen del portal de Microsoft Endpoint Manager2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="5d1d9-147">Agrega el usuario o dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="5d1d9-148">En el **panel > todos los grupos,** abra el nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="5d1d9-149">Seleccione  **Miembros > Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="5d1d9-150">Busca el usuario o dispositivo de prueba y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-151">![Imagen del portal de Microsoft Endpoint Manager3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="5d1d9-152">El grupo de pruebas ahora tiene un miembro que probar.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="5d1d9-153">Paso 2: Crear directivas de configuración para configurar las capacidades de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="5d1d9-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="5d1d9-154">En la siguiente sección, creará una serie de directivas de configuración.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="5d1d9-155">Primero es una directiva de configuración para seleccionar qué grupos de usuarios o dispositivos se incorporarán a Defender for Endpoint:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="5d1d9-156">EDR</span><span class="sxs-lookup"><span data-stu-id="5d1d9-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="5d1d9-157">A continuación, seguirá creando varios tipos diferentes de directivas de seguridad de extremo:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="5d1d9-158">Protección de última generación</span><span class="sxs-lookup"><span data-stu-id="5d1d9-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="5d1d9-159">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="5d1d9-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="5d1d9-160">EDR</span><span class="sxs-lookup"><span data-stu-id="5d1d9-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="5d1d9-161">Abra el portal de MEM.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5d1d9-162">Vaya a **Seguridad de > de detección y respuesta del extremo**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="5d1d9-163">Haga clic en **Crear perfil**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-164">![Imagen del portal de Microsoft Endpoint Manager4](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="5d1d9-165">En **Plataforma, selecciona Windows 10 y versiones posteriores, Perfil: detección de puntos de** conexión y respuesta > Crear .</span><span class="sxs-lookup"><span data-stu-id="5d1d9-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="5d1d9-166">Escriba un nombre y una descripción y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-167">![Imagen del portal de Microsoft Endpoint Manager5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="5d1d9-168">Seleccione la configuración según sea necesario y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-169">![Imagen del portal de Microsoft Endpoint Manager6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d1d9-170">En este caso, esto se ha rellenado automáticamente como Defender para endpoint ya se ha integrado con Intune.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="5d1d9-171">Para obtener más información sobre la integración, vea [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span><span class="sxs-lookup"><span data-stu-id="5d1d9-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="5d1d9-172">La siguiente imagen es un ejemplo de lo que verá cuando Microsoft Defender para Endpoint no esté integrado con Intune:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Imagen del portal de Microsoft Endpoint Manager7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="5d1d9-174">Agregue etiquetas de ámbito si es necesario y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-175">![Imagen del portal de Microsoft Endpoint Manager8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="5d1d9-176">Para agregar un grupo de prueba, haga clic en **Seleccionar grupos para incluir** y elegir el grupo y, a continuación, seleccione  **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-177">![Imagen del portal de Microsoft Endpoint Manager9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="5d1d9-178">Revise y acepte y, a continuación,  **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-179">![Imagen del portal de Microsoft Endpoint Manager10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="5d1d9-180">Puede ver la directiva completada.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-181">![Imagen del portal de Microsoft Endpoint Manager11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="5d1d9-182">Protección de última generación</span><span class="sxs-lookup"><span data-stu-id="5d1d9-182">Next-generation protection</span></span>

1.  <span data-ttu-id="5d1d9-183">Abra el portal de MEM.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5d1d9-184">Vaya a **Endpoint security > Antivirus > Create Policy**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-185">![Imagen del portal de Microsoft Endpoint Manager12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="5d1d9-186">Seleccione **Plataforma - Windows 10 y versiones posteriores - Windows y Perfil : Antivirus** de Microsoft Defender > Crear .</span><span class="sxs-lookup"><span data-stu-id="5d1d9-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="5d1d9-187">Escriba el nombre y la descripción y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-188">![Imagen del portal de Microsoft Endpoint Manager13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="5d1d9-189">En la **página Configuración:** establezca las configuraciones que necesita para Antivirus de Microsoft Defender (protección en la nube, exclusiones, Real-Time protección y corrección).</span><span class="sxs-lookup"><span data-stu-id="5d1d9-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-190">![Imagen del portal de Microsoft Endpoint Manager14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="5d1d9-191">Agregue etiquetas de ámbito si es necesario y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-192">![Imagen del portal de Microsoft Endpoint Manager15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="5d1d9-193">Seleccione los grupos que desea incluir, asígnelos al grupo de prueba y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-194">![Imagen del portal de Microsoft Endpoint Manager16](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="5d1d9-195">Revise y cree y, a continuación,  **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-196">![Imagen del portal de Microsoft Endpoint Manager17](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="5d1d9-197">Verá la directiva de configuración que creó.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-198">![Imagen del portal de Microsoft Endpoint Manager18](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="5d1d9-199">Reducción de superficie de ataque: reglas de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="5d1d9-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="5d1d9-200">Abra el portal de MEM.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5d1d9-201">Navegue hasta **Endpoint security > Reducción de superficie de ataque**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="5d1d9-202">Seleccione  **Crear directiva**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="5d1d9-203">Selecciona **Plataforma - Windows 10 y versiones posteriores: Perfil: reglas de** reducción de superficie > Crear .</span><span class="sxs-lookup"><span data-stu-id="5d1d9-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-204">![Imagen del portal de Microsoft Endpoint Manager19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="5d1d9-205">Escriba un nombre y una descripción y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-206">![Imagen del portal de Microsoft Endpoint Manager20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="5d1d9-207">En la **página Configuración:** Establezca las configuraciones que necesita para las reglas de reducción de superficie de ataque y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d1d9-208">Configuraremos todas las reglas de reducción de superficie de ataque en Auditar.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="5d1d9-209">Para obtener más información, consulta [Reglas de reducción de superficie de ataque](attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="5d1d9-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-210">![Imagen del portal de Microsoft Endpoint Manager21](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="5d1d9-211">Agregue etiquetas de ámbito según sea necesario y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-212">![Imagen del portal de Microsoft Endpoint Manager22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="5d1d9-213">Seleccione los grupos que desea incluir y asignar al grupo de prueba y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-214">![Imagen del portal de Microsoft Endpoint Manager23](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="5d1d9-215">Revise los detalles y, a continuación,  **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-216">![Imagen del portal de Microsoft Endpoint Manager24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="5d1d9-217">Ver la directiva.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-218">![Imagen del portal de Microsoft Endpoint Manager25](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="5d1d9-219">Reducción de superficie de ataque: protección web</span><span class="sxs-lookup"><span data-stu-id="5d1d9-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="5d1d9-220">Abra el portal de MEM.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5d1d9-221">Navegue hasta **Endpoint security > Reducción de superficie de ataque**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="5d1d9-222">Seleccione  **Crear directiva**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="5d1d9-223">Seleccione **Windows 10 y versiones posteriores: protección > Crear**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-224">![Imagen del portal de Microsoft Endpoint Manager26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="5d1d9-225">Escriba un nombre y una descripción y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-226">![Imagen del portal de Microsoft Endpoint Manager27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="5d1d9-227">En la **página Configuración:** Establezca las configuraciones que necesita para Protección web y, a continuación,  **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d1d9-228">Estamos configurando Protección web para bloquear.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="5d1d9-229">Para obtener más información, vea [Web Protection](web-protection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5d1d9-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-230">![Imagen del portal de Microsoft Endpoint Manager28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="5d1d9-231">Agregue **etiquetas de ámbito según > Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-232">![Imagen del portal de Microsoft Endpoint Manager29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="5d1d9-233">Seleccione **Asignar a grupo de prueba > Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-234">![Imagen del portal de Microsoft Endpoint Manager30](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="5d1d9-235">Seleccione **Revisar y Crear > Crear**.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-236">![Imagen del portal de Microsoft Endpoint Manager31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="5d1d9-237">Ver la directiva.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-238">![Imagen del portal de Microsoft Endpoint Manager32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="5d1d9-239">Validar opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="5d1d9-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="5d1d9-240">Confirmar que se han aplicado directivas</span><span class="sxs-lookup"><span data-stu-id="5d1d9-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="5d1d9-241">Una vez asignada la directiva de configuración, llevará algún tiempo aplicarla.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="5d1d9-242">Para obtener información sobre el tiempo, consulta [Información de configuración de Intune](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span><span class="sxs-lookup"><span data-stu-id="5d1d9-242">For information on timing, see [Intune configuration information](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="5d1d9-243">Para confirmar que la directiva de configuración se ha aplicado al dispositivo de prueba, siga el siguiente proceso para cada directiva de configuración.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="5d1d9-244">Abra el portal de MEM y vaya a la directiva correspondiente, como se muestra en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="5d1d9-245">En el ejemplo siguiente se muestra la configuración de protección de próxima generación.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-246">[![Imagen del portal de Microsoft Endpoint Manager33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="5d1d9-247">Seleccione la **directiva de configuración** para ver el estado de la directiva.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-248">[![Imagen del portal de Microsoft Endpoint Manager34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="5d1d9-249">Selecciona  **Estado del dispositivo** para ver el estado.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-250">[![Imagen del portal de Microsoft Endpoint Manager35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="5d1d9-251">Seleccione  **Estado de usuario** para ver el estado.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-252">[![Imagen del portal de Microsoft Endpoint Manager36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="5d1d9-253">Seleccione  **Estado por configuración para** ver el estado.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="5d1d9-254">Esta vista es muy útil para identificar cualquier configuración que entre en conflicto con otra directiva.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-255">[![Imagen del portal de Microsoft Endpoint Manager37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="5d1d9-256">EDR</span><span class="sxs-lookup"><span data-stu-id="5d1d9-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="5d1d9-257">Antes de aplicar la configuración, no se debe iniciar el servicio defender para Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-258">[![Imagen del panel de servicios1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="5d1d9-259">Una vez aplicada la configuración, debe iniciarse el servicio defender para Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-260">[![Imagen del panel de servicios2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="5d1d9-261">Una vez que los servicios se ejecutan en el dispositivo, el dispositivo aparece en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-262">[![Imagen del Centro de seguridad de Microsoft Defender ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="5d1d9-263">Protección de última generación</span><span class="sxs-lookup"><span data-stu-id="5d1d9-263">Next-generation protection</span></span>

1.  <span data-ttu-id="5d1d9-264">Antes de aplicar la directiva en un dispositivo de prueba, debes poder administrar manualmente la configuración como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-265">![Imagen de la página de configuración1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="5d1d9-266">Después de aplicar la directiva, no debería poder administrar manualmente la configuración.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d1d9-267">En la siguiente **imagen, se muestran como administrados Activar** la protección entregada en la nube y Activar la protección en tiempo real. </span><span class="sxs-lookup"><span data-stu-id="5d1d9-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5d1d9-268">![Imagen de la página de configuración2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="5d1d9-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="5d1d9-269">Reducción de superficie de ataque: reglas de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="5d1d9-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="5d1d9-270">Antes de aplicar la directiva en un dispositivo de prueba, escriba una ventana de PowerShell y escriba `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="5d1d9-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="5d1d9-271">Esto debe responder con las siguientes líneas sin contenido:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="5d1d9-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="5d1d9-273">AttackSurfaceReductionRules_Actions:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="5d1d9-274">AttackSurfaceReductionRules_Ids:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![Imagen de la línea de comandos1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="5d1d9-276">Después de aplicar la directiva en un dispositivo de prueba, abra un Windows de PowerShell y escriba `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="5d1d9-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="5d1d9-277">Esto debe responder con las siguientes líneas con contenido como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="5d1d9-277">This should respond with the following lines with content as shown below:</span></span>

    ![Imagen de la línea de comandos2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="5d1d9-279">Reducción de superficie de ataque: protección web</span><span class="sxs-lookup"><span data-stu-id="5d1d9-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="5d1d9-280">En el dispositivo de prueba, abra un Windows de PowerShell y escriba `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="5d1d9-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="5d1d9-281">Esto debe responder con un 0 como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-281">This should respond with a 0 as shown below.</span></span>

    ![Imagen de la línea de comandos3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="5d1d9-283">Después de aplicar la directiva, abra un Windows de PowerShell y escriba `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="5d1d9-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="5d1d9-284">Esto debe responder con un 1 como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="5d1d9-284">This should respond with a 1 as shown below.</span></span>

    ![Imagen de la línea de comandos4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
