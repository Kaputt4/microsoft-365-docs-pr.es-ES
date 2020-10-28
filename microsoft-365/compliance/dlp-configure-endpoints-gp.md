---
title: Dispositivos de Windows 10 incorporados mediante la Directiva de grupo
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
description: Use la Directiva de grupo para implementar el paquete de configuración en dispositivos Windows 10 para que estén integrados en el servicio.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769510"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="ba917-103">Dispositivos de Windows 10 incorporados mediante la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="ba917-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="ba917-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ba917-104">**Applies to:**</span></span>

- [<span data-ttu-id="ba917-105">Prevención de pérdida de datos (DLP) de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ba917-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="ba917-106">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="ba917-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="ba917-107">Para usar actualizaciones de la Directiva de grupo (GP) para implementar el paquete, debe estar en Windows Server 2008 R2 o posterior.</span><span class="sxs-lookup"><span data-stu-id="ba917-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="ba917-108">En el caso de Windows Server 2019, es posible que necesite reemplazar AUTHORITY\Well-Known-System-Account de NT con NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de la Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="ba917-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="ba917-109">Dispositivos incorporados que usan la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="ba917-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="ba917-110">Abra el archivo package. zip de configuración de GP ( *DeviceComplianceOnboardingPackage.zip* ) que ha descargado desde el Asistente de incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="ba917-110">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="ba917-111">También puede obtener el paquete del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="ba917-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="ba917-112">En el panel de navegación, seleccione incorporación de dispositivos de **configuración**  >  **Device Onboarding** .</span><span class="sxs-lookup"><span data-stu-id="ba917-112">In the navigation pane, select **Settings** > **Device Onboarding** .</span></span>

3. <span data-ttu-id="ba917-113">En el campo **método de implementación** , seleccione Directiva de **Grupo** .</span><span class="sxs-lookup"><span data-stu-id="ba917-113">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="ba917-114">Haga clic en **Descargar paquete** y guarde el archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="ba917-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="ba917-115">Extraiga el contenido del archivo. zip en una ubicación compartida de solo lectura a la que pueda obtener acceso el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba917-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="ba917-116">Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *DeviceComplianceLocalOnboardingScript. cmd* .</span><span class="sxs-lookup"><span data-stu-id="ba917-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="ba917-117">Abra la [consola de administración de directivas de grupo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar** .</span><span class="sxs-lookup"><span data-stu-id="ba917-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="ba917-118">En el **Editor de administración de directivas de grupo** , vaya a **configuración del equipo** , **preferencias** y configuración del **Panel de control** .</span><span class="sxs-lookup"><span data-stu-id="ba917-118">In the **Group Policy Management Editor** , go to **Computer configuration** , then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="ba917-119">Haga clic con el botón secundario en **tareas programadas** , seleccione **nuevo** y, a continuación, haga clic en **tarea inmediata (como mínimo, Windows 7)** .</span><span class="sxs-lookup"><span data-stu-id="ba917-119">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate Task (At least Windows 7)** .</span></span>

9. <span data-ttu-id="ba917-120">En la ventana de **tareas** que se abre, vaya a la pestaña **General** . En **Opciones de seguridad** , haga clic en **cambiar usuario o grupo** y escriba sistema y, a continuación, haga clic en **Comprobar nombres** y, después, en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="ba917-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK** .</span></span> <span data-ttu-id="ba917-121">NT AUTHORITY\SYSTEM aparece como la cuenta de usuario con la que se ejecutará la tarea.</span><span class="sxs-lookup"><span data-stu-id="ba917-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="ba917-122">Seleccione **ejecutar tanto si un usuario inició sesión como si no** y active la casilla de verificación **ejecutar con los privilegios más altos** .</span><span class="sxs-lookup"><span data-stu-id="ba917-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="ba917-123">Vaya a la ficha **acciones** y haga clic en **nuevo...** Asegúrese de que la acción **iniciar un programa** está seleccionada en el campo **acción** .</span><span class="sxs-lookup"><span data-stu-id="ba917-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="ba917-124">Escriba el nombre de archivo y la ubicación del archivo *WindowsDefenderATPOnboardingScript. cmd* compartido.</span><span class="sxs-lookup"><span data-stu-id="ba917-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="ba917-125">Haga clic en **Aceptar** y cierre todas las ventanas de GPMC abiertas.</span><span class="sxs-lookup"><span data-stu-id="ba917-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="ba917-126">Dispositivos desincorpora con la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="ba917-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="ba917-127">Por motivos de seguridad, el paquete que se usa para desincorpora dispositivos expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="ba917-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="ba917-128">Los paquetes de retirada expirados enviados a un dispositivo se rechazarán.</span><span class="sxs-lookup"><span data-stu-id="ba917-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="ba917-129">Al descargar un paquete de descarga, recibirá una notificación de la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="ba917-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="ba917-130">Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario se producirán colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="ba917-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="ba917-131">Obtenga el paquete de descarga del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span><span class="sxs-lookup"><span data-stu-id="ba917-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="ba917-132">En el panel de navegación, seleccione **configuración**  >  **//Device incorporación** de la  >  **descarga** .</span><span class="sxs-lookup"><span data-stu-id="ba917-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="ba917-133">En el campo **método de implementación** , seleccione Directiva de **Grupo** .</span><span class="sxs-lookup"><span data-stu-id="ba917-133">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="ba917-134">Haga clic en **Descargar paquete** y guarde el archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="ba917-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="ba917-135">Extraiga el contenido del archivo. zip en una ubicación compartida de solo lectura a la que pueda obtener acceso el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba917-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="ba917-136">Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .</span><span class="sxs-lookup"><span data-stu-id="ba917-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6. <span data-ttu-id="ba917-137">Abra la [consola de administración de directivas de grupo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar** .</span><span class="sxs-lookup"><span data-stu-id="ba917-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="ba917-138">En el **Editor de administración de directivas de grupo** , vaya a **configuración del equipo,** **preferencias** y configuración del **Panel de control** .</span><span class="sxs-lookup"><span data-stu-id="ba917-138">In the **Group Policy Management Editor** , go to **Computer configuration,** then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="ba917-139">Haga clic con el botón secundario en **tareas programadas** , seleccione **nuevo** y, a continuación, haga clic en **tarea inmediata** .</span><span class="sxs-lookup"><span data-stu-id="ba917-139">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate task** .</span></span>

9. <span data-ttu-id="ba917-140">En la ventana de **tareas** que se abre, vaya a la pestaña **General** . Elija la cuenta de usuario del sistema local (BUILTIN\SYSTEM) en **Opciones de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="ba917-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options** .</span></span>

10. <span data-ttu-id="ba917-141">Seleccione **ejecutar tanto si un usuario inició sesión como si no** y active la casilla **ejecutar con los privilegios más altos** .</span><span class="sxs-lookup"><span data-stu-id="ba917-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="ba917-142">Vaya a la ficha **acciones** y haga clic en **nuevo...** Asegúrese de que la acción **iniciar un programa** está seleccionada en el campo **acción** .</span><span class="sxs-lookup"><span data-stu-id="ba917-142">Go to the **Actions** tab and click **New...** . Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="ba917-143">Escriba el nombre de archivo y la ubicación del archivo Shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .</span><span class="sxs-lookup"><span data-stu-id="ba917-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="ba917-144">Haga clic en **Aceptar** y cierre todas las ventanas de GPMC abiertas.</span><span class="sxs-lookup"><span data-stu-id="ba917-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba917-145">La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero datos del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba917-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="ba917-146">Supervisar la configuración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba917-146">Monitor device configuration</span></span>
<span data-ttu-id="ba917-147">Con la Directiva de grupo no existe una opción para supervisar la implementación de directivas en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba917-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="ba917-148">La supervisión se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.</span><span class="sxs-lookup"><span data-stu-id="ba917-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="ba917-149">Supervisar dispositivos con el portal</span><span class="sxs-lookup"><span data-stu-id="ba917-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="ba917-150">Vaya al [centro de cumplimiento de Microsoft](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ba917-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="ba917-151">Haga clic en lista de **dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="ba917-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="ba917-152">Compruebe que aparecen dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba917-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="ba917-153">Los dispositivos pueden tardar varios días en comenzar a mostrarse en la **lista de dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="ba917-153">It can take several days for devices to start showing on the **Devices list** .</span></span> <span data-ttu-id="ba917-154">Esto incluye el tiempo que tarda la distribución de las directivas en el dispositivo, el tiempo que tarda antes de que el usuario inicie sesión y el tiempo que tarda el punto de conexión en iniciar la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="ba917-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ba917-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ba917-155">Related topics</span></span>
- [<span data-ttu-id="ba917-156">Dispositivos con Windows 10 en placa mediante el administrador de configuración de Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="ba917-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="ba917-157">Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="ba917-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="ba917-158">Dispositivos de Windows 10 incorporados que usan un script local</span><span class="sxs-lookup"><span data-stu-id="ba917-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="ba917-159">Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados</span><span class="sxs-lookup"><span data-stu-id="ba917-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="ba917-160">Ejecutar una prueba de detección en los dispositivos ATP de Microsoft defender recién integrados</span><span class="sxs-lookup"><span data-stu-id="ba917-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="ba917-161">Solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="ba917-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
