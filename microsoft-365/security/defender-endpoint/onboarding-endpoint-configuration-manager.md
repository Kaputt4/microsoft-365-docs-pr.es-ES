---
title: Incorporación mediante Microsoft Endpoint Configuration Manager
description: Obtenga información sobre cómo incorporarse a Microsoft Defender para endpoint mediante Microsoft Endpoint Configuration Manager
keywords: incorporación, configuración, implementación, administrador de configuración de puntos de conexión, Microsoft Defender para endpoint, creación de colecciones, respuesta de detección de puntos de conexión, protección de próxima generación, reducción de superficie de ataque, administrador de configuración de puntos de conexión de Microsoft
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
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843511"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="40281-104">Incorporación mediante Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="40281-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40281-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="40281-105">**Applies to:**</span></span>
- [<span data-ttu-id="40281-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="40281-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="40281-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40281-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="40281-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="40281-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="40281-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="40281-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="40281-110">Este artículo forma parte de la guía de implementación y actúa como un método de incorporación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="40281-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="40281-111">En el [tema Planeación,](deployment-strategy.md) se proporcionaron varios métodos para incorporar dispositivos al servicio.</span><span class="sxs-lookup"><span data-stu-id="40281-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="40281-112">En este tema se trata la arquitectura de administración en colaboración.</span><span class="sxs-lookup"><span data-stu-id="40281-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="40281-113">![Imagen de arquitectura nativa de la nube ](images/co-management-architecture.png)
 *Diagrama de arquitecturas de entorno*</span><span class="sxs-lookup"><span data-stu-id="40281-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="40281-114">Aunque Defender para endpoint admite la incorporación de varios puntos de conexión y herramientas, este artículo no los cubre.</span><span class="sxs-lookup"><span data-stu-id="40281-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="40281-115">Para obtener información sobre la incorporación general con otras herramientas y métodos de implementación compatibles, vea [Onboarding overview](onboarding.md).</span><span class="sxs-lookup"><span data-stu-id="40281-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="40281-116">En este tema se guía a los usuarios en:</span><span class="sxs-lookup"><span data-stu-id="40281-116">This topic guides users in:</span></span>
- <span data-ttu-id="40281-117">Paso 1: Incorporación de Windows dispositivos al servicio</span><span class="sxs-lookup"><span data-stu-id="40281-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="40281-118">Paso 2: Configuración de las capacidades de Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="40281-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="40281-119">Esta guía de incorporación le ayudará a seguir los siguientes pasos básicos que debe seguir al usar Microsoft Endpoint Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="40281-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="40281-120">**Crear una colección en Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="40281-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="40281-121">**Configurar Las capacidades de Microsoft Defender para puntos de conexión mediante Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="40281-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="40281-122">Solo Windows dispositivos se tratan en este ejemplo de implementación.</span><span class="sxs-lookup"><span data-stu-id="40281-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="40281-123">Paso 1: Incorporación Windows dispositivos con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="40281-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="40281-124">Creación de colecciones</span><span class="sxs-lookup"><span data-stu-id="40281-124">Collection creation</span></span>
<span data-ttu-id="40281-125">Para incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager, la implementación puede dirigirse a una colección existente o se puede crear una nueva colección para pruebas.</span><span class="sxs-lookup"><span data-stu-id="40281-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="40281-126">La incorporación mediante herramientas como la directiva de grupo o el método manual no instala ningún agente en el sistema.</span><span class="sxs-lookup"><span data-stu-id="40281-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="40281-127">Dentro de Microsoft Endpoint Configuration Manager consola, el proceso de incorporación se configurará como parte de la configuración de cumplimiento dentro de la consola.</span><span class="sxs-lookup"><span data-stu-id="40281-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="40281-128">Cualquier sistema que reciba esta configuración necesaria mantendrá esa configuración mientras el cliente de Configuration Manager siga recibiendo esta directiva desde el punto de administración.</span><span class="sxs-lookup"><span data-stu-id="40281-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="40281-129">Siga los pasos siguientes para incorporar puntos de conexión mediante Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="40281-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="40281-130">En Microsoft Endpoint Configuration Manager consola, vaya a **Assets and Compliance Overview Device \> \> Collections**.</span><span class="sxs-lookup"><span data-stu-id="40281-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Imagen de Microsoft Endpoint Configuration Manager wizard1](images/configmgr-device-collections.png)

2. <span data-ttu-id="40281-132">Haga clic con el **botón secundario en Colección de** dispositivos y seleccione Crear colección de **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="40281-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager wizard2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="40281-134">Proporcione una **colección Name** y **Limiting y,** a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager wizard3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="40281-136">Seleccione **Agregar regla** y elija Regla de **consulta**.</span><span class="sxs-lookup"><span data-stu-id="40281-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager wizard4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="40281-138">Haga **clic en Siguiente** en el Asistente para pertenencia **directa** y haga clic en Editar **instrucción query**.</span><span class="sxs-lookup"><span data-stu-id="40281-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Imagen de Microsoft Endpoint Configuration Manager wizard5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="40281-140">Seleccione **Criterios** y, a continuación, elija el icono de estrella.</span><span class="sxs-lookup"><span data-stu-id="40281-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Imagen de Microsoft Endpoint Configuration Manager wizard6](images/configmgr-criteria.png)

7. <span data-ttu-id="40281-142">Mantenga el tipo de criterio como valor **simple**,  elija dónde como Sistema operativo **-** número de compilación , operador como mayor o igual que y valor **14393** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40281-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager wizard7](images/configmgr-simple-value.png)

8. <span data-ttu-id="40281-144">Seleccione **Siguiente** y **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="40281-144">Select **Next** and **Close**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager wizard8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="40281-146">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-146">Select **Next**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager wizard9](images/configmgr-confirm.png)


<span data-ttu-id="40281-148">Después de completar esta tarea, ahora tienes una colección de dispositivos con todos los Windows 10 en el entorno.</span><span class="sxs-lookup"><span data-stu-id="40281-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="40281-149">Paso 2: Configurar Microsoft Defender para las funcionalidades de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="40281-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="40281-150">En esta sección se le guía en la configuración de las siguientes funcionalidades mediante Microsoft Endpoint Configuration Manager en Windows dispositivos:</span><span class="sxs-lookup"><span data-stu-id="40281-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="40281-151">**EDR**</span><span class="sxs-lookup"><span data-stu-id="40281-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="40281-152">**Protección de última generación**</span><span class="sxs-lookup"><span data-stu-id="40281-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="40281-153">**Reducción de la superficie expuesta a ataques**</span><span class="sxs-lookup"><span data-stu-id="40281-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="40281-154">EDR</span><span class="sxs-lookup"><span data-stu-id="40281-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="40281-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="40281-155">Windows 10</span></span>
<span data-ttu-id="40281-156">Desde dentro del Centro de seguridad de Microsoft Defender es posible descargar la directiva ".onboarding" que se puede usar para crear la directiva en System Center Configuration Manager e implementar esa directiva en Windows 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="40281-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="40281-157">En un portal Centro de seguridad de Microsoft Defender, [seleccione Configuración y,](https://securitycenter.windows.com/preferences2/onboarding)a continuación, Incorporación .</span><span class="sxs-lookup"><span data-stu-id="40281-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="40281-158">En Método de implementación, seleccione la versión compatible **de Microsoft Endpoint Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="40281-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Imagen del Asistente para incorporación de Microsoft Defender para endpoint10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="40281-160">Seleccione **Descargar paquete**.</span><span class="sxs-lookup"><span data-stu-id="40281-160">Select **Download package**.</span></span>

    ![Imagen del Asistente para la incorporación de Microsoft Defender para puntos de conexión11](images/mdatp-download-package.png)

4. <span data-ttu-id="40281-162">Guarde el paquete en una ubicación accesible.</span><span class="sxs-lookup"><span data-stu-id="40281-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="40281-163">En Microsoft Endpoint Configuration Manager, vaya a: **Assets and Compliance > Overview > Endpoint Protection > ATP de Microsoft Defender Policies**.</span><span class="sxs-lookup"><span data-stu-id="40281-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="40281-164">Haga clic con el **botón ATP de Microsoft Defender y** seleccione Crear ATP de Microsoft Defender **directiva**.</span><span class="sxs-lookup"><span data-stu-id="40281-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager wizard12](images/configmgr-create-policy.png)

7. <span data-ttu-id="40281-166">Escriba el nombre y la descripción, compruebe **que la incorporación** está seleccionada y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager wizard13](images/configmgr-policy-name.png)


8. <span data-ttu-id="40281-168">Haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="40281-168">Click **Browse**.</span></span>

9. <span data-ttu-id="40281-169">Vaya a la ubicación del archivo descargado desde el paso 4 anterior.</span><span class="sxs-lookup"><span data-stu-id="40281-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="40281-170">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-170">Click **Next**.</span></span>
11. <span data-ttu-id="40281-171">Configure el agente con los ejemplos adecuados (**Ninguno** o **Todos los tipos de archivo**).</span><span class="sxs-lookup"><span data-stu-id="40281-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Imagen de las opciones de configuración1](images/configmgr-config-settings.png)

12. <span data-ttu-id="40281-173">Seleccione la telemetría adecuada (**Normal** o **Expedited**) y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Imagen de las opciones de configuración2](images/configmgr-telemetry.png)

14. <span data-ttu-id="40281-175">Compruebe la configuración y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-175">Verify the configuration, then click **Next**.</span></span>

     ![Imagen de configuración3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="40281-177">Haga **clic en** Cerrar cuando se complete el Asistente.</span><span class="sxs-lookup"><span data-stu-id="40281-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="40281-178">En la Microsoft Endpoint Configuration Manager, haga clic con el botón secundario en la directiva defender para extremo que acaba de crear y seleccione **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="40281-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Imagen de las opciones de configuración4](images/configmgr-deploy.png)

17. <span data-ttu-id="40281-180">En el panel derecho, seleccione la colección creada anteriormente y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40281-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Imagen de configuración5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="40281-182">Versiones anteriores de Windows Client (Windows 7 y Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="40281-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="40281-183">Siga los pasos que se indican a continuación para identificar el identificador del área de trabajo de endpoint y la clave de área de trabajo de Defender for Endpoint, que serán necesarios para la incorporación de versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="40281-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="40281-184">En un portal Centro de seguridad de Microsoft Defender, **seleccione Configuración > incorporación .**</span><span class="sxs-lookup"><span data-stu-id="40281-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="40281-185">En sistema operativo, **elija Windows 7 SP1 y 8.1**.</span><span class="sxs-lookup"><span data-stu-id="40281-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="40281-186">Copie el **identificador del área de trabajo** y la clave de área de **trabajo** y guárdelos.</span><span class="sxs-lookup"><span data-stu-id="40281-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="40281-187">Se usarán más adelante en el proceso.</span><span class="sxs-lookup"><span data-stu-id="40281-187">They will be used later in the process.</span></span>

    ![Imagen de incorporación](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="40281-189">Instale el Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="40281-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="40281-190">MMA actualmente (a partir de enero de 2019) es compatible con los siguientes sistemas Windows operativos:</span><span class="sxs-lookup"><span data-stu-id="40281-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="40281-191">SKU del servidor: Windows Server 2008 SP1 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="40281-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="40281-192">SKU de cliente: Windows 7 SP1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="40281-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="40281-193">El agente mma tendrá que instalarse en Windows dispositivos.</span><span class="sxs-lookup"><span data-stu-id="40281-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="40281-194">Para instalar el agente, algunos sistemas [](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) tendrán que descargar la actualización para la experiencia del cliente y la telemetría de diagnóstico para recopilar los datos con MMA.</span><span class="sxs-lookup"><span data-stu-id="40281-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="40281-195">Estas versiones del sistema incluyen, pero no pueden limitarse a:</span><span class="sxs-lookup"><span data-stu-id="40281-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="40281-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="40281-196">Windows 8.1</span></span>

    -   <span data-ttu-id="40281-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="40281-197">Windows 7</span></span>

    -   <span data-ttu-id="40281-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="40281-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="40281-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="40281-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="40281-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="40281-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="40281-201">En concreto, para Windows 7 SP1, deben instalarse las siguientes revisiones:</span><span class="sxs-lookup"><span data-stu-id="40281-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="40281-202">Instalar [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="40281-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="40281-203">Instale .NET Framework [4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) **o** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span><span class="sxs-lookup"><span data-stu-id="40281-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="40281-204">No instale ambos en el mismo sistema.</span><span class="sxs-lookup"><span data-stu-id="40281-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="40281-205">Si usa un proxy para conectarse a Internet, consulte la sección Configurar opciones de proxy.</span><span class="sxs-lookup"><span data-stu-id="40281-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="40281-206">Una vez completado, debería ver puntos de conexión incorporados en el portal en una hora.</span><span class="sxs-lookup"><span data-stu-id="40281-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="40281-207">Protección de última generación</span><span class="sxs-lookup"><span data-stu-id="40281-207">Next generation protection</span></span> 
<span data-ttu-id="40281-208">El Antivirus de Microsoft Defender es una solución antimalware integrada que proporciona una protección de última generación para equipos de escritorio, equipos portátiles y servidores.</span><span class="sxs-lookup"><span data-stu-id="40281-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="40281-209">En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection \> \> \> Antimalware Polices** y elija **Create Antimalware Policy**.</span><span class="sxs-lookup"><span data-stu-id="40281-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Imagen de la directiva antimalware](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="40281-211">Seleccione **Exámenes programados,** Configuración del examen **,** Acciones predeterminadas **,** Protección en tiempo **real** **,** Configuración de exclusión **,** Avanzadas , Invalidaciones de **amenazas,** Servicio **de protección** en la nube y Actualizaciones de inteligencia de **seguridad** y elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40281-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Imagen del panel de protección de próxima generación1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="40281-213">En determinados sectores o en algunos clientes empresariales selectos puede haber necesidades específicas sobre cómo se configura Antivirus.</span><span class="sxs-lookup"><span data-stu-id="40281-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="40281-214">Examen rápido frente a examen completo y examen personalizado</span><span class="sxs-lookup"><span data-stu-id="40281-214">Quick scan versus full scan and custom scan</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="40281-215">Para obtener más información, [vea Seguridad de Windows marco de configuración](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="40281-215">For more details, see [Windows Security configuration framework](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Imagen del panel de protección de próxima generación2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Imagen del panel de protección de próxima generación3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Imagen del panel de protección de próxima generación4](images/a28afc02c1940d5220b233640364970c.png)

    ![Imagen del panel de protección de próxima generación5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Imagen del panel de protección de próxima generación6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Imagen del panel de protección de próxima generación7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Imagen del panel de protección de próxima generación8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Imagen del panel de protección de próxima generación9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="40281-224">Haga clic con el botón secundario en la directiva antimalware recién creada y seleccione **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="40281-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Imagen del panel de protección de próxima generación10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="40281-226">Dirigir la nueva directiva antimalware a la colección Windows 10 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40281-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Imagen del panel de protección de próxima generación11](images/configmgr-select-collection.png)

<span data-ttu-id="40281-228">Después de completar esta tarea, ahora ha configurado correctamente Antivirus de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="40281-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="40281-229">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="40281-229">Attack surface reduction</span></span>
<span data-ttu-id="40281-230">El pilar de reducción de superficie de ataque de Defender para endpoint incluye el conjunto de características que está disponible en Protección contra vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="40281-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="40281-231">Reglas de reducción de superficie de ataque (ASR), Acceso controlado a carpetas, Protección de red y Protección contra vulnerabilidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="40281-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="40281-232">Todas estas características proporcionan un modo de auditoría y un modo de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="40281-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="40281-233">En el modo de auditoría no hay ningún impacto para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="40281-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="40281-234">Todo lo que hace es recopilar telemetría adicional y hacer que esté disponible en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="40281-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="40281-235">El objetivo con una implementación es mover paso a paso los controles de seguridad al modo de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="40281-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="40281-236">Para establecer reglas ASR en modo auditoría:</span><span class="sxs-lookup"><span data-stu-id="40281-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="40281-237">En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** y elija **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="40281-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Imagen de Microsoft Endpoint Configuration Manager console0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="40281-239">Selecciona **Reducción de superficie de ataque**.</span><span class="sxs-lookup"><span data-stu-id="40281-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="40281-240">Establezca reglas en **Auditar** y haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Imagen de Microsoft Endpoint Configuration Manager console1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="40281-242">Para confirmar la nueva directiva de Protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager console2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="40281-244">Una vez creada la directiva, haga clic **en Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="40281-244">Once the policy is created click **Close**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager console3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Imagen de Microsoft Endpoint Manager console1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="40281-247">Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="40281-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Imagen de Microsoft Endpoint Configuration Manager console4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="40281-249">Dirigir la directiva a la colección recién Windows 10 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40281-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Imagen de Microsoft Endpoint Configuration Manager console5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="40281-251">Después de completar esta tarea, ahora ha configurado correctamente las reglas de ASR en el modo de auditoría.</span><span class="sxs-lookup"><span data-stu-id="40281-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="40281-252">A continuación se indican pasos adicionales para comprobar si las reglas ASR se aplican correctamente a los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="40281-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="40281-253">(Esto puede tardar unos minutos)</span><span class="sxs-lookup"><span data-stu-id="40281-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="40281-254">Desde un explorador web, vaya a <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="40281-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="40281-255">Seleccione **Administración de configuración** en el menú del lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="40281-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="40281-256">Haz **clic en Ir a la administración de superficies de** ataque en el panel Administración de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="40281-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Imagen de la administración de superficies de ataque](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="40281-258">Haga clic **en la pestaña** Configuración en Informes de reglas de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="40281-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="40281-259">Muestra información general sobre la configuración de reglas ASR y el estado de las reglas ASR en cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="40281-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![Una captura de pantalla de informes de reglas de reducción de superficie de ataque1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="40281-261">Haga clic en cada dispositivo para ver los detalles de configuración de las reglas de ASR.</span><span class="sxs-lookup"><span data-stu-id="40281-261">Click each device shows configuration details of ASR rules.</span></span>

    ![Una captura de pantalla de informes de reglas de reducción de superficie de ataque2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="40281-263">Consulte [Optimizar la implementación y detecciones](/microsoft-365/security/defender-endpoint/configure-machines-asr)   de reglas ASR para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="40281-263">See [Optimize ASR rule deployment and detections](/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="40281-264">Establecer reglas de protección de red en modo auditoría:</span><span class="sxs-lookup"><span data-stu-id="40281-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="40281-265">En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** y elija **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="40281-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Una captura de System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="40281-267">Seleccione **Protección de red**.</span><span class="sxs-lookup"><span data-stu-id="40281-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="40281-268">Establezca la configuración en **Auditar** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![Una captura System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="40281-270">Para confirmar la nueva directiva de Protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![Una captura de pantalla Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="40281-272">Una vez creada la directiva, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="40281-272">Once the policy is created click on **Close**.</span></span>

    ![Una captura de pantalla Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="40281-274">Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="40281-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Una captura de pantalla de Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="40281-276">Seleccione la directiva de la colección de Windows 10 recién creada y elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40281-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![Una captura de pantalla de Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="40281-278">Después de completar esta tarea, ahora ha configurado correctamente Protección de red en modo auditoría.</span><span class="sxs-lookup"><span data-stu-id="40281-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="40281-279">Para establecer reglas de acceso controlado a carpetas en modo auditoría:</span><span class="sxs-lookup"><span data-stu-id="40281-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="40281-280">En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** y elija **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="40281-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="40281-282">Seleccione **Acceso controlado a carpetas**.</span><span class="sxs-lookup"><span data-stu-id="40281-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="40281-283">Establezca la configuración en **Auditar** y haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="40281-285">Confirme la nueva directiva de Protección contra vulnerabilidades de seguridad haciendo clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40281-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="40281-287">Una vez creada la directiva, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="40281-287">Once the policy is created click on **Close**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="40281-289">Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="40281-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="40281-291">Dirigir la directiva a la colección recién Windows 10 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40281-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="40281-293">Ahora ha configurado correctamente Acceso controlado a carpetas en modo auditoría.</span><span class="sxs-lookup"><span data-stu-id="40281-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="40281-294">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="40281-294">Related topic</span></span>
- [<span data-ttu-id="40281-295">Incorporación con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="40281-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
