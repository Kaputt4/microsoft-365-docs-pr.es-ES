---
title: 'ATP de Microsoft Defender para Mac: extensiones del sistema (versión preliminar)'
description: Este artículo contiene instrucciones para probar la funcionalidad de extensiones del sistema de ATP de Microsoft Defender para Mac. Esta funcionalidad está actualmente en versión preliminar pública.
keywords: microsoft, defender, atp, mac, kernel, system, extensions, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 6becdd995d70c0b8193e8df097c9256dc38c72a2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185902"
---
# <a name="microsoft-defender-for-endpoint-for-mac---system-extensions-public-preview"></a><span data-ttu-id="1f600-105">Microsoft Defender para Endpoint para Mac: versión preliminar pública de extensiones del sistema)</span><span class="sxs-lookup"><span data-stu-id="1f600-105">Microsoft Defender for Endpoint for Mac - system extensions public preview)</span></span>

<span data-ttu-id="1f600-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1f600-106">**Applies to:**</span></span>
- [<span data-ttu-id="1f600-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1f600-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1f600-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f600-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1f600-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="1f600-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1f600-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="1f600-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1f600-111">En alineación con la evolución de macOS, estamos preparando una actualización de Defender para Endpoint para Mac que aprovecha las extensiones del sistema en lugar de las extensiones de kernel.</span><span class="sxs-lookup"><span data-stu-id="1f600-111">In alignment with macOS evolution, we are preparing a Defender for Endpoint for Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="1f600-112">Esta actualización solo se aplicará a macOS Catalina (10.15.4) y versiones posteriores de macOS.</span><span class="sxs-lookup"><span data-stu-id="1f600-112">This update will only apply to macOS Catalina (10.15.4) and later versions of macOS.</span></span>

<span data-ttu-id="1f600-113">Esta funcionalidad está actualmente en versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="1f600-113">This functionality is currently in public preview.</span></span> <span data-ttu-id="1f600-114">En este artículo se describe cómo habilitar esta funcionalidad en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1f600-114">This article describes how to enable this functionality on your device.</span></span> <span data-ttu-id="1f600-115">Puedes probar esta característica localmente en tu propio dispositivo o configurarla de forma remota a través de una herramienta de administración.</span><span class="sxs-lookup"><span data-stu-id="1f600-115">You can try out this feature locally on your own device or configure it remotely through a management tool.</span></span>

<span data-ttu-id="1f600-116">Estos pasos suponen que ya tienes Defender for Endpoint ejecutándose en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1f600-116">These steps assume you already have Defender for Endpoint running on your device.</span></span> <span data-ttu-id="1f600-117">Para obtener más información, consulte [esta página](microsoft-defender-endpoint-mac.md).</span><span class="sxs-lookup"><span data-stu-id="1f600-117">For more information, see [this page](microsoft-defender-endpoint-mac.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="1f600-118">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="1f600-118">Known issues</span></span>

- <span data-ttu-id="1f600-119">Hemos recibido informes sobre la extensión de red que interfiere con la extensión Kerberos de SSO de Apple.</span><span class="sxs-lookup"><span data-stu-id="1f600-119">We’ve received reports of the network extension interfering with the Apple SSO Kerberos extension.</span></span>
- <span data-ttu-id="1f600-120">La versión actual del producto sigue instalando una extensión de kernel.</span><span class="sxs-lookup"><span data-stu-id="1f600-120">The current version of the product still installs a kernel extension.</span></span> <span data-ttu-id="1f600-121">La extensión del kernel solo se usa como mecanismo de reserva y se quitará antes de que esta característica llegue a la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="1f600-121">The kernel extension is only used as a fallback mechanism and will be removed before this feature reaches public preview.</span></span>
- <span data-ttu-id="1f600-122">Todavía estamos trabajando en una versión de producto que implementa y funciona correctamente en macOS 11 Big Sur.</span><span class="sxs-lookup"><span data-stu-id="1f600-122">We're still working on a product version that deploys and functions properly on macOS 11 Big Sur.</span></span>

## <a name="deployment-prerequisites"></a><span data-ttu-id="1f600-123">Requisitos previos de implementación</span><span class="sxs-lookup"><span data-stu-id="1f600-123">Deployment prerequisites</span></span>

- <span data-ttu-id="1f600-124">Versión mínima del sistema operativo macOS: **10.15.4**</span><span class="sxs-lookup"><span data-stu-id="1f600-124">Minimum macOS operating system version: **10.15.4**</span></span>
- <span data-ttu-id="1f600-125">Versión mínima del producto: **101.03.73**</span><span class="sxs-lookup"><span data-stu-id="1f600-125">Minimum product version: **101.03.73**</span></span>
- <span data-ttu-id="1f600-126">El dispositivo debe estar en el canal **de actualización rápida de Insider**.</span><span class="sxs-lookup"><span data-stu-id="1f600-126">Your device must be in the **Insider Fast update channel**.</span></span> <span data-ttu-id="1f600-127">Puede comprobar el canal de actualización mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1f600-127">You can check the update channel by using the following command:</span></span>

  ```bash
  mdatp health --field release_ring
  ```

  <span data-ttu-id="1f600-128">Si el dispositivo aún no está en el canal de actualización rápida de Insider, ejecuta el siguiente comando desde el Terminal.</span><span class="sxs-lookup"><span data-stu-id="1f600-128">If your device isn't already in the Insider Fast update channel, execute the following command from the Terminal.</span></span> <span data-ttu-id="1f600-129">La actualización de canal surte efecto la próxima vez que se inicie el producto (cuando se instale la siguiente actualización del producto o cuando se reinicie el dispositivo).</span><span class="sxs-lookup"><span data-stu-id="1f600-129">The channel update takes effect the next time the product starts (when the next product update is installed, or when the device is rebooted).</span></span>

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  <span data-ttu-id="1f600-130">Como alternativa, si está en un entorno administrado (JAMF o Intune), puede configurar el canal de actualización de forma remota.</span><span class="sxs-lookup"><span data-stu-id="1f600-130">Alternatively, if you're in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="1f600-131">Para obtener más información, vea [Deploy updates for Microsoft Defender ATP for Mac: Set the channel name](mac-updates.md#set-the-channel-name).</span><span class="sxs-lookup"><span data-stu-id="1f600-131">For more information, see [Deploy updates for Microsoft Defender ATP for Mac: Set the channel name](mac-updates.md#set-the-channel-name).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="1f600-132">Pasos para la implementación</span><span class="sxs-lookup"><span data-stu-id="1f600-132">Deployment steps</span></span>

<span data-ttu-id="1f600-133">Siga los pasos de implementación correspondientes al entorno y al método preferido para probar esta característica.</span><span class="sxs-lookup"><span data-stu-id="1f600-133">Follow the deployment steps that correspond to your environment and your preferred method of trying out this feature.</span></span>

### <a name="manual-deployment"></a><span data-ttu-id="1f600-134">Implementación manual</span><span class="sxs-lookup"><span data-stu-id="1f600-134">Manual deployment</span></span>

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a><span data-ttu-id="1f600-135">Aprobar las extensiones del sistema y habilitar la extensión de red</span><span class="sxs-lookup"><span data-stu-id="1f600-135">Approve the system extensions and enable the network extension</span></span>

1. <span data-ttu-id="1f600-136">Una vez que se cumplan todos los requisitos previos de implementación, reinicia el dispositivo para iniciar el proceso de aprobación y activación de la extensión del sistema.</span><span class="sxs-lookup"><span data-stu-id="1f600-136">After all deployment prerequisites are met, restart your device to launch the system extension approval and activation process.</span></span>

   <span data-ttu-id="1f600-137">Verá una serie de avisos del sistema para aprobar las extensiones del sistema Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f600-137">You'll see a series of system prompts to approve the Defender for Endpoint system extensions.</span></span> <span data-ttu-id="1f600-138">Debes aprobar **todos los** mensajes de la serie, ya que macOS requiere una aprobación explícita para cada extensión que Defender para Endpoint para Mac instala en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1f600-138">You must approve **all** prompts from the series, because macOS requires an explicit approval for each extension that Defender for Endpoint for Mac installs on the device.</span></span>
   
   <span data-ttu-id="1f600-139">Para cada aprobación, seleccione **Abrir preferencias de** seguridad y, a continuación, **seleccione Permitir** para permitir que se ejecute la extensión del sistema.</span><span class="sxs-lookup"><span data-stu-id="1f600-139">For each approval, select **Open Security Preferences** and then select **Allow** to allow the system extension to run.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1f600-140">Debe cerrar y volver a abrir la ventana **Seguridad** de preferencias  >  **del & privacidad** entre las aprobaciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="1f600-140">You must close and reopen the **System Preferences** > **Security & Privacy** window between subsequent approvals.</span></span> <span data-ttu-id="1f600-141">De lo contrario, macOS no mostrará la siguiente aprobación.</span><span class="sxs-lookup"><span data-stu-id="1f600-141">Otherwise, macOS will not display the next approval.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1f600-142">Hay un tiempo de espera de un minuto antes de que el producto vuelva a la extensión del kernel.</span><span class="sxs-lookup"><span data-stu-id="1f600-142">There is a one-minute timeout before the product falls back to the kernel extension.</span></span> <span data-ttu-id="1f600-143">Esto garantiza que el dispositivo está protegido.</span><span class="sxs-lookup"><span data-stu-id="1f600-143">This ensures that the device is protected.</span></span>
   >
   > <span data-ttu-id="1f600-144">Si transcurre más de un minuto, reinicie el demonio reiniciando el dispositivo o usando para desencadenar de nuevo `sudo killall -9 wdavdaemon` el flujo de aprobación.</span><span class="sxs-lookup"><span data-stu-id="1f600-144">If more than one minute elapses, restart the daemon by rebooting the device or by using `sudo killall -9 wdavdaemon` to trigger the approval flow again.</span></span>

   ![Ventana emergente de aprobación de extensión del sistema](images/mac-system-extension-approval.png)

   ![Ventana de aprobación de extensión del sistema](images/mac-system-extension-pref.png)

1. <span data-ttu-id="1f600-147">Una vez aprobadas las extensiones del sistema, macOS solicita una aprobación para permitir el filtrado del tráfico de red.</span><span class="sxs-lookup"><span data-stu-id="1f600-147">After the system extensions are approved, macOS prompts for an approval to allow network traffic to be filtered.</span></span> <span data-ttu-id="1f600-148">Haga clic **en Permitir**.</span><span class="sxs-lookup"><span data-stu-id="1f600-148">Click **Allow**.</span></span>

   ![Pop-up de aprobación de extensión de red](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a><span data-ttu-id="1f600-150">Conceder acceso en disco completo a la extensión del sistema Endpoint Security</span><span class="sxs-lookup"><span data-stu-id="1f600-150">Grant Full Disk Access to the Endpoint Security system extension</span></span>

<span data-ttu-id="1f600-151">Abra la **pestaña Seguridad de &** preferencias del sistema y conceda acceso en disco completo a la extensión de seguridad de extremo  >    >   de Microsoft **Defender.** </span><span class="sxs-lookup"><span data-stu-id="1f600-151">Open the **System Preferences** > **Security & Privacy** > **Privacy** tab and grant **Full Disk Access** to the **Microsoft Defender Endpoint Security Extension**.</span></span>

![Acceso en disco completo para la extensión del sistema Endpoint Security](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a><span data-ttu-id="1f600-153">Reiniciar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="1f600-153">Reboot your device</span></span>

<span data-ttu-id="1f600-154">Para que los cambios entren en vigor, debes reiniciar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1f600-154">In order for the changes to take effect, you must reboot your device.</span></span>

#### <a name="verify-that-the-system-extensions-are-running"></a><span data-ttu-id="1f600-155">Comprobar que las extensiones del sistema se están ejecutando</span><span class="sxs-lookup"><span data-stu-id="1f600-155">Verify that the system extensions are running</span></span>

<span data-ttu-id="1f600-156">Desde el Terminal, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1f600-156">From the Terminal, run the following command:</span></span>

```bash
mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="1f600-157">La salida `endpoint_security_extension` de terminal indica que el producto usa la funcionalidad de extensiones del sistema.</span><span class="sxs-lookup"><span data-stu-id="1f600-157">Terminal output `endpoint_security_extension` indicates the product is using the system extensions functionality.</span></span>

### <a name="managed-deployment"></a><span data-ttu-id="1f600-158">Implementación administrada</span><span class="sxs-lookup"><span data-stu-id="1f600-158">Managed deployment</span></span>

<span data-ttu-id="1f600-159">Consulte Nuevos perfiles de configuración para macOS Catalina y versiones más recientes de [macOS: JAMF](mac-sysext-policies.md#jamf) para los nuevos perfiles de configuración que debe implementar para esta nueva característica.</span><span class="sxs-lookup"><span data-stu-id="1f600-159">Refer to [New configuration profiles for macOS Catalina and newer versions of macOS: JAMF](mac-sysext-policies.md#jamf) for the new configuration profiles you must deploy for this new feature.</span></span>

<span data-ttu-id="1f600-160">Además de estos perfiles, asegúrese de configurar los dispositivos de destino para que se encuentran en el canal de actualización rápida de Insider, como se describe en [Requisitos previos de implementación.](#deployment-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="1f600-160">In addition to those profiles, make sure to configure the target devices to be in the Insider Fast update channel, as described in [Deployment prerequisites](#deployment-prerequisites).</span></span>

<span data-ttu-id="1f600-161">En un dispositivo donde se cumplan todos los requisitos previos y se hayan implementado los nuevos perfiles de configuración, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1f600-161">On a device where all prerequisites are met and the new configuration profiles have been deployed, run the following command:</span></span>

```bash
$ mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="1f600-162">Si este comando imprime `endpoint_security_extension` , el producto usa la funcionalidad de extensiones del sistema.</span><span class="sxs-lookup"><span data-stu-id="1f600-162">If this command prints `endpoint_security_extension`, the product is using the system extensions functionality.</span></span>

## <a name="validate-basic-scenarios"></a><span data-ttu-id="1f600-163">Validar escenarios básicos</span><span class="sxs-lookup"><span data-stu-id="1f600-163">Validate basic scenarios</span></span>

1. <span data-ttu-id="1f600-164">Probar la detección del Instituto Europeo de Investigación de Antivirus informáticos (EICAR).</span><span class="sxs-lookup"><span data-stu-id="1f600-164">Test European Institute for Computer Antivirus Research (EICAR) detection.</span></span> <span data-ttu-id="1f600-165">Desde una ventana de Terminal, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1f600-165">From a Terminal window, run the following command:</span></span>

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   <span data-ttu-id="1f600-166">Compruebe que el archivo EICAR está en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="1f600-166">Verify that the EICAR file is quarantined.</span></span> <span data-ttu-id="1f600-167">Puede comprobar el estado del archivo en la página Historial de protección de la interfaz de usuario o desde una línea de comandos mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1f600-167">You can verify the file's status on the Protection History page in the user interface, or from a command line by using the following command:</span></span>

    ```bash
    mdatp threat list
    ```

2. <span data-ttu-id="1f600-168">Pruebe el escenario DE DEtección y respuesta de puntos de conexión (EDR) DE BRICOLAJE.</span><span class="sxs-lookup"><span data-stu-id="1f600-168">Test the Endpoint Detection and Response (EDR) DIY scenario.</span></span> <span data-ttu-id="1f600-169">Desde una ventana de terminal, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1f600-169">From a terminal window, run the following command:</span></span>

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   <span data-ttu-id="1f600-170">Valide que se han publicado dos alertas en el portal en la página del equipo para escenarios DE BRICOLAJE de EICAR y EDR.</span><span class="sxs-lookup"><span data-stu-id="1f600-170">Validate that two alerts popped up in the portal on the machine page for EICAR and EDR DIY scenarios.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="1f600-171">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="1f600-171">Frequently asked questions</span></span>

- <span data-ttu-id="1f600-172">P: ¿Por qué todavía veo `kernel_extension` cuando se `mdatp health --field real_time_protection_subsystem` ejecuta?</span><span class="sxs-lookup"><span data-stu-id="1f600-172">Q: Why am I still seeing `kernel_extension` when I run `mdatp health --field real_time_protection_subsystem`?</span></span>

    <span data-ttu-id="1f600-173">A: Vuelva a consultar la sección [Requisitos previos de implementación](#deployment-prerequisites) y compruebe que se cumplen todos los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="1f600-173">A: Refer back to the [Deployment prerequisites](#deployment-prerequisites) section and double-check that all prerequisites are met.</span></span> <span data-ttu-id="1f600-174">Si se cumplen todos los requisitos previos, reinicia el dispositivo y vuelve a comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="1f600-174">If all prerequisites are met, restart your device and check again.</span></span>

- <span data-ttu-id="1f600-175">P: ¿Cuándo se admite macOS 11 Big Sur?</span><span class="sxs-lookup"><span data-stu-id="1f600-175">Q: When will macOS 11 Big Sur be supported?</span></span>

    <span data-ttu-id="1f600-176">A: Estamos trabajando activamente en agregar compatibilidad con macOS 11.</span><span class="sxs-lookup"><span data-stu-id="1f600-176">A: We are actively working on adding support for macOS 11.</span></span> <span data-ttu-id="1f600-177">Publicaremos más información en la [página Novedades.](mac-whatsnew.md)</span><span class="sxs-lookup"><span data-stu-id="1f600-177">We will post more information to the [What's new](mac-whatsnew.md) page.</span></span>
