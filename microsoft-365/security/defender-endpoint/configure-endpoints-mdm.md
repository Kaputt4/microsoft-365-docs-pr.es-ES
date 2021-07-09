---
title: Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles
description: Usa las herramientas de administración de dispositivos móviles para implementar el paquete de configuración en dispositivos para que los dispositivos se incorpore al servicio.
keywords: incorporar dispositivos con mdm, administración de dispositivos, incorporación de Microsoft Defender para dispositivos de punto de conexión, mdm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f0a0a35d41d56abfcc7975c9e79ff7d537b72f40
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338582"
---
# <a name="onboard-the-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="bbcd9-104">Incorporar los dispositivos Windows 10 con las herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="bbcd9-104">Onboard the Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bbcd9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bbcd9-105">**Applies to:**</span></span>
- [<span data-ttu-id="bbcd9-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bbcd9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bbcd9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbcd9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bbcd9-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="bbcd9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bbcd9-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="bbcd9-110">Puedes usar soluciones de administración de dispositivos móviles (MDM) para configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="bbcd9-111">Defender for Endpoint admite MDM proporcionando OMA-URIs para crear directivas para administrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="bbcd9-112">Para obtener más información sobre cómo usar Defender para CSP de extremo, consulta [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) y [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="bbcd9-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bbcd9-113">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="bbcd9-113">Before you begin</span></span>
<span data-ttu-id="bbcd9-114">Si estás usando Microsoft Intune, debes tener el dispositivo MDM inscrito.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="bbcd9-115">De lo contrario, la configuración no se aplicará correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="bbcd9-116">Para obtener más información sobre cómo habilitar MDM con Microsoft Intune, consulta [Inscripción de dispositivos (Microsoft Intune).](/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="bbcd9-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="bbcd9-117">Incorporar dispositivos con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bbcd9-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="bbcd9-118">[![Imagen del PDF que muestra los dispositivos de incorporación a Defender for Endpoint mediante Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="bbcd9-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="bbcd9-119">Consulte el [ARCHIVO PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver las distintas rutas de acceso en la implementación de Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="bbcd9-120">Siga las instrucciones de [Intune](/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="bbcd9-120">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="bbcd9-121">Para obtener más información sobre cómo usar Defender para CSP de extremo, consulta [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) y [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="bbcd9-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="bbcd9-122">La **directiva Estado de mantenimiento para dispositivos incorporados** usa propiedades de solo lectura y no se puede corregir.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="bbcd9-123">La configuración de la frecuencia de informes de datos de diagnóstico solo está disponible para dispositivos Windows 10, versión 1703.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="bbcd9-124">Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que un dispositivo está correctamente incorporado al servicio.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="bbcd9-125">Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint](run-detection-test.md)recién incorporado.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="bbcd9-126">Consulte el [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) o [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver las distintas rutas de acceso para implementar Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="bbcd9-127">Offboard y supervisar dispositivos con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="bbcd9-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="bbcd9-128">Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="bbcd9-129">Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="bbcd9-130">Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="bbcd9-131">Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="bbcd9-132">Obtener el paquete de offboarding desde [Microsoft 365 Defender portal](https://security.microsoft.com/):</span><span class="sxs-lookup"><span data-stu-id="bbcd9-132">Get the offboarding package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

   1. <span data-ttu-id="bbcd9-133">En el panel de navegación, **seleccione Configuración**  >  **Endpoints** Administración  >  **de dispositivos**  >  **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-133">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Offboarding**.</span></span>

   1. <span data-ttu-id="bbcd9-134">Seleccione Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="bbcd9-135">En el **campo Método de** implementación, seleccione Administración de **dispositivos móviles / Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="bbcd9-136">Haga **clic en Descargar paquete** y guarde el .zip archivo.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="bbcd9-137">Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que puedan tener acceso los administradores de red que implementarán el paquete.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="bbcd9-138">Debe tener un archivo denominado *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="bbcd9-139">Use la Microsoft Intune de configuración personalizada para implementar la siguiente configuración de OMA-URI compatible.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="bbcd9-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="bbcd9-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="bbcd9-141">Tipo de fecha: String</span><span class="sxs-lookup"><span data-stu-id="bbcd9-141">Date type: String</span></span><br/>
      <span data-ttu-id="bbcd9-142">Valor: [Copiar y pegar el valor del contenido del archivo WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="bbcd9-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="bbcd9-143">Para obtener más información sobre Microsoft Intune configuración de directiva, [consulte Windows 10 configuración de directiva en Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="bbcd9-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="bbcd9-144">La **directiva Estado de mantenimiento para dispositivos fuera deborde** usa propiedades de solo lectura y no se puede corregir.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbcd9-145">Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.</span><span class="sxs-lookup"><span data-stu-id="bbcd9-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bbcd9-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bbcd9-146">Related topics</span></span>
- [<span data-ttu-id="bbcd9-147">Incorporación Windows 10 dispositivos con directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="bbcd9-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="bbcd9-148">Incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bbcd9-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="bbcd9-149">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="bbcd9-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="bbcd9-150">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="bbcd9-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="bbcd9-151">Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado</span><span class="sxs-lookup"><span data-stu-id="bbcd9-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="bbcd9-152">Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bbcd9-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
