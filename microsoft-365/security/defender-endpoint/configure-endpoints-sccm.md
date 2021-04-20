---
title: Incorporar dispositivos Windows 10 con Configuration Manager
description: Use Configuration Manager para implementar el paquete de configuración en dispositivos para que se incorpore al servicio.
keywords: incorporar dispositivos con sccm, administración de dispositivos, configurar dispositivos de Windows ATP, configurar Microsoft Defender para dispositivos de punto de conexión
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
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: 3550bec28945ab888efbe2ca46f12ca7f96aab4a
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892868"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="6f07d-104">Incorporar dispositivos Windows 10 con Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6f07d-104">Onboard Windows 10 devices using Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f07d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6f07d-105">**Applies to:**</span></span>

- [<span data-ttu-id="6f07d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6f07d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6f07d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f07d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="6f07d-108">Rama actual de Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6f07d-108">Microsoft Endpoint Configuration Manager current branch</span></span>
- <span data-ttu-id="6f07d-109">Administrador de configuración de System Center 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6f07d-109">System Center 2012 R2 Configuration Manager</span></span>

><span data-ttu-id="6f07d-110">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6f07d-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6f07d-111">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6f07d-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a><span data-ttu-id="6f07d-112">Sistemas operativos cliente compatibles</span><span class="sxs-lookup"><span data-stu-id="6f07d-112">Supported client operating systems</span></span>

<span data-ttu-id="6f07d-113">En función de la versión de Configuration Manager que esté ejecutando, se pueden incorporar los siguientes sistemas operativos cliente:</span><span class="sxs-lookup"><span data-stu-id="6f07d-113">Based on the version of Configuration Manager you're running, the following client operating systems can be onboarded:</span></span>

#### <a name="configuration-manager-version-1910-and-prior"></a><span data-ttu-id="6f07d-114">Configuration Manager versión 1910 y anterior</span><span class="sxs-lookup"><span data-stu-id="6f07d-114">Configuration Manager version 1910 and prior</span></span>

- <span data-ttu-id="6f07d-115">Equipos clientes que ejecutan Windows 10</span><span class="sxs-lookup"><span data-stu-id="6f07d-115">Clients computers running Windows 10</span></span> 

#### <a name="configuration-manager-version-2002-and-later"></a><span data-ttu-id="6f07d-116">Configuration Manager versión 2002 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="6f07d-116">Configuration Manager version 2002 and later</span></span>

<span data-ttu-id="6f07d-117">A partir de la versión 2002 de Configuration Manager, puede incorporar los siguientes sistemas operativos:</span><span class="sxs-lookup"><span data-stu-id="6f07d-117">Starting in Configuration Manager version 2002, you can onboard the following operating systems:</span></span>

- <span data-ttu-id="6f07d-118">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="6f07d-118">Windows 8.1</span></span>
- <span data-ttu-id="6f07d-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="6f07d-119">Windows 10</span></span>
- <span data-ttu-id="6f07d-120">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6f07d-120">Windows Server 2012 R2</span></span>
- <span data-ttu-id="6f07d-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="6f07d-121">Windows Server 2016</span></span>
- <span data-ttu-id="6f07d-122">Windows Server 2016, versión 1803 o posterior</span><span class="sxs-lookup"><span data-stu-id="6f07d-122">Windows Server 2016, version 1803 or later</span></span>
- <span data-ttu-id="6f07d-123">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="6f07d-123">Windows Server 2019</span></span>

>[!NOTE]
><span data-ttu-id="6f07d-124">Para obtener más información sobre cómo incorporar Windows Server 2012 R2, Windows Server 2016 y Windows Server 2019, consulte [Onboard Windows servers](configure-server-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="6f07d-124">For more information on how to onboard Windows Server 2012 R2, Windows Server 2016, and Windows Server 2019, see, [Onboard Windows servers](configure-server-endpoints.md).</span></span>



### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="6f07d-125">Incorporar dispositivos con System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6f07d-125">Onboard devices using System Center Configuration Manager</span></span>


<span data-ttu-id="6f07d-126">[![Imagen del PDF que muestra las distintas rutas de implementación](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6f07d-126">[![Image of the PDF showing the various deployment paths](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span></span>


<span data-ttu-id="6f07d-127">Consulte el [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  o  [Visio para](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ver las distintas rutas de acceso en la implementación de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f07d-127">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span> 



1. <span data-ttu-id="6f07d-128">Abra el archivo .zip del paquete de configuración de Configuration Manager (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del Asistente para incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="6f07d-128">Open the Configuration Manager configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="6f07d-129">También puede obtener el paquete del Centro de seguridad [de Microsoft Defender:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="6f07d-129">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="6f07d-130">En el panel de navegación, seleccione **Configuración**  >  **incorporación**.</span><span class="sxs-lookup"><span data-stu-id="6f07d-130">In the navigation pane, select **Settings** > **Onboarding**.</span></span>
    
    1. <span data-ttu-id="6f07d-131">Selecciona Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6f07d-131">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="6f07d-132">En el **campo Método de** implementación, seleccione System Center Configuration Manager **2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="6f07d-132">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="6f07d-133">Seleccione **Descargar paquete** y guarde el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="6f07d-133">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="6f07d-134">Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan tener acceso los administradores de red que implementarán el paquete.</span><span class="sxs-lookup"><span data-stu-id="6f07d-134">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="6f07d-135">Debe tener un archivo denominado *WindowsDefenderATPOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="6f07d-135">You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="6f07d-136">Implemente el paquete siguiendo los pasos descritos en el artículo Paquetes y programas [en System Center 2012 de Configuration Manager de R2.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="6f07d-136">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="6f07d-137">a.</span><span class="sxs-lookup"><span data-stu-id="6f07d-137">a.</span></span> <span data-ttu-id="6f07d-138">Elija una colección de dispositivos predefinida en la que implementar el paquete.</span><span class="sxs-lookup"><span data-stu-id="6f07d-138">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="6f07d-139">Defender for Endpoint no admite la incorporación durante la fase de la experiencia de implementación [(OOBE).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87)</span><span class="sxs-lookup"><span data-stu-id="6f07d-139">Defender for Endpoint doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="6f07d-140">Asegúrate de que los usuarios completen OOBE después de ejecutar la instalación o actualización de Windows.</span><span class="sxs-lookup"><span data-stu-id="6f07d-140">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="6f07d-141">Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que un dispositivo está correctamente incorporado al servicio.</span><span class="sxs-lookup"><span data-stu-id="6f07d-141">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="6f07d-142">Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo defender para endpoint](run-detection-test.md)recién incorporado.</span><span class="sxs-lookup"><span data-stu-id="6f07d-142">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>
>
> <span data-ttu-id="6f07d-143">Ten en cuenta que es posible crear una regla de detección en una aplicación de Configuration Manager para comprobar continuamente si se ha incorporado un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f07d-143">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="6f07d-144">Una aplicación es un tipo diferente de objeto que un paquete y un programa.</span><span class="sxs-lookup"><span data-stu-id="6f07d-144">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="6f07d-145">Si un dispositivo aún no está incorporado (debido a la finalización de OOBE pendiente o a cualquier otro motivo), Configuration Manager volverá a intentar incorporar el dispositivo hasta que la regla detecte el cambio de estado.</span><span class="sxs-lookup"><span data-stu-id="6f07d-145">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="6f07d-146">Este comportamiento se puede lograr mediante la creación de una regla de detección que comprueba si el valor del Registro "OnboardingState" (de tipo REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="6f07d-146">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="6f07d-147">Este valor del Registro se encuentra en "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="6f07d-147">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="6f07d-148">Para obtener más información, vea [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span><span class="sxs-lookup"><span data-stu-id="6f07d-148">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="6f07d-149">Configuración de la colección de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f07d-149">Configure sample collection settings</span></span>

<span data-ttu-id="6f07d-150">Para cada dispositivo, puedes establecer un valor de configuración para especificar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través del Centro de seguridad de Microsoft Defender para enviar un archivo para un análisis profundo.</span><span class="sxs-lookup"><span data-stu-id="6f07d-150">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="6f07d-151">Estas opciones de configuración normalmente se realizan a través de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="6f07d-151">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="6f07d-152">Puedes establecer una regla de cumplimiento para el elemento de configuración en Configuration Manager para cambiar la configuración de recurso compartido de ejemplo en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f07d-152">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="6f07d-153">Esta regla debe ser un elemento de *configuración* de regla de cumplimiento corrector que establece el valor de una clave del Registro en dispositivos dirigidos para asegurarse de que son quejas.</span><span class="sxs-lookup"><span data-stu-id="6f07d-153">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="6f07d-154">La configuración se establece mediante la siguiente entrada de clave del Registro:</span><span class="sxs-lookup"><span data-stu-id="6f07d-154">The configuration is set through the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

<span data-ttu-id="6f07d-155">Donde:</span><span class="sxs-lookup"><span data-stu-id="6f07d-155">Where:</span></span><br>
<span data-ttu-id="6f07d-156">El tipo de clave es un D-WORD.</span><span class="sxs-lookup"><span data-stu-id="6f07d-156">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="6f07d-157">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="6f07d-157">Possible values are:</span></span>
- <span data-ttu-id="6f07d-158">0: no permite el uso compartido de muestras desde este dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f07d-158">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="6f07d-159">1: permite compartir todos los tipos de archivo desde este dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f07d-159">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="6f07d-160">El valor predeterminado en caso de que la clave del Registro no exista es 1.</span><span class="sxs-lookup"><span data-stu-id="6f07d-160">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="6f07d-161">Para obtener más información sobre el cumplimiento de System Center Configuration Manager, vea Introducción a la [configuración de cumplimiento en System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span><span class="sxs-lookup"><span data-stu-id="6f07d-161">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="6f07d-162">Otras opciones de configuración recomendadas</span><span class="sxs-lookup"><span data-stu-id="6f07d-162">Other recommended configuration settings</span></span>
<span data-ttu-id="6f07d-163">Después de incorporar dispositivos al servicio, es importante aprovechar las capacidades de protección contra amenazas incluidas al habilitarlos con las siguientes opciones de configuración recomendadas.</span><span class="sxs-lookup"><span data-stu-id="6f07d-163">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="6f07d-164">Configuración de la colección de dispositivos</span><span class="sxs-lookup"><span data-stu-id="6f07d-164">Device collection configuration</span></span>
<span data-ttu-id="6f07d-165">Si usa Endpoint Configuration Manager, versión 2002 o posterior, puede ampliar la implementación para incluir servidores o clientes de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="6f07d-165">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="6f07d-166">Configuración de protección de próxima generación</span><span class="sxs-lookup"><span data-stu-id="6f07d-166">Next generation protection configuration</span></span>
<span data-ttu-id="6f07d-167">Se recomiendan las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="6f07d-167">The following configuration settings are recommended:</span></span>

<span data-ttu-id="6f07d-168">**Escanear**</span><span class="sxs-lookup"><span data-stu-id="6f07d-168">**Scan**</span></span> <br>
- <span data-ttu-id="6f07d-169">Examinar dispositivos de almacenamiento extraíbles, como unidades USB: Sí</span><span class="sxs-lookup"><span data-stu-id="6f07d-169">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="6f07d-170">**Protección en tiempo real**</span><span class="sxs-lookup"><span data-stu-id="6f07d-170">**Real-time Protection**</span></span> <br>
- <span data-ttu-id="6f07d-171">Habilitar supervisión de comportamiento: Sí</span><span class="sxs-lookup"><span data-stu-id="6f07d-171">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="6f07d-172">Habilitar la protección contra aplicaciones potencialmente no deseadas en la descarga y antes de la instalación: Sí</span><span class="sxs-lookup"><span data-stu-id="6f07d-172">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="6f07d-173">**Servicio de protección en la nube**</span><span class="sxs-lookup"><span data-stu-id="6f07d-173">**Cloud Protection Service**</span></span>
- <span data-ttu-id="6f07d-174">Tipo de pertenencia al Servicio de protección en la nube: pertenencia avanzada</span><span class="sxs-lookup"><span data-stu-id="6f07d-174">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="6f07d-175">**Reducción de superficie de ataque** Configure todas las reglas disponibles en Auditar.</span><span class="sxs-lookup"><span data-stu-id="6f07d-175">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="6f07d-176">El bloqueo de estas actividades puede interrumpir procesos empresariales legítimos.</span><span class="sxs-lookup"><span data-stu-id="6f07d-176">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="6f07d-177">El mejor enfoque es establecer todo para auditar, identificar cuáles son seguros para activarse y, a continuación, habilitar esa configuración en puntos de conexión que no tienen detecciones de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="6f07d-177">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>


<span data-ttu-id="6f07d-178">**Protección de red**</span><span class="sxs-lookup"><span data-stu-id="6f07d-178">**Network protection**</span></span> <br>
<span data-ttu-id="6f07d-179">Antes de habilitar la protección de red en modo de auditoría o bloqueo, asegúrese de que ha instalado la actualización de la plataforma antimalware, que se puede obtener desde la [página de soporte técnico](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span><span class="sxs-lookup"><span data-stu-id="6f07d-179">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="6f07d-180">**Acceso controlado a carpetas**</span><span class="sxs-lookup"><span data-stu-id="6f07d-180">**Controlled folder access**</span></span><br>
<span data-ttu-id="6f07d-181">Habilite la característica en modo auditoría durante al menos 30 días.</span><span class="sxs-lookup"><span data-stu-id="6f07d-181">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="6f07d-182">Después de este período, revise las detecciones y cree una lista de aplicaciones que puedan escribir en directorios protegidos.</span><span class="sxs-lookup"><span data-stu-id="6f07d-182">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="6f07d-183">Para obtener más información, vea [Evaluate controlled folder access](evaluate-controlled-folder-access.md).</span><span class="sxs-lookup"><span data-stu-id="6f07d-183">For more information, see [Evaluate controlled folder access](evaluate-controlled-folder-access.md).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="6f07d-184">Dispositivos offboard con Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6f07d-184">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="6f07d-185">Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="6f07d-185">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="6f07d-186">Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f07d-186">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="6f07d-187">Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="6f07d-187">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="6f07d-188">Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="6f07d-188">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a><span data-ttu-id="6f07d-189">Dispositivos offboard con la rama actual de Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="6f07d-189">Offboard devices using Microsoft Endpoint Manager current branch</span></span>

<span data-ttu-id="6f07d-190">Si usa la rama actual de Microsoft Endpoint Manager, vea [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span><span class="sxs-lookup"><span data-stu-id="6f07d-190">If you use Microsoft Endpoint Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="6f07d-191">Dispositivos offboard con System Center 2012 Configuration Manager de R2</span><span class="sxs-lookup"><span data-stu-id="6f07d-191">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="6f07d-192">Obtener el paquete de offboarding del Centro de [seguridad de Microsoft Defender:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="6f07d-192">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="6f07d-193">En el panel de navegación, seleccione **Configuración**  >   **de offboarding**.</span><span class="sxs-lookup"><span data-stu-id="6f07d-193">In the navigation pane, select **Settings** >  **Offboarding**.</span></span>

    1. <span data-ttu-id="6f07d-194">Selecciona Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6f07d-194">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="6f07d-195">En el **campo Método de** implementación, seleccione System Center Configuration Manager **2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="6f07d-195">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="6f07d-196">Seleccione **Descargar paquete** y guarde el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="6f07d-196">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="6f07d-197">Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan tener acceso los administradores de red que implementarán el paquete.</span><span class="sxs-lookup"><span data-stu-id="6f07d-197">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="6f07d-198">Debe tener un archivo denominado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="6f07d-198">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="6f07d-199">Implemente el paquete siguiendo los pasos descritos en el artículo Paquetes y programas [en System Center 2012 de Configuration Manager de R2.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="6f07d-199">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="6f07d-200">a.</span><span class="sxs-lookup"><span data-stu-id="6f07d-200">a.</span></span> <span data-ttu-id="6f07d-201">Elija una colección de dispositivos predefinida en la que implementar el paquete.</span><span class="sxs-lookup"><span data-stu-id="6f07d-201">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f07d-202">Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.</span><span class="sxs-lookup"><span data-stu-id="6f07d-202">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="6f07d-203">Supervisar la configuración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f07d-203">Monitor device configuration</span></span>

<span data-ttu-id="6f07d-204">Si usa la rama actual de Microsoft Endpoint Manager, use el panel integrado de Defender para endpoint en la consola de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="6f07d-204">If you're using Microsoft Endpoint Manager current branch, use the built-in Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="6f07d-205">Para obtener más información, [vea Defender for Endpoint - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span><span class="sxs-lookup"><span data-stu-id="6f07d-205">For more information, see [Defender for Endpoint - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="6f07d-206">Si usa System Center 2012 Configuration Manager de R2, la supervisión consta de dos partes:</span><span class="sxs-lookup"><span data-stu-id="6f07d-206">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="6f07d-207">Confirmar que el paquete de configuración se ha implementado correctamente y se está ejecutando (o se ha ejecutado correctamente) en los dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="6f07d-207">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="6f07d-208">Comprobar que los dispositivos son compatibles con el servicio Defender for Endpoint (esto garantiza que el dispositivo pueda completar el proceso de incorporación y pueda seguir informando de los datos al servicio).</span><span class="sxs-lookup"><span data-stu-id="6f07d-208">Checking that the devices are compliant with the Defender for Endpoint service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="6f07d-209">Confirmar que el paquete de configuración se ha implementado correctamente</span><span class="sxs-lookup"><span data-stu-id="6f07d-209">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="6f07d-210">En la consola de Configuration Manager, haga clic **en Supervisión** en la parte inferior del panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="6f07d-210">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="6f07d-211">Seleccione **Información** general y, a continuación, **Implementaciones**.</span><span class="sxs-lookup"><span data-stu-id="6f07d-211">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="6f07d-212">Seleccione en la implementación con el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="6f07d-212">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="6f07d-213">Revise los indicadores de estado en **Estadísticas de finalización** y **Estado de contenido**.</span><span class="sxs-lookup"><span data-stu-id="6f07d-213">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="6f07d-214">Si hay implementaciones con errores (dispositivos con **errores,** requisitos no cumplidos o estados **con errores),** es posible que deba solucionar los problemas de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6f07d-214">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="6f07d-215">Para obtener más información, vea [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span><span class="sxs-lookup"><span data-stu-id="6f07d-215">For more information, see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>

    ![Configuration Manager que muestra una implementación correcta sin errores](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="6f07d-217">Comprobar que los dispositivos son compatibles con el servicio de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="6f07d-217">Check that the devices are compliant with the Microsoft Defender for Endpoint service</span></span>

<span data-ttu-id="6f07d-218">Puede establecer una regla de cumplimiento para el elemento de configuración en System Center 2012 Configuration Manager de R2 para supervisar la implementación.</span><span class="sxs-lookup"><span data-stu-id="6f07d-218">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

<span data-ttu-id="6f07d-219">Esta regla debe ser un elemento de configuración de regla de cumplimiento no *correctivo* que supervisa el valor de una clave del Registro en dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="6f07d-219">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="6f07d-220">Supervise la siguiente entrada de clave del Registro:</span><span class="sxs-lookup"><span data-stu-id="6f07d-220">Monitor the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

<span data-ttu-id="6f07d-221">Para obtener más información, vea [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span><span class="sxs-lookup"><span data-stu-id="6f07d-221">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6f07d-222">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6f07d-222">Related topics</span></span>
- [<span data-ttu-id="6f07d-223">Incorporación de dispositivos Windows 10 con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="6f07d-223">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="6f07d-224">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="6f07d-224">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="6f07d-225">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="6f07d-225">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="6f07d-226">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="6f07d-226">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="6f07d-227">Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado</span><span class="sxs-lookup"><span data-stu-id="6f07d-227">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="6f07d-228">Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6f07d-228">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
