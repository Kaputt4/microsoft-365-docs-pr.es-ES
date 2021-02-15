---
title: Incorporar dispositivos Windows 10 mediante la directiva de grupo
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Usa la directiva de grupo para implementar el paquete de configuración en dispositivos Windows 10 para que se incorpore al servicio.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769510"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="b955e-103">Incorporar dispositivos Windows 10 mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b955e-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="b955e-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b955e-104">**Applies to:**</span></span>

- [<span data-ttu-id="b955e-105">Prevención de pérdida de datos (DLP) de Punto de conexión de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b955e-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="b955e-106">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b955e-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="b955e-107">Para usar las actualizaciones de directiva de grupo (GP) para implementar el paquete, debes estar en Windows Server 2008 R2 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b955e-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="b955e-108">Para Windows Server 2019, es posible que deba reemplazar NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="b955e-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="b955e-109">Incorporar dispositivos mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b955e-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="b955e-110">Abre el archivo .zip del paquete de configuración de GP (*DeviceComplianceOnboardingPackage.zip*) que descargaste desde el Asistente para la incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="b955e-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="b955e-111">También puede obtener el paquete desde el Centro [de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="b955e-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="b955e-112">En el panel de navegación, selecciona **Configuración de** incorporación  >  **de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="b955e-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="b955e-113">En el **campo Método de** implementación, seleccione Directiva de **grupo.**</span><span class="sxs-lookup"><span data-stu-id="b955e-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="b955e-114">Haz **clic en Descargar paquete** y guarda el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="b955e-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="b955e-115">Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda acceder el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b955e-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="b955e-116">Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *DeviceComplianceLocalOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="b955e-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="b955e-117">Abre la [Consola de administración de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) directivas de grupo (GPMC), haz clic con el botón derecho en el objeto de directiva de grupo (GPO) que quieras configurar y haz clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="b955e-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="b955e-118">En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo, preferencias **y,** a continuación, configuración del Panel **de control.**</span><span class="sxs-lookup"><span data-stu-id="b955e-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="b955e-119">Haga clic con el **botón secundario en Tareas programadas**, elija **Nuevo** y, a continuación, haga clic en Tarea **inmediata (al menos Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="b955e-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="b955e-120">En la **ventana** Tarea que se abre, vaya a la **pestaña** General. En **Opciones de seguridad,** **haga clic en Cambiar** usuario o grupo y escriba SISTEMA y, a continuación, haga clic en Comprobar nombres y, **a** continuación, **en Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="b955e-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="b955e-121">NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.</span><span class="sxs-lookup"><span data-stu-id="b955e-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="b955e-122">Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con los **privilegios** más altos.</span><span class="sxs-lookup"><span data-stu-id="b955e-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="b955e-123">Vaya a la **pestaña Acciones** y haga clic **en Nuevo...** Asegúrese de **que la opción Iniciar un programa** esté seleccionada en el **campo** Acción.</span><span class="sxs-lookup"><span data-stu-id="b955e-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="b955e-124">Escribe el nombre de archivo y la ubicación del archivo *compartido WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="b955e-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="b955e-125">Haga **clic en Aceptar** y cierre las ventanas de GPMC abiertas.</span><span class="sxs-lookup"><span data-stu-id="b955e-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="b955e-126">Quitar dispositivos mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b955e-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="b955e-127">Por motivos de seguridad, el paquete usado para los dispositivos de descarga expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="b955e-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="b955e-128">Se rechazarán los paquetes de baja expirados enviados a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b955e-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="b955e-129">Al descargar un paquete de descarga, se te notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="b955e-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="b955e-130">Las directivas de incorporación y baja no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="b955e-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="b955e-131">Obtenga el paquete de descarga del Centro [de cumplimiento de Microsoft.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="b955e-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="b955e-132">En el panel de navegación, seleccione **Configuración**  >  **//Incorporación de**  >  **dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="b955e-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="b955e-133">En el **campo Método de** implementación, seleccione Directiva de **grupo.**</span><span class="sxs-lookup"><span data-stu-id="b955e-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="b955e-134">Haz **clic en Descargar paquete** y guarda el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="b955e-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="b955e-135">Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda acceder el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b955e-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="b955e-136">Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="b955e-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="b955e-137">Abre la [Consola de administración de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) directivas de grupo (GPMC), haz clic con el botón derecho en el objeto de directiva de grupo (GPO) que quieras configurar y haz clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="b955e-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="b955e-138">En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo, preferencias** **y,** a continuación, configuración del Panel **de control.**</span><span class="sxs-lookup"><span data-stu-id="b955e-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="b955e-139">Haga clic con el botón secundario **en Tareas programadas,** **elija Nuevo** y, a continuación, haga clic en **Tarea inmediata.**</span><span class="sxs-lookup"><span data-stu-id="b955e-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="b955e-140">En la **ventana** Tarea que se abre, vaya a la **pestaña** General. Elija la cuenta de usuario del SISTEMA local (BUILTIN\SYSTEM) en **Opciones de seguridad.**</span><span class="sxs-lookup"><span data-stu-id="b955e-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="b955e-141">Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con los **privilegios** más altos.</span><span class="sxs-lookup"><span data-stu-id="b955e-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="b955e-142">Vaya a la **pestaña Acciones** y haga clic **en Nuevo...**. Asegúrese de **que la opción Iniciar un programa** esté seleccionada en el **campo** Acción.</span><span class="sxs-lookup"><span data-stu-id="b955e-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="b955e-143">Escriba el nombre de archivo y la ubicación del archivo *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="b955e-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="b955e-144">Haga **clic en Aceptar** y cierre las ventanas de GPMC abiertas.</span><span class="sxs-lookup"><span data-stu-id="b955e-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b955e-145">La baja hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b955e-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="b955e-146">Supervisar la configuración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b955e-146">Monitor device configuration</span></span>
<span data-ttu-id="b955e-147">Con la directiva de grupo no hay una opción para supervisar la implementación de directivas en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b955e-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="b955e-148">La supervisión se puede realizar directamente en el portal o mediante las diferentes herramientas de implementación.</span><span class="sxs-lookup"><span data-stu-id="b955e-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="b955e-149">Supervisar dispositivos mediante el portal</span><span class="sxs-lookup"><span data-stu-id="b955e-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="b955e-150">Vaya al [Centro de cumplimiento de Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="b955e-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="b955e-151">Haga clic **en Lista de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b955e-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="b955e-152">Comprueba que los dispositivos aparezcan.</span><span class="sxs-lookup"><span data-stu-id="b955e-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="b955e-153">Los dispositivos pueden tardar varios días en aparecer en la **lista de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="b955e-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="b955e-154">Esto incluye el tiempo que tardan las directivas en distribuirse al dispositivo, el tiempo que tarda antes de que el usuario inicie sesión y el tiempo que tarda el punto de conexión en empezar a informar.</span><span class="sxs-lookup"><span data-stu-id="b955e-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b955e-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b955e-155">Related topics</span></span>
- [<span data-ttu-id="b955e-156">Incorporar dispositivos Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b955e-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="b955e-157">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="b955e-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="b955e-158">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="b955e-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="b955e-159">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="b955e-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="b955e-160">Ejecutar una prueba de detección en dispositivos ATP de Microsoft Defender recién incorporados</span><span class="sxs-lookup"><span data-stu-id="b955e-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="b955e-161">Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b955e-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
