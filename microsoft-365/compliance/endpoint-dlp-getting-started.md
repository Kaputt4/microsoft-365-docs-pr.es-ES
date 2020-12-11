---
title: Introducción a la prevención de pérdida de datos de Microsoft 365 Endpoint
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
ms.openlocfilehash: 7dbceb97b7ccb542a0a4933f3e3cccf5a38026ea
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604268"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="bbc47-103">Introducción a la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bbc47-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="bbc47-104">La prevención de pérdida de datos de Microsoft Endpoint (Endpoint DLP) es parte de la serie de características de prevención de pérdida de datos (DLP) de Microsoft 365 que se pueden usar para detectar y proteger elementos confidenciales en los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bbc47-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="bbc47-105">Para obtener más información sobre las ofertas de DLP de Microsoft, consulte [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bbc47-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="bbc47-106">Para más información sobre la DLP de punto de conexión, consulte [Obtener información sobre la prevención de pérdida de datos de punto de conexión](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="bbc47-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="bbc47-107">Microsoft Endpoint DLP le permite supervisar dispositivos con Windows 10 y detectar cuándo se usan y comparten elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="bbc47-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="bbc47-108">Esto le proporciona la visibilidad y el control que necesita para asegurarse de que se usan y protegen correctamente, así como para ayudar a evitar algún comportamiento peligroso que podría comprometerlos.</span><span class="sxs-lookup"><span data-stu-id="bbc47-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bbc47-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="bbc47-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="bbc47-110">Licencias de SKU/suscripciones</span><span class="sxs-lookup"><span data-stu-id="bbc47-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="bbc47-111">Antes de empezar con Endpoint DLP, debe confirmar la [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y cualquier complemento.</span><span class="sxs-lookup"><span data-stu-id="bbc47-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="bbc47-112">Para acceder y usar la funcionalidad Endpoint DLP, debe tener una de estas suscripciones o complementos.</span><span class="sxs-lookup"><span data-stu-id="bbc47-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="bbc47-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bbc47-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="bbc47-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="bbc47-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="bbc47-115">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bbc47-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="bbc47-116">Cumplimiento de Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="bbc47-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="bbc47-117">Gobierno y protección de información de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bbc47-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="bbc47-118">Gobierno y protección de información de Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="bbc47-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="bbc47-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="bbc47-119">Permissions</span></span>

<span data-ttu-id="bbc47-120">Para habilitar la administración de dispositivos, la cuenta que use debe pertenecer a uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="bbc47-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="bbc47-121">Administrador global</span><span class="sxs-lookup"><span data-stu-id="bbc47-121">Global admin</span></span>
- <span data-ttu-id="bbc47-122">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="bbc47-122">Security admin</span></span>
- <span data-ttu-id="bbc47-123">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbc47-123">Compliance admin</span></span>

<span data-ttu-id="bbc47-124">Si desea usar una cuenta personalizada para ver la configuración de administración de dispositivos, debe tener uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="bbc47-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="bbc47-125">Administrador global</span><span class="sxs-lookup"><span data-stu-id="bbc47-125">Global admin</span></span>
- <span data-ttu-id="bbc47-126">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbc47-126">Compliance admin</span></span>
- <span data-ttu-id="bbc47-127">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbc47-127">Compliance data admin</span></span>
- <span data-ttu-id="bbc47-128">Lector global</span><span class="sxs-lookup"><span data-stu-id="bbc47-128">Global reader</span></span>

<span data-ttu-id="bbc47-129">Si desea usar una cuenta personalizada para acceder a la página de incorporación y baja, debe tener uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="bbc47-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="bbc47-130">Administrador global</span><span class="sxs-lookup"><span data-stu-id="bbc47-130">Global admin</span></span>
- <span data-ttu-id="bbc47-131">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbc47-131">Compliance admin</span></span>

<span data-ttu-id="bbc47-132">Si desea usar una cuenta personalizada para activar o desactivar la supervisión de dispositivos, debe tener uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="bbc47-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="bbc47-133">Administrador global</span><span class="sxs-lookup"><span data-stu-id="bbc47-133">Global admin</span></span>
- <span data-ttu-id="bbc47-134">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbc47-134">Compliance admin</span></span>

<span data-ttu-id="bbc47-135">Los datos de Endpoint DLP se pueden ver en el [Explorador de actividad](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="bbc47-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="bbc47-136">Hay cuatro roles que conceden permisos al explorador de actividad; la cuenta que use para acceder a los datos debe pertenecer a uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="bbc47-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="bbc47-137">Administrador global</span><span class="sxs-lookup"><span data-stu-id="bbc47-137">Global admin</span></span>
- <span data-ttu-id="bbc47-138">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbc47-138">Compliance admin</span></span>
- <span data-ttu-id="bbc47-139">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="bbc47-139">Security admin</span></span>
- <span data-ttu-id="bbc47-140">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbc47-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="bbc47-141">Preparar los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="bbc47-141">Prepare your endpoints</span></span>

<span data-ttu-id="bbc47-142">Asegúrese de que los dispositivos con Windows 10 en los que planee implementar Endpoint DLP cumplan los siguientes requisitos.</span><span class="sxs-lookup"><span data-stu-id="bbc47-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="bbc47-143">Debe estar ejecutando Windows 10 x64 compilación 1809 o posterior.</span><span class="sxs-lookup"><span data-stu-id="bbc47-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="bbc47-144">La versión del cliente antimalware es 4.18.2009.7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="bbc47-144">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="bbc47-145">Para comprobar la versión actual, abra la aplicación de Seguridad de Windows, seleccione el icono Configuración y, a continuación, Acerca de.</span><span class="sxs-lookup"><span data-stu-id="bbc47-145">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="bbc47-146">El número de versión aparece en la versión del cliente antimalware.</span><span class="sxs-lookup"><span data-stu-id="bbc47-146">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="bbc47-147">Instale Windows Update KB4052623 para actualizar a la última versión del cliente antimalware.</span><span class="sxs-lookup"><span data-stu-id="bbc47-147">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> <span data-ttu-id="bbc47-148">Nota: no es necesario que ninguno de los componentes de Seguridad de Windows estén activos; puede ejecutar DLP en punto de conexión independiente del estado de Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="bbc47-148">Note: None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status.</span></span>

3. <span data-ttu-id="bbc47-149">Se instalan las siguientes actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="bbc47-149">The following Windows Updates are installed.</span></span> <span data-ttu-id="bbc47-150">Nota: estas actualizaciones no son un requisito previo para incorporar un dispositivo a DLP en punto de conexión, pero contienen correcciones de problemas importantes y, por lo tanto, deben instalarse antes de usar el producto.</span><span class="sxs-lookup"><span data-stu-id="bbc47-150">Note: These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="bbc47-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="bbc47-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="bbc47-152">Para Windows 10 1903 o 1909 - KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="bbc47-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="bbc47-153">For Windows 10 2004 - KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="bbc47-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="bbc47-154">Para dispositivos que ejecutan Office 2016 (en lugar de cualquier otra versión de Office): KB4577063</span><span class="sxs-lookup"><span data-stu-id="bbc47-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="bbc47-155">Todos los dispositivos deben estar [unidos a Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) o unidos a Azure AD híbrido.</span><span class="sxs-lookup"><span data-stu-id="bbc47-155">All devices must be [Azure Active Directory (Azure AD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>

5. <span data-ttu-id="bbc47-156">Instale el explorador Chromium Edge de Microsoft en el dispositivo del punto de conexión para aplicar acciones de directiva para cargar a la actividad de la nube.</span><span class="sxs-lookup"><span data-stu-id="bbc47-156">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="bbc47-157">Consulte [Descargar el nuevo Microsoft Edge basado en Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="bbc47-157">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="bbc47-158">Si está en el canal mensual de la empresa de las versiones 2004 a 2008 de Aplicaciones de Microsoft 365, hay un problema conocido con el punto de conexión de DLP que clasifica el contenido de Office y tendrá que actualizar a la versión 2009 o posterior.</span><span class="sxs-lookup"><span data-stu-id="bbc47-158">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="bbc47-159">Vea [Historial de actualizaciones de las Aplicaciones de Microsoft 365 (enumeradas por fecha)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) las versiones actuales.</span><span class="sxs-lookup"><span data-stu-id="bbc47-159">See [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="bbc47-160">Para obtener más información sobre este problema, vea la sección Office Suite de [Notas de la versión para obtener las versiones del canal actuales en 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span><span class="sxs-lookup"><span data-stu-id="bbc47-160">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="bbc47-161">Incorporación de dispositivos a la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="bbc47-161">Onboarding devices into device management</span></span>

<span data-ttu-id="bbc47-162">Para poder supervisar y proteger los elementos confidenciales de un dispositivo, es necesario que habilite la supervisión del dispositivo y que incorpore los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="bbc47-162">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="bbc47-163">Ambas acciones se realizan en el portal de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bbc47-163">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="bbc47-164">Cuando quiera incorporar dispositivos que todavía no hayan sido incorporados, descargue el script apropiado y, luego, impleméntelo en esos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bbc47-164">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="bbc47-165">Siga los pasos del [Procedimiento de incorporación de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="bbc47-165">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="bbc47-166">Si ya tiene dispositivos incorporados en [ Microsoft Defender para punto de conexión (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/), estos aparecerán en la lista de dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="bbc47-166">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="bbc47-167">Siga el [procedimiento con dispositivos incorporados en Microsoft Defender para punto de conexión](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&source=docs#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="bbc47-167">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&source=docs#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="bbc47-168">Incorporar dispositivos</span><span class="sxs-lookup"><span data-stu-id="bbc47-168">Onboarding devices</span></span>

<span data-ttu-id="bbc47-169">En este escenario de implementación, incorporará dispositivos que aún no hayan sido incorporados y, además, solo quiere supervisar y proteger elementos confidenciales frente al uso compartido no intencionado en dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bbc47-169">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="bbc47-170">Abra el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="bbc47-170">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="bbc47-171">Abra la página de configuración del Centro de cumplimiento y elija **Incorporar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="bbc47-171">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbc47-172">![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="bbc47-172">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="bbc47-173">Aunque, por lo general, habilitar la incorporación de dispositivos tarda aproximadamente 60 segundos, espere 30 minutos antes de ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbc47-173">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="bbc47-174">Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="bbc47-174">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="bbc47-175">La lista estará vacía hasta que haya incorporado dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bbc47-175">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="bbc47-176">Elija **Incorporación** para iniciar el proceso de incorporación.</span><span class="sxs-lookup"><span data-stu-id="bbc47-176">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="bbc47-177">Elija el modo en que desea implementar estos dispositivos adicionales de la lista **Método de implementación** y, después, **Descargar paquete**.</span><span class="sxs-lookup"><span data-stu-id="bbc47-177">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbc47-178">![método de implementación](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="bbc47-178">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="bbc47-179">Siga los procedimientos adecuados que puede consultar en [Herramientas y métodos de incorporación para equipos con Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="bbc47-179">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="bbc47-180">Este vínculo le lleva a una página de destino en la que puede acceder a los procedimientos de Microsoft Defender para punto de conexión que coinciden con el paquete de implementación que seleccionó en el paso 5:</span><span class="sxs-lookup"><span data-stu-id="bbc47-180">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="bbc47-181">Incorporar equipos con Windows 10 usando Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="bbc47-181">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="bbc47-182">Incorporar equipos con Windows con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bbc47-182">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="bbc47-183">Incorporar equipos con Windows 10 con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="bbc47-183">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="bbc47-184">Incorporar equipos con Windows 10 usando un script local</span><span class="sxs-lookup"><span data-stu-id="bbc47-184">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="bbc47-185">Incorporar equipos de infraestructura de escritorio virtual no persistente (VDI).</span><span class="sxs-lookup"><span data-stu-id="bbc47-185">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="bbc47-186">Una vez que se haya incorporado el punto de conexión, debería estar visible en la lista de dispositivos y también empezar a informar de los registros de actividad de auditoría al explorador de actividad.</span><span class="sxs-lookup"><span data-stu-id="bbc47-186">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc47-187">Esta experiencia requiere la aplicación de una licencia.</span><span class="sxs-lookup"><span data-stu-id="bbc47-187">This experience is under license enforcement.</span></span> <span data-ttu-id="bbc47-188">Sin la licencia necesaria, los datos no serán visibles ni accesibles.</span><span class="sxs-lookup"><span data-stu-id="bbc47-188">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="bbc47-189">Con dispositivos incorporados en Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bbc47-189">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="bbc47-190">En este escenario, Microsoft Defender para punto de conexión ya está implementada y existen puntos de conexión de los que se informa.</span><span class="sxs-lookup"><span data-stu-id="bbc47-190">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="bbc47-191">Todos estos puntos de conexión aparecerán en la lista de dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="bbc47-191">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="bbc47-192">Puede seguir incorporando nuevos dispositivos a Endpoint DLP para ampliar la cobertura siguiendo el [Procedimiento de incorporación de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="bbc47-192">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="bbc47-193">Abra el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="bbc47-193">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="bbc47-194">Abra la página de configuración del Centro de cumplimiento y elija **Habilitar supervisión de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="bbc47-194">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="bbc47-195">Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="bbc47-195">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="bbc47-196">Debe ver la lista de dispositivos sobre los que ya se envían informes a Microsoft Defender para punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bbc47-196">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbc47-197">![administración de dispositivos](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="bbc47-197">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="bbc47-198">Elija **Incorporación** si necesita incorporar dispositivos adicionales.</span><span class="sxs-lookup"><span data-stu-id="bbc47-198">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="bbc47-199">Elija el modo en que desea implementar estos dispositivos adicionales de la lista **Método de implementación** y, después, **Descargar paquete**.</span><span class="sxs-lookup"><span data-stu-id="bbc47-199">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="bbc47-200">Siga los procedimientos adecuados que puede consultar en [Herramientas y métodos de incorporación para equipos con Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="bbc47-200">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="bbc47-201">Este vínculo le lleva a una página de destino en la que puede acceder a los procedimientos de Microsoft Defender para punto de conexión que coinciden con el paquete de implementación que seleccionó en el paso 5:</span><span class="sxs-lookup"><span data-stu-id="bbc47-201">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="bbc47-202">Incorporar equipos con Windows 10 usando Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="bbc47-202">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="bbc47-203">Incorporar equipos con Windows con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bbc47-203">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="bbc47-204">Incorporar equipos con Windows 10 con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="bbc47-204">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="bbc47-205">Incorporar equipos con Windows 10 usando un script local</span><span class="sxs-lookup"><span data-stu-id="bbc47-205">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="bbc47-206">Incorporar equipos de infraestructura de escritorio virtual no persistente (VDI).</span><span class="sxs-lookup"><span data-stu-id="bbc47-206">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="bbc47-207">Una vez que se haya incorporado el punto de conexión, debería estar visible en la tabla **Dispositivos** y también empezar a informar de los registros de auditoría al **Explorador de actividad**.</span><span class="sxs-lookup"><span data-stu-id="bbc47-207">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="bbc47-208">Esta experiencia requiere la aplicación de una licencia.</span><span class="sxs-lookup"><span data-stu-id="bbc47-208">This experience is under license enforcement.</span></span> <span data-ttu-id="bbc47-209">Sin la licencia necesaria, los datos no serán visibles ni accesibles.</span><span class="sxs-lookup"><span data-stu-id="bbc47-209">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="bbc47-210">Visualizar alertas de DLP del punto de conexión en el panel de administración de alertas de DLP</span><span class="sxs-lookup"><span data-stu-id="bbc47-210">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="bbc47-211">Abra la página sobre la prevención de pérdida de datos en el Centro de cumplimiento de Microsoft 365 y elija Alertas.</span><span class="sxs-lookup"><span data-stu-id="bbc47-211">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="bbc47-212">Consulte los procedimientos descritos en [Cómo configurar y ver las alertas de las directivas DLP](dlp-configure-view-alerts-policies.md) para ver las alertas de las directivas DLP del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bbc47-212">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="bbc47-213">Visualizar datos de Endpoint DLP en el explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="bbc47-213">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="bbc47-214">Abra la [Página clasificación de datos](https://compliance.microsoft.com/dataclassification?viewid=overview) del dominio en el Centro de cumplimiento de Microsoft 365 y elija Explorador de actividad.</span><span class="sxs-lookup"><span data-stu-id="bbc47-214">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="bbc47-215">Consulte los procedimientos descritos en [Introducción al explorador de actividad](data-classification-activity-explorer.md) para tener acceso a todos los datos de los dispositivos con Endpoint y filtrarlos.</span><span class="sxs-lookup"><span data-stu-id="bbc47-215">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbc47-216">![filtro de explorador de actividad filtro para dispositivos de punto de conexión](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="bbc47-216">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="bbc47-217">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bbc47-217">Next steps</span></span>
<span data-ttu-id="bbc47-218">Ahora que tiene dispositivos incorporados y puede ver los datos de la actividad en el explorador de actividad, está listo para realizar el siguiente paso, donde puede crear directivas DLP que protegen los elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="bbc47-218">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="bbc47-219">Uso de la prevención de pérdida de datos de Endpoint (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="bbc47-219">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="bbc47-220">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bbc47-220">See also</span></span>

- [<span data-ttu-id="bbc47-221">Obtenga información sobre la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bbc47-221">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="bbc47-222">Uso de la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bbc47-222">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="bbc47-223">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="bbc47-223">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="bbc47-224">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="bbc47-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="bbc47-225">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="bbc47-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="bbc47-226">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bbc47-226">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- <span data-ttu-id="bbc47-227">[Herramientas y métodos de incorporación para equipos con Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="bbc47-227">[Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span></span>
- [<span data-ttu-id="bbc47-228">Suscripción a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bbc47-228">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="bbc47-229">Dispositivos de Azure AD Unidos</span><span class="sxs-lookup"><span data-stu-id="bbc47-229">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="bbc47-230">Descargar el nuevo Microsoft Edge basado en Chromium</span><span class="sxs-lookup"><span data-stu-id="bbc47-230">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
