---
title: Habilitar el bloqueo a primera vista para detectar malware en segundos
description: Active la característica de bloqueo a primera vista para detectar y bloquear el malware en pocos segundos.
keywords: analizar, bloquear a primera vista, malware, primera vista, nube, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/17/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a6bcc023571e544819ae7f276e6c3af5c1fc1335
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007406"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="b946d-104">Activar el bloqueo a primera vista</span><span class="sxs-lookup"><span data-stu-id="b946d-104">Turn on block at first sight</span></span>

<span data-ttu-id="b946d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b946d-105">**Applies to:**</span></span>

- [<span data-ttu-id="b946d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b946d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b946d-107">En este artículo se describe una característica de antivirus o antimalware conocida como "bloqueo a primera vista" y se describe cómo habilitar el bloqueo a primera vista para la organización.</span><span class="sxs-lookup"><span data-stu-id="b946d-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="b946d-108">Este artículo está destinado a administradores empresariales y profesionales de TI que administran la configuración de seguridad para organizaciones.</span><span class="sxs-lookup"><span data-stu-id="b946d-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="b946d-109">Si no es un administrador empresarial o un profesional de TI, pero tiene preguntas sobre el bloqueo a primera vista, consulte la sección[¿No es un administrador empresarial o un profesional de TI?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="b946d-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see the [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro) section.</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="b946d-110">¿Qué es "bloqueo a primera vista"?</span><span class="sxs-lookup"><span data-stu-id="b946d-110">What is "block at first sight"?</span></span>

<span data-ttu-id="b946d-111">El bloqueo a primera vista es una característica de protección contra amenazas de protección de nueva generación que detecta nuevo malware y lo bloquea en pocos segundos.</span><span class="sxs-lookup"><span data-stu-id="b946d-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="b946d-112">El bloqueo a primera vista se habilita cuando se habilitan determinadas opciones de configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b946d-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="b946d-113">Entre estas opciones se incluyen:</span><span class="sxs-lookup"><span data-stu-id="b946d-113">These settings include:</span></span>

- <span data-ttu-id="b946d-114">Protección entregada en la nube;</span><span class="sxs-lookup"><span data-stu-id="b946d-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="b946d-115">Un tiempo de espera de envío de ejemplo especificado (como 50 segundos); y</span><span class="sxs-lookup"><span data-stu-id="b946d-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="b946d-116">Un nivel de bloqueo de archivos alto.</span><span class="sxs-lookup"><span data-stu-id="b946d-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="b946d-117">En la mayoría de las organizaciones empresariales, la configuración necesaria para habilitar el bloqueo a primera vista se configura con las implementaciones de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b946d-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="b946d-118">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="b946d-118">How it works</span></span>

<span data-ttu-id="b946d-119">Cuando Antivirus de Microsoft Defender encuentra un archivo sospechoso pero no detectado, consulta nuestro back-end de protección de la nube.</span><span class="sxs-lookup"><span data-stu-id="b946d-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="b946d-120">El back-end de la nube aplica heurística, aprendizaje automático y análisis automatizado del archivo para determinar si los archivos son malintencionados o no son una amenaza.</span><span class="sxs-lookup"><span data-stu-id="b946d-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="b946d-121">Antivirus de Microsoft Defender usa varias tecnologías de detección y prevención para ofrecer una protección inteligente, en tiempo real y precisa.</span><span class="sxs-lookup"><span data-stu-id="b946d-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Lista de motores AV de Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="b946d-123">Para más información, consulte este blog: [Conozca las tecnologías avanzadas en el núcleo de la protección de última generación de Microsoft Defender para punto de conexión](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="b946d-123">To learn more, see [(Blog) Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="b946d-124">Algunas cosas que debe saber sobre el bloqueo a primera vista</span><span class="sxs-lookup"><span data-stu-id="b946d-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="b946d-125">En Windows 10, versión 1803 y versiones posteriores, el bloqueo a primera vista puede bloquear los archivos ejecutables no portátiles (como JS, VBS o macros) y los archivos ejecutables.</span><span class="sxs-lookup"><span data-stu-id="b946d-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="b946d-126">Bloqueo a primera vista usa solo el back-end de protección en la nube para archivos ejecutables y archivos ejecutables no portátiles que se descargan de Internet o que se originan desde la zona de Internet.</span><span class="sxs-lookup"><span data-stu-id="b946d-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="b946d-127">Se comprueba un valor de hash del archivo .exe a través del back-end de la nube, para determinar si se trata de un archivo no detectado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b946d-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="b946d-128">Si el back-end de la nube no consigue determinar, Antivirus de Microsoft Defender bloquea el archivo y carga una copia en la nube.</span><span class="sxs-lookup"><span data-stu-id="b946d-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="b946d-129">La nube realiza más análisis para alcanzar una determinación antes de permitir que el archivo se ejecute o bloquearlo en todos las futuras apariciones, en función de si determina que el archivo es malintencionado o no es una amenaza.</span><span class="sxs-lookup"><span data-stu-id="b946d-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="b946d-130">En muchos casos, este proceso puede reducir el tiempo de respuesta para el nuevo malware de horas a segundos.</span><span class="sxs-lookup"><span data-stu-id="b946d-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="b946d-131">Puede [especificar durante cuánto tiempo debe impedirse la ejecución del archivo](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) mientras el servicio de protección basado en la nube analiza el archivo.</span><span class="sxs-lookup"><span data-stu-id="b946d-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="b946d-132">Además, puede [personalizar el mensaje que aparece en los escritorios de los usuarios ](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md)cuando se bloquea un archivo.</span><span class="sxs-lookup"><span data-stu-id="b946d-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="b946d-133">Puede cambiar el nombre de la empresa, la información de contacto y la dirección URL de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b946d-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="b946d-134">Activar el bloqueo a primera vista con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b946d-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="b946d-135">Microsoft Intune ahora forma parte de Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="b946d-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="b946d-136">En el Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), vaya a **Dispositivos** > **Perfiles de configuración**.</span><span class="sxs-lookup"><span data-stu-id="b946d-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="b946d-137">Seleccione o cree un perfil con el tipo de perfil **Restricciones de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b946d-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="b946d-138">En las **Opciones de configuración** del perfil Restricciones de dispositivo, establezca o confirme las opciones siguientes en **Antivirus de Microsoft Defender**:</span><span class="sxs-lookup"><span data-stu-id="b946d-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="b946d-139">**Protección proporcionada por la nube**: Habilitar</span><span class="sxs-lookup"><span data-stu-id="b946d-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="b946d-140">**Nivel de bloqueo de archivos**: Alto</span><span class="sxs-lookup"><span data-stu-id="b946d-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="b946d-141">**Extensión de tiempo para el análisis de archivos de la nube**: 50</span><span class="sxs-lookup"><span data-stu-id="b946d-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="b946d-142">**Avisar a los usuarios antes del envío de muestras**: Enviar todos los datos sin avisar</span><span class="sxs-lookup"><span data-stu-id="b946d-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   :::image type="content" source="../../media/intune-block-at-first-sight.png" alt-text="Bloque de configuración de Intune a primera vista":::

4. <span data-ttu-id="b946d-144">Guarde la configuración.</span><span class="sxs-lookup"><span data-stu-id="b946d-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="b946d-145">Si establece el nivel de bloqueo de archivos en **Alto**, se aplica un nivel de detección muy riguroso.</span><span class="sxs-lookup"><span data-stu-id="b946d-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="b946d-146">En el caso poco probable de que el bloqueo de archivos cause una detección de falso positivo de archivos legítimos, el equipo de operaciones de seguridad puede [restaurar los archivos en cuarentena](./restore-quarantined-files-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="b946d-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="b946d-147">Para obtener más información sobre cómo configurar las restricciones de dispositivos de Antivirus de Microsoft Defender en Intune, consulte[ Configurar las opciones de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="b946d-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="b946d-148">Para obtener una lista de las restricciones de los dispositivos de Antivirus de Microsoft Defender en Intune, consulte [Configuración de restricción de dispositivos para Windows 10 (y posteriores) en Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="b946d-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="b946d-149">Activar el bloqueo a primera vista con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b946d-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="b946d-150">Si está buscando Microsoft Endpoint Configuration Manager, ahora forma parte de Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="b946d-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="b946d-151">En Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), vaya a **Seguridad de punto de conexión** > **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="b946d-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="b946d-152">Seleccione una directiva existente o cree una directiva con el tipo de perfil **Antivirus de Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="b946d-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="b946d-153">Establezca o confirme las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="b946d-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="b946d-154">**Activar la protección proporcionada en la nube**: Sí</span><span class="sxs-lookup"><span data-stu-id="b946d-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="b946d-155">**Nivel de protección proporcionada en la nube**: Alto</span><span class="sxs-lookup"><span data-stu-id="b946d-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="b946d-156">**Tiempo de espera extendido de la nube de Defender**: 50</span><span class="sxs-lookup"><span data-stu-id="b946d-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Configuración de bloqueo a primera vista en Endpoint Manager":::

4. <span data-ttu-id="b946d-158">Aplique el perfil del Antivirus de Microsoft Defender a un grupo, como **Todos los usuarios**, **Todos los dispositivos** o **Todos los usuarios y dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b946d-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="b946d-159">Activar el bloqueo a primera vista con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b946d-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="b946d-160">Se recomienda usar Intune o Microsoft Endpoint Manager para activar el bloqueo a primera vista.</span><span class="sxs-lookup"><span data-stu-id="b946d-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="b946d-161">En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón secundario en el objeto de directiva de grupo que quiera configurar y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b946d-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="b946d-162">Con el **Editor de administración de directivas de grupo** vaya a **Configuración del equipo** > **Plantillas administrativas** > **Componentes de Windows** > **Antivirus de Microsoft Defender** > **MAPAS**.</span><span class="sxs-lookup"><span data-stu-id="b946d-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="b946d-163">En la sección MAPAS, haga doble clic en **Configurar la característica "Bloquear a primera vista"**, establezca esta opción en **Habilitado** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b946d-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b946d-164">Establecerla en **Preguntar siempre (0)** reducirá el estado de protección del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b946d-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="b946d-165">Establecerla en **No enviar nunca (2)** significa que el bloqueo a primera vista no funcionará.</span><span class="sxs-lookup"><span data-stu-id="b946d-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="b946d-166">En la sección MAPAS, haga doble clic en **Enviar archivos de muestra cuando sea necesario realizar análisis adicionales** y establézcalo en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="b946d-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="b946d-167">En **Enviar archivos de muestra cuando sea necesario realizar análisis adicionales**, seleccione **Enviar todas las muestras** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b946d-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="b946d-168">Vuelva a implementar el objeto de directiva de grupo en la red como lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="b946d-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="b946d-169">Confirmar que el bloqueo a primera vista está habilitado en dispositivos de clientes individuales</span><span class="sxs-lookup"><span data-stu-id="b946d-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="b946d-170">Puede confirmar que el bloqueo a primera vista está habilitado en dispositivos cliente individuales con la aplicación de Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="b946d-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="b946d-171">El bloqueo a primera vista se habilita automáticamente siempre y cuando las opciones **Protección basada en la nube** y **Envío de muestras automático** estén activadas.</span><span class="sxs-lookup"><span data-stu-id="b946d-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="b946d-172">Abra la aplicación Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="b946d-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="b946d-173">Seleccione **Protección antivirus y contra amenazas** y, luego, en **Configuración de antivirus y protección contra amenazas**, seleccione **Administrar la configuración**.</span><span class="sxs-lookup"><span data-stu-id="b946d-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Captura de pantalla de la etiqueta de configuración de Protección antivirus y contra amenazas en la aplicación Seguridad de Windows":::

3. <span data-ttu-id="b946d-175">Confirme que las opciones **Protección basada en la nube** y **Envío de muestras automático** estén activadas.</span><span class="sxs-lookup"><span data-stu-id="b946d-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="b946d-176">Si la configuración de requisitos previos se configura e implementa mediante la directiva de grupo, la configuración que se describe en esta sección aparecerá atenuada y su uso no estará disponible en los puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="b946d-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="b946d-177">Los cambios realizados a través de un objeto de directiva de grupo deben implementarse en primer lugar en los extremos individuales antes de que se actualice la configuración en la configuración de Windows.</span><span class="sxs-lookup"><span data-stu-id="b946d-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="b946d-178">Validar que esté funcionando el bloqueo a primera vista</span><span class="sxs-lookup"><span data-stu-id="b946d-178">Validate block at first sight is working</span></span>

<span data-ttu-id="b946d-179">Para validar que la característica funciona, descargue el archivo de ejemplo [Bloquear a primera vista](https://demo.wd.microsoft.com/Page/BAFS).</span><span class="sxs-lookup"><span data-stu-id="b946d-179">To validate that the feature is working, download the [Block at first sight sample file](https://demo.wd.microsoft.com/Page/BAFS).</span></span> <span data-ttu-id="b946d-180">Para descargar el archivo, necesitará una cuenta en Azure AD que tenga asignado el rol Administrador de seguridad o Administrador global.</span><span class="sxs-lookup"><span data-stu-id="b946d-180">To download the file, you will need an account in Azure AD that has either the Security Administrator or Global Administrator role assigned.</span></span>

<span data-ttu-id="b946d-181">Para validar que la protección habilitada para la nube funciona, siga las instrucciones de [Validar las conexiones entre la red y la nube](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span><span class="sxs-lookup"><span data-stu-id="b946d-181">To validate that cloud-enabled protection is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span> 

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="b946d-182">Desactivar el bloqueo a primera vista</span><span class="sxs-lookup"><span data-stu-id="b946d-182">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="b946d-183">Al desactivar el bloqueo a primera vista disminuirá el estado de protección de los dispositivos y de la red.</span><span class="sxs-lookup"><span data-stu-id="b946d-183">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="b946d-184">Puede optar por deshabilitar el bloqueo a primera vista si quiere conservar la configuración de requisitos previos sin usar la protección del bloqueo a primera vista.</span><span class="sxs-lookup"><span data-stu-id="b946d-184">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="b946d-185">Puede desactivar temporalmente el bloqueo a primera vista para ver cómo afecta esta característica a su red.</span><span class="sxs-lookup"><span data-stu-id="b946d-185">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="b946d-186">Sin embargo, no se recomienda deshabilitar la protección de bloqueo a primera vista de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="b946d-186">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="b946d-187">Desactivar el bloqueo a primera vista con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b946d-187">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="b946d-188">Vaya al Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="b946d-188">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="b946d-189">Vaya a **Seguridad de punto de conexión** > **Antivirus** y, después, seleccione la directiva de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b946d-189">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="b946d-190">En **Administrar**, elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b946d-190">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="b946d-191">Junto a **Opciones de configuración**, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b946d-191">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="b946d-192">Cambie una o varias de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b946d-192">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="b946d-193">Establezca **Activar la protección proporcionada en la nube** en **No** o **Sin configurar**.</span><span class="sxs-lookup"><span data-stu-id="b946d-193">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="b946d-194">Establezca **Nivel de protección proporcionada en la nube** en **Sin configurar**.</span><span class="sxs-lookup"><span data-stu-id="b946d-194">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="b946d-195">Desactive la casilla de **Tiempo de espera extendido en segundos en la nube de Defender**.</span><span class="sxs-lookup"><span data-stu-id="b946d-195">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="b946d-196">Revise y guarde la configuración.</span><span class="sxs-lookup"><span data-stu-id="b946d-196">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="b946d-197">Desactivar el bloqueo a primera vista con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b946d-197">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="b946d-198">En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón secundario en el objeto de directiva de grupo que quiera configurar y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b946d-198">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="b946d-199">Con el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="b946d-199">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="b946d-200">Expanda el árbol en **Componentes de Windows** > **Antivirus de Windows Defender** > **MAPAS**.</span><span class="sxs-lookup"><span data-stu-id="b946d-200">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="b946d-201">Haz doble clic en **Configurar la característica 'Bloqueo a primera vista'** y establezca la opción en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b946d-201">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b946d-202">Si deshabilita el bloqueo a primera vista, no se deshabilitarán ni modificarán las directivas de grupo de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="b946d-202">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="b946d-203">¿No es un administrador empresarial o un profesional de TI?</span><span class="sxs-lookup"><span data-stu-id="b946d-203">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="b946d-204">Si no es un administrador empresarial o un profesional de TI, pero tiene preguntas sobre el bloqueo a primera vista, esta sección es para usted.</span><span class="sxs-lookup"><span data-stu-id="b946d-204">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="b946d-205">El bloqueo a primera vista es una característica de protección contra amenazas que detecta y bloquea malware en pocos segundos.</span><span class="sxs-lookup"><span data-stu-id="b946d-205">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="b946d-206">Aunque no existe una configuración específica denominada "Bloqueo a primera vista", la característica se habilita cuando se configuran opciones específicas en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b946d-206">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="b946d-207">Cómo administrar el bloqueo a primera vista para activarlo o desactivarlo en su propio dispositivo</span><span class="sxs-lookup"><span data-stu-id="b946d-207">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="b946d-208">Si tiene un dispositivo personal que no está administrado por una organización, puede que se pregunte cómo activar o desactivar el bloqueo a primera vista.</span><span class="sxs-lookup"><span data-stu-id="b946d-208">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="b946d-209">Puede usar la aplicación de Seguridad de Windows para administrar el bloqueo a primera vista.</span><span class="sxs-lookup"><span data-stu-id="b946d-209">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="b946d-210">En el equipo con Windows 10, abra la aplicación de Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="b946d-210">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="b946d-211">Seleccione **Protección antivirus y contra amenazas**.</span><span class="sxs-lookup"><span data-stu-id="b946d-211">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="b946d-212">En **Configuración de antivirus y protección contra amenazas**, seleccione **Administrar la configuración**.</span><span class="sxs-lookup"><span data-stu-id="b946d-212">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="b946d-213">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b946d-213">Take one of the following steps:</span></span>

   - <span data-ttu-id="b946d-214">Para habilitar el bloqueo a primera vista, asegúrese de que **Protección proporcionada en la nube** y **Envío de muestras automático** están activados.</span><span class="sxs-lookup"><span data-stu-id="b946d-214">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="b946d-215">Para deshabilitar el bloqueo a primera vista, desactive la **Protección proporcionada en la nube** o **Envío de muestras automático**.</span><span class="sxs-lookup"><span data-stu-id="b946d-215">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="b946d-216">Desactivar el bloque a primera vista disminuye el nivel de protección del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b946d-216">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="b946d-217">No se recomienda deshabilitar permanentemente el bloqueo a primera vista.</span><span class="sxs-lookup"><span data-stu-id="b946d-217">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="b946d-218">Vea también</span><span class="sxs-lookup"><span data-stu-id="b946d-218">See also</span></span>

- [<span data-ttu-id="b946d-219">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="b946d-219">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="b946d-220">Habilitar la protección proporcionada en la nube</span><span class="sxs-lookup"><span data-stu-id="b946d-220">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b946d-221">Manténgase protegido con Seguridad de Windows</span><span class="sxs-lookup"><span data-stu-id="b946d-221">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
