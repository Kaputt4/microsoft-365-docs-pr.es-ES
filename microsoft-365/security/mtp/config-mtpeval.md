---
title: Configurar los pilares de Microsoft 365 Defender para el entorno de prueba o piloto
description: Configure los pilares de Microsoft 365 Defender, como Microsoft Defender para Office 365, Microsoft Defender para Identidad, Microsoft Cloud App Security y Microsoft Defender para Endpoint, para su entorno de prueba o piloto.
keywords: configurar la prueba de Protección contra amenazas de Microsoft, la configuración de prueba de la Protección contra amenazas de Microsoft, configurar el proyecto piloto de La Protección contra amenazas de Microsoft, configurar los pilares de la Protección contra amenazas de Microsoft, los pilares de la Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932243"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="55c26-104">Configurar los pilares de Microsoft 365 Defender para su entorno de prueba o piloto</span><span class="sxs-lookup"><span data-stu-id="55c26-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="55c26-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="55c26-105">**Applies to:**</span></span>
- <span data-ttu-id="55c26-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55c26-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="55c26-107">Crear un entorno de prueba o piloto de Microsoft 365 Defender e implementarlo es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="55c26-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="55c26-108">[![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="55c26-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="55c26-109">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="55c26-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="55c26-110">[![Fase 2: Configurar](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="55c26-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="55c26-111">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="55c26-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Fase 3: Incorporación](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="55c26-113">Fase 3: Incorporación</span><span class="sxs-lookup"><span data-stu-id="55c26-113">Phase 3: Onboard</span></span> | <span data-ttu-id="55c26-114">[![Volver al piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="55c26-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="55c26-115">Volver al libro de juegos piloto</span><span class="sxs-lookup"><span data-stu-id="55c26-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="55c26-116">*¡Estás aquí!*</span><span class="sxs-lookup"><span data-stu-id="55c26-116">*You are here!*</span></span> | |

<span data-ttu-id="55c26-117">Actualmente se encuentra en la fase de configuración.</span><span class="sxs-lookup"><span data-stu-id="55c26-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="55c26-118">La preparación es clave para una implementación correcta.</span><span class="sxs-lookup"><span data-stu-id="55c26-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="55c26-119">En este artículo, se te guiará sobre los puntos que debes tener en cuenta a medida que te preparas para implementar Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="55c26-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="55c26-120">Pilares de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55c26-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="55c26-121">Microsoft 365 Defender consta de cuatro pilares.</span><span class="sxs-lookup"><span data-stu-id="55c26-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="55c26-122">Aunque un pilar ya puede proporcionar valor a la seguridad de su organización de red, habilitar los cuatro pilares de Microsoft 365 Defender dará a su organización el máximo valor.</span><span class="sxs-lookup"><span data-stu-id="55c26-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Imagen of_Microsoft solución de Defender 365 para usuarios, Microsoft Defender para Identidad, para puntos de conexión de Microsoft Defender para puntos de conexión, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="55c26-124">Esta sección le guiará a configurar:</span><span class="sxs-lookup"><span data-stu-id="55c26-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="55c26-125">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="55c26-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="55c26-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="55c26-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="55c26-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="55c26-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="55c26-128">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="55c26-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="55c26-129">Configurar Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="55c26-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="55c26-130">Omita este paso si ya ha habilitado Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="55c26-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="55c26-131">Hay un módulo de PowerShell denominado Analizador de configuración recomendado de Protección contra amenazas *avanzada (ORCA) de Office 365* que ayuda a determinar algunas de estas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="55c26-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="55c26-132">Cuando se ejecuta como administrador en su espacio empresarial, get-ORCAReport le ayudará a generar una evaluación de la configuración de higiene de mensajes, antiphishing y contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="55c26-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="55c26-133">Puede descargar este módulo desde https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="55c26-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="55c26-134">Vaya a La directiva de administración de amenazas del Centro & seguridad de [Office 365.](https://protection.office.com/homepage)  >    >  </span><span class="sxs-lookup"><span data-stu-id="55c26-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Página de of_Office de administración de amenazas del Centro & seguridad y cumplimiento de 365](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="55c26-136">Haga **clic en Anti-phishing,** seleccione **Crear** y rellene el nombre y la descripción de la directiva.</span><span class="sxs-lookup"><span data-stu-id="55c26-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="55c26-137">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="55c26-137">Click **Next**.</span></span>

   ![Imagen of_Office página de directiva anti-phishing del Centro de seguridad & cumplimiento 365 donde puede nombrar la directiva](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="55c26-139">Edite la directiva contra suplantación de identidad avanzada en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="55c26-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="55c26-140">Cambie **el umbral de suplantación de** identidad avanzada a **2: agresivo.**</span><span class="sxs-lookup"><span data-stu-id="55c26-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="55c26-141">Haga clic **en el menú desplegable Agregar** una condición y seleccione los dominios como dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="55c26-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="55c26-142">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="55c26-142">Click **Next**.</span></span>

   ![Imagen of_Office página de directiva contra suplantación de identidad del Centro de seguridad & cumplimiento 365 donde puede agregar una condición para su aplicación](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="55c26-144">Revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="55c26-144">Review your settings.</span></span> <span data-ttu-id="55c26-145">Haga **clic en Crear esta directiva** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="55c26-145">Click **Create this policy** to confirm.</span></span> 

   ![Imagen of_Office página de directiva contra suplantación de identidad del Centro de seguridad & cumplimiento 365 donde puede revisar la configuración y hacer clic en el botón crear esta directiva](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="55c26-147">Seleccione **Datos adjuntos** seguros y seleccione **la opción Activar ATP para SharePoint, OneDrive y Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="55c26-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365 donde puede activar ATP para SharePoint, OneDrive y Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="55c26-149">Haga clic en el icono + para crear una nueva directiva de datos adjuntos seguros y aplíquela como dominio de destinatario a sus dominios.</span><span class="sxs-lookup"><span data-stu-id="55c26-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="55c26-150">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55c26-150">Click **Save**.</span></span>

   ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365 donde puede crear una nueva directiva de datos adjuntos seguros](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="55c26-152">A continuación, seleccione la **directiva de vínculos** seguros y, a continuación, haga clic en el icono de lápiz para editar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="55c26-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="55c26-153">Asegúrese de que la **opción No realizar seguimiento cuando** los usuarios hacen clic en vínculos seguros no está seleccionada, mientras que el resto de las opciones están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="55c26-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="55c26-154">Consulte [la configuración de vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="55c26-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="55c26-155">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55c26-155">Click **Save**.</span></span> 

   ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365, que muestra que la opción No realizar seguimiento cuando los usuarios hacen clic en seguro no está seleccionada](../../media/mtp-eval-38.png)

9. <span data-ttu-id="55c26-157">A continuación, **seleccione la directiva antimalware,** seleccione la predeterminada y elija el icono de lápiz.</span><span class="sxs-lookup"><span data-stu-id="55c26-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="55c26-158">Haga **clic en** Configuración y seleccione Sí y use el texto de notificación **predeterminado** para habilitar la respuesta **de detección de malware.**</span><span class="sxs-lookup"><span data-stu-id="55c26-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="55c26-159">Activar el **filtro de tipos comunes de datos adjuntos.**</span><span class="sxs-lookup"><span data-stu-id="55c26-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="55c26-160">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55c26-160">Click **Save**.</span></span>

    ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365 que muestra que la respuesta de detección de malware está activada con la notificación predeterminada y que el filtro de tipos de datos adjuntos comunes está activado](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="55c26-162">Vaya a la búsqueda del registro de auditoría del Centro de & seguridad y cumplimiento de [Office 365](https://protection.office.com/homepage)y  >    >   active la auditoría.</span><span class="sxs-lookup"><span data-stu-id="55c26-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365, donde puede activar la búsqueda del registro de auditoría](../../media/mtp-eval-40.png)

12. <span data-ttu-id="55c26-164">Integre Microsoft Defender para Office 365 con Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="55c26-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="55c26-165">Vaya al Explorador de administración de amenazas del Centro de seguridad & Cumplimiento de [Office 365](https://protection.office.com/homepage)y seleccione Microsoft Defender para Configuración de puntos de conexión en la esquina superior  >    >   derecha de la pantalla. </span><span class="sxs-lookup"><span data-stu-id="55c26-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="55c26-166">En el cuadro de diálogo Conexión de Defender para extremo, active **Conectar a Microsoft Defender para Endpoint.**</span><span class="sxs-lookup"><span data-stu-id="55c26-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365, donde puede activar la conexión de Microsoft Defender para puntos de conexión](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="55c26-168">Configurar Microsoft Defender para la identidad</span><span class="sxs-lookup"><span data-stu-id="55c26-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="55c26-169">Omita este paso si ya ha habilitado Microsoft Defender para Identity</span><span class="sxs-lookup"><span data-stu-id="55c26-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="55c26-170">Vaya al [Centro de seguridad de Microsoft 365](https://security.microsoft.com/info) > más **recursos** de Microsoft Defender  >  **para identidad.**</span><span class="sxs-lookup"><span data-stu-id="55c26-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Imagen of_Microsoft página del Centro de seguridad 365 donde hay una opción para abrir Microsoft Defender para Identidad](../../media/mtp-eval-42.png)

2. <span data-ttu-id="55c26-172">Haga **clic en** Crear para iniciar el Asistente de Microsoft Defender para identidades.</span><span class="sxs-lookup"><span data-stu-id="55c26-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Imagen of_Microsoft asistente de Defender para identidad donde debería hacer clic en el botón Crear](../../media/mtp-eval-43.png)

3. <span data-ttu-id="55c26-174">Elija **Proporcionar un nombre de usuario y una contraseña para conectarse al bosque de Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="55c26-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Página principal de Image of_Microsoft Defender for Identity](../../media/mtp-eval-44.png)

4. <span data-ttu-id="55c26-176">Escriba sus credenciales locales de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55c26-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="55c26-177">Puede ser cualquier cuenta de usuario que tenga acceso de lectura a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55c26-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Página de of_Microsoft defender para los servicios de directorio de identidad donde debe colocar las credenciales](../../media/mtp-eval-45.png)

5. <span data-ttu-id="55c26-179">A continuación, **elija Descargar configuración del sensor** y transferir el archivo al controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="55c26-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Página de Image of_Microsoft Defender for Identity en la que puedes seleccionar Descargar configuración del sensor](../../media/mtp-eval-46.png)

6. <span data-ttu-id="55c26-181">Ejecuta Microsoft Defender para la configuración del sensor de identidad y empieza a seguir el asistente.</span><span class="sxs-lookup"><span data-stu-id="55c26-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Página de of_Microsoft Defender para identidad en la que debes hacer clic junto para seguir el asistente del sensor de Microsoft Defender para identidad](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="55c26-183">Haz **clic en Siguiente** en el tipo de implementación del sensor.</span><span class="sxs-lookup"><span data-stu-id="55c26-183">Click **Next** at the sensor deployment type.</span></span>

   ![Página de of_Microsoft Defender para identidad donde debe hacer clic junto para ir a la página siguiente](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="55c26-185">Copie la tecla de acceso porque tiene que escribirla a continuación en el Asistente.</span><span class="sxs-lookup"><span data-stu-id="55c26-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Página de of_the sensores de imagen en la que debes copiar la tecla de acceso que necesitas escribir en la siguiente página del Asistente para configuración del sensor de Microsoft Defender para identidad](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="55c26-187">Copie la clave de acceso en el Asistente y haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="55c26-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Página of_Microsoft asistente del sensor defender para identidad donde debes proporcionar la tecla de acceso y, a continuación, hacer clic en el botón de instalación](../../media/mtp-eval-50.png)

10. <span data-ttu-id="55c26-189">Enhorabuena, ha configurado correctamente Microsoft Defender para Identity en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="55c26-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="55c26-191">En la [sección Configuración de Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2040449) para identidad, selecciona \*\*Microsoft Defender para punto de conexión \*\*y, a continuación, activa el botón de alternancia.</span><span class="sxs-lookup"><span data-stu-id="55c26-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="55c26-192">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55c26-192">Click **Save**.</span></span> 

    ![Imagen of_the página de configuración de Microsoft Defender para identidad donde debes activar el botón de alternancia de Microsoft Defender para punto de conexión](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="55c26-194">Windows Defender se ha cambiado el nombre de ATP como Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="55c26-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="55c26-195">El cambio de marca de los cambios en todos nuestros portales se está implantando para mantener la coherencia.</span><span class="sxs-lookup"><span data-stu-id="55c26-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="55c26-196">Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="55c26-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="55c26-197">Omita este paso si ya ha habilitado Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="55c26-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="55c26-198">Vaya al [Centro de seguridad de Microsoft 365](https://security.microsoft.com/info)Más  >  **recursos** de  >  **Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="55c26-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Imagen of_Microsoft página del Centro de seguridad 365 donde puede ver la tarjeta de Microsoft Cloud App y debe hacer clic en el botón Abrir](../../media/mtp-eval-53.png)

2. <span data-ttu-id="55c26-200">En el símbolo del sistema de información para integrar Microsoft Defender for Identity, seleccione **Habilitar Microsoft Defender para la integración de datos de identidad.**</span><span class="sxs-lookup"><span data-stu-id="55c26-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Mensaje de of_the de información de imagen para integrar Microsoft Defender for Identity donde debe seleccionar el vínculo Habilitar Microsoft Defender para la integración de datos de identidad](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="55c26-202">Si no ve este mensaje, puede significar que la integración de datos de Microsoft Defender para Identidad ya está habilitada.</span><span class="sxs-lookup"><span data-stu-id="55c26-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="55c26-203">Sin embargo, si no está seguro, póngase en contacto con el administrador de TI para confirmarlo.</span><span class="sxs-lookup"><span data-stu-id="55c26-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="55c26-204">Vaya a **Configuración,** active el botón de alternancia de **integración** de Microsoft Defender para identidad y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="55c26-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Página de of_the configuración de la imagen en la que debería activar el botón de alternancia de integración de Microsoft Defender para identidades y, a continuación, haga clic en Guardar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="55c26-206">Para las nuevas instancias de Microsoft Defender para identidad, este botón de alternancia de integración se activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="55c26-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="55c26-207">Confirme que la integración de Microsoft Defender para identidades se ha habilitado antes de continuar con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="55c26-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="55c26-208">En la configuración de detección de nube, **selecciona Microsoft Defender para la integración** de puntos de conexión y, a continuación, habilita la integración.</span><span class="sxs-lookup"><span data-stu-id="55c26-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="55c26-209">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="55c26-209">Click **Save**.</span></span>

   ![Imagen of_the página de Microsoft Defender para puntos de conexión en la que está seleccionada la casilla bloquear aplicaciones no seleccionadas en Microsoft Defender para la integración de puntos de conexión.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="55c26-212">En Configuración de detección de nube, seleccione **Enriquecimiento de usuarios** y, a continuación, habilite la integración con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55c26-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Imagen de la sección de enriquecimiento de usuarios en la que está activada la casilla de verificación de enriquecimiento de los identificadores de usuario detectados con nombres de usuario de Azure Active Directory](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="55c26-214">Configurar Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="55c26-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="55c26-215">Omita este paso si ya ha habilitado Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="55c26-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="55c26-216">Vaya al [Centro de seguridad de Microsoft 365](https://security.microsoft.com/info)Más  >  **recursos** del  >  **Centro de seguridad de Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="55c26-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="55c26-217">Haga clic en **Open** (Abrir).</span><span class="sxs-lookup"><span data-stu-id="55c26-217">Click **Open**.</span></span>

   ![Imagen of_Microsoft Centro de seguridad de Defender en la página Centro de seguridad de Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="55c26-219">Sigue el Asistente de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="55c26-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="55c26-220">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="55c26-220">Click **Next**.</span></span> 

   ![Página de of_the del Centro de seguridad de Microsoft Defender](../../media/mtp-eval-59.png)

3. <span data-ttu-id="55c26-222">Elija en función de la ubicación de almacenamiento de datos preferida, la directiva de retención de datos, el tamaño de la organización y la participación en las características de vista previa.</span><span class="sxs-lookup"><span data-stu-id="55c26-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Página de of_the imagen para seleccionar el país de almacenamiento de datos, la directiva de retención y el tamaño de la organización.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="55c26-225">No puede cambiar algunas de las opciones de configuración, como la ubicación de almacenamiento de datos, más adelante.</span><span class="sxs-lookup"><span data-stu-id="55c26-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="55c26-226">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="55c26-226">Click **Next**.</span></span> 

4. <span data-ttu-id="55c26-227">Haz **clic en Continuar** y aprovisionará el inquilino de Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="55c26-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Imagen of_the página en la que se le pide que haga clic en el botón Continuar para crear la instancia de nube](../../media/mtp-eval-61.png)

5. <span data-ttu-id="55c26-229">Incorpore los puntos de conexión a través de directivas de grupo, Microsoft Endpoint Manager o mediante la ejecución de un script local en Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="55c26-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="55c26-230">Por motivos de simplicidad, esta guía usa el script local.</span><span class="sxs-lookup"><span data-stu-id="55c26-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="55c26-231">Haz **clic en Descargar paquete** y copia el script de incorporación en tus puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="55c26-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Imagen of_page que te pide que hagas clic en el botón Descargar paquete para copiar el script de incorporación a tu punto de conexión o puntos de conexión](../../media/mtp-eval-62.png)

7. <span data-ttu-id="55c26-233">En el punto de conexión, ejecuta el script de incorporación como administrador y elige Y.</span><span class="sxs-lookup"><span data-stu-id="55c26-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Imagen of_the línea de comandos donde se ejecuta el script de incorporación y se elige Y para continuar](../../media/mtp-eval-63.png)

8. <span data-ttu-id="55c26-235">Enhorabuena, ha incorporado su primer punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="55c26-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Imagen of_the línea de comandos donde obtienes la confirmación de que has incorporado el primer punto de conexión.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="55c26-238">Copiar y pegar la prueba de detección desde el Asistente de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="55c26-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the run a detection test step where you should click Copy to copy the detection test script that you should paste in the command prompt](../../media/mtp-eval-65.png)

10. <span data-ttu-id="55c26-240">Copie el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="55c26-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Mensaje de of_command imagen donde debe copiar el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="55c26-242">Selecciona **Empezar a usar Microsoft Defender para Endpoint** en el Asistente.</span><span class="sxs-lookup"><span data-stu-id="55c26-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Mensaje of_the confirmación del asistente en el que debes hacer clic en Empezar a usar Microsoft Defender para puntos de conexión](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="55c26-244">Visite el Centro [de seguridad de Microsoft Defender.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="55c26-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="55c26-245">Vaya a **Configuración** y, a continuación, seleccione **Características avanzadas.**</span><span class="sxs-lookup"><span data-stu-id="55c26-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Imagen of_Microsoft configuración del Centro de seguridad de Defender donde debes seleccionar características avanzadas](../../media/mtp-eval-68.png)

13. <span data-ttu-id="55c26-247">Active la integración con **Microsoft Defender para Identity.**</span><span class="sxs-lookup"><span data-stu-id="55c26-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Image of_Microsoft Defender Security Center Advanced features, Microsoft Defender for Identity option toggle that you need to turn on](../../media/mtp-eval-69.png)

14. <span data-ttu-id="55c26-249">Active la integración con inteligencia **de amenazas de Office 365.**</span><span class="sxs-lookup"><span data-stu-id="55c26-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced features, Office 365 Threat Intelligence option toggle that you need to turn on](../../media/mtp-eval-70.png)

15. <span data-ttu-id="55c26-251">Active la integración con **Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="55c26-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Imagen of_Microsoft características avanzadas del Centro de seguridad de Defender, alternancia de opción de Microsoft Cloud App Security que necesitas activar](../../media/mtp-eval-71.png)

16. <span data-ttu-id="55c26-253">Desplácese hacia abajo y haga **clic en Guardar** preferencias para confirmar las nuevas integraciones.</span><span class="sxs-lookup"><span data-stu-id="55c26-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Botón of_Save preferencias de imagen en el que necesitas hacer clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="55c26-255">Iniciar el servicio de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55c26-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="55c26-256">A partir del 1 de junio de 2020, Microsoft habilita automáticamente las características de Microsoft 365 Defender para todos los inquilinos elegibles.</span><span class="sxs-lookup"><span data-stu-id="55c26-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="55c26-257">Consulta este [artículo de Microsoft Tech Community sobre la elegibilidad de licencias](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="55c26-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="55c26-258">Vaya al [Centro de seguridad de Microsoft 365.](https://security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="55c26-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="55c26-259">Vaya a **Configuración** y, a continuación, **seleccione Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="55c26-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="55c26-260">Imagen of_Microsoft captura de pantalla de la opción defender 365 de la página Configuración del Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="55c26-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="55c26-261">Para obtener una guía más completa, [vea Activar Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="55c26-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="55c26-262">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="55c26-262">Congratulations!</span></span> <span data-ttu-id="55c26-263">Acaba de crear el entorno piloto o el entorno de prueba de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="55c26-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="55c26-264">Ahora puede familiarizarse con la interfaz de usuario de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="55c26-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="55c26-265">Vea lo que puede aprender de la siguiente guía interactiva de Microsoft 365 Defender y sepa cómo usar cada panel para sus tareas diarias de operación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="55c26-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="55c26-266">A continuación, puedes simular un ataque y ver cómo las funcionalidades entre productos detectan, crean alertas y responden automáticamente a un ataque sin archivos en un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="55c26-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="55c26-267">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="55c26-267">Next step</span></span>
|[<span data-ttu-id="55c26-268">Fase de simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="55c26-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="55c26-269">Ejecute la simulación de ataques para su entorno piloto de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="55c26-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
