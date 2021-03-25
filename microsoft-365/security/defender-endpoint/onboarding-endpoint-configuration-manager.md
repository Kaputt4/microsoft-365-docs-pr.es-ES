---
title: Incorporación con Microsoft Endpoint Configuration Manager
description: Obtenga información sobre cómo incorporarse a Microsoft Defender para endpoint con Microsoft Endpoint Configuration Manager
keywords: incorporación, configuración, implementación, implementación, administrador de configuración de puntos de conexión, mdatp, protección contra amenazas avanzada, creación de colecciones, respuesta de detección de puntos de conexión, protección de próxima generación, reducción de superficie de ataque, administrador de configuración de puntos de conexión de Microsoft
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
ms.openlocfilehash: 31c946ccad84aca3b2fc86c95655cea9e66e182f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186406"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="bfcd2-104">Incorporación con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bfcd2-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bfcd2-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bfcd2-105">**Applies to:**</span></span>
- [<span data-ttu-id="bfcd2-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bfcd2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bfcd2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfcd2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bfcd2-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="bfcd2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bfcd2-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="bfcd2-110">Este artículo forma parte de la guía de implementación y actúa como un método de incorporación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="bfcd2-111">En el [tema Planeación,](deployment-strategy.md) se proporcionaron varios métodos para incorporar dispositivos al servicio.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="bfcd2-112">En este tema se trata la arquitectura de administración en colaboración.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="bfcd2-113">![Imagen de arquitectura nativa de la nube ](images/co-management-architecture.png)
 *Diagrama de arquitecturas de entorno*</span><span class="sxs-lookup"><span data-stu-id="bfcd2-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="bfcd2-114">Aunque Defender para endpoint admite la incorporación de varios puntos de conexión y herramientas, este artículo no los cubre.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="bfcd2-115">Para obtener información sobre la incorporación general con otras herramientas y métodos de implementación compatibles, vea [Onboarding overview](onboarding.md).</span><span class="sxs-lookup"><span data-stu-id="bfcd2-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="bfcd2-116">En este tema se guía a los usuarios en:</span><span class="sxs-lookup"><span data-stu-id="bfcd2-116">This topic guides users in:</span></span>
- <span data-ttu-id="bfcd2-117">Paso 1: Incorporación de dispositivos Windows al servicio</span><span class="sxs-lookup"><span data-stu-id="bfcd2-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="bfcd2-118">Paso 2: Configuración de las capacidades de Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="bfcd2-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="bfcd2-119">Esta guía de incorporación le ayudará a seguir los siguientes pasos básicos que debe seguir al usar Microsoft Endpoint Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="bfcd2-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="bfcd2-120">**Creación de una colección en Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="bfcd2-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="bfcd2-121">**Configuración de Las capacidades de Microsoft Defender para endpoints con Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="bfcd2-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="bfcd2-122">Solo los dispositivos Windows se tratan en esta implementación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="bfcd2-123">Paso 1: Incorporar dispositivos Windows con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bfcd2-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="bfcd2-124">Creación de colecciones</span><span class="sxs-lookup"><span data-stu-id="bfcd2-124">Collection creation</span></span>
<span data-ttu-id="bfcd2-125">Para incorporar dispositivos Windows 10 con Microsoft Endpoint Configuration Manager, la implementación puede dirigirse a una colección existente o se puede crear una nueva colección para pruebas.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="bfcd2-126">La incorporación mediante herramientas como la directiva de grupo o el método manual no instala ningún agente en el sistema.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="bfcd2-127">En la consola de Microsoft Endpoint Configuration Manager, el proceso de incorporación se configurará como parte de la configuración de cumplimiento de la consola.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="bfcd2-128">Cualquier sistema que reciba esta configuración necesaria mantendrá esa configuración mientras el cliente de Configuration Manager siga recibiendo esta directiva desde el punto de administración.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="bfcd2-129">Siga los pasos siguientes para incorporar puntos de conexión con Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="bfcd2-130">En la consola de Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Device \> \> Collections**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Imagen del asistente de Microsoft Endpoint Configuration Manager1](images/configmgr-device-collections.png)

2. <span data-ttu-id="bfcd2-132">Haga clic con el **botón secundario en Colección de** dispositivos y seleccione Crear colección de **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Imagen del Asistente para Microsoft Endpoint Configuration Manager2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="bfcd2-134">Proporcione una **colección Name** y **Limiting y,** a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Imagen del Asistente para Microsoft Endpoint Configuration Manager3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="bfcd2-136">Seleccione **Agregar regla** y elija Regla de **consulta**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Imagen del Asistente para Microsoft Endpoint Configuration Manager4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="bfcd2-138">Haga **clic en Siguiente** en el Asistente para pertenencia **directa** y haga clic en Editar **instrucción query**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Imagen del Asistente para Microsoft Endpoint Configuration Manager5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="bfcd2-140">Seleccione **Criterios** y, a continuación, elija el icono de estrella.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Imagen del Asistente para Microsoft Endpoint Configuration Manager6](images/configmgr-criteria.png)

7. <span data-ttu-id="bfcd2-142">Mantenga el tipo de criterio como valor **simple**,  elija dónde como Sistema operativo **-** número de compilación , operador como mayor o igual que y valor **14393** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Imagen del Asistente para Microsoft Endpoint Configuration Manager7](images/configmgr-simple-value.png)

8. <span data-ttu-id="bfcd2-144">Seleccione **Siguiente** y **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-144">Select **Next** and **Close**.</span></span>

    ![Imagen del Asistente para Microsoft Endpoint Configuration Manager8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="bfcd2-146">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-146">Select **Next**.</span></span>

    ![Imagen del Asistente para Microsoft Endpoint Configuration Manager9](images/configmgr-confirm.png)


<span data-ttu-id="bfcd2-148">Después de completar esta tarea, ahora tienes una colección de dispositivos con todos los puntos de conexión de Windows 10 en el entorno.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="bfcd2-149">Paso 2: Configurar Microsoft Defender para las funcionalidades de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bfcd2-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="bfcd2-150">En esta sección se le guía en la configuración de las siguientes funcionalidades con Microsoft Endpoint Configuration Manager en dispositivos Windows:</span><span class="sxs-lookup"><span data-stu-id="bfcd2-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="bfcd2-151">**Detección y respuesta de puntos de conexión.**</span><span class="sxs-lookup"><span data-stu-id="bfcd2-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="bfcd2-152">**Protección de última generación**</span><span class="sxs-lookup"><span data-stu-id="bfcd2-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="bfcd2-153">**Reducción de la superficie expuesta a ataques**</span><span class="sxs-lookup"><span data-stu-id="bfcd2-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="bfcd2-154">Detección y respuesta de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="bfcd2-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bfcd2-155">Windows 10</span></span>
<span data-ttu-id="bfcd2-156">Desde el Centro de seguridad de Microsoft Defender es posible descargar la directiva ".onboarding" que se puede usar para crear la directiva en System Center Configuration Manager e implementarla en dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="bfcd2-157">En un Portal del Centro de seguridad de Microsoft Defender, seleccione Configuración y, a [continuación, Incorporación](https://securitycenter.windows.com/preferences2/onboarding).</span><span class="sxs-lookup"><span data-stu-id="bfcd2-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="bfcd2-158">En Método de implementación, seleccione la versión compatible de **Microsoft Endpoint Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Imagen del Asistente para incorporación de Microsoft Defender para endpoint10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="bfcd2-160">Seleccione **Descargar paquete**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-160">Select **Download package**.</span></span>

    ![Imagen del Asistente para la incorporación de Microsoft Defender para puntos de conexión11](images/mdatp-download-package.png)

4. <span data-ttu-id="bfcd2-162">Guarde el paquete en una ubicación accesible.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="bfcd2-163">En Microsoft Endpoint Configuration Manager, vaya a: **Assets and Compliance > Overview > Endpoint Protection > Directivas de ATP** de Microsoft Defender .</span><span class="sxs-lookup"><span data-stu-id="bfcd2-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="bfcd2-164">Haga clic con el botón **secundario en Directivas de ATP de Microsoft Defender** y seleccione Crear directiva de ATP de Microsoft **Defender**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Imagen del Asistente para Microsoft Endpoint Configuration Manager12](images/configmgr-create-policy.png)

7. <span data-ttu-id="bfcd2-166">Escriba el nombre y la descripción, compruebe **que la incorporación** está seleccionada y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Imagen del Asistente para Microsoft Endpoint Configuration Manager13](images/configmgr-policy-name.png)


8. <span data-ttu-id="bfcd2-168">Haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-168">Click **Browse**.</span></span>

9. <span data-ttu-id="bfcd2-169">Vaya a la ubicación del archivo descargado desde el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="bfcd2-170">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-170">Click **Next**.</span></span>
11. <span data-ttu-id="bfcd2-171">Configure el agente con los ejemplos adecuados (**Ninguno** o **Todos los tipos de archivo**).</span><span class="sxs-lookup"><span data-stu-id="bfcd2-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Imagen de las opciones de configuración1](images/configmgr-config-settings.png)

12. <span data-ttu-id="bfcd2-173">Seleccione la telemetría adecuada (**Normal** o **Expedited**) y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Imagen de las opciones de configuración2](images/configmgr-telemetry.png)

14. <span data-ttu-id="bfcd2-175">Compruebe la configuración y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-175">Verify the configuration, then click **Next**.</span></span>

     ![Imagen de configuración3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="bfcd2-177">Haga **clic en** Cerrar cuando se complete el Asistente.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="bfcd2-178">En la consola de Microsoft Endpoint Configuration Manager, haga clic con el botón secundario en la directiva defender para puntos de conexión que acaba de crear y seleccione **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Imagen de las opciones de configuración4](images/configmgr-deploy.png)

17. <span data-ttu-id="bfcd2-180">En el panel derecho, seleccione la colección creada anteriormente y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Imagen de configuración5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="bfcd2-182">Versiones anteriores de Windows Client (Windows 7 y Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="bfcd2-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="bfcd2-183">Siga los pasos siguientes para identificar el identificador del área de trabajo de punto de conexión y la clave de área de trabajo de Defender for Endpoint, que serán necesarios para la incorporación de versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="bfcd2-184">En un Portal del Centro de seguridad de Microsoft Defender, seleccione **Configuración > incorporación**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="bfcd2-185">En sistema operativo, **elija Windows 7 SP1 y 8.1**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="bfcd2-186">Copie el **identificador del área de trabajo** y la clave de área de **trabajo** y guárdelos.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="bfcd2-187">Se usarán más adelante en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-187">They will be used later in the process.</span></span>

    ![Imagen de incorporación](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="bfcd2-189">Instale Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="bfcd2-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="bfcd2-190">MMA actualmente (a partir de enero de 2019) es compatible con los siguientes sistemas operativos Windows:</span><span class="sxs-lookup"><span data-stu-id="bfcd2-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="bfcd2-191">SKU de servidor: Windows Server 2008 SP1 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="bfcd2-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="bfcd2-192">SKU de cliente: Windows 7 SP1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="bfcd2-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="bfcd2-193">El agente mma tendrá que instalarse en dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="bfcd2-194">Para instalar el agente, algunos sistemas [](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) tendrán que descargar la actualización para la experiencia del cliente y la telemetría de diagnóstico para recopilar los datos con MMA.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="bfcd2-195">Estas versiones del sistema incluyen, pero no pueden limitarse a:</span><span class="sxs-lookup"><span data-stu-id="bfcd2-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="bfcd2-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="bfcd2-196">Windows 8.1</span></span>

    -   <span data-ttu-id="bfcd2-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="bfcd2-197">Windows 7</span></span>

    -   <span data-ttu-id="bfcd2-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="bfcd2-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="bfcd2-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bfcd2-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="bfcd2-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="bfcd2-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="bfcd2-201">Específicamente, para Windows 7 SP1, deben instalarse las siguientes revisiones:</span><span class="sxs-lookup"><span data-stu-id="bfcd2-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="bfcd2-202">Instalar [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="bfcd2-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="bfcd2-203">Instale .NET Framework [4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) **o** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span><span class="sxs-lookup"><span data-stu-id="bfcd2-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="bfcd2-204">No instale ambos en el mismo sistema.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="bfcd2-205">Si usa un proxy para conectarse a Internet, consulte la sección Configurar opciones de proxy.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="bfcd2-206">Una vez completado, debería ver puntos de conexión incorporados en el portal en una hora.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="bfcd2-207">Protección de última generación</span><span class="sxs-lookup"><span data-stu-id="bfcd2-207">Next generation protection</span></span> 
<span data-ttu-id="bfcd2-208">El Antivirus de Microsoft Defender es una solución antimalware integrada que proporciona una protección de última generación para equipos de escritorio, equipos portátiles y servidores.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="bfcd2-209">En la consola de Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection \> \> \> Antimalware Polices** y elija **Create Antimalware Policy**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Imagen de la directiva antimalware](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="bfcd2-211">Seleccione **Exámenes programados,** Configuración del examen **,** Acciones predeterminadas **,** Protección en tiempo **real** **,** Configuración de exclusión **,** Avanzadas , Invalidaciones de **amenazas,** Servicio **de protección** en la nube y Actualizaciones de inteligencia de **seguridad** y elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Imagen del panel de protección de próxima generación1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="bfcd2-213">En determinados sectores o en algunos clientes empresariales selectos puede haber necesidades específicas sobre cómo se configura Antivirus.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="bfcd2-214">Examen rápido frente a examen completo y examen personalizado</span><span class="sxs-lookup"><span data-stu-id="bfcd2-214">Quick scan versus full scan and custom scan</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="bfcd2-215">Para obtener más información, consulta [Marco de configuración de seguridad de Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="bfcd2-215">For more details, see [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Imagen del panel de protección de próxima generación2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Imagen del panel de protección de próxima generación3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Imagen del panel de protección de próxima generación4](images/a28afc02c1940d5220b233640364970c.png)

    ![Imagen del panel de protección de próxima generación5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Imagen del panel de protección de próxima generación6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Imagen del panel de protección de próxima generación7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Imagen del panel de protección de próxima generación8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Imagen del panel de protección de próxima generación9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="bfcd2-224">Haga clic con el botón secundario en la directiva antimalware recién creada y seleccione **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Imagen del panel de protección de próxima generación10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="bfcd2-226">Dirigir la nueva directiva antimalware a la colección de Windows 10 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Imagen del panel de protección de próxima generación11](images/configmgr-select-collection.png)

<span data-ttu-id="bfcd2-228">Después de completar esta tarea, ahora ha configurado correctamente Windows Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="bfcd2-229">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="bfcd2-229">Attack surface reduction</span></span>
<span data-ttu-id="bfcd2-230">El pilar de reducción de superficie de ataque de Defender para endpoint incluye el conjunto de características que está disponible en Protección contra vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="bfcd2-231">Reglas de reducción de superficie de ataque (ASR), Acceso controlado a carpetas, Protección de red y Protección contra vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="bfcd2-232">Todas estas características proporcionan un modo de auditoría y un modo de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="bfcd2-233">En el modo de auditoría no hay ningún impacto para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="bfcd2-234">Todo lo que hace es recopilar telemetría adicional y hacer que esté disponible en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="bfcd2-235">El objetivo con una implementación es mover paso a paso los controles de seguridad al modo de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="bfcd2-236">Para establecer reglas ASR en modo auditoría:</span><span class="sxs-lookup"><span data-stu-id="bfcd2-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="bfcd2-237">En la consola de Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** y elija **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Imagen de la consola de Microsoft Endpoint Configuration Manager0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="bfcd2-239">Selecciona **Reducción de superficie de ataque**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="bfcd2-240">Establezca reglas en **Auditar** y haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Imagen de la consola de Microsoft Endpoint Configuration Manager1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="bfcd2-242">Para confirmar la nueva directiva de Protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Imagen de la consola de Microsoft Endpoint Configuration Manager2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="bfcd2-244">Una vez creada la directiva, haga clic **en Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-244">Once the policy is created click **Close**.</span></span>

    ![Imagen de la consola de Microsoft Endpoint Configuration Manager3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Imagen de la consola de Microsoft Endpoint Manager1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="bfcd2-247">Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Imagen de la consola de Microsoft Endpoint Configuration Manager4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="bfcd2-249">Dirigir la directiva a la colección de Windows 10 recién creada y hacer clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Imagen de la consola de Microsoft Endpoint Configuration Manager5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="bfcd2-251">Después de completar esta tarea, ahora ha configurado correctamente las reglas de ASR en el modo de auditoría.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="bfcd2-252">A continuación se indican pasos adicionales para comprobar si las reglas ASR se aplican correctamente a los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="bfcd2-253">(Esto puede tardar unos minutos)</span><span class="sxs-lookup"><span data-stu-id="bfcd2-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="bfcd2-254">Desde un explorador web, vaya a <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="bfcd2-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="bfcd2-255">Seleccione **Administración de configuración** en el menú del lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="bfcd2-256">Haz **clic en Ir a la administración de superficies de** ataque en el panel Administración de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Imagen de la administración de superficies de ataque](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="bfcd2-258">Haga clic **en la pestaña** Configuración en Informes de reglas de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="bfcd2-259">Muestra información general sobre la configuración de reglas ASR y el estado de las reglas ASR en cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![Una captura de pantalla de informes de reglas de reducción de superficie de ataque1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="bfcd2-261">Haga clic en cada dispositivo para ver los detalles de configuración de las reglas de ASR.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-261">Click each device shows configuration details of ASR rules.</span></span>

    ![Una captura de pantalla de informes de reglas de reducción de superficie de ataque2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="bfcd2-263">Consulte [Optimizar la implementación y detecciones](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   de reglas ASR para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-263">See [Optimize ASR rule deployment and detections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="bfcd2-264">Establecer reglas de protección de red en modo auditoría:</span><span class="sxs-lookup"><span data-stu-id="bfcd2-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="bfcd2-265">En la consola de Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** y elija **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Una captura de pantalla de System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="bfcd2-267">Seleccione **Protección de red**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="bfcd2-268">Establezca la configuración en **Auditar** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![Una captura de pantalla de System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="bfcd2-270">Para confirmar la nueva directiva de Protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![Una captura de pantalla Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="bfcd2-272">Una vez creada la directiva, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-272">Once the policy is created click on **Close**.</span></span>

    ![Una captura de pantalla Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="bfcd2-274">Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Una captura de pantalla de Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="bfcd2-276">Selecciona la directiva de la colección de Windows 10 recién creada y elige **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![Una captura de pantalla de Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="bfcd2-278">Después de completar esta tarea, ahora ha configurado correctamente Protección de red en modo auditoría.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="bfcd2-279">Para establecer reglas de acceso controlado a carpetas en modo auditoría:</span><span class="sxs-lookup"><span data-stu-id="bfcd2-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="bfcd2-280">En la consola de Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** y elija **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="bfcd2-282">Seleccione **Acceso controlado a carpetas**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="bfcd2-283">Establezca la configuración en **Auditar** y haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="bfcd2-285">Confirme la nueva directiva de Protección contra vulnerabilidades de seguridad haciendo clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="bfcd2-287">Una vez creada la directiva, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-287">Once the policy is created click on **Close**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="bfcd2-289">Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="bfcd2-291">Dirigir la directiva a la colección de Windows 10 recién creada y hacer clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="bfcd2-293">Ahora ha configurado correctamente Acceso controlado a carpetas en modo auditoría.</span><span class="sxs-lookup"><span data-stu-id="bfcd2-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="bfcd2-294">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="bfcd2-294">Related topic</span></span>
- [<span data-ttu-id="bfcd2-295">Incorporación con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="bfcd2-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
