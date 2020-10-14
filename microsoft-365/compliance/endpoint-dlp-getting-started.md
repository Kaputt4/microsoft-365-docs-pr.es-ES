---
title: Introducción a la prevención de pérdida de datos de Microsoft 365 Endpoint (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Configure la prevención de pérdida de datos de Microsoft 365 Endpoint para supervisar las actividades de archivo e implemente acciones de protección de estos archivos en los puntos de conexión.
ms.openlocfilehash: c579d0bbfdc72e56d99558ffa7e6812d00098c0d
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430685"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="88a3e-103">Introducción a la prevención de pérdida de datos de Endpoint (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="88a3e-103">Get started with Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="88a3e-104">La prevención de pérdida de datos de Microsoft Endpoint (Endpoint DLP) es parte de la serie de características de prevención de pérdida de datos (DLP) de Microsoft 365 que se pueden usar para detectar y proteger elementos confidenciales en los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88a3e-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="88a3e-105">Para obtener más información sobre las ofertas de DLP de Microsoft, consulte [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="88a3e-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="88a3e-106">Para obtener más información sobre la DLP de Endpoint, consulte [Obtener más información sobre la prevención de pérdida de datos de Endpoint (versión preliminar)](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="88a3e-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention (preview)](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="88a3e-107">Microsoft Endpoint DLP le permite supervisar dispositivos con Windows 10 y detectar cuándo se usan y comparten elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="88a3e-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="88a3e-108">Esto le proporciona la visibilidad y el control que necesita para asegurarse de que se usan y protegen correctamente, así como para ayudar a evitar algún comportamiento peligroso que podría comprometerlos.</span><span class="sxs-lookup"><span data-stu-id="88a3e-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="88a3e-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="88a3e-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="88a3e-110">Licencias de SKU/suscripciones</span><span class="sxs-lookup"><span data-stu-id="88a3e-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="88a3e-111">Antes de empezar con Endpoint DLP, debe confirmar la [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y cualquier complemento.</span><span class="sxs-lookup"><span data-stu-id="88a3e-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="88a3e-112">Para acceder y usar la funcionalidad Endpoint DLP, debe tener una de estas suscripciones o complementos.</span><span class="sxs-lookup"><span data-stu-id="88a3e-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="88a3e-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="88a3e-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="88a3e-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="88a3e-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="88a3e-115">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="88a3e-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="88a3e-116">Cumplimiento de Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="88a3e-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="88a3e-117">Gobierno y protección de información de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="88a3e-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="88a3e-118">Gobierno y protección de información de Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="88a3e-118">Microsoft 365 A5 information protection and governance</span></span>

### <a name="permissions"></a><span data-ttu-id="88a3e-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="88a3e-119">Permissions</span></span>

<span data-ttu-id="88a3e-120">Para habilitar la administración de dispositivos, la cuenta que use debe pertenecer a uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="88a3e-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="88a3e-121">Administrador global</span><span class="sxs-lookup"><span data-stu-id="88a3e-121">Global admin</span></span>
- <span data-ttu-id="88a3e-122">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="88a3e-122">Security admin</span></span>
- <span data-ttu-id="88a3e-123">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="88a3e-123">Compliance admin</span></span>

<span data-ttu-id="88a3e-124">Si desea usar una cuenta personalizada para ver la configuración de administración de dispositivos, debe tener uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="88a3e-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="88a3e-125">Administrador global</span><span class="sxs-lookup"><span data-stu-id="88a3e-125">Global admin</span></span>
- <span data-ttu-id="88a3e-126">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="88a3e-126">Compliance admin</span></span>
- <span data-ttu-id="88a3e-127">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="88a3e-127">Compliance data admin</span></span>
- <span data-ttu-id="88a3e-128">Lector global</span><span class="sxs-lookup"><span data-stu-id="88a3e-128">Global reader</span></span>

<span data-ttu-id="88a3e-129">Si desea usar una cuenta personalizada para acceder a la página de incorporación y baja, debe tener uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="88a3e-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="88a3e-130">Administrador global</span><span class="sxs-lookup"><span data-stu-id="88a3e-130">Global admin</span></span>
- <span data-ttu-id="88a3e-131">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="88a3e-131">Compliance admin</span></span>

<span data-ttu-id="88a3e-132">Si desea usar una cuenta personalizada para activar o desactivar la supervisión de dispositivos, debe tener uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="88a3e-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="88a3e-133">Administrador global</span><span class="sxs-lookup"><span data-stu-id="88a3e-133">Global admin</span></span>
- <span data-ttu-id="88a3e-134">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="88a3e-134">Compliance admin</span></span>

<span data-ttu-id="88a3e-135">Los datos de Endpoint DLP se pueden ver en el [Explorador de actividad](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="88a3e-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="88a3e-136">Hay cuatro roles que conceden permisos al explorador de actividad; la cuenta que use para acceder a los datos debe pertenecer a uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="88a3e-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="88a3e-137">Administrador global</span><span class="sxs-lookup"><span data-stu-id="88a3e-137">Global admin</span></span>
- <span data-ttu-id="88a3e-138">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="88a3e-138">Compliance admin</span></span>
- <span data-ttu-id="88a3e-139">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="88a3e-139">Security admin</span></span>
- <span data-ttu-id="88a3e-140">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="88a3e-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="88a3e-141">Preparar los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="88a3e-141">Prepare your endpoints</span></span>

<span data-ttu-id="88a3e-142">Asegúrese de que los dispositivos con Windows 10 en los que planee implementar Endpoint DLP cumplan los siguientes requisitos.</span><span class="sxs-lookup"><span data-stu-id="88a3e-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="88a3e-143">Debe estar ejecutando Windows 10 x64 compilación 1809 o posterior.</span><span class="sxs-lookup"><span data-stu-id="88a3e-143">Must be running Windows 10 x64 build 1809 or later.</span></span>
2. <span data-ttu-id="88a3e-144">Todos los dispositivos deben estar [unidos a Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) o unidos a Azure AD híbrido.</span><span class="sxs-lookup"><span data-stu-id="88a3e-144">All devices must be [Azure Active Directory (AAD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>
3. <span data-ttu-id="88a3e-145">Instale el explorador Chromium Edge de Microsoft en el dispositivo del punto de conexión para aplicar acciones de directiva para cargar a la actividad de la nube.</span><span class="sxs-lookup"><span data-stu-id="88a3e-145">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="88a3e-146">Consulte [Descargar el nuevo Microsoft Edge basado en Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="88a3e-146">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="88a3e-147">Incorporación de dispositivos a la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="88a3e-147">Onboarding devices into device management</span></span>

 <span data-ttu-id="88a3e-148">Para poder supervisar y proteger los elementos confidenciales de un dispositivo, es necesario que habilite la supervisión del dispositivo y que incorpore los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="88a3e-148">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="88a3e-149">Ambas acciones se realizan en el portal de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88a3e-149">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="88a3e-150">Cuando quiera incorporar dispositivos que todavía no hayan sido incorporados, descargue el script apropiado y, luego, impleméntelo en esos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="88a3e-150">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="88a3e-151">Siga los pasos del [Procedimiento de incorporación de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="88a3e-151">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="88a3e-152">Si ya tiene dispositivos incorporados en [ Microsoft Defender para punto de conexión (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/), estos aparecerán en la lista de dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="88a3e-152">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="88a3e-153">Siga el [procedimiento con dispositivos incorporados en Microsoft Defender para punto de conexión](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span><span class="sxs-lookup"><span data-stu-id="88a3e-153">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="88a3e-154">Incorporar dispositivos</span><span class="sxs-lookup"><span data-stu-id="88a3e-154">Onboarding devices</span></span>

<span data-ttu-id="88a3e-155">En este escenario de implementación, incorporará dispositivos que aún no hayan sido incorporados y, además, solo quiere supervisar y proteger elementos confidenciales frente al uso compartido no intencionado en dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="88a3e-155">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="88a3e-156">Abra el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="88a3e-156">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="88a3e-157">Abra la página de configuración del Centro de cumplimiento y elija **Incorporar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="88a3e-157">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   ![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > <span data-ttu-id="88a3e-159">Aunque, por lo general, habilitar la incorporación de dispositivos tarda aproximadamente 60 segundos, espere 30 minutos antes de ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="88a3e-159">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="88a3e-160">Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="88a3e-160">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="88a3e-161">La lista estará vacía hasta que haya incorporado dispositivos.</span><span class="sxs-lookup"><span data-stu-id="88a3e-161">The list will be empty until you onboard devices.</span></span>
4. <span data-ttu-id="88a3e-162">Elija **Incorporación** para iniciar el proceso de incorporación.</span><span class="sxs-lookup"><span data-stu-id="88a3e-162">Choose **Onboarding** to begin the onboarding process.</span></span>
5. <span data-ttu-id="88a3e-163">Elija el modo en que desea implementar estos dispositivos adicionales de la lista **Método de implementación** y, después, **Descargar paquete**.</span><span class="sxs-lookup"><span data-stu-id="88a3e-163">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   ![método de implementación](../media/endpoint-dlp-getting-started-3-deployment-method.png)
6. <span data-ttu-id="88a3e-165">Siga los procedimientos adecuados que puede consultar en [Herramientas y métodos de incorporación para equipos con Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="88a3e-165">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="88a3e-166">Este vínculo le lleva a una página de destino en la que puede acceder a los procedimientos de Microsoft Defender para punto de conexión que coinciden con el paquete de implementación que seleccionó en el paso 5:</span><span class="sxs-lookup"><span data-stu-id="88a3e-166">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="88a3e-167">Incorporar equipos con Windows 10 usando Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="88a3e-167">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="88a3e-168">Incorporar equipos con Windows con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="88a3e-168">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="88a3e-169">Incorporar equipos con Windows 10 con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="88a3e-169">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="88a3e-170">Incorporar equipos con Windows 10 usando un script local</span><span class="sxs-lookup"><span data-stu-id="88a3e-170">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="88a3e-171">Incorporar equipos de infraestructura de escritorio virtual no persistente (VDI).</span><span class="sxs-lookup"><span data-stu-id="88a3e-171">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="88a3e-172">Una vez que se haya incorporado el punto de conexión, debería estar visible en la lista de dispositivos y también empezar a informar de los registros de actividad de auditoría al explorador de actividad.</span><span class="sxs-lookup"><span data-stu-id="88a3e-172">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="88a3e-173">Esta experiencia requiere la aplicación de una licencia.</span><span class="sxs-lookup"><span data-stu-id="88a3e-173">This experience is under license enforcement.</span></span> <span data-ttu-id="88a3e-174">Sin la licencia necesaria, los datos no serán visibles ni accesibles.</span><span class="sxs-lookup"><span data-stu-id="88a3e-174">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="88a3e-175">Con dispositivos incorporados en Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="88a3e-175">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="88a3e-176">En este escenario, Microsoft Defender para punto de conexión ya está implementada y existen puntos de conexión de los que se informa.</span><span class="sxs-lookup"><span data-stu-id="88a3e-176">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="88a3e-177">Todos estos puntos de conexión aparecerán en la lista de dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="88a3e-177">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="88a3e-178">Puede seguir incorporando nuevos dispositivos a Endpoint DLP para ampliar la cobertura siguiendo el [Procedimiento de incorporación de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="88a3e-178">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="88a3e-179">Abra el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="88a3e-179">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="88a3e-180">Abra la página de configuración del Centro de cumplimiento y elija **Habilitar supervisión de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="88a3e-180">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>
3. <span data-ttu-id="88a3e-181">Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="88a3e-181">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="88a3e-182">Debe ver la lista de dispositivos sobre los que ya se envían informes a Microsoft Defender para punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="88a3e-182">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="88a3e-183">![administración de dispositivos](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="88a3e-183">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
4. <span data-ttu-id="88a3e-184">Elija **Incorporación** si necesita incorporar dispositivos adicionales.</span><span class="sxs-lookup"><span data-stu-id="88a3e-184">Choose **Onboarding** if you need to onboard additional devices.</span></span>
5. <span data-ttu-id="88a3e-185">Elija el modo en que desea implementar estos dispositivos adicionales de la lista **Método de implementación** y, después, **Descargar paquete**.</span><span class="sxs-lookup"><span data-stu-id="88a3e-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>
6. <span data-ttu-id="88a3e-186">Siga los procedimientos adecuados que puede consultar en [Herramientas y métodos de incorporación para equipos con Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="88a3e-186">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="88a3e-187">Este vínculo le lleva a una página de destino en la que puede acceder a los procedimientos de Microsoft Defender para punto de conexión que coinciden con el paquete de implementación que seleccionó en el paso 5:</span><span class="sxs-lookup"><span data-stu-id="88a3e-187">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="88a3e-188">Incorporar equipos con Windows 10 usando Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="88a3e-188">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="88a3e-189">Incorporar equipos con Windows con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="88a3e-189">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="88a3e-190">Incorporar equipos con Windows 10 con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="88a3e-190">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="88a3e-191">Incorporar equipos con Windows 10 usando un script local</span><span class="sxs-lookup"><span data-stu-id="88a3e-191">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="88a3e-192">Incorporar equipos de infraestructura de escritorio virtual no persistente (VDI).</span><span class="sxs-lookup"><span data-stu-id="88a3e-192">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="88a3e-193">Una vez que se haya incorporado el punto de conexión, debería estar visible en la tabla **Dispositivos** y también empezar a informar de los registros de auditoría al **Explorador de actividad**.</span><span class="sxs-lookup"><span data-stu-id="88a3e-193">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="88a3e-194">Esta experiencia requiere la aplicación de una licencia.</span><span class="sxs-lookup"><span data-stu-id="88a3e-194">This experience is under license enforcement.</span></span> <span data-ttu-id="88a3e-195">Sin la licencia necesaria, los datos no serán visibles ni accesibles.</span><span class="sxs-lookup"><span data-stu-id="88a3e-195">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="88a3e-196">Visualizar datos de Endpoint DLP en el explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="88a3e-196">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="88a3e-197">Abra la [Página clasificación de datos](https://compliance.microsoft.com/dataclassification?viewid=overview) del dominio en el Centro de cumplimiento de Microsoft 365 y elija Explorador de actividad.</span><span class="sxs-lookup"><span data-stu-id="88a3e-197">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>
2. <span data-ttu-id="88a3e-198">Consulte los procedimientos descritos en [Introducción al explorador de actividad](data-classification-activity-explorer.md) para tener acceso a todos los datos de los dispositivos con Endpoint y filtrarlos.</span><span class="sxs-lookup"><span data-stu-id="88a3e-198">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

![filtro de explorador de actividad filtro para dispositivos de punto de conexióin](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a><span data-ttu-id="88a3e-200">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="88a3e-200">Next steps</span></span>
<span data-ttu-id="88a3e-201">Ahora que tiene dispositivos incorporados y puede ver los datos de la actividad en el explorador de actividad, está listo para realizar el siguiente paso, donde puede crear directivas DLP que protegen los elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="88a3e-201">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="88a3e-202">Uso de la prevención de pérdida de datos de Endpoint (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="88a3e-202">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="88a3e-203">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88a3e-203">See also</span></span>

- [<span data-ttu-id="88a3e-204">Obtenga más información sobre la prevención de pérdida de datos de Endpoint (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="88a3e-204">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="88a3e-205">Uso de la prevención de pérdida de datos de Endpoint (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="88a3e-205">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="88a3e-206">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="88a3e-206">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="88a3e-207">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="88a3e-207">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="88a3e-208">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="88a3e-208">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="88a3e-209">Protección contra amenazas avanzada de Microsoft Defender (ATP de Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="88a3e-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- <span data-ttu-id="88a3e-210">[Herramientas y métodos de incorporación para equipos con Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="88a3e-210">[Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span></span>
- [<span data-ttu-id="88a3e-211">Suscripción a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88a3e-211">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="88a3e-212">Unido a Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="88a3e-212">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="88a3e-213">Descargar el nuevo Microsoft Edge basado en Chromium</span><span class="sxs-lookup"><span data-stu-id="88a3e-213">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
