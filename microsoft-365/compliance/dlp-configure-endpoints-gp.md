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
ms.openlocfilehash: b786d011a46f69e7bcac846e726e2aeb3031ae08
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918026"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="47ce9-103">Incorporación de dispositivos Windows 10 con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="47ce9-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="47ce9-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="47ce9-104">**Applies to:**</span></span>

- [<span data-ttu-id="47ce9-105">Prevención de pérdida de datos del extremo de Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="47ce9-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="47ce9-106">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="47ce9-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="47ce9-107">Para usar las actualizaciones de directiva de grupo (GP) para implementar el paquete, debes estar en Windows Server 2008 R2 o posterior.</span><span class="sxs-lookup"><span data-stu-id="47ce9-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="47ce9-108">Para Windows Server 2019, es posible que deba reemplazar NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="47ce9-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="47ce9-109">Incorporación de dispositivos mediante directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="47ce9-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="47ce9-110">Abra el archivo .zip del paquete de configuración de GP (*DeviceComplianceOnboardingPackage.zip*) que descargó del Asistente para incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="47ce9-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="47ce9-111">También puede obtener el paquete desde el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="47ce9-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="47ce9-112">En el panel de navegación, seleccione **Configuración de** incorporación  >  **de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="47ce9-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="47ce9-113">En el **campo Método de** implementación, seleccione Directiva de **grupo**.</span><span class="sxs-lookup"><span data-stu-id="47ce9-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="47ce9-114">Haga **clic en Descargar paquete** y guarde el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="47ce9-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="47ce9-115">Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47ce9-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="47ce9-116">Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *DeviceComplianceLocalOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="47ce9-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="47ce9-117">Abra la [Consola de administración de directivas de](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="47ce9-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="47ce9-118">En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo , luego Preferencias **y,** a continuación, **Configuración del panel de control.**</span><span class="sxs-lookup"><span data-stu-id="47ce9-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="47ce9-119">Haga clic con el botón secundario en **Tareas programadas**, elija **Nuevo** y, a continuación, haga clic en Tarea inmediata **(al menos Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="47ce9-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="47ce9-120">En la **ventana Tarea** que se abre, vaya a la **pestaña General.** En **Opciones de seguridad,** **haga clic en Cambiar usuario o grupo** y escriba SISTEMA y, a continuación, haga clic en Comprobar nombres **y, a** continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="47ce9-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="47ce9-121">NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.</span><span class="sxs-lookup"><span data-stu-id="47ce9-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="47ce9-122">Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.</span><span class="sxs-lookup"><span data-stu-id="47ce9-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="47ce9-123">Vaya a la **pestaña Acciones** y haga clic **en Nuevo...** Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción.</span><span class="sxs-lookup"><span data-stu-id="47ce9-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="47ce9-124">Escriba el nombre de archivo y la ubicación del archivo *compartido WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="47ce9-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="47ce9-125">Haga **clic en Aceptar** y cierre las ventanas GPMC abiertas.</span><span class="sxs-lookup"><span data-stu-id="47ce9-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="47ce9-126">Dispositivos offboard con directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="47ce9-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="47ce9-127">Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="47ce9-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="47ce9-128">Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47ce9-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="47ce9-129">Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="47ce9-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="47ce9-130">Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="47ce9-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="47ce9-131">Obtenga el paquete de offboarding del [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span><span class="sxs-lookup"><span data-stu-id="47ce9-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="47ce9-132">En el panel de navegación, seleccione **Configuración**  >  **//Incorporación de**  >  **dispositivos Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="47ce9-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="47ce9-133">En el **campo Método de** implementación, seleccione Directiva de **grupo**.</span><span class="sxs-lookup"><span data-stu-id="47ce9-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="47ce9-134">Haga **clic en Descargar paquete** y guarde el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="47ce9-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="47ce9-135">Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47ce9-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="47ce9-136">Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="47ce9-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="47ce9-137">Abra la [Consola de administración de directivas de](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="47ce9-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="47ce9-138">En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo, preferencias** **y,** a continuación, **configuración del panel de control.**</span><span class="sxs-lookup"><span data-stu-id="47ce9-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="47ce9-139">Haga clic con el botón secundario **en Tareas programadas**, **elija Nuevo** y, a continuación, haga clic en **Tarea inmediata**.</span><span class="sxs-lookup"><span data-stu-id="47ce9-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="47ce9-140">En la **ventana Tarea** que se abre, vaya a la **pestaña General.** Elija la cuenta de usuario del SISTEMA local (BUILTIN\SYSTEM) en **Opciones de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="47ce9-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="47ce9-141">Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.</span><span class="sxs-lookup"><span data-stu-id="47ce9-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="47ce9-142">Vaya a la **pestaña Acciones** y haga clic **en Nuevo...**. Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción.</span><span class="sxs-lookup"><span data-stu-id="47ce9-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="47ce9-143">Escriba el nombre de archivo y la ubicación del archivo  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* compartido.</span><span class="sxs-lookup"><span data-stu-id="47ce9-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="47ce9-144">Haga **clic en Aceptar** y cierre las ventanas GPMC abiertas.</span><span class="sxs-lookup"><span data-stu-id="47ce9-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47ce9-145">El offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47ce9-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="47ce9-146">Supervisar la configuración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="47ce9-146">Monitor device configuration</span></span>
<span data-ttu-id="47ce9-147">Con la directiva de grupo no hay una opción para supervisar la implementación de directivas en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="47ce9-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="47ce9-148">La supervisión se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.</span><span class="sxs-lookup"><span data-stu-id="47ce9-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="47ce9-149">Supervisar dispositivos con el portal</span><span class="sxs-lookup"><span data-stu-id="47ce9-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="47ce9-150">Vaya al [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="47ce9-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="47ce9-151">Haga clic **en Lista dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="47ce9-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="47ce9-152">Compruebe que aparecen dispositivos.</span><span class="sxs-lookup"><span data-stu-id="47ce9-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="47ce9-153">Los dispositivos pueden tardar varios días en aparecer en la **lista Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="47ce9-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="47ce9-154">Esto incluye el tiempo que tardan las directivas en distribuirse en el dispositivo, el tiempo que tarda antes de que el usuario inicie sesión y el tiempo que tarda el punto de conexión en iniciar la presentación de informes.</span><span class="sxs-lookup"><span data-stu-id="47ce9-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="47ce9-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="47ce9-155">Related topics</span></span>
- [<span data-ttu-id="47ce9-156">Incorporación de dispositivos Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="47ce9-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="47ce9-157">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="47ce9-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="47ce9-158">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="47ce9-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="47ce9-159">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="47ce9-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="47ce9-160">Ejecutar una prueba de detección en un dispositivo ATP de Microsoft Defender recién incorporado</span><span class="sxs-lookup"><span data-stu-id="47ce9-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="47ce9-161">Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="47ce9-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)