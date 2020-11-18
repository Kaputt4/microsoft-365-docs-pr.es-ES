---
title: Configuración de los pilares de 365 defender de Microsoft para el entorno de prueba o el entorno piloto
description: Configure los pilares de 365 defender de Microsoft, como Microsoft defender para Office 365, Microsoft defender para identidad, Microsoft Cloud App Security y Microsoft defender for Endpoint, para su laboratorio de pruebas o entorno piloto.
keywords: configurar Microsoft Threat Protection prueba, configuración de prueba de protección contra amenazas de Microsoft, configurar el proyecto piloto de Microsoft Threat Protection Pilot, configurar los pilares de la protección contra amenazas de Microsoft, pilares de la protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131302"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="e8e9b-104">Configuración de los pilares de 365 defender de Microsoft para el entorno de prueba o el entorno piloto</span><span class="sxs-lookup"><span data-stu-id="e8e9b-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e8e9b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e8e9b-105">**Applies to:**</span></span>
- <span data-ttu-id="e8e9b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8e9b-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="e8e9b-107">La creación de un entorno de prueba de Microsoft 365 defender o un entorno piloto y su implementación es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="e8e9b-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="e8e9b-108">[![Fase 1: preparación](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="e8e9b-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="e8e9b-109">Fase 1: preparación</span><span class="sxs-lookup"><span data-stu-id="e8e9b-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="e8e9b-110">[![Fase 2: configurar](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="e8e9b-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="e8e9b-111">Fase 2: configurar</span><span class="sxs-lookup"><span data-stu-id="e8e9b-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Fase 3: incorporada](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="e8e9b-113">Fase 3: incorporada</span><span class="sxs-lookup"><span data-stu-id="e8e9b-113">Phase 3: Onboard</span></span> | <span data-ttu-id="e8e9b-114">[![Volver a la prueba piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="e8e9b-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="e8e9b-115">Volver a la guía piloto</span><span class="sxs-lookup"><span data-stu-id="e8e9b-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="e8e9b-116">*Ya está aquí.*</span><span class="sxs-lookup"><span data-stu-id="e8e9b-116">*You are here!*</span></span> | |

<span data-ttu-id="e8e9b-117">Actualmente se encuentra en la fase de configuración.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="e8e9b-118">La preparación es fundamental para todas las implementaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="e8e9b-119">En este artículo, se le guiará en los puntos que debe tener en cuenta a la hora de preparar la implementación de Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="e8e9b-120">Pilares de 365 defender de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e8e9b-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="e8e9b-121">Microsoft 365 defender consta de cuatro pilares.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="e8e9b-122">Aunque un pilar ya puede proporcionar valor a la seguridad de su organización de red, la habilitación de los cuatro pilares de Microsoft 365 defender dará mayor valor a su organización.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Imagen of_Microsoft solución de 365 defender para usuarios, Microsoft defender para identidad, para extremos Microsoft defender para Endpoint, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft defender para Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="e8e9b-124">Esta sección le guiará para configurar:</span><span class="sxs-lookup"><span data-stu-id="e8e9b-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="e8e9b-125">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e8e9b-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="e8e9b-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e8e9b-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="e8e9b-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e8e9b-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="e8e9b-128">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e8e9b-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="e8e9b-129">Configurar Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e8e9b-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="e8e9b-130">Omita este paso si ya ha habilitado defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="e8e9b-131">Hay un módulo de PowerShell denominado analizador de configuración de la *protección contra amenazas avanzada de Office 365 (Orca)* que ayuda a determinar algunas de estas opciones.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="e8e9b-132">Cuando se ejecuta como administrador en su espacio empresarial, Get-ORCAReport le ayudará a generar una evaluación de la configuración de protección contra correo electrónico no deseado, anti-phish y otros mensajes.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="e8e9b-133">Puede descargar este módulo desde https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="e8e9b-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="e8e9b-134">Vaya a la Directiva de administración de amenazas [& cumplimiento del centro de cumplimiento de Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Página de la Directiva de administración de amenazas de seguridad of_Office 365 de & de seguridad del centro de cumplimiento](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="e8e9b-136">Haga clic en **anti-phishing**, seleccione **crear** y rellene el nombre y la descripción de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="e8e9b-137">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-137">Click **Next**.</span></span>

   ![Página de la Directiva de la Directiva antiphishing del centro de cumplimiento de la & de seguridad of_Office 365, donde puede asignar un nombre a la Directiva](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="e8e9b-139">Edite su Directiva antiphishing avanzada en Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e8e9b-140">Cambiar el **umbral de suplantación de identidad avanzado** a **2-agresivo**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="e8e9b-141">Haga clic en el menú desplegable **Agregar condición** y seleccione su dominio o dominios como dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="e8e9b-142">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-142">Click **Next**.</span></span>

   ![Página de la Directiva de la Directiva antiphishing del centro de cumplimiento de la & de seguridad of_Office 365, donde puede Agregar una condición para su aplicación](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="e8e9b-144">Revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-144">Review your settings.</span></span> <span data-ttu-id="e8e9b-145">Haga clic en **crear esta directiva** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-145">Click **Create this policy** to confirm.</span></span> 

   ![Imagen of_Office 365 de seguridad & página de la Directiva de antiphishing del centro de cumplimiento, donde puede revisar la configuración y hacer clic en el botón crear esta Directiva](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="e8e9b-147">Seleccione **datos adjuntos seguros** y seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="e8e9b-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar ATP para SharePoint, OneDrive y Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="e8e9b-149">Haga clic en el icono + para crear una nueva Directiva de datos adjuntos seguros, aplíquela como dominio del destinatario en sus dominios.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="e8e9b-150">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-150">Click **Save**.</span></span>

   ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede crear una nueva Directiva de datos adjuntos seguros](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="e8e9b-152">A continuación, seleccione la directiva **vínculos seguros** y, a continuación, haga clic en el icono de lápiz para editar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="e8e9b-153">Asegúrese de que la opción no **realizar seguimiento cuando los usuarios hagan clic en vínculos seguros** no esté seleccionada, mientras que el resto de las opciones están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="e8e9b-154">Vea [configuración de vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="e8e9b-155">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-155">Click **Save**.</span></span> 

   ![Página of_Office 365 de seguridad & de centro de cumplimiento que muestra que la opción no realiza un seguimiento cuando los usuarios hacen clic en seguro no está seleccionado](../../media/mtp-eval-38.png)

9. <span data-ttu-id="e8e9b-157">A continuación, seleccione la directiva **antimalware** , seleccione la opción predeterminada y elija el icono de lápiz.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="e8e9b-158">Haga clic en **configuración** y seleccione **sí y use el texto de notificación predeterminado** para habilitar la **respuesta de detección de malware**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="e8e9b-159">Active el **filtro tipos de datos adjuntos comunes** en.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="e8e9b-160">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-160">Click **Save**.</span></span>

    ![Página of_Office 365 de seguridad & de centro de cumplimiento que muestra que la respuesta de detección de malware está activada con notificación predeterminada y el filtro tipos de datos adjuntos comunes está activado](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="e8e9b-162">Vaya a [Office 365 Security & cumplimiento del centro](https://protection.office.com/homepage)  >  **Search**  >  de **Auditoría** búsqueda y active la auditoría.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar la búsqueda de registros de auditoría](../../media/mtp-eval-40.png)

12. <span data-ttu-id="e8e9b-164">Integración de Microsoft defender para Office 365 con Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e8e9b-165">Vaya a [Office 365 Security & cumplimiento](https://protection.office.com/homepage)  >  del centro de **Administración de amenazas**  >  **Explorer** y seleccione **Microsoft defender for Endpoint Settings** en la esquina superior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="e8e9b-166">En el cuadro de diálogo defender para conexión de extremo, Active **conectar con Microsoft defender para el extremo**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar Microsoft defender para la conexión de extremo](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="e8e9b-168">Configurar Microsoft defender para identidad</span><span class="sxs-lookup"><span data-stu-id="e8e9b-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="e8e9b-169">Omita este paso si ya ha habilitado Microsoft defender para identidad</span><span class="sxs-lookup"><span data-stu-id="e8e9b-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="e8e9b-170">Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info) > seleccione **más recursos**  >  **Microsoft defender para identidad**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Página del centro de seguridad de of_Microsoft de imágenes 365 donde hay una opción para abrir Microsoft defender para identidad](../../media/mtp-eval-42.png)

2. <span data-ttu-id="e8e9b-172">Haga clic en **crear** para iniciar el Asistente de Microsoft defender para identidad.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Imagen del asistente de of_Microsoft defender para la identidad donde debe hacer clic en el botón crear](../../media/mtp-eval-43.png)

3. <span data-ttu-id="e8e9b-174">Elija **proporcionar un nombre de usuario y una contraseña para conectar con el bosque de Active** Directory.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Imagen of_Microsoft defender para la página de bienvenida de identidad](../../media/mtp-eval-44.png)

4. <span data-ttu-id="e8e9b-176">Escriba sus credenciales locales de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="e8e9b-177">Puede ser cualquier cuenta de usuario que tenga acceso de lectura a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Imagen of_Microsoft defender para la página de servicios de directorio de identidad donde debe colocar sus credenciales](../../media/mtp-eval-45.png)

5. <span data-ttu-id="e8e9b-179">A continuación, seleccione **descargar la configuración del sensor** y transferir el archivo a su controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Imagen of_Microsoft defender para la página de identidad donde puede seleccionar Descargar configuración del sensor](../../media/mtp-eval-46.png)

6. <span data-ttu-id="e8e9b-181">Ejecute Microsoft defender para la configuración del sensor de identidad y comience a seguir el asistente.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Imagen of_Microsoft defender para la página de identidad donde debe hacer clic en siguiente para seguir el Asistente de Microsoft defender para el sensor de identidad](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="e8e9b-183">Haga clic en **siguiente** en el tipo de implementación de sensor.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-183">Click **Next** at the sensor deployment type.</span></span>

   ![Imagen of_Microsoft defender para la página de identidad donde debe hacer clic en siguiente para ir a la página siguiente](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="e8e9b-185">Copie la clave de acceso porque tiene que escribirla a continuación en el asistente.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Página de of_the de imágenes de sensores donde debe copiar la clave de acceso que necesita introducir en la próxima página del Asistente para la instalación de Microsoft defender para el sensor de identidad](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="e8e9b-187">Copie la clave de acceso en el asistente y haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Imagen of_Microsoft defender para el Asistente para el sensor de identidad donde debe proporcionar la clave de acceso y, a continuación, haga clic en el botón instalar](../../media/mtp-eval-50.png)

10. <span data-ttu-id="e8e9b-189">Enhorabuena, ha configurado correctamente Microsoft defender para identidad en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Imagen of_Microsoft defender para el Asistente para el sensor de identidad finalizó la instalación donde debe hacer clic en el botón Finalizar](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="e8e9b-191">En la sección [Microsoft defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) Settings, seleccione \* \* Microsoft defender for Endpoint \* \* y, a continuación, active la opción de alternancia.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="e8e9b-192">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-192">Click **Save**.</span></span> 

    ![Imagen of_the página de Microsoft defender para obtener la configuración de la identidad en la que se debe activar o desactivar el cambio de Microsoft defender para el punto de conexión](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="e8e9b-194">Windows Defender ATP ha cambiado de marca como Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e8e9b-195">Los cambios de personalización de marca en todos nuestros portales se están implementando para lograr coherencia.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="e8e9b-196">Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e8e9b-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="e8e9b-197">Omita este paso si ya ha habilitado Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="e8e9b-198">Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **más recursos**  >  **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Página del centro de seguridad de of_Microsoft de imágenes 365 donde puede ver la tarjeta de Microsoft Cloud App y debe hacer clic en el botón abrir](../../media/mtp-eval-53.png)

2. <span data-ttu-id="e8e9b-200">En la información solicitada para integrar Microsoft defender para identidad, seleccione **Habilitar Microsoft defender para la integración de datos de identidad**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Image of_the información del mensaje para integrar Microsoft defender para identidad donde debe seleccionar el vínculo habilitar Microsoft defender para la integración de datos de identidades](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="e8e9b-202">Si no ve este mensaje, puede significar que ya se ha habilitado Microsoft defender para la integración de datos de identidad.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="e8e9b-203">Sin embargo, si no está seguro, póngase en contacto con su administrador de TI para confirmarlo.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="e8e9b-204">Vaya a **configuración**, active el botón de alternancia **de Microsoft defender para integración de identidades** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Página de configuración de of_the de imágenes donde debe activar el botón de alternancia de Microsoft defender para la integración de identidades y, a continuación, haga clic en guardar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="e8e9b-206">En el caso de los nuevos Microsoft defender para instancias de identidad, este cambio de integración se activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="e8e9b-207">Confirme que se haya habilitado Microsoft defender para la integración de identidad antes de continuar con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="e8e9b-208">En configuración de detección en la nube, seleccione **Microsoft defender for Endpoint Integration** y, a continuación, habilite la integración.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="e8e9b-209">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-209">Click **Save**.</span></span>

   ![Imagen of_the página Microsoft defender para el punto de conexión donde está seleccionada la casilla bloquear aplicaciones sin autorizar en Microsoft defender para la integración de extremos.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="e8e9b-212">En configuración de detección en la nube, seleccione **enriquecimiento de usuario** y, a continuación, habilite la integración con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Imagen de la sección enriquecimiento de usuario donde está seleccionada la casilla enriquecer los identificadores de usuario detectados con nombres de usuario de Azure Active Directory](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="e8e9b-214">Configurar Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e8e9b-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="e8e9b-215">Omita este paso si ya ha habilitado Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="e8e9b-216">Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **más recursos**  >  **centro de seguridad de Microsoft defender**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="e8e9b-217">Haga clic en **Open** (Abrir).</span><span class="sxs-lookup"><span data-stu-id="e8e9b-217">Click **Open**.</span></span>

   ![Imagen of_Microsoft defender Security Center Option en la página del centro de seguridad de Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="e8e9b-219">Siga el Asistente de Microsoft defender para extremo.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="e8e9b-220">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-220">Click **Next**.</span></span> 

   ![Imagen of_the página del asistente de bienvenida del centro de seguridad de Microsoft defender](../../media/mtp-eval-59.png)

3. <span data-ttu-id="e8e9b-222">Elija en función de la ubicación de almacenamiento de datos preferida, la Directiva de retención de datos, el tamaño de la organización y las características de vista previa.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Imagen of_the página para seleccionar su país de almacenamiento de datos, la Directiva de retención y el tamaño de la organización.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="e8e9b-225">No puede cambiar algunos de los valores, como la ubicación de almacenamiento de datos, más adelante.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="e8e9b-226">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-226">Click **Next**.</span></span> 

4. <span data-ttu-id="e8e9b-227">Haga clic en **continuar** y se aprovisionará su Microsoft defender para inquilino de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Imagen of_the página que le pide que haga clic en el botón continuar para crear su instancia de nube](../../media/mtp-eval-61.png)

5. <span data-ttu-id="e8e9b-229">Incorpore los puntos de conexión a través de directivas de grupo, Microsoft Endpoint Manager o mediante la ejecución de un script local a Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e8e9b-230">Para simplificar, esta guía usa el script local.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="e8e9b-231">Haga clic en **Descargar paquete** y copie el script de incorporación en los extremos.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Imagen of_page le pregunta si desea hacer clic en el botón Descargar paquete para copiar el script de incorporación en el extremo o los extremos](../../media/mtp-eval-62.png)

7. <span data-ttu-id="e8e9b-233">En el punto de conexión, ejecute el script de incorporación como administrador y elija Y.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Image of_the CommandLine donde se ejecuta el script de incorporación y elija y para continuar.](../../media/mtp-eval-63.png)

8. <span data-ttu-id="e8e9b-235">Enhorabuena, ha incorporado el primer punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the CommandLine donde recibirá la confirmación de que ha incorporado el primer punto de conexión.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="e8e9b-238">Copie y pegue la prueba de detección desde el Asistente de Microsoft defender para extremo.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Imagen of_the ejecute un paso de prueba de detección en el que debe hacer clic en copiar para copiar el script de prueba de detección que debe pegar en el símbolo del sistema](../../media/mtp-eval-65.png)

10. <span data-ttu-id="e8e9b-240">Copie el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Image of_command prompt donde debe copiar el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="e8e9b-242">Seleccione **empezar a usar Microsoft defender para el extremo** desde el asistente.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Imagen of_the mensaje de confirmación del asistente donde debe hacer clic en empezar a usar Microsoft defender para el punto de conexión](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="e8e9b-244">Visite el [centro de seguridad de Microsoft defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="e8e9b-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="e8e9b-245">Vaya a **configuración** y, a continuación, seleccione **características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Menú de configuración del centro de seguridad de imágenes of_Microsoft defender donde debe seleccionar características avanzadas](../../media/mtp-eval-68.png)

13. <span data-ttu-id="e8e9b-247">Active la integración con **Microsoft defender para identidad**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Características avanzadas del centro de seguridad de imágenes of_Microsoft defender, Microsoft defender para la opción de identidad para alternar entre los que debe activar](../../media/mtp-eval-69.png)

14. <span data-ttu-id="e8e9b-249">Active la integración con la **inteligencia sobre amenazas de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Características avanzadas del centro de seguridad de imágenes of_Microsoft defender, Office 365 Threat Intelligence opción para alternar la activación](../../media/mtp-eval-70.png)

15. <span data-ttu-id="e8e9b-251">Active la integración con **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft defender Security Center Advanced Security Features, Microsoft Cloud App Security opción alternar la activación](../../media/mtp-eval-71.png)

16. <span data-ttu-id="e8e9b-253">Desplácese hacia abajo y haga clic en **Guardar preferencias** para confirmar las nuevas integraciones.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Botón de preferencias de of_Save de imagen en el que debe hacer clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="e8e9b-255">Iniciar el servicio de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8e9b-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="e8e9b-256">A partir del 1 de junio de 2020, Microsoft habilita automáticamente las características de Microsoft 365 defender para todos los inquilinos elegibles.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="e8e9b-257">Consulte este [artículo de la comunidad tecnológica de Microsoft sobre la elegibilidad de licencias](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="e8e9b-258">Vaya al [centro de seguridad 365 de Microsoft](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="e8e9b-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="e8e9b-259">Vaya a **configuración** y, a continuación, seleccione **Microsoft 365 defender**.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="e8e9b-260">Captura de pantalla de la opción imagen of_Microsoft 365 defender desde la página Configuración del centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8e9b-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="e8e9b-261">Para obtener una guía más completa, consulte [Activar Microsoft 365 defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="e8e9b-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="e8e9b-262">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="e8e9b-262">Congratulations!</span></span> <span data-ttu-id="e8e9b-263">Acaba de crear su entorno de prueba de Microsoft 365 defender o un entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="e8e9b-264">Ahora puede familiarizarse con la interfaz de usuario de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="e8e9b-265">Vea lo que puede aprender de la siguiente guía interactiva de Microsoft 365 defender y sepa cómo usar cada panel para las tareas de la operación de seguridad diaria.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="e8e9b-266">A continuación, puede simular un ataque y ver cómo las capacidades cruzadas del producto detectan, crean alertas y responden automáticamente a un ataque de archivos no deseados en un extremo.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="e8e9b-267">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e8e9b-267">Next step</span></span>
|[<span data-ttu-id="e8e9b-268">Fase de simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="e8e9b-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="e8e9b-269">Ejecute la simulación de ataques para su entorno piloto de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="e8e9b-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
