---
title: Habilitar bloque a primera vista para detectar malware en segundos
description: Activa la característica de bloqueo a primera vista para detectar y bloquear malware en cuestión de segundos.
keywords: scan, BAFS, malware, first seen, first sight, cloud, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 1baa770da677ec755bd56db9b92c071680efae7b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765760"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="a7f63-104">Activar el bloque a primera vista</span><span class="sxs-lookup"><span data-stu-id="a7f63-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a7f63-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a7f63-105">**Applies to:**</span></span>

- [<span data-ttu-id="a7f63-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a7f63-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a7f63-107">Bloquear a primera vista proporciona una forma de detectar y bloquear nuevo malware en segundos.</span><span class="sxs-lookup"><span data-stu-id="a7f63-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="a7f63-108">Esta protección está habilitada de forma predeterminada cuando se habilitan determinadas opciones de configuración de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="a7f63-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="a7f63-109">Estas opciones incluyen protección entregada en la nube, un tiempo de espera de envío de ejemplo especificado (como 50 segundos) y un nivel de bloqueo de archivos alto.</span><span class="sxs-lookup"><span data-stu-id="a7f63-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="a7f63-110">En la mayoría de las organizaciones empresariales, esta configuración está habilitada de forma predeterminada con las implementaciones de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a7f63-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="a7f63-111">Puede especificar [cuánto tiempo se](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) debe impedir que un archivo se ejecute mientras el servicio de protección basado en la nube analiza el archivo.</span><span class="sxs-lookup"><span data-stu-id="a7f63-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="a7f63-112">Además, puede personalizar [el mensaje que se muestra en los escritorios de los](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) usuarios cuando se bloquea un archivo.</span><span class="sxs-lookup"><span data-stu-id="a7f63-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="a7f63-113">Puede cambiar el nombre de la empresa, la información de contacto y la dirección URL del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7f63-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="a7f63-114">Visite el sitio web de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las características funcionan y ver cómo funcionan.</span><span class="sxs-lookup"><span data-stu-id="a7f63-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="a7f63-115">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="a7f63-115">How it works</span></span>

<span data-ttu-id="a7f63-116">Cuando Antivirus de Microsoft Defender encuentra un archivo sospechoso pero no detectado, consulta nuestro back-end de protección en la nube.</span><span class="sxs-lookup"><span data-stu-id="a7f63-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="a7f63-117">El back-end en la nube aplica heurística, aprendizaje automático y análisis automatizado del archivo para determinar si los archivos son malintencionados o no son una amenaza.</span><span class="sxs-lookup"><span data-stu-id="a7f63-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="a7f63-118">Microsoft Defender Antivirus usa varias tecnologías de detección y prevención para ofrecer una protección precisa, inteligente y en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="a7f63-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="a7f63-119">Para obtener más información, vea este blog: Conozca las tecnologías avanzadas en el núcleo de Microsoft Defender para la [protección de última generación de Endpoint](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="a7f63-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="a7f63-120">![Lista de motores antivirus de Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="a7f63-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="a7f63-121">En Windows 10, versión 1803 o posterior, bloquear a primera vista puede bloquear archivos ejecutables no portátiles (como JS, VBS o macros), así como archivos ejecutables.</span><span class="sxs-lookup"><span data-stu-id="a7f63-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="a7f63-122">Bloquear a primera vista solo usa el back-end de protección en la nube para archivos ejecutables y archivos ejecutables no portátiles que se descargan de Internet o que se originan en la zona de Internet.</span><span class="sxs-lookup"><span data-stu-id="a7f63-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="a7f63-123">Un valor hash del archivo .exe se comprueba a través del back-end de la nube para determinar si el archivo es un archivo no detectado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a7f63-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="a7f63-124">Si el back-end de la nube no puede tomar una determinación, Antivirus de Microsoft Defender bloquea el archivo y carga una copia en la nube.</span><span class="sxs-lookup"><span data-stu-id="a7f63-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="a7f63-125">La nube realiza análisis adicionales para llegar a una determinación antes de que permita que el archivo se ejecute o lo bloquee en todos los futuros encuentros, en función de si determina que el archivo es malintencionado o seguro.</span><span class="sxs-lookup"><span data-stu-id="a7f63-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="a7f63-126">En muchos casos, este proceso puede reducir el tiempo de respuesta del nuevo malware de horas a segundos.</span><span class="sxs-lookup"><span data-stu-id="a7f63-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="a7f63-127">Activar el bloque a primera vista con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a7f63-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="a7f63-128">Microsoft Intune ahora forma parte de Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="a7f63-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="a7f63-129">En el Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), vaya a **Perfiles de** configuración de  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="a7f63-130">Seleccione o cree un perfil con el **tipo de perfil Restricciones de** dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a7f63-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="a7f63-131">En configuración **para** el perfil restricciones de dispositivos, establezca o confirme la siguiente configuración en **Antivirus de Microsoft Defender**:</span><span class="sxs-lookup"><span data-stu-id="a7f63-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="a7f63-132">**Protección entregada en la nube:** habilitada</span><span class="sxs-lookup"><span data-stu-id="a7f63-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="a7f63-133">**Nivel de bloqueo de archivos:** alto</span><span class="sxs-lookup"><span data-stu-id="a7f63-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="a7f63-134">**Extensión de tiempo para el examen de archivos por la nube:** 50</span><span class="sxs-lookup"><span data-stu-id="a7f63-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="a7f63-135">**Preguntar a los usuarios antes del envío de** ejemplo: enviar todos los datos sin preguntar</span><span class="sxs-lookup"><span data-stu-id="a7f63-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Configuración de Intune](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="a7f63-137">Guarda la configuración.</span><span class="sxs-lookup"><span data-stu-id="a7f63-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="a7f63-138">Al establecer el nivel de bloqueo de archivos en **High** se aplica un nivel de detección fuerte.</span><span class="sxs-lookup"><span data-stu-id="a7f63-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="a7f63-139">En el improbable caso de que el bloqueo de archivos cause una detección de falsos positivos de archivos legítimos, puede [restaurar archivos en cuarentena.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a7f63-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="a7f63-140">Para obtener más información acerca de cómo configurar las restricciones de dispositivos antivirus de Microsoft Defender en Intune, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="a7f63-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="a7f63-141">Para obtener una lista de las restricciones de dispositivos antivirus de Microsoft Defender en Intune, consulta Restricción de dispositivos [para Windows 10 (y](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)versiones más recientes) en Intune .</span><span class="sxs-lookup"><span data-stu-id="a7f63-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="a7f63-142">Activar el bloque a primera vista con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="a7f63-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="a7f63-143">Si está buscando Microsoft Endpoint Configuration Manager, ahora forma parte de Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="a7f63-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="a7f63-144">En Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), vaya a Endpoint **security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="a7f63-145">Seleccione una directiva existente o cree una nueva con el tipo de perfil antivirus de **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="a7f63-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="a7f63-146">Establezca o confirme las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="a7f63-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="a7f63-147">**Activar la protección entregada en la nube:** Sí</span><span class="sxs-lookup"><span data-stu-id="a7f63-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="a7f63-148">**Nivel de protección entregado en la nube:** alto</span><span class="sxs-lookup"><span data-stu-id="a7f63-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="a7f63-149">**Tiempo de espera extendido de la nube de Defender en segundos:** 50</span><span class="sxs-lookup"><span data-stu-id="a7f63-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Bloquear la configuración a primera vista en Endpoint Manager":::

4. <span data-ttu-id="a7f63-151">Aplica el perfil antivirus de Microsoft Defender a un grupo, como Todos los **usuarios,** Todos los dispositivos **o** **Todos los usuarios y dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="a7f63-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="a7f63-152">Activar el bloque a primera vista con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="a7f63-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="a7f63-153">Se recomienda usar Intune o Microsoft Endpoint Manager para activar el bloque a primera vista.</span><span class="sxs-lookup"><span data-stu-id="a7f63-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="a7f63-154">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="a7f63-155">Con el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo Plantillas   >  **administrativas** Componentes  >  **de Windows**  >  **Microsoft Defender Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="a7f63-156">En la sección MAPAS, haga doble clic en Configurar la característica **"Bloquear** a primera vista" y estadúrela en **Habilitado** y, a continuación, **seleccione Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a7f63-157">Si se **establece en Preguntar siempre (0),** se disminuirá el estado de protección del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a7f63-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="a7f63-158">Establecer en **Nunca enviar (2)** significa que el bloqueo a primera vista no funcionará.</span><span class="sxs-lookup"><span data-stu-id="a7f63-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="a7f63-159">En la sección MAPAS, haga doble clic en **Enviar** ejemplos de archivos cuando sea necesario realizar más análisis y establóquelo en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="a7f63-160">En **Enviar ejemplos de archivos cuando sea necesario** realizar un análisis adicional, seleccione Enviar todas **las** muestras y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="a7f63-161">Si ha cambiado alguna configuración, vuelva a implementar el objeto de directiva de grupo en toda la red para asegurarse de que se tratan todos los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="a7f63-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="a7f63-162">Confirmar que el bloque a primera vista está habilitado en clientes individuales</span><span class="sxs-lookup"><span data-stu-id="a7f63-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="a7f63-163">Puedes confirmar que el bloqueo a primera vista está habilitado en clientes individuales mediante la configuración de seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="a7f63-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="a7f63-164">El bloqueo a primera vista se  habilita automáticamente siempre que la protección entregada en la nube y el **envío** automático de muestra estén activados.</span><span class="sxs-lookup"><span data-stu-id="a7f63-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="a7f63-165">Abre la aplicación Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="a7f63-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="a7f63-166">Seleccione **Protección contra & virus** y, a continuación, en Configuración de protección contra & **virus,** seleccione **Administrar configuración**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Captura de pantalla de la etiqueta & de protección contra amenazas de virus en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="a7f63-168">Confirme que **la protección entregada en la nube** y el envío automático de **muestras** están activados.</span><span class="sxs-lookup"><span data-stu-id="a7f63-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="a7f63-169">Si la configuración de requisitos previos se configura e implementa mediante la directiva de grupo, la configuración descrita en esta sección será grised-out y no estará disponible para su uso en puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="a7f63-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="a7f63-170">Los cambios realizados a través de un objeto de directiva de grupo deben implementarse primero en puntos de conexión individuales antes de que la configuración se actualice en Configuración de Windows.</span><span class="sxs-lookup"><span data-stu-id="a7f63-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="a7f63-171">Validar bloque a primera vista funciona</span><span class="sxs-lookup"><span data-stu-id="a7f63-171">Validate block at first sight is working</span></span>

<span data-ttu-id="a7f63-172">Para validar que la característica funciona, siga las instrucciones de [Validar conexiones entre la red y la nube.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="a7f63-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="a7f63-173">Desactivar el bloque a primera vista</span><span class="sxs-lookup"><span data-stu-id="a7f63-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="a7f63-174">Desactivar el bloque a primera vista disminuirá el estado de protección de los dispositivos y la red.</span><span class="sxs-lookup"><span data-stu-id="a7f63-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="a7f63-175">Es posible que elija deshabilitar el bloqueo a primera vista si desea conservar la configuración de requisitos previos sin usar realmente la protección de bloqueo a primera vista.</span><span class="sxs-lookup"><span data-stu-id="a7f63-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="a7f63-176">Puedes desactivar temporalmente el bloqueo a primera vista si tienes problemas de latencia o quieres probar el impacto de la característica en la red.</span><span class="sxs-lookup"><span data-stu-id="a7f63-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="a7f63-177">Sin embargo, no recomendamos deshabilitar el bloqueo a primera vista de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="a7f63-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="a7f63-178">Desactivar el bloque a primera vista con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="a7f63-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="a7f63-179">Vaya al Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a7f63-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="a7f63-180">Vaya a **Endpoint security**  >  **Antivirus** y, a continuación, seleccione la directiva antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a7f63-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="a7f63-181">En **Administrar**, elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="a7f63-182">Junto a **Configuración,** elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="a7f63-183">Cambie una o varias de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7f63-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="a7f63-184">Establezca **Activar la protección entregada en la nube** en **No** o No **configurado**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="a7f63-185">Establezca **el nivel de protección entregado en la nube** en No **configurado.**</span><span class="sxs-lookup"><span data-stu-id="a7f63-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="a7f63-186">Desactive el **cuadro Tiempo de espera extendido de Defender Cloud en** segundos.</span><span class="sxs-lookup"><span data-stu-id="a7f63-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="a7f63-187">Revise y guarde la configuración.</span><span class="sxs-lookup"><span data-stu-id="a7f63-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="a7f63-188">Desactivar el bloque a primera vista con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="a7f63-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="a7f63-189">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="a7f63-190">Con el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="a7f63-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="a7f63-191">Expande el árbol a través **de componentes de Windows** Microsoft Defender  >  **Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="a7f63-192">Haga doble clic **en Configurar la característica "Bloquear a primera vista"** y establezca la opción en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="a7f63-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a7f63-193">Deshabilitar el bloque a primera vista no deshabilita ni modifica las directivas de grupo de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="a7f63-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7f63-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7f63-194">See also</span></span>

- [<span data-ttu-id="a7f63-195">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="a7f63-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="a7f63-196">Habilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="a7f63-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)