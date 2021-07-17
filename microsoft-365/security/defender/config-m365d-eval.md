---
title: Configurar Microsoft 365 Defender para el laboratorio de prueba o el entorno piloto
description: Configure Microsoft 365 Defender, como Microsoft Defender para Office 365, Microsoft Defender para la identidad, Microsoft Cloud App Security y Microsoft Defender para endpoint, para su entorno piloto o laboratorio de prueba.
keywords: configurar Microsoft 365 Defender prueba, Microsoft 365 Defender de prueba, configurar Microsoft 365 Defender proyecto piloto, configurar Microsoft 365 Defender pilares, Microsoft 365 Defender pilares
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e50210f02d14be33c357517515d456318aac4bb6
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458852"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="71c56-104">Configurar Microsoft 365 Defender para el entorno piloto o el laboratorio de prueba</span><span class="sxs-lookup"><span data-stu-id="71c56-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="71c56-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="71c56-105">**Applies to:**</span></span>
- <span data-ttu-id="71c56-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71c56-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="71c56-107">Crear un Microsoft 365 Defender de prueba o un entorno piloto e implementarlo es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="71c56-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="71c56-108">[![Fase 1: Preparación](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="71c56-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="71c56-109">Fase 1: Preparación</span><span class="sxs-lookup"><span data-stu-id="71c56-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="71c56-110">[![Fase 2: Configuración](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="71c56-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="71c56-111">Fase 2: Configuración</span><span class="sxs-lookup"><span data-stu-id="71c56-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![Fase 3: Incorporación](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="71c56-113">Fase 3: Incorporación</span><span class="sxs-lookup"><span data-stu-id="71c56-113">Phase 3: Onboard</span></span> | <span data-ttu-id="71c56-114">[![Volver al piloto](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="71c56-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="71c56-115">Volver al libro de reproducción piloto</span><span class="sxs-lookup"><span data-stu-id="71c56-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="71c56-116">*¡Estás aquí!*</span><span class="sxs-lookup"><span data-stu-id="71c56-116">*You are here!*</span></span> | |

<span data-ttu-id="71c56-117">Actualmente está en la fase de configuración.</span><span class="sxs-lookup"><span data-stu-id="71c56-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="71c56-118">La preparación es clave para cualquier implementación correcta.</span><span class="sxs-lookup"><span data-stu-id="71c56-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="71c56-119">En este artículo, se te guiará sobre los puntos que tendrás que tener en cuenta mientras te preparas para implementar Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="71c56-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>

## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="71c56-120">Microsoft 365 Defender pilares</span><span class="sxs-lookup"><span data-stu-id="71c56-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="71c56-121">Microsoft 365 Defender consta de cuatro pilares.</span><span class="sxs-lookup"><span data-stu-id="71c56-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="71c56-122">Aunque un pilar ya puede proporcionar valor a la seguridad de la organización de red, habilitar los cuatro pilares Microsoft 365 Defender le dará a la organización el mayor valor.</span><span class="sxs-lookup"><span data-stu-id="71c56-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Imagen of_Microsoft solución de 365 Defender para usuarios, Microsoft Defender para identidad, para puntos de conexión de Microsoft Defender para endpoint, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="71c56-124">En esta sección se le guiará para configurar:</span><span class="sxs-lookup"><span data-stu-id="71c56-124">This section will guide you to configure:</span></span>

- <span data-ttu-id="71c56-125">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="71c56-125">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="71c56-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="71c56-126">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="71c56-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="71c56-127">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="71c56-128">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="71c56-128">Microsoft Defender for Endpoint</span></span>

## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="71c56-129">Configurar Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="71c56-129">Configure Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="71c56-130">Omita este paso si ya ha habilitado Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="71c56-130">Skip this step if you've already enabled Defender for Office 365.</span></span>

<span data-ttu-id="71c56-131">Hay un módulo de PowerShell denominado *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* que ayuda a determinar algunas de estas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="71c56-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="71c56-132">Cuando se ejecuta como administrador en el espacio empresarial, get-ORCAReport ayudará a generar una evaluación de la configuración de higiene de mensajes, contra correo no deseado y antiphishing.</span><span class="sxs-lookup"><span data-stu-id="71c56-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="71c56-133">Puede descargar este módulo desde https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="71c56-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span>

1. <span data-ttu-id="71c56-134">Vaya a la [Office 365 administración & de](https://protection.office.com/homepage)amenazas del Centro de seguridad  >  **y**  >  **cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="71c56-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Página de of_Office de administración de amenazas del Centro de seguridad & 365](../../media/mtp-eval-32.png)

2. <span data-ttu-id="71c56-136">Haga **clic en Anti-phishing**, **seleccione Crear** y rellene el nombre y la descripción de la directiva.</span><span class="sxs-lookup"><span data-stu-id="71c56-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="71c56-137">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="71c56-137">Click **Next**.</span></span>

   ![Página de of_Office 365 Security & Compliance Center anti-phishing donde puede nombrar su directiva](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="71c56-139">Edite la directiva anti phishing avanzada en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="71c56-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="71c56-140">Cambiar **el umbral de suplantación de** identidad avanzada a **2 : agresivo**.</span><span class="sxs-lookup"><span data-stu-id="71c56-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="71c56-141">Haga clic **en el menú desplegable Agregar** una condición y seleccione los dominios como dominio de destinatario.</span><span class="sxs-lookup"><span data-stu-id="71c56-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="71c56-142">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="71c56-142">Click **Next**.</span></span>

   ![Página of_Office directiva contra phishing del Centro de seguridad & 365 donde puede agregar una condición para su aplicación](../../media/mtp-eval-34.png)

4. <span data-ttu-id="71c56-144">Revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="71c56-144">Review your settings.</span></span> <span data-ttu-id="71c56-145">Haga **clic en Crear esta directiva** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="71c56-145">Click **Create this policy** to confirm.</span></span>

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)

5. <span data-ttu-id="71c56-147">Seleccione **Caja fuerte datos adjuntos** y seleccione la opción Activar **ATP para SharePoint, OneDrive y Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="71c56-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Página of_Office Centro de seguridad y & cumplimiento de 365 donde puedes activar ATP para SharePoint, OneDrive y Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="71c56-149">Haga clic en el icono + para crear una nueva directiva de datos adjuntos seguros y aplicarla como dominio de destinatario a los dominios.</span><span class="sxs-lookup"><span data-stu-id="71c56-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="71c56-150">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="71c56-150">Click **Save**.</span></span>

   ![Página of_Office 365 Security & Compliance Center donde puede crear una nueva directiva de datos adjuntos seguros](../../media/mtp-eval-37.png)

7. <span data-ttu-id="71c56-152">Después, seleccione la directiva **Caja fuerte vínculos y,** a continuación, haga clic en el icono de lápiz para editar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="71c56-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="71c56-153">Asegúrese de que la opción No realizar **un seguimiento** cuando los usuarios hacen clic en vínculos seguros no está seleccionada, mientras que el resto de las opciones están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="71c56-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="71c56-154">Consulta [Caja fuerte de vínculos para](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="71c56-154">See [Safe Links settings](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="71c56-155">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="71c56-155">Click **Save**.</span></span>

   ![Image of_Office 365 Security & Compliance Center page which shows that the option Do not track when users click safe is not selected](../../media/mtp-eval-38.png)

9. <span data-ttu-id="71c56-157">A continuación, **seleccione la directiva antimalware,** seleccione el valor predeterminado y elija el icono de lápiz.</span><span class="sxs-lookup"><span data-stu-id="71c56-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="71c56-158">Haga **clic Configuración** y seleccione Sí y use el texto de notificación **predeterminado** para habilitar La respuesta **de detección de malware**.</span><span class="sxs-lookup"><span data-stu-id="71c56-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="71c56-159">Active el **filtro Tipos comunes de datos adjuntos.**</span><span class="sxs-lookup"><span data-stu-id="71c56-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="71c56-160">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="71c56-160">Click **Save**.</span></span>

    ![Página of_Office Centro de seguridad y & cumplimiento de 365 365, que muestra que la respuesta de detección de malware está activada con la notificación predeterminada y el filtro de tipos de datos adjuntos comunes está activado](../../media/mtp-eval-39.png)

11. <span data-ttu-id="71c56-162">Vaya a Office 365 búsqueda & registro de auditoría del Centro de seguridad [y](https://protection.office.com/homepage)cumplimiento y  >    >   active Auditoría.</span><span class="sxs-lookup"><span data-stu-id="71c56-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Página of_Office centro de seguridad y & 365 donde puede activar la búsqueda de registro de auditoría](../../media/mtp-eval-40.png)

12. <span data-ttu-id="71c56-164">Integre Microsoft Defender para Office 365 con Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="71c56-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="71c56-165">Vaya a [Office 365 Explorador](https://protection.office.com/homepage)& administración de amenazas del Centro de seguridad y cumplimiento y seleccione Microsoft Defender para Endpoint Configuración en la esquina superior derecha de la  >    >   pantalla. </span><span class="sxs-lookup"><span data-stu-id="71c56-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="71c56-166">En el cuadro de diálogo Conexión de Defender para extremo, active **Conectar a Microsoft Defender para Endpoint**.</span><span class="sxs-lookup"><span data-stu-id="71c56-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Página of_Office centro de seguridad y & 365 donde puedes activar la conexión de Microsoft Defender para endpoint](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="71c56-168">Configurar Microsoft Defender para la identidad</span><span class="sxs-lookup"><span data-stu-id="71c56-168">Configure Microsoft Defender for Identity</span></span>

> [!NOTE]
> <span data-ttu-id="71c56-169">Omita este paso si ya ha habilitado Microsoft Defender para Identity</span><span class="sxs-lookup"><span data-stu-id="71c56-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="71c56-170">Vaya a [Microsoft 365 Centro de seguridad](https://security.microsoft.com/info) > seleccione Más **recursos** De Microsoft Defender  >  **para identidad**.</span><span class="sxs-lookup"><span data-stu-id="71c56-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Imagen of_Microsoft página del Centro de seguridad de 365 donde hay una opción para abrir Microsoft Defender para identidad](../../media/mtp-eval-42.png)

2. <span data-ttu-id="71c56-172">Haga **clic en** Crear para iniciar el Asistente para Microsoft Defender para identidades.</span><span class="sxs-lookup"><span data-stu-id="71c56-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span>

   ![Página of_Microsoft asistente de Defender for Identity en la que debes hacer clic en El botón Crear](../../media/mtp-eval-43.png)

3. <span data-ttu-id="71c56-174">Elija **Proporcionar un nombre de usuario y una contraseña para conectarse al bosque de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="71c56-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>

   ![Página of_Microsoft de inicio de Defender for Identity](../../media/mtp-eval-44.png)

4. <span data-ttu-id="71c56-176">Escriba las credenciales locales de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="71c56-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="71c56-177">Puede ser cualquier cuenta de usuario que tenga acceso de lectura a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="71c56-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Página de of_Microsoft Defender para los servicios de directorio de identidad donde debe colocar sus credenciales](../../media/mtp-eval-45.png)

5. <span data-ttu-id="71c56-179">A continuación, **elija Descargar instalación del sensor** y transferir el archivo al controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="71c56-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Página de of_Microsoft Defender para identidad en la que puedes seleccionar Descargar configuración del sensor](../../media/mtp-eval-46.png)

6. <span data-ttu-id="71c56-181">Ejecute el programa de instalación del sensor de identidad de Microsoft Defender y comience a seguir el asistente.</span><span class="sxs-lookup"><span data-stu-id="71c56-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Página de of_Microsoft Defender para la identidad en la que debes hacer clic junto para seguir el Asistente para sensores de Microsoft Defender para identidad](../../media/mtp-eval-47.png)

7. <span data-ttu-id="71c56-183">Haga **clic en Siguiente** en el tipo de implementación del sensor.</span><span class="sxs-lookup"><span data-stu-id="71c56-183">Click **Next** at the sensor deployment type.</span></span>

   ![Página of_Microsoft Defender for Identity donde debes hacer clic junto para ir a la página siguiente](../../media/mtp-eval-48.png)

8. <span data-ttu-id="71c56-185">Copie la clave de acceso porque debe escribirla a continuación en el Asistente.</span><span class="sxs-lookup"><span data-stu-id="71c56-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Página de of_the sensores de imagen en la que debe copiar la clave de acceso que necesita escribir en la siguiente página del Asistente para la configuración del sensor de Microsoft Defender para identidades](../../media/mtp-eval-49.png)

9. <span data-ttu-id="71c56-187">Copie la clave de acceso en el Asistente y haga clic **en Instalar**.</span><span class="sxs-lookup"><span data-stu-id="71c56-187">Copy the access key into the Wizard and click **Install**.</span></span>

   ![Página of_Microsoft asistente del sensor defender para la identidad donde debe proporcionar la clave de acceso y, a continuación, haga clic en el botón instalar](../../media/mtp-eval-50.png)

10. <span data-ttu-id="71c56-189">Enhorabuena, ha configurado correctamente Microsoft Defender para Identity en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="71c56-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Finalización of_Microsoft instalación del asistente para el sensor de Defender for Identity donde debes hacer clic en el botón finalizar](../../media/mtp-eval-51.png)

11. <span data-ttu-id="71c56-191">En la [sección Configuración de Microsoft Defender para](https://go.microsoft.com/fwlink/?linkid=2040449) identidad, selecciona \*\*Microsoft Defender para endpoint \*\*, luego activa la alternancia.</span><span class="sxs-lookup"><span data-stu-id="71c56-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="71c56-192">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="71c56-192">Click **Save**.</span></span>

    ![Página of_the configuración de Microsoft Defender para identidad donde debes activar la alternancia de Microsoft Defender para endpoint](../../media/mtp-eval-52.png)

## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="71c56-194">Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="71c56-194">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="71c56-195">Omita este paso si ya ha habilitado Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="71c56-195">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span>

1. <span data-ttu-id="71c56-196">Vaya a [Microsoft 365 Centro de seguridad](https://security.microsoft.com/info)Más  >  **recursos**  >  **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="71c56-196">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Imagen of_Microsoft página del Centro de seguridad de 365 donde puede ver la tarjeta de Microsoft Cloud App y debe hacer clic en el botón abrir](../../media/mtp-eval-53.png)

2. <span data-ttu-id="71c56-198">En el símbolo del sistema de información para integrar Microsoft Defender for Identity, seleccione **Habilitar Microsoft Defender para la integración de datos de identidad.**</span><span class="sxs-lookup"><span data-stu-id="71c56-198">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>

   ![Mensaje de información of_the imagen para integrar Microsoft Defender for Identity donde debe seleccionar el vínculo Habilitar la integración de datos de Microsoft Defender para identidad](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="71c56-200">Si no ve este mensaje, puede significar que la integración de datos de Microsoft Defender para identidad ya está habilitada.</span><span class="sxs-lookup"><span data-stu-id="71c56-200">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="71c56-201">Sin embargo, si no está seguro, póngase en contacto con el administrador de TI para confirmarlo.</span><span class="sxs-lookup"><span data-stu-id="71c56-201">However, if you are not sure, contact your IT Administrator to confirm.</span></span>

3. <span data-ttu-id="71c56-202">Vaya a **Configuración**, active el botón de alternancia de **integración** de Microsoft Defender para identidad y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="71c56-202">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span>

   ![Página de of_the configuración de imagen en la que debes activar el botón de alternancia de integración de Microsoft Defender para identidades y, a continuación, haz clic en Guardar](../../media/mtp-eval-55.png)

   > [!NOTE]
   > <span data-ttu-id="71c56-204">Para las nuevas instancias de Microsoft Defender para Identity, esta alternancia de integración se activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="71c56-204">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="71c56-205">Confirme que la integración de Microsoft Defender para identidades se ha habilitado antes de continuar con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="71c56-205">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>

4. <span data-ttu-id="71c56-206">En La configuración de detección en la nube, **selecciona Microsoft Defender para la** integración de puntos de conexión y, a continuación, habilita la integración.</span><span class="sxs-lookup"><span data-stu-id="71c56-206">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="71c56-207">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="71c56-207">Click **Save**.</span></span>

   ![Imagen of_the página de Microsoft Defender para endpoint donde está activada la casilla bloquear aplicaciones no seleccionadas en Microsoft Defender para la integración de puntos de conexión.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="71c56-210">En Configuración de detección en la nube, seleccione **Enriquecimiento de usuario** y, a continuación, habilite la integración con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="71c56-210">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Imagen de la sección Enriquecimiento del usuario en la que se selecciona la casilla enriquecer los identificadores de usuario detectados Azure Active Directory nombres de usuario](../../media/mtp-eval-57.png)

## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="71c56-212">Configurar Microsoft Defender para el extremo</span><span class="sxs-lookup"><span data-stu-id="71c56-212">Configure Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="71c56-213">Omita este paso si ya ha habilitado Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="71c56-213">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="71c56-214">Vaya a [Microsoft 365 Centro de seguridad](https://security.microsoft.com/info)Más  >  **recursos**  >  **Centro de seguridad de Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="71c56-214">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="71c56-215">Haga clic en **Open** (Abrir).</span><span class="sxs-lookup"><span data-stu-id="71c56-215">Click **Open**.</span></span>

   ![Imagen of_Microsoft centro de seguridad de Defender en la página Microsoft 365 Centro de seguridad](../../media/mtp-eval-58.png)

2. <span data-ttu-id="71c56-217">Siga el Asistente para Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="71c56-217">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="71c56-218">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="71c56-218">Click **Next**.</span></span>

   ![Página of_the Centro de seguridad de Microsoft Defender asistente de bienvenida](../../media/mtp-eval-59.png)

3. <span data-ttu-id="71c56-220">Elija en función de la ubicación de almacenamiento de datos preferida, la directiva de retención de datos, el tamaño de la organización y la participación en las características de vista previa.</span><span class="sxs-lookup"><span data-stu-id="71c56-220">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Página of_the imagen para seleccionar el país de almacenamiento de datos, la directiva de retención y el tamaño de la organización.](../../media/mtp-eval-60.png)

   > [!NOTE]
   > <span data-ttu-id="71c56-223">No puede cambiar parte de la configuración, como la ubicación de almacenamiento de datos, después.</span><span class="sxs-lookup"><span data-stu-id="71c56-223">You cannot change some of the settings, like data storage location, afterwards.</span></span>

   <span data-ttu-id="71c56-224">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="71c56-224">Click **Next**.</span></span>

4. <span data-ttu-id="71c56-225">Haga **clic en** Continuar y aprovisionará el inquilino de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="71c56-225">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Página de of_the que le pedirá que haga clic en el botón Continuar para crear la instancia en la nube](../../media/mtp-eval-61.png)

5. <span data-ttu-id="71c56-227">Incorpore los puntos de conexión a través de directivas de grupo, Microsoft Endpoint Manager o ejecutando un script local en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="71c56-227">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="71c56-228">Para simplificar, esta guía usa el script local.</span><span class="sxs-lookup"><span data-stu-id="71c56-228">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="71c56-229">Haga **clic en Descargar paquete** y copie el script de incorporación en los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="71c56-229">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Image of_page prompting you click the Download package button to copy the onboarding script to your endpoint or endpoints](../../media/mtp-eval-62.png)

7. <span data-ttu-id="71c56-231">En el punto de conexión, ejecute el script de incorporación como administrador y elija Y.</span><span class="sxs-lookup"><span data-stu-id="71c56-231">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>

   ![Image of_the commandline where you run the onboarding script and choose Y to proceed](../../media/mtp-eval-63.png)

8. <span data-ttu-id="71c56-233">Enhorabuena, ha incorporado su primer punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="71c56-233">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Imagen of_the línea de comandos donde obtienes la confirmación de que has incorporado el primer punto de conexión.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="71c56-236">Copie y pegue la prueba de detección desde el Asistente para Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="71c56-236">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the un paso de prueba de detección donde debe hacer clic en Copiar para copiar el script de prueba de detección que debe pegar en el símbolo del sistema](../../media/mtp-eval-65.png)

10. <span data-ttu-id="71c56-238">Copie el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="71c56-238">Copy the PowerShell script to an elevated command prompt and run it.</span></span>

    ![Símbolo of_command donde debe copiar el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="71c56-240">Seleccione **Empezar a usar Microsoft Defender para endpoint** en el Asistente.</span><span class="sxs-lookup"><span data-stu-id="71c56-240">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Mensaje of_the confirmación del asistente donde debe hacer clic en Empezar a usar Microsoft Defender para endpoint](../../media/mtp-eval-67.png)

12. <span data-ttu-id="71c56-242">Visite el [Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="71c56-242">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="71c56-243">Vaya a **Configuración** y, a continuación, seleccione **Características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="71c56-243">Go to **Settings** and then select **Advanced features**.</span></span>

    ![Menú of_Microsoft centro de seguridad de Defender Configuración donde debe seleccionar Características avanzadas](../../media/mtp-eval-68.png)

13. <span data-ttu-id="71c56-245">Activa la integración con **Microsoft Defender para Identity**.</span><span class="sxs-lookup"><span data-stu-id="71c56-245">Turn on the integration with **Microsoft Defender for Identity**.</span></span>

    ![Opciones of_Microsoft Advanced del Centro de seguridad de Defender, opción de Microsoft Defender para identidad que necesitas activar](../../media/mtp-eval-69.png)

14. <span data-ttu-id="71c56-247">Active la integración con **Office 365 threat intelligence**.</span><span class="sxs-lookup"><span data-stu-id="71c56-247">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Características of_Microsoft Advanced del Centro de seguridad de Defender, Office 365 opción de inteligencia de amenazas que necesitas activar](../../media/mtp-eval-70.png)

15. <span data-ttu-id="71c56-249">Activar la integración **con Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="71c56-249">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Características of_Microsoft avanzadas del Centro de seguridad de Defender, Microsoft Cloud App Security opción de alternancia que necesita activar](../../media/mtp-eval-71.png)

16. <span data-ttu-id="71c56-251">Desplácese hacia abajo y haga **clic en Guardar preferencias** para confirmar las nuevas integraciones.</span><span class="sxs-lookup"><span data-stu-id="71c56-251">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Botón of_Save preferencias de imagen que necesita hacer clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="71c56-253">Iniciar el servicio de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71c56-253">Start the Microsoft 365 Defender service</span></span>

> [!NOTE]
> <span data-ttu-id="71c56-254">A partir del 1 de junio de 2020, Microsoft habilita automáticamente Microsoft 365 Defender características para todos los inquilinos elegibles.</span><span class="sxs-lookup"><span data-stu-id="71c56-254">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="71c56-255">Vea este [artículo de Microsoft Tech Community sobre elegibilidad de licencias](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="71c56-255">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span>

<span data-ttu-id="71c56-256">Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="71c56-256">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="71c56-257">Vaya a **Configuración** y, a continuación, **seleccione Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="71c56-257">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![Imagen of_Microsoft captura de pantalla de la opción 365 Defender desde la Microsoft 365 del Centro de seguridad Configuración pantalla](../../media/mtp-eval-72b.png)

<span data-ttu-id="71c56-259">Para obtener una guía más completa, vea [Activar Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="71c56-259">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="71c56-260">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="71c56-260">Congratulations!</span></span> <span data-ttu-id="71c56-261">Acaba de crear su entorno piloto Microsoft 365 Defender de prueba o de prueba.</span><span class="sxs-lookup"><span data-stu-id="71c56-261">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="71c56-262">Ahora puedes familiarizarte con la interfaz Microsoft 365 Defender usuario.</span><span class="sxs-lookup"><span data-stu-id="71c56-262">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="71c56-263">Vea lo que puede aprender en la siguiente guía Microsoft 365 Defender interactiva y sepa cómo usar cada panel para sus tareas diarias de operación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71c56-263">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>

[<span data-ttu-id="71c56-264">Eche un vistazo a la guía interactiva</span><span class="sxs-lookup"><span data-stu-id="71c56-264">Check out the interactive guide</span></span>](https://aka.ms/MTP-Interactive-Guide)

<span data-ttu-id="71c56-265">A continuación, puedes simular un ataque y ver cómo las capacidades entre productos detectan, crean alertas y responden automáticamente a un ataque sin archivos en un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="71c56-265">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="71c56-266">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="71c56-266">Next step</span></span>

- <span data-ttu-id="71c56-267">[Generar una alerta de prueba:](generate-test-alert.md) ejecute una simulación de ataque en el Microsoft 365 Defender de prueba.</span><span class="sxs-lookup"><span data-stu-id="71c56-267">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>
