---
title: Incorporar dispositivos Windows 10 con Configuration Manager
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
description: Usa Configuration Manager para implementar el paquete de configuración en dispositivos para que se incorpore al servicio.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769517"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="9e629-103">Incorporar dispositivos Windows 10 con Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9e629-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="9e629-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9e629-104">**Applies to:**</span></span>

- [<span data-ttu-id="9e629-105">Prevención de pérdida de datos (DLP) de Punto de conexión de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e629-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="9e629-106">Administrador de configuración de System Center 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9e629-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="9e629-107">Incorporar dispositivos con System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9e629-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="9e629-108">Abre el archivo .zip del paquete de configuración de Configuration Manager (*DeviceComplianceOnboardingPackage.zip*) que descargaste desde el Asistente para la incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="9e629-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="9e629-109">También puede obtener el paquete del Centro [de cumplimiento de Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="9e629-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="9e629-110">En el panel de navegación, selecciona **Configuración**  >  **de incorporación de**  >  **dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="9e629-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="9e629-111">En el **campo Método** de implementación, seleccione Microsoft Endpoint Configuration **Manager 2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="9e629-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
 
4. <span data-ttu-id="9e629-112">Seleccione **Descargar paquete** y guarde el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="9e629-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="9e629-113">Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los administradores de red que implementarán el paquete.</span><span class="sxs-lookup"><span data-stu-id="9e629-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="9e629-114">Debe tener un archivo denominado *DeviceComplianceOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="9e629-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="9e629-115">Implementa el paquete siguiendo los pasos del artículo [Paquetes y programas de System Center 2012 de Configuration Manager R2.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="9e629-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

7. <span data-ttu-id="9e629-116">Elige una colección de dispositivos predefinida en la que implementar el paquete.</span><span class="sxs-lookup"><span data-stu-id="9e629-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="9e629-117">La prevención de pérdida de datos de puntos de conexión de Microsoft 365 no admite la incorporación durante la fase de configuración integrada [(OOBE).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87)</span><span class="sxs-lookup"><span data-stu-id="9e629-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="9e629-118">Asegúrate de que los usuarios completen la configuración rápida después de ejecutar la instalación o actualización de Windows.</span><span class="sxs-lookup"><span data-stu-id="9e629-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="9e629-119">Después de incorporar el dispositivo, puedes ejecutar una prueba de detección para comprobar que un dispositivo está correctamente incorporado al servicio.</span><span class="sxs-lookup"><span data-stu-id="9e629-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="9e629-120">Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo atp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)de Microsoft Defender recién incorporado.</span><span class="sxs-lookup"><span data-stu-id="9e629-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="9e629-121">Ten en cuenta que es posible crear una regla de detección en una aplicación de Configuration Manager para comprobar continuamente si se ha incorporado un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e629-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="9e629-122">Una aplicación es un tipo diferente de objeto que un paquete y un programa.</span><span class="sxs-lookup"><span data-stu-id="9e629-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="9e629-123">Si un dispositivo aún no está incorporado (debido a la finalización OOBE pendiente o a cualquier otro motivo), Configuration Manager volverá a intentar incorporar el dispositivo hasta que la regla detecte el cambio de estado.</span><span class="sxs-lookup"><span data-stu-id="9e629-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="9e629-124">Este comportamiento se puede lograr mediante la creación de una comprobación de regla de detección si el valor del Registro "OnboardingState" (de tipo REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="9e629-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="9e629-125">Este valor del Registro se encuentra en "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="9e629-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="9e629-126">Para obtener más información, consulta [Configurar métodos de detección System Center 2012 Administrador de configuración de R2.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="9e629-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="9e629-127">Configuración de las opciones de la colección de muestras</span><span class="sxs-lookup"><span data-stu-id="9e629-127">Configure sample collection settings</span></span>

<span data-ttu-id="9e629-128">Para cada dispositivo, puedes establecer un valor de configuración para especificar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través del Centro de seguridad de Microsoft Defender para enviar un archivo para un análisis detallado.</span><span class="sxs-lookup"><span data-stu-id="9e629-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="9e629-129">Estas opciones de configuración se suelen realizar a través de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9e629-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="9e629-130">Puedes establecer una regla de cumplimiento para el elemento de configuración en Configuration Manager para cambiar la configuración del recurso compartido de ejemplo en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e629-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="9e629-131">Esta regla debe ser un *elemento* de configuración de regla de cumplimiento correctivo que establece el valor de una clave del Registro en los dispositivos de destino para asegurarse de que son quejas.</span><span class="sxs-lookup"><span data-stu-id="9e629-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="9e629-132">La configuración se establece a través de la siguiente entrada de clave del Registro:</span><span class="sxs-lookup"><span data-stu-id="9e629-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="9e629-133">Donde:</span><span class="sxs-lookup"><span data-stu-id="9e629-133">Where:</span></span><br>
<span data-ttu-id="9e629-134">El tipo de clave es D-WORD.</span><span class="sxs-lookup"><span data-stu-id="9e629-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="9e629-135">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="9e629-135">Possible values are:</span></span>
- <span data-ttu-id="9e629-136">0: no permite el uso compartido de muestras desde este dispositivo</span><span class="sxs-lookup"><span data-stu-id="9e629-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="9e629-137">1: permite el uso compartido de todos los tipos de archivo desde este dispositivo</span><span class="sxs-lookup"><span data-stu-id="9e629-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="9e629-138">El valor predeterminado en caso de que la clave del Registro no exista es 1.</span><span class="sxs-lookup"><span data-stu-id="9e629-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="9e629-139">Para obtener más información sobre el cumplimiento de System Center Configuration Manager, consulta Introducción a la configuración de cumplimiento [en System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="9e629-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="9e629-140">Otras opciones de configuración recomendadas</span><span class="sxs-lookup"><span data-stu-id="9e629-140">Other recommended configuration settings</span></span>
<span data-ttu-id="9e629-141">Después de incorporar dispositivos al servicio, es importante aprovechar las capacidades de protección contra amenazas incluidas al habilitarlos con las siguientes opciones de configuración recomendadas.</span><span class="sxs-lookup"><span data-stu-id="9e629-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="9e629-142">Configuración de recopilación de dispositivos</span><span class="sxs-lookup"><span data-stu-id="9e629-142">Device collection configuration</span></span>
<span data-ttu-id="9e629-143">Si usa Endpoint Configuration Manager, versión 2002 o posterior, puede ampliar la implementación para incluir servidores o clientes de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="9e629-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="9e629-144">Configuración de protección de próxima generación</span><span class="sxs-lookup"><span data-stu-id="9e629-144">Next generation protection configuration</span></span>

<span data-ttu-id="9e629-145">Se recomiendan las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="9e629-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="9e629-146">**Escanear**</span><span class="sxs-lookup"><span data-stu-id="9e629-146">**Scan**</span></span>

- <span data-ttu-id="9e629-147">Examinar dispositivos de almacenamiento extraíbles como unidades USB: Sí</span><span class="sxs-lookup"><span data-stu-id="9e629-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="9e629-148">**Protección en tiempo real**</span><span class="sxs-lookup"><span data-stu-id="9e629-148">**Real-time Protection**</span></span>

- <span data-ttu-id="9e629-149">Habilitar supervisión de comportamiento: Sí</span><span class="sxs-lookup"><span data-stu-id="9e629-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="9e629-150">Habilitar la protección contra aplicaciones potencialmente no deseadas durante la descarga y antes de la instalación: Sí</span><span class="sxs-lookup"><span data-stu-id="9e629-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="9e629-151">**Servicio de protección en la nube**</span><span class="sxs-lookup"><span data-stu-id="9e629-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="9e629-152">Tipo de pertenencia al Servicio de protección en la nube: pertenencia avanzada</span><span class="sxs-lookup"><span data-stu-id="9e629-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="9e629-153">**Reducción de superficie de ataque** Configure todas las reglas disponibles para auditar.</span><span class="sxs-lookup"><span data-stu-id="9e629-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="9e629-154">El bloqueo de estas actividades puede interrumpir procesos empresariales legítimos.</span><span class="sxs-lookup"><span data-stu-id="9e629-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="9e629-155">El mejor enfoque es establecer todo para auditar, identificar cuáles son seguros de activar y, a continuación, habilitar esa configuración en los puntos de conexión que no tienen detecciones de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="9e629-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="9e629-156">**Protección de red**</span><span class="sxs-lookup"><span data-stu-id="9e629-156">**Network protection**</span></span>

<span data-ttu-id="9e629-157">Antes de habilitar la protección de red en modo de auditoría o bloqueo, asegúrese de que ha instalado la actualización de la plataforma antimalware, que se puede obtener desde la página [de soporte técnico.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)</span><span class="sxs-lookup"><span data-stu-id="9e629-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="9e629-158">**Acceso controlado a carpetas**</span><span class="sxs-lookup"><span data-stu-id="9e629-158">**Controlled folder access**</span></span>

<span data-ttu-id="9e629-159">Habilita la característica en modo auditoría durante al menos 30 días.</span><span class="sxs-lookup"><span data-stu-id="9e629-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="9e629-160">Después de este período, revisa las detecciones y crea una lista de aplicaciones que pueden escribir en directorios protegidos.</span><span class="sxs-lookup"><span data-stu-id="9e629-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="9e629-161">Para obtener más información, vea [Evaluar acceso controlado a carpetas.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)</span><span class="sxs-lookup"><span data-stu-id="9e629-161">For more information, see [Evaluate controlled folder access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="9e629-162">Quitar dispositivos con Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9e629-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="9e629-163">Por motivos de seguridad, el paquete usado para los dispositivos de descarga expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="9e629-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="9e629-164">Se rechazarán los paquetes de baja expirados enviados a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e629-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="9e629-165">Al descargar un paquete de descarga, se te notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="9e629-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="9e629-166">Las directivas de incorporación y baja no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario se provocarán colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="9e629-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="9e629-167">Quitar dispositivos con la rama actual de Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9e629-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="9e629-168">Si usas la rama actual de Microsoft Endpoint Configuration Manager, consulta Crear un archivo de configuración [de descarga.](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)</span><span class="sxs-lookup"><span data-stu-id="9e629-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="9e629-169">Quitar dispositivos con System Center 2012 Administrador de configuración de R2</span><span class="sxs-lookup"><span data-stu-id="9e629-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="9e629-170">Obtenga el paquete de descarga del Centro [de cumplimiento de Microsoft:](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="9e629-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="9e629-171">En el panel de navegación, selecciona **Configuración**  >   **de la incorporación de dispositivos.** >  </span><span class="sxs-lookup"><span data-stu-id="9e629-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="9e629-172">Selecciona Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9e629-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="9e629-173">En el **campo Método** de implementación, seleccione Microsoft Endpoint Configuration **Manager 2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="9e629-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
5. <span data-ttu-id="9e629-174">Seleccione **Descargar paquete** y guarde el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="9e629-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="9e629-175">Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los administradores de red que implementarán el paquete.</span><span class="sxs-lookup"><span data-stu-id="9e629-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="9e629-176">Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="9e629-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="9e629-177">Implementa el paquete siguiendo los pasos del artículo [Paquetes y programas de System Center 2012 de Configuration Manager R2.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="9e629-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

8. <span data-ttu-id="9e629-178">Elige una colección de dispositivos predefinida en la que implementar el paquete.</span><span class="sxs-lookup"><span data-stu-id="9e629-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e629-179">La baja hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.</span><span class="sxs-lookup"><span data-stu-id="9e629-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="9e629-180">Supervisar la configuración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="9e629-180">Monitor device configuration</span></span>

<span data-ttu-id="9e629-181">Si usas la rama actual de Microsoft Endpoint Configuration Manager, usa el panel integrado de ATP de Microsoft Defender en la consola de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9e629-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="9e629-182">Para obtener más información, vea [Protección contra amenazas avanzada de Microsoft Defender: Supervisar.](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)</span><span class="sxs-lookup"><span data-stu-id="9e629-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="9e629-183">Si usas el administrador de configuración System Center 2012 R2, la supervisión consta de dos partes:</span><span class="sxs-lookup"><span data-stu-id="9e629-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="9e629-184">Confirmar que el paquete de configuración se ha implementado correctamente y se está ejecutando (o se ha ejecutado correctamente) en los dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="9e629-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="9e629-185">Comprobar que los dispositivos cumplen con el servicio de prevención de pérdida de datos del punto de conexión de Microsoft 365 (esto garantiza que el dispositivo pueda completar el proceso de incorporación y pueda seguir informando de los datos al servicio).</span><span class="sxs-lookup"><span data-stu-id="9e629-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="9e629-186">Confirmar que el paquete de configuración se ha implementado correctamente</span><span class="sxs-lookup"><span data-stu-id="9e629-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="9e629-187">En la consola de Configuration Manager, haga clic en **Supervisión** en la parte inferior del panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="9e629-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="9e629-188">Seleccione **Información general** y, a continuación, **Implementaciones.**</span><span class="sxs-lookup"><span data-stu-id="9e629-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="9e629-189">Selecciona la implementación con el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="9e629-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="9e629-190">Revise los indicadores de estado en **Estadísticas de finalización** y **Estado del contenido.**</span><span class="sxs-lookup"><span data-stu-id="9e629-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="9e629-191">Si hay implementaciones con errores (dispositivos con **errores,** requisitos no cumplidos o estados con **errores),** es posible que deba solucionar los problemas de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9e629-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="9e629-192">Para obtener más información, consulte Solucionar problemas de incorporación de Protección contra amenazas avanzada [de Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="9e629-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Configuration Manager muestra una implementación correcta sin errores](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="9e629-194">Comprobar que los dispositivos cumplen con el servicio de prevención de pérdida de datos del punto de conexión de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e629-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="9e629-195">Puedes establecer una regla de cumplimiento para el elemento de configuración en System Center 2012 Administrador de configuración R2 para supervisar la implementación.</span><span class="sxs-lookup"><span data-stu-id="9e629-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="9e629-196">Este procedimiento y la entrada del Registro se aplican a DLP de Punto de conexión, así como a la Protección contra amenazas avanzada.</span><span class="sxs-lookup"><span data-stu-id="9e629-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="9e629-197">Esta regla debe ser un elemento *de configuración de* regla de cumplimiento no correctivo que supervisa el valor de una clave del Registro en los dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="9e629-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="9e629-198">Supervise la siguiente entrada de clave del Registro:</span><span class="sxs-lookup"><span data-stu-id="9e629-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="9e629-199">Para obtener más información, consulta [Introducción a la configuración de cumplimiento en System Center 2012 Administrador de configuración de R2.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="9e629-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9e629-200">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9e629-200">Related topics</span></span>
- [<span data-ttu-id="9e629-201">Incorporar dispositivos Windows 10 mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="9e629-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="9e629-202">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="9e629-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="9e629-203">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="9e629-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="9e629-204">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="9e629-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="9e629-205">Ejecutar una prueba de detección en un dispositivo atp de Microsoft Defender recién incorporado</span><span class="sxs-lookup"><span data-stu-id="9e629-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="9e629-206">Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9e629-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
