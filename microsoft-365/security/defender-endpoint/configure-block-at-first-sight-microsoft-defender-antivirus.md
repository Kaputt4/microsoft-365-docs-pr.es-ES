---
title: Habilitar bloque a primera vista para detectar malware en segundos
description: Activa la característica de bloqueo a primera vista para detectar y bloquear malware en cuestión de segundos.
keywords: scan, block at first sight, malware, first sight, cloud, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079208"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="e99f6-104">Activar el bloqueo a primera vista</span><span class="sxs-lookup"><span data-stu-id="e99f6-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e99f6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e99f6-105">**Applies to:**</span></span>

- [<span data-ttu-id="e99f6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e99f6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e99f6-107">En este artículo se describe una característica antivirus/antimalware conocida como "bloqueo a primera vista" y se describe cómo habilitar el bloqueo a primera vista para su organización.</span><span class="sxs-lookup"><span data-stu-id="e99f6-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="e99f6-108">Este artículo está dirigido a administradores empresariales y profesionales de TI que administran la configuración de seguridad de las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="e99f6-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="e99f6-109">Si no es un administrador enteprise o un profesional de TI, pero tiene preguntas sobre el bloqueo a primera vista, vea [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="e99f6-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="e99f6-110">¿Qué es "bloquear a primera vista"?</span><span class="sxs-lookup"><span data-stu-id="e99f6-110">What is "block at first sight"?</span></span>

<span data-ttu-id="e99f6-111">Bloquear a primera vista es una característica de protección contra amenazas de la protección de próxima generación que detecta malware nuevo y lo bloquea en segundos.</span><span class="sxs-lookup"><span data-stu-id="e99f6-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="e99f6-112">El bloqueo a primera vista está habilitado cuando se habilitan determinadas opciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e99f6-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="e99f6-113">Estas opciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="e99f6-113">These settings include:</span></span>

- <span data-ttu-id="e99f6-114">Protección entregada en la nube;</span><span class="sxs-lookup"><span data-stu-id="e99f6-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="e99f6-115">Un tiempo de espera de envío de ejemplo especificado (como 50 segundos); y</span><span class="sxs-lookup"><span data-stu-id="e99f6-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="e99f6-116">Un nivel de bloqueo de archivos de alto.</span><span class="sxs-lookup"><span data-stu-id="e99f6-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="e99f6-117">En la mayoría de las organizaciones empresariales, la configuración necesaria para habilitar el bloqueo a primera vista se configura con implementaciones de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e99f6-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="e99f6-118">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="e99f6-118">How it works</span></span>

<span data-ttu-id="e99f6-119">Cuando Antivirus de Microsoft Defender encuentra un archivo sospechoso pero no detectado, consulta nuestro back-end de protección en la nube.</span><span class="sxs-lookup"><span data-stu-id="e99f6-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="e99f6-120">El back-end en la nube aplica heurística, aprendizaje automático y análisis automatizado del archivo para determinar si los archivos son malintencionados o no son una amenaza.</span><span class="sxs-lookup"><span data-stu-id="e99f6-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="e99f6-121">Microsoft Defender Antivirus usa varias tecnologías de detección y prevención para ofrecer una protección precisa, inteligente y en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="e99f6-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Lista de motores antivirus de Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="e99f6-123">Para obtener más información, vea este blog: Conozca las tecnologías avanzadas en el núcleo de Microsoft Defender para la [protección de última generación de Endpoint](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="e99f6-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="e99f6-124">Algunas cosas que debe saber sobre el bloqueo a primera vista</span><span class="sxs-lookup"><span data-stu-id="e99f6-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="e99f6-125">En Windows 10, versión 1803 o posterior, bloquear a primera vista puede bloquear archivos ejecutables no portátiles (como JS, VBS o macros) y archivos ejecutables.</span><span class="sxs-lookup"><span data-stu-id="e99f6-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="e99f6-126">Bloquear a primera vista solo usa el back-end de protección en la nube para archivos ejecutables y archivos ejecutables no portátiles que se descargan de Internet o que se originan en la zona de Internet.</span><span class="sxs-lookup"><span data-stu-id="e99f6-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="e99f6-127">Un valor hash del archivo .exe se comprueba a través del back-end de la nube para determinar si el archivo es un archivo no detectado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e99f6-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="e99f6-128">Si el back-end de la nube no puede tomar una determinación, Antivirus de Microsoft Defender bloquea el archivo y carga una copia en la nube.</span><span class="sxs-lookup"><span data-stu-id="e99f6-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="e99f6-129">La nube realiza más análisis para llegar a una determinación antes de que permita que el archivo se ejecute o lo bloquee en todos los futuros encuentros, en función de si determina que el archivo es malintencionado o no una amenaza.</span><span class="sxs-lookup"><span data-stu-id="e99f6-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="e99f6-130">En muchos casos, este proceso puede reducir el tiempo de respuesta del nuevo malware de horas a segundos.</span><span class="sxs-lookup"><span data-stu-id="e99f6-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="e99f6-131">Puede especificar [cuánto tiempo se](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) debe impedir que un archivo se ejecute mientras el servicio de protección basado en la nube analiza el archivo.</span><span class="sxs-lookup"><span data-stu-id="e99f6-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="e99f6-132">Además, puede personalizar [el mensaje que se muestra en los escritorios de los](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) usuarios cuando se bloquea un archivo.</span><span class="sxs-lookup"><span data-stu-id="e99f6-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="e99f6-133">Puede cambiar el nombre de la empresa, la información de contacto y la dirección URL del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e99f6-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="e99f6-134">Activar el bloque a primera vista con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e99f6-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="e99f6-135">Microsoft Intune ahora forma parte de Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="e99f6-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="e99f6-136">En el Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), vaya a **Perfiles de** configuración de  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="e99f6-137">Seleccione o cree un perfil con el **tipo de perfil Restricciones de** dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e99f6-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="e99f6-138">En configuración **para** el perfil restricciones de dispositivos, establezca o confirme la siguiente configuración en **Antivirus de Microsoft Defender**:</span><span class="sxs-lookup"><span data-stu-id="e99f6-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="e99f6-139">**Protección entregada en la nube:** habilitada</span><span class="sxs-lookup"><span data-stu-id="e99f6-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="e99f6-140">**Nivel de bloqueo de archivos:** alto</span><span class="sxs-lookup"><span data-stu-id="e99f6-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="e99f6-141">**Extensión de tiempo para el examen de archivos por la nube:** 50</span><span class="sxs-lookup"><span data-stu-id="e99f6-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="e99f6-142">**Preguntar a los usuarios antes del envío de** ejemplo: enviar todos los datos sin preguntar</span><span class="sxs-lookup"><span data-stu-id="e99f6-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Configuración de Intune](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="e99f6-144">Guarda la configuración.</span><span class="sxs-lookup"><span data-stu-id="e99f6-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="e99f6-145">Al establecer el nivel de bloqueo de archivos en **High** se aplica un nivel de detección fuerte.</span><span class="sxs-lookup"><span data-stu-id="e99f6-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="e99f6-146">En el improbable caso de que el bloqueo de archivos cause una detección de falsos positivos de archivos legítimos, el equipo de operaciones de seguridad puede [restaurar archivos en cuarentena.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e99f6-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="e99f6-147">Para obtener más información acerca de cómo configurar las restricciones de dispositivos antivirus de Microsoft Defender en Intune, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="e99f6-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="e99f6-148">Para obtener una lista de las restricciones de dispositivos antivirus de Microsoft Defender en Intune, consulta Restricción de dispositivos [para Windows 10 (y](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)versiones más recientes) en Intune .</span><span class="sxs-lookup"><span data-stu-id="e99f6-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="e99f6-149">Activar el bloque a primera vista con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="e99f6-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="e99f6-150">Si está buscando Microsoft Endpoint Configuration Manager, ahora forma parte de Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="e99f6-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="e99f6-151">En Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), vaya a Endpoint **security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="e99f6-152">Seleccione una directiva existente o cree una nueva con el tipo de perfil antivirus de **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="e99f6-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="e99f6-153">Establezca o confirme las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="e99f6-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="e99f6-154">**Activar la protección entregada en la nube:** Sí</span><span class="sxs-lookup"><span data-stu-id="e99f6-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="e99f6-155">**Nivel de protección entregado en la nube:** alto</span><span class="sxs-lookup"><span data-stu-id="e99f6-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="e99f6-156">**Tiempo de espera extendido de la nube de Defender en segundos:** 50</span><span class="sxs-lookup"><span data-stu-id="e99f6-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Bloquear la configuración a primera vista en Endpoint Manager":::

4. <span data-ttu-id="e99f6-158">Aplica el perfil antivirus de Microsoft Defender a un grupo, como Todos los **usuarios,** Todos los dispositivos **o** **Todos los usuarios y dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="e99f6-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="e99f6-159">Activar el bloque a primera vista con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="e99f6-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="e99f6-160">Se recomienda usar Intune o Microsoft Endpoint Manager para activar el bloque a primera vista.</span><span class="sxs-lookup"><span data-stu-id="e99f6-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="e99f6-161">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="e99f6-162">Con el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo Plantillas   >  **administrativas** Componentes  >  **de Windows**  >  **Microsoft Defender Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="e99f6-163">En la sección MAPAS, haga doble clic en Configurar la característica **"Bloquear** a primera vista" y estadúrela en **Habilitado** y, a continuación, **seleccione Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e99f6-164">Si se **establece en Preguntar siempre (0),** se disminuirá el estado de protección del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e99f6-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="e99f6-165">Establecer en **Nunca enviar (2)** significa que el bloqueo a primera vista no funcionará.</span><span class="sxs-lookup"><span data-stu-id="e99f6-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="e99f6-166">En la sección MAPAS, haga doble clic en **Enviar** ejemplos de archivos cuando sea necesario realizar más análisis y establóquelo en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="e99f6-167">En **Enviar ejemplos de archivos cuando sea necesario** realizar un análisis adicional, seleccione Enviar todos los **ejemplos** y, a continuación, **seleccione Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="e99f6-168">Vuelva a implementar el objeto de directiva de grupo en toda la red como suele hacer.</span><span class="sxs-lookup"><span data-stu-id="e99f6-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="e99f6-169">Confirmar que el bloque a primera vista está habilitado en dispositivos cliente individuales</span><span class="sxs-lookup"><span data-stu-id="e99f6-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="e99f6-170">Puedes confirmar que el bloqueo a primera vista está habilitado en dispositivos cliente individuales mediante la aplicación Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="e99f6-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="e99f6-171">El bloqueo a primera vista se  habilita automáticamente siempre que la protección entregada en la nube y el **envío** automático de muestra estén activados.</span><span class="sxs-lookup"><span data-stu-id="e99f6-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="e99f6-172">Abre la aplicación Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="e99f6-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="e99f6-173">Seleccione **Protección contra & virus** y, a continuación, en Configuración de protección contra & **virus,** seleccione **Administrar configuración**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Captura de pantalla de la etiqueta & de protección contra amenazas de virus en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="e99f6-175">Confirme que **la protección entregada en la nube** y el envío automático de **muestras** están activados.</span><span class="sxs-lookup"><span data-stu-id="e99f6-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="e99f6-176">Si la configuración de requisitos previos se configura e implementa mediante la directiva de grupo, la configuración descrita en esta sección será grised-out y no estará disponible para su uso en puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="e99f6-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="e99f6-177">Los cambios realizados a través de un objeto de directiva de grupo deben implementarse primero en puntos de conexión individuales antes de que la configuración se actualice en Configuración de Windows.</span><span class="sxs-lookup"><span data-stu-id="e99f6-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="e99f6-178">Validar bloque a primera vista funciona</span><span class="sxs-lookup"><span data-stu-id="e99f6-178">Validate block at first sight is working</span></span>

<span data-ttu-id="e99f6-179">Para validar que la característica funciona, siga las instrucciones de [Validar conexiones entre la red y la nube.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="e99f6-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="e99f6-180">Desactivar el bloque a primera vista</span><span class="sxs-lookup"><span data-stu-id="e99f6-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="e99f6-181">Desactivar el bloque a primera vista disminuirá el estado de protección de los dispositivos y la red.</span><span class="sxs-lookup"><span data-stu-id="e99f6-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="e99f6-182">Es posible que elija deshabilitar el bloqueo a primera vista si desea conservar la configuración de requisitos previos sin usar realmente la protección de bloqueo a primera vista.</span><span class="sxs-lookup"><span data-stu-id="e99f6-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="e99f6-183">Puede desactivar temporalmente el bloqueo a primera vista para ver cómo afecta esta característica a la red.</span><span class="sxs-lookup"><span data-stu-id="e99f6-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="e99f6-184">Sin embargo, no recomendamos deshabilitar el bloqueo a primera vista de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="e99f6-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="e99f6-185">Desactivar el bloque a primera vista con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="e99f6-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="e99f6-186">Vaya al Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="e99f6-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="e99f6-187">Vaya a **Endpoint security**  >  **Antivirus** y, a continuación, seleccione la directiva antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e99f6-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="e99f6-188">En **Administrar**, elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="e99f6-189">Junto a **Configuración,** elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="e99f6-190">Cambie una o varias de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e99f6-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="e99f6-191">Establezca **Activar la protección entregada en la nube** en **No** o No **configurado**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="e99f6-192">Establezca **el nivel de protección entregado en la nube** en No **configurado.**</span><span class="sxs-lookup"><span data-stu-id="e99f6-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="e99f6-193">Desactive la casilla de verificación **de Tiempo de espera extendido de Defender Cloud en segundos**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="e99f6-194">Revise y guarde la configuración.</span><span class="sxs-lookup"><span data-stu-id="e99f6-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="e99f6-195">Desactivar el bloque a primera vista con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="e99f6-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="e99f6-196">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="e99f6-197">Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo** y seleccione **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="e99f6-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="e99f6-198">Expande el árbol a través **de componentes de Windows** Microsoft Defender  >  **Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="e99f6-199">Haga doble clic **en Configurar la característica "Bloquear a primera vista"** y establezca la opción en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e99f6-200">Deshabilitar el bloque a primera vista no deshabilita ni modifica las directivas de grupo de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="e99f6-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="e99f6-201">¿No es un administrador de empresa ni un profesional de TI?</span><span class="sxs-lookup"><span data-stu-id="e99f6-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="e99f6-202">Si no es un administrador de empresa o un profesional de TI, pero tiene preguntas sobre el bloqueo a primera vista, esta sección es para usted.</span><span class="sxs-lookup"><span data-stu-id="e99f6-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="e99f6-203">Bloquear a primera vista es una característica de protección contra amenazas que detecta y bloquea el malware en cuestión de segundos.</span><span class="sxs-lookup"><span data-stu-id="e99f6-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="e99f6-204">Aunque no hay una configuración específica denominada "Bloquear a primera vista", la característica se habilita cuando se configuran determinadas opciones de configuración en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e99f6-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="e99f6-205">Cómo administrar el bloqueo a primera vista en o desactivado en tu propio dispositivo</span><span class="sxs-lookup"><span data-stu-id="e99f6-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="e99f6-206">Si tienes un dispositivo personal que no está administrado por una organización, es posible que te estés preguntando cómo activar o desactivar el bloqueo a primera vista.</span><span class="sxs-lookup"><span data-stu-id="e99f6-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="e99f6-207">Puedes usar la aplicación Seguridad de Windows para administrar el bloque a primera vista.</span><span class="sxs-lookup"><span data-stu-id="e99f6-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="e99f6-208">En el equipo con Windows 10, abre la aplicación Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="e99f6-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="e99f6-209">Seleccione **Protección contra & virus**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="e99f6-210">En **Configuración de protección contra & virus,** seleccione Administrar **configuración**.</span><span class="sxs-lookup"><span data-stu-id="e99f6-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="e99f6-211">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e99f6-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="e99f6-212">Para habilitar el bloqueo a primera  vista, asegúrese de que tanto la protección entregada en la nube como el **envío** automático de muestra estén activados.</span><span class="sxs-lookup"><span data-stu-id="e99f6-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="e99f6-213">Para deshabilitar el bloqueo a primera vista, desactive **la protección entregada** en la nube o el envío de muestra **automático.**</span><span class="sxs-lookup"><span data-stu-id="e99f6-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="e99f6-214">Desactivar el bloque a primera vista reduce el nivel de protección del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e99f6-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="e99f6-215">No se recomienda deshabilitar permanentemente el bloque a primera vista.</span><span class="sxs-lookup"><span data-stu-id="e99f6-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="e99f6-216">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e99f6-216">See also</span></span>

- [<span data-ttu-id="e99f6-217">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="e99f6-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="e99f6-218">Habilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="e99f6-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e99f6-219">Mantenerse protegido con Seguridad de Windows</span><span class="sxs-lookup"><span data-stu-id="e99f6-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)