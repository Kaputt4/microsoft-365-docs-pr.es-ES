---
title: Incorporar dispositivos Windows 10 mediante un script local
description: Use un script local para implementar el paquete de configuración en dispositivos para habilitar la incorporación de los dispositivos al servicio.
keywords: configurar dispositivos mediante un script local, administración de dispositivos, configurar Microsoft Defender para dispositivos de punto de conexión
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
ms.openlocfilehash: e15a02753c7a1b346021a4351af24b8fd28315da
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339651"
---
# <a name="onboard-the-windows-10-devices-using-a-local-script"></a><span data-ttu-id="a21db-104">Incorporación de Windows 10 dispositivos con un script local</span><span class="sxs-lookup"><span data-stu-id="a21db-104">Onboard the Windows 10 devices using a local script</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [<span data-ttu-id="a21db-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a21db-105">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="a21db-106">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a21db-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a21db-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a21db-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="a21db-108">También puedes incorporar manualmente dispositivos individuales a Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="a21db-108">You can also manually onboard individual devices to Defender for Endpoint.</span></span> <span data-ttu-id="a21db-109">Es posible que quieras hacerlo primero al probar el servicio antes de comprometerte a incorporar todos los dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="a21db-109">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a21db-110">Este script se ha optimizado para su uso en hasta 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a21db-110">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="a21db-111">Para implementar a escala, use [otras opciones de implementación.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="a21db-111">To deploy at scale, use [other deployment options](configure-endpoints.md).</span></span> <span data-ttu-id="a21db-112">Por ejemplo, puede implementar un script de incorporación en más de 10 dispositivos en producción con el script disponible en [Onboard Windows 10 devices using Group Policy](configure-endpoints-gp.md).</span><span class="sxs-lookup"><span data-stu-id="a21db-112">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="a21db-113">Incorporar dispositivos</span><span class="sxs-lookup"><span data-stu-id="a21db-113">Onboard devices</span></span> 

<span data-ttu-id="a21db-114">[![Imagen del PDF que muestra las distintas rutas de implementación](images/onboard-script.png)](images/onboard-script.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a21db-114">[![Image of the PDF showing the various deployment paths](images/onboard-script.png)](images/onboard-script.png#lightbox)</span></span>


<span data-ttu-id="a21db-115">Consulte el [ARCHIVO PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver las distintas rutas de acceso en la implementación de Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="a21db-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 


1.  <span data-ttu-id="a21db-116">Abra el archivo de configuración .zip GP (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del asistente para incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="a21db-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="a21db-117">También puede obtener el paquete desde [Microsoft 365 Portal de Defender:](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="a21db-117">You can also get the package from [Microsoft 365  Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="a21db-118">En el panel de navegación, **seleccione Configuración**  >  **Endpoints**  >  **Device management**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="a21db-118">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

    1. <span data-ttu-id="a21db-119">Seleccione Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a21db-119">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="a21db-120">En el **campo Método de** implementación, seleccione Script **local**.</span><span class="sxs-lookup"><span data-stu-id="a21db-120">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="a21db-121">Haga **clic en Descargar paquete** y guarde el .zip archivo.</span><span class="sxs-lookup"><span data-stu-id="a21db-121">Click **Download package** and save the .zip file.</span></span>

  
2.  <span data-ttu-id="a21db-122">Extrae el contenido del paquete de configuración en una ubicación en el dispositivo que quieras incorporar (por ejemplo, el escritorio).</span><span class="sxs-lookup"><span data-stu-id="a21db-122">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="a21db-123">Debe tener un archivo denominado *WindowsDefenderATPLocalOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="a21db-123">You should have a file named *WindowsDefenderATPLocalOnboardingScript.cmd*.</span></span>

3.  <span data-ttu-id="a21db-124">Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:</span><span class="sxs-lookup"><span data-stu-id="a21db-124">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="a21db-125">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="a21db-125">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="a21db-126">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a21db-126">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![Ventana menú Inicio apuntar a Ejecutar como administrador](images/run-as-admin.png)

4.  <span data-ttu-id="a21db-128">Escriba la ubicación del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="a21db-128">Type the location of the script file.</span></span> <span data-ttu-id="a21db-129">Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="a21db-129">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*</span></span>

5.  <span data-ttu-id="a21db-130">Presione la **tecla Entrar** o haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a21db-130">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="a21db-131">Para obtener información sobre cómo validar manualmente que el dispositivo es compatible e informa correctamente de los datos del sensor, consulte [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span><span class="sxs-lookup"><span data-stu-id="a21db-131">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>


>[!TIP]
> <span data-ttu-id="a21db-132">Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que un dispositivo está correctamente incorporado al servicio.</span><span class="sxs-lookup"><span data-stu-id="a21db-132">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="a21db-133">Para obtener más información, vea [Ejecutar una prueba de detección en un](run-detection-test.md)punto de conexión de Microsoft Defender para endpoint recién incorporado.</span><span class="sxs-lookup"><span data-stu-id="a21db-133">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-sample-collection-settings"></a><span data-ttu-id="a21db-134">Configuración de la colección de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a21db-134">Configure sample collection settings</span></span>
<span data-ttu-id="a21db-135">Para cada dispositivo, puedes establecer un valor de configuración para especificar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través de Microsoft 365 Defender enviar un archivo para un análisis profundo.</span><span class="sxs-lookup"><span data-stu-id="a21db-135">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft 365 Defender to submit a file for deep analysis.</span></span>

<span data-ttu-id="a21db-136">Puedes configurar manualmente la configuración de uso compartido de ejemplo en el dispositivo mediante *regedit* o creando y ejecutando un *archivo .reg.*</span><span class="sxs-lookup"><span data-stu-id="a21db-136">You can manually configure the sample sharing setting on the device by using *regedit* or creating and running a *.reg* file.</span></span>  

<span data-ttu-id="a21db-137">La configuración se establece mediante la siguiente entrada de clave del Registro:</span><span class="sxs-lookup"><span data-stu-id="a21db-137">The configuration is set through the following registry key entry:</span></span>

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="a21db-138">Donde:</span><span class="sxs-lookup"><span data-stu-id="a21db-138">Where:</span></span><br>
<span data-ttu-id="a21db-139">El tipo de nombre es un D-WORD.</span><span class="sxs-lookup"><span data-stu-id="a21db-139">Name type is a D-WORD.</span></span> <br>
<span data-ttu-id="a21db-140">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="a21db-140">Possible values are:</span></span>
- <span data-ttu-id="a21db-141">0: no permite el uso compartido de muestras desde este dispositivo</span><span class="sxs-lookup"><span data-stu-id="a21db-141">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="a21db-142">1: permite compartir todos los tipos de archivo desde este dispositivo</span><span class="sxs-lookup"><span data-stu-id="a21db-142">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="a21db-143">El valor predeterminado en caso de que la clave del Registro no exista es 1.</span><span class="sxs-lookup"><span data-stu-id="a21db-143">The default value in case the registry key doesn’t exist is 1.</span></span>


## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="a21db-144">Dispositivos offboard con un script local</span><span class="sxs-lookup"><span data-stu-id="a21db-144">Offboard devices using a local script</span></span>
<span data-ttu-id="a21db-145">Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="a21db-145">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="a21db-146">Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a21db-146">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="a21db-147">Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="a21db-147">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="a21db-148">Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="a21db-148">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="a21db-149">Obtener el paquete de offboarding desde [Microsoft 365 Defender portal](https://security.microsoft.com/):</span><span class="sxs-lookup"><span data-stu-id="a21db-149">Get the offboarding package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="a21db-150">En el panel de navegación, **seleccione Configuración**  >  **Endpoints** Administración  >  **de dispositivos**  > **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="a21db-150">In the navigation pane, select **Settings** > **Endpoints** > **Device management** >**Offboarding**.</span></span>

    1. <span data-ttu-id="a21db-151">Seleccione Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a21db-151">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="a21db-152">En el **campo Método de** implementación, seleccione Script **local**.</span><span class="sxs-lookup"><span data-stu-id="a21db-152">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="a21db-153">Haga **clic en Descargar paquete** y guarde el .zip archivo.</span><span class="sxs-lookup"><span data-stu-id="a21db-153">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="a21db-154">Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que puedan tener acceso los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a21db-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="a21db-155">Debe tener un archivo denominado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="a21db-155">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3.  <span data-ttu-id="a21db-156">Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:</span><span class="sxs-lookup"><span data-stu-id="a21db-156">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="a21db-157">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="a21db-157">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="a21db-158">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a21db-158">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![Ventana menú Inicio apuntar a Ejecutar como administrador](images/run-as-admin.png)

4.  <span data-ttu-id="a21db-160">Escriba la ubicación del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="a21db-160">Type the location of the script file.</span></span> <span data-ttu-id="a21db-161">Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="a21db-161">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

5.  <span data-ttu-id="a21db-162">Presione la **tecla Entrar** o haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a21db-162">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a21db-163">Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.</span><span class="sxs-lookup"><span data-stu-id="a21db-163">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="a21db-164">Supervisar la configuración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a21db-164">Monitor device configuration</span></span>
<span data-ttu-id="a21db-165">Puede seguir los distintos pasos de comprobación en [solucionar](troubleshoot-onboarding.md) problemas de incorporación para comprobar que el script se completó correctamente y que el agente se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="a21db-165">You can follow the different verification steps in the [Troubleshoot onboarding issues](troubleshoot-onboarding.md) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="a21db-166">La supervisión también se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.</span><span class="sxs-lookup"><span data-stu-id="a21db-166">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="a21db-167">Supervisar dispositivos con el portal</span><span class="sxs-lookup"><span data-stu-id="a21db-167">Monitor devices using the portal</span></span>
1. <span data-ttu-id="a21db-168">Vaya a Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="a21db-168">Go to Microsoft 365 Defender portal.</span></span>

2. <span data-ttu-id="a21db-169">Haga clic **en Inventario de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="a21db-169">Click **Devices inventory**.</span></span>

3. <span data-ttu-id="a21db-170">Compruebe que aparecen dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a21db-170">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a21db-171">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a21db-171">Related topics</span></span>
- [<span data-ttu-id="a21db-172">Incorporación Windows 10 dispositivos con directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="a21db-172">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="a21db-173">Incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a21db-173">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="a21db-174">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="a21db-174">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="a21db-175">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="a21db-175">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="a21db-176">Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado</span><span class="sxs-lookup"><span data-stu-id="a21db-176">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="a21db-177">Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a21db-177">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
