---
title: Incorporar dispositivos Windows 10 mediante un script local
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Use un script local para implementar el paquete de configuración en dispositivos para que se incorpore al servicio.
ms.openlocfilehash: e9efa76af72f9169bdec1acf35d72066ac0a776e
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893311"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="a141f-103">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="a141f-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="a141f-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a141f-104">**Applies to:**</span></span>

- [<span data-ttu-id="a141f-105">Microsoft 365 Prevención de pérdida de datos de extremo (DLP)</span><span class="sxs-lookup"><span data-stu-id="a141f-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="a141f-106">También puede incorporar manualmente dispositivos individuales para Microsoft 365 prevención de pérdida de datos de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a141f-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="a141f-107">Es posible que quieras hacerlo primero al probar el servicio antes de comprometerte a incorporar todos los dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="a141f-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a141f-108">Este script se ha optimizado para su uso en hasta 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a141f-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="a141f-109">Para implementar a escala, use [otras opciones de implementación.](dlp-configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="a141f-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="a141f-110">Por ejemplo, puede implementar un script de incorporación en más de 10 dispositivos en producción con el script disponible en [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span><span class="sxs-lookup"><span data-stu-id="a141f-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="a141f-111">Dispositivos integrados</span><span class="sxs-lookup"><span data-stu-id="a141f-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="a141f-112">Abra el archivo de configuración .zip GP (*DeviceComplianceOnboardingPackage.zip*) que descargó del asistente para incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="a141f-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="a141f-113">También puede obtener el paquete desde el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a141f-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="a141f-114">En el panel de navegación, **seleccione Configuración** Incorporación  >  **de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="a141f-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="a141f-115">En el **campo Método de** implementación, seleccione Script **local**.</span><span class="sxs-lookup"><span data-stu-id="a141f-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="a141f-116">Haga **clic en Descargar paquete** y guarde el .zip archivo.</span><span class="sxs-lookup"><span data-stu-id="a141f-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="a141f-117">Extrae el contenido del paquete de configuración en una ubicación en el dispositivo que quieras incorporar (por ejemplo, el escritorio).</span><span class="sxs-lookup"><span data-stu-id="a141f-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="a141f-118">Debe tener un archivo denominado *DeviceOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="a141f-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="a141f-119">Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:</span><span class="sxs-lookup"><span data-stu-id="a141f-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="a141f-120">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="a141f-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="a141f-121">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a141f-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Menú Inicio de ventana que apunta a Ejecutar como administrador](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="a141f-123">Escriba la ubicación del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="a141f-123">Type the location of the script file.</span></span> <span data-ttu-id="a141f-124">Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="a141f-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="a141f-125">Presione la **tecla Entrar** o haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a141f-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="a141f-126">Para obtener información sobre cómo validar manualmente que el dispositivo es compatible e informa correctamente de los datos del sensor, [consulte Troubleshoot Protección contra amenazas avanzada de Microsoft Defender onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="a141f-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="a141f-127">Dispositivos offboard con un script local</span><span class="sxs-lookup"><span data-stu-id="a141f-127">Offboard devices using a local script</span></span>
<span data-ttu-id="a141f-128">Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="a141f-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="a141f-129">Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a141f-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="a141f-130">Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="a141f-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="a141f-131">Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="a141f-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="a141f-132">Obtener el paquete de offboarding desde el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a141f-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="a141f-133">En el panel de navegación, **seleccione Configuración**  >  **Desaborde dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a141f-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="a141f-134">En el **campo Método de** implementación, seleccione Script **local**.</span><span class="sxs-lookup"><span data-stu-id="a141f-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="a141f-135">Haga **clic en Descargar paquete** y guarde el .zip archivo.</span><span class="sxs-lookup"><span data-stu-id="a141f-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="a141f-136">Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que puedan tener acceso los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a141f-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="a141f-137">Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="a141f-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="a141f-138">Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:</span><span class="sxs-lookup"><span data-stu-id="a141f-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="a141f-139">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="a141f-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="a141f-140">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a141f-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Menú Inicio de ventana que apunta a Ejecutar como administrador](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="a141f-142">Escriba la ubicación del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="a141f-142">Type the location of the script file.</span></span> <span data-ttu-id="a141f-143">Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="a141f-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="a141f-144">Presione la **tecla Entrar** o haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a141f-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a141f-145">El offboarding hace que el dispositivo deje de enviar datos del sensor al portal.</span><span class="sxs-lookup"><span data-stu-id="a141f-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="a141f-146">Supervisar la configuración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a141f-146">Monitor device configuration</span></span>
<span data-ttu-id="a141f-147">Puede seguir los diferentes pasos de comprobación en [Solucionar problemas de incorporación](( para comprobar que el script se completó correctamente https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) y que el agente se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="a141f-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="a141f-148">La supervisión también se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.</span><span class="sxs-lookup"><span data-stu-id="a141f-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="a141f-149">Supervisar dispositivos con el portal</span><span class="sxs-lookup"><span data-stu-id="a141f-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="a141f-150">Vaya a [Microsoft 365 Centro de cumplimiento](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a141f-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="a141f-151">Elija **Configuración**  >  **Dispositivos de incorporación de**  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="a141f-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="a141f-152">Compruebe que aparecen dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a141f-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a141f-153">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a141f-153">Related topics</span></span>
- [<span data-ttu-id="a141f-154">Incorporación Windows 10 dispositivos con directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="a141f-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="a141f-155">Incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a141f-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="a141f-156">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="a141f-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="a141f-157">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="a141f-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="a141f-158">Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado</span><span class="sxs-lookup"><span data-stu-id="a141f-158">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="a141f-159">Solucionar Protección contra amenazas avanzada de Microsoft Defender problemas de incorporación</span><span class="sxs-lookup"><span data-stu-id="a141f-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)