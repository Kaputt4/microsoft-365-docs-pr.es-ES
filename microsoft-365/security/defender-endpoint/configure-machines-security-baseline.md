---
title: Aumentar el cumplimiento de la línea base de seguridad de ATP de Microsoft Defender
description: La línea base de seguridad de ATP de Microsoft Defender establece los controles de seguridad de ATP de Microsoft Defender para proporcionar una protección óptima.
keywords: Administración de Intune, MDATP, WDATP, Microsoft Defender, ASR de protección contra amenazas avanzada, línea base de seguridad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 74073441ad7be89e0af278ff1e371133251b5ea7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163404"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="a11bf-104">Aumentar el cumplimiento de la línea base de seguridad de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="a11bf-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a11bf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a11bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="a11bf-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a11bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a11bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a11bf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a11bf-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a11bf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a11bf-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a11bf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="a11bf-110">Las líneas base de seguridad garantizan que las características de seguridad estén configuradas de acuerdo con las instrucciones de expertos en seguridad y administradores expertos del sistema Windows.</span><span class="sxs-lookup"><span data-stu-id="a11bf-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="a11bf-111">Cuando se implementa, la línea base de seguridad de Defender para endpoint establece los controles de seguridad de Defender for Endpoint para proporcionar una protección óptima.</span><span class="sxs-lookup"><span data-stu-id="a11bf-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="a11bf-112">Para comprender las líneas base de seguridad y cómo se asignan en Intune mediante perfiles de configuración, [lea estas preguntas más frecuentes](https://docs.microsoft.com/intune/security-baselines#q--a).</span><span class="sxs-lookup"><span data-stu-id="a11bf-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](https://docs.microsoft.com/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="a11bf-113">Antes de implementar y realizar un seguimiento del cumplimiento de las líneas base de seguridad:</span><span class="sxs-lookup"><span data-stu-id="a11bf-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="a11bf-114">Inscribir los dispositivos en la administración de Intune</span><span class="sxs-lookup"><span data-stu-id="a11bf-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="a11bf-115">Asegúrese de que tiene los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="a11bf-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines"></a><span data-ttu-id="a11bf-116">Comparar la ATP de Microsoft Defender y las líneas base de seguridad de Windows Intune</span><span class="sxs-lookup"><span data-stu-id="a11bf-116">Compare the Microsoft Defender ATP and the Windows Intune security baselines</span></span>
<span data-ttu-id="a11bf-117">La línea base de seguridad de Windows Intune proporciona un conjunto completo de opciones recomendadas necesarias para configurar de forma segura los dispositivos que ejecutan Windows, incluida la configuración del explorador, la configuración de PowerShell, así como la configuración de algunas características de seguridad como Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a11bf-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="a11bf-118">En cambio, la línea base de Defender para punto de conexión proporciona opciones que optimizan todos los controles de seguridad de la pila defender para puntos de conexión, incluida la configuración para la detección y respuesta de puntos de conexión (EDR), así como la configuración que también se encuentra en la línea base de seguridad de Windows Intune.</span><span class="sxs-lookup"><span data-stu-id="a11bf-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="a11bf-119">Para obtener más información acerca de cada línea base, vea:</span><span class="sxs-lookup"><span data-stu-id="a11bf-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="a11bf-120">Configuración de línea base de seguridad de Windows para Intune</span><span class="sxs-lookup"><span data-stu-id="a11bf-120">Windows security baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-windows)
- [<span data-ttu-id="a11bf-121">Configuración de línea base de ATP de Microsoft Defender para Intune</span><span class="sxs-lookup"><span data-stu-id="a11bf-121">Microsoft Defender ATP baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="a11bf-122">Lo ideal es que los dispositivos incorporados a Defender for Endpoint se implementen en ambas líneas base: la línea base de seguridad de Windows Intune para proteger inicialmente Windows y, a continuación, la línea base de seguridad de Defender para endpoints en capas superiores para configurar de forma óptima los controles de seguridad de Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="a11bf-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="a11bf-123">Para beneficiarse de los últimos datos sobre riesgos y amenazas y para minimizar los conflictos a medida que evolucionan las líneas base, aplique siempre las versiones más recientes de las líneas base en todos los productos tan pronto como se liberan.</span><span class="sxs-lookup"><span data-stu-id="a11bf-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="a11bf-124">La línea base de seguridad de Defender for Endpoint se ha optimizado para dispositivos físicos y actualmente no se recomienda su uso en máquinas virtuales (VM) o puntos de conexión VDI.</span><span class="sxs-lookup"><span data-stu-id="a11bf-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="a11bf-125">Ciertas opciones de configuración de línea base pueden afectar a sesiones interactivas remotas en entornos virtualizados.</span><span class="sxs-lookup"><span data-stu-id="a11bf-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="a11bf-126">Supervisar el cumplimiento de la línea base de seguridad de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a11bf-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="a11bf-127">La tarjeta De [](configure-machines.md) línea **base** de seguridad en la administración de configuración de dispositivos proporciona una introducción al cumplimiento en todos los dispositivos Windows 10 a los que se ha asignado la línea base de seguridad defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="a11bf-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="a11bf-128">![Tarjeta de línea base de seguridad](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="a11bf-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="a11bf-129">*Tarjeta que muestra el cumplimiento de la línea base de seguridad de Defender for Endpoint*</span><span class="sxs-lookup"><span data-stu-id="a11bf-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="a11bf-130">Cada dispositivo tiene uno de los siguientes tipos de estado:</span><span class="sxs-lookup"><span data-stu-id="a11bf-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="a11bf-131">**Coincide con la línea** base: la configuración del dispositivo coincide con todas las opciones de la línea base</span><span class="sxs-lookup"><span data-stu-id="a11bf-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="a11bf-132">**No coincide con la línea base:** al menos una configuración del dispositivo no coincide con la línea base</span><span class="sxs-lookup"><span data-stu-id="a11bf-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="a11bf-133">**Mal configurado:** al menos una configuración de línea base no está configurada correctamente en el dispositivo y está en un estado de conflicto, error o pendiente</span><span class="sxs-lookup"><span data-stu-id="a11bf-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="a11bf-134">**No aplicable:** al menos una configuración de línea base no es aplicable en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="a11bf-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="a11bf-135">Para revisar dispositivos específicos, seleccione **Configurar la línea base de seguridad** en la tarjeta.</span><span class="sxs-lookup"><span data-stu-id="a11bf-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="a11bf-136">Esto te lleva a la administración de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="a11bf-136">This takes you to Intune device management.</span></span> <span data-ttu-id="a11bf-137">Desde allí, selecciona **Estado del dispositivo** para los nombres y estados de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a11bf-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="a11bf-138">Es posible que experimente discrepancias en los datos agregados que se muestran en la página de administración de configuración del dispositivo y en los que se muestran en pantallas de información general en Intune.</span><span class="sxs-lookup"><span data-stu-id="a11bf-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="a11bf-139">Revisar y asignar la línea base de seguridad de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="a11bf-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="a11bf-140">La administración de configuración de dispositivos supervisa el cumplimiento previsto solo de dispositivos Windows 10 a los que se asignó específicamente la línea base de seguridad de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="a11bf-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="a11bf-141">Puedes revisar cómodamente la línea base y asignarla a dispositivos en la administración de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="a11bf-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="a11bf-142">Selecciona **Configurar la línea base de** seguridad en la tarjeta de **línea** base de seguridad para ir a Administración de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="a11bf-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="a11bf-143">Se muestra una descripción general similar del cumplimiento de la línea base.</span><span class="sxs-lookup"><span data-stu-id="a11bf-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="a11bf-144">Como alternativa, puede navegar a la línea base de seguridad defender para puntos de conexión en Microsoft Azure Portal desde Todos los servicios > Intune > Seguridad del dispositivo > Líneas base de seguridad > línea base de ATP de **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="a11bf-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="a11bf-145">Crear un perfil nuevo.</span><span class="sxs-lookup"><span data-stu-id="a11bf-145">Create a new profile.</span></span>

   <span data-ttu-id="a11bf-146">![Introducción a la línea base de seguridad de Microsoft Defender para endpoints en Intune](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="a11bf-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="a11bf-147">*Introducción a la línea base de seguridad de Microsoft Defender para endpoints en Intune*</span><span class="sxs-lookup"><span data-stu-id="a11bf-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="a11bf-148">Durante la creación de perfiles, puede revisar y ajustar la configuración específica de la línea base.</span><span class="sxs-lookup"><span data-stu-id="a11bf-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="a11bf-149">![Opciones de línea base de seguridad durante la creación de perfiles en Intune](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="a11bf-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="a11bf-150">*Opciones de línea base de seguridad durante la creación de perfiles en Intune*</span><span class="sxs-lookup"><span data-stu-id="a11bf-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="a11bf-151">Asigna el perfil al grupo de dispositivos adecuado.</span><span class="sxs-lookup"><span data-stu-id="a11bf-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="a11bf-152">![Perfiles de línea base de seguridad en Intune](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="a11bf-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="a11bf-153">*Asignar el perfil de línea base de seguridad en Intune*</span><span class="sxs-lookup"><span data-stu-id="a11bf-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="a11bf-154">Crea el perfil para guardarlo e implementarlo en el grupo de dispositivos asignado.</span><span class="sxs-lookup"><span data-stu-id="a11bf-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="a11bf-155">![Asignar la línea base de seguridad en Intune](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="a11bf-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="a11bf-156">*Creación del perfil de línea base de seguridad en Intune*</span><span class="sxs-lookup"><span data-stu-id="a11bf-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="a11bf-157">Las líneas base de seguridad en Intune proporcionan una forma cómoda de proteger y proteger exhaustivamente los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a11bf-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="a11bf-158">[Obtenga más información sobre las líneas base de seguridad en Intune](https://docs.microsoft.com/intune/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="a11bf-158">[Learn more about security baselines on Intune](https://docs.microsoft.com/intune/security-baselines).</span></span>

><span data-ttu-id="a11bf-159">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="a11bf-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a11bf-160">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a11bf-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="a11bf-161">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a11bf-161">Related topics</span></span>
- [<span data-ttu-id="a11bf-162">Asegúrese de que los dispositivos estén configurados correctamente</span><span class="sxs-lookup"><span data-stu-id="a11bf-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="a11bf-163">Obtener dispositivos incorporados a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="a11bf-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="a11bf-164">Optimizar la implementación y detecciones de reglas ASR</span><span class="sxs-lookup"><span data-stu-id="a11bf-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
