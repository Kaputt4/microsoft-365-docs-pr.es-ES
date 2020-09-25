---
title: Configurar los pilares de la protección contra amenazas de Microsoft para el entorno piloto o el laboratorio de prueba
description: Configure Microsoft Threat Protection pilares, como Office 365 ATP, Azure ATP, Microsoft Cloud App Security y Microsoft defender ATP, para su laboratorio de pruebas o entorno piloto.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 43facffde9c31dc33445de87997d2b91cba6a9f1
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277551"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="620ed-104">Configurar los pilares de la protección contra amenazas de Microsoft para el entorno de prueba o el entorno piloto</span><span class="sxs-lookup"><span data-stu-id="620ed-104">Configure Microsoft Threat Protection pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="620ed-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="620ed-105">**Applies to:**</span></span>
- <span data-ttu-id="620ed-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="620ed-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="620ed-107">La creación de un entorno piloto o un laboratorio de pruebas de Microsoft Threat Protection y su implementación es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="620ed-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparar el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection" />
      <br/><span data-ttu-id="620ed-109">Fase 1: preparación </a></span><span class="sxs-lookup"><span data-stu-id="620ed-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Configurar el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection" />
      <br/><span data-ttu-id="620ed-111">Fase 2: configuración </a></span><span class="sxs-lookup"><span data-stu-id="620ed-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurar cada pilar de protección contra amenazas de Microsoft para su laboratorio de prueba de Microsoft Threat Protection o entorno piloto y los extremos incorporados" />
      <br/><span data-ttu-id="620ed-113">Fase 3: configurar & incorporado </a></span><span class="sxs-lookup"><span data-stu-id="620ed-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>
  </tr>
</table>

<span data-ttu-id="620ed-114">Actualmente se encuentra en la fase de configuración.</span><span class="sxs-lookup"><span data-stu-id="620ed-114">You're currently in the configuration phase.</span></span>


<span data-ttu-id="620ed-115">La preparación es fundamental para todas las implementaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="620ed-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="620ed-116">En este artículo, se le guiará en los puntos que necesitará tener en cuenta a la hora de prepararse para implementar ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="620ed-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="620ed-117">Pilares de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="620ed-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="620ed-118">La protección contra amenazas de Microsoft consta de cuatro pilares.</span><span class="sxs-lookup"><span data-stu-id="620ed-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="620ed-119">Aunque un pilar ya puede proporcionar valor a la seguridad de su organización de red, la habilitación de los cuatro pilares de la protección contra amenazas de Microsoft dará mayor valor a su organización.</span><span class="sxs-lookup"><span data-stu-id="620ed-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![<span data-ttu-id="620ed-120">Solución de protección contra amenazas of_Microsoft de imágenes para los usuarios, la protección contra amenazas avanzada de Azure, para extremos protección contra amenazas avanzada de Microsoft defender, para aplicaciones en la nube, seguridad de aplicación en la nube de Microsoft y para datos, protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="620ed-120">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp-eval-31.png)

<span data-ttu-id="620ed-121">Esta sección le guiará para configurar:</span><span class="sxs-lookup"><span data-stu-id="620ed-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="620ed-122">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="620ed-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="620ed-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="620ed-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="620ed-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="620ed-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="620ed-125">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="620ed-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="620ed-126">Configuración de la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="620ed-126">Configure Office 365 Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="620ed-127">Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="620ed-127">Skip this step if you've already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="620ed-128">Hay un módulo de PowerShell denominado analizador de configuración de la *protección contra amenazas avanzada de Office 365 (Orca)* que ayuda a determinar algunas de estas opciones.</span><span class="sxs-lookup"><span data-stu-id="620ed-128">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="620ed-129">Cuando se ejecuta como administrador en su espacio empresarial, Get-ORCAReport le ayudará a generar una evaluación de la configuración de protección contra correo electrónico no deseado, anti-phish y otros mensajes.</span><span class="sxs-lookup"><span data-stu-id="620ed-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="620ed-130">Puede descargar este módulo desde https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="620ed-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="620ed-131">Vaya a la Directiva de administración de amenazas [& cumplimiento del centro de cumplimiento de Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="620ed-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Página de la Directiva de administración de amenazas de seguridad of_Office 365 de & de seguridad del centro de cumplimiento](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="620ed-133">Haga clic en **anti-phishing ATP**, seleccione **crear** y rellene el nombre y la descripción de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="620ed-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="620ed-134">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="620ed-134">Click **Next**.</span></span>

   ![Página de la Directiva de la Directiva antiphishing del centro de cumplimiento de la & de seguridad of_Office 365, donde puede asignar un nombre a la Directiva](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="620ed-136">Edite la Directiva antiphishing de ATP avanzada.</span><span class="sxs-lookup"><span data-stu-id="620ed-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="620ed-137">Cambiar el **umbral de suplantación de identidad avanzado** a **2-agresivo**.</span><span class="sxs-lookup"><span data-stu-id="620ed-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="620ed-138">Haga clic en el menú desplegable **Agregar condición** y seleccione su dominio o dominios como dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="620ed-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="620ed-139">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="620ed-139">Click **Next**.</span></span>

   ![Página de la Directiva de la Directiva antiphishing del centro de cumplimiento de la & de seguridad of_Office 365, donde puede Agregar una condición para su aplicación](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="620ed-141">Revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="620ed-141">Review your settings.</span></span> <span data-ttu-id="620ed-142">Haga clic en **crear esta directiva** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="620ed-142">Click **Create this policy** to confirm.</span></span> 

   ![Imagen of_Office 365 de seguridad & página de la Directiva de antiphishing del centro de cumplimiento, donde puede revisar la configuración y hacer clic en el botón crear esta Directiva](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="620ed-144">Seleccione **datos adjuntos seguros de ATP** y seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="620ed-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar ATP para SharePoint, OneDrive y Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="620ed-146">Haga clic en el icono + para crear una nueva Directiva de datos adjuntos seguros, aplíquela como dominio del destinatario en sus dominios.</span><span class="sxs-lookup"><span data-stu-id="620ed-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="620ed-147">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="620ed-147">Click **Save**.</span></span>

   ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede crear una nueva Directiva de datos adjuntos seguros](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="620ed-149">A continuación, seleccione la Directiva de **vínculos seguros ATP** y haga clic en el icono de lápiz para editar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="620ed-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="620ed-150">Asegúrese de que la opción no **realizar seguimiento cuando los usuarios hagan clic en vínculos seguros** no esté seleccionada, mientras que el resto de las opciones están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="620ed-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="620ed-151">Vea [configuración de vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="620ed-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="620ed-152">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="620ed-152">Click **Save**.</span></span> 

   ![Página of_Office 365 de seguridad & de centro de cumplimiento que muestra que la opción no realiza un seguimiento cuando los usuarios hacen clic en seguro no está seleccionado](../../media/mtp-eval-38.png)

9. <span data-ttu-id="620ed-154">A continuación, seleccione la directiva **antimalware** , seleccione la opción predeterminada y elija el icono de lápiz.</span><span class="sxs-lookup"><span data-stu-id="620ed-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="620ed-155">Haga clic en **configuración** y seleccione **sí y use el texto de notificación predeterminado** para habilitar la **respuesta de detección de malware**.</span><span class="sxs-lookup"><span data-stu-id="620ed-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="620ed-156">Active el **filtro tipos de datos adjuntos comunes** en.</span><span class="sxs-lookup"><span data-stu-id="620ed-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="620ed-157">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="620ed-157">Click **Save**.</span></span>

    ![Página of_Office 365 de seguridad & de centro de cumplimiento que muestra que la respuesta de detección de malware está activada con notificación predeterminada y el filtro tipos de datos adjuntos comunes está activado](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="620ed-159">Vaya a [Office 365 Security & cumplimiento del centro](https://protection.office.com/homepage)  >  **Search**  >  de**Auditoría** búsqueda y active la auditoría.</span><span class="sxs-lookup"><span data-stu-id="620ed-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar la búsqueda de registros de auditoría](../../media/mtp-eval-40.png)

12. <span data-ttu-id="620ed-161">Integrar Office 365 ATP con Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="620ed-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="620ed-162">Vaya a [Office 365 Security & cumplimiento](https://protection.office.com/homepage)  >  del centro de**Administración de amenazas**  >  **Explorer** y seleccione **WDATP configuración** en la esquina superior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="620ed-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="620ed-163">En el cuadro de diálogo conexión ATP de Microsoft defender, Active **conectarse a ATP de Windows**.</span><span class="sxs-lookup"><span data-stu-id="620ed-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>

    ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar la conexión ATP de Windows Defender](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="620ed-165">Configurar la protección contra amenazas avanzada de Azure</span><span class="sxs-lookup"><span data-stu-id="620ed-165">Configure Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="620ed-166">Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Azure</span><span class="sxs-lookup"><span data-stu-id="620ed-166">Skip this step if you've already enabled Azure Advanced Threat Protection</span></span>

1. <span data-ttu-id="620ed-167">Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info) > seleccione **más recursos**  >  **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="620ed-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>

   ![Página del centro de seguridad de Image of_Microsoft 365 donde hay una opción para abrir la protección contra amenazas avanzada de Azure](../../media/mtp-eval-42.png)

2. <span data-ttu-id="620ed-169">Haga clic en **crear** para iniciar el Asistente de Azure Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="620ed-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 

   ![Imagen of_Azure página del asistente de protección contra amenazas avanzada donde debe hacer clic en el botón crear](../../media/mtp-eval-43.png)

3. <span data-ttu-id="620ed-171">Elija **proporcionar un nombre de usuario y una contraseña para conectar con el bosque de Active**Directory.</span><span class="sxs-lookup"><span data-stu-id="620ed-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Imagen of_Azure Página principal de la protección contra amenazas avanzada](../../media/mtp-eval-44.png)

4. <span data-ttu-id="620ed-173">Escriba sus credenciales locales de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="620ed-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="620ed-174">Puede ser cualquier cuenta de usuario que tenga acceso de lectura a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="620ed-174">This can be any user account that has read access to Active Directory.</span></span>

   ![Imagen of_Azure página de servicios de directorio de protección contra amenazas avanzada donde debe colocar sus credenciales](../../media/mtp-eval-45.png)

5. <span data-ttu-id="620ed-176">A continuación, seleccione **descargar la configuración del sensor** y transferir el archivo a su controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="620ed-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Imagen of_Azure página protección avanzada contra amenazas donde puede seleccionar Descargar configuración del sensor](../../media/mtp-eval-46.png)

6. <span data-ttu-id="620ed-178">Ejecute la configuración del sensor ATP de Azure y comience a seguir el asistente.</span><span class="sxs-lookup"><span data-stu-id="620ed-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>

   ![Imagen of_Azure página protección avanzada contra amenazas, en la que debe hacer clic en siguiente para seguir el Asistente para sensores ATP de Azure](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="620ed-180">Haga clic en **siguiente** en el tipo de implementación de sensor.</span><span class="sxs-lookup"><span data-stu-id="620ed-180">Click **Next** at the sensor deployment type.</span></span>

   ![Imagen of_Azure página protección avanzada contra amenazas en la que debe hacer clic en siguiente para ir a la página siguiente](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="620ed-182">Copie la clave de acceso porque tiene que escribirla a continuación en el asistente.</span><span class="sxs-lookup"><span data-stu-id="620ed-182">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Página de of_the de la imagen sensores donde debe copiar la clave de acceso que necesita escribir en la próxima página del Asistente para la configuración de sensores de ATP de Azure](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="620ed-184">Copie la clave de acceso en el asistente y haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="620ed-184">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Imagen of_Azure página del Asistente para la protección contra amenazas avanzada de Azure ATP donde debe proporcionar la clave de acceso y, a continuación, haga clic en el botón instalar](../../media/mtp-eval-50.png)

10. <span data-ttu-id="620ed-186">Enhorabuena, ha configurado correctamente la protección contra amenazas avanzada de Azure en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="620ed-186">Congratulations, you've successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>

    ![Imagen of_Azure protección contra amenazas avanzadas Asistente para sensores ATP de Azure finalización de la instalación donde debe hacer clic en el botón Finalizar](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="620ed-188">En la sección configuración de ATP de Azure [Azure](https://go.microsoft.com/fwlink/?linkid=2040449) , seleccione **ATP de Windows Defender**y, a continuación, active la alternancia.</span><span class="sxs-lookup"><span data-stu-id="620ed-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn on the toggle.</span></span> <span data-ttu-id="620ed-189">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="620ed-189">Click **Save**.</span></span> 

    ![Imagen of_the página de configuración de ATP de Azure Azure donde deberías activar el botón de alternancia de ATP de Windows Defender](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="620ed-191">Windows Defender ATP ha cambiado de marca como ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="620ed-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="620ed-192">Los cambios de personalización de marca en todos nuestros portales se están implementando para lograr coherencia.</span><span class="sxs-lookup"><span data-stu-id="620ed-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="620ed-193">Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="620ed-193">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="620ed-194">Omita este paso si ya ha habilitado Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="620ed-194">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="620ed-195">Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **más recursos**  >  **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="620ed-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Página del centro de seguridad de of_Microsoft de imágenes 365 donde puede ver la tarjeta de Microsoft Cloud App y debe hacer clic en el botón abrir](../../media/mtp-eval-53.png)

2. <span data-ttu-id="620ed-197">En la solicitud de información para integrar ATP de Azure, seleccione **Habilitar la integración de datos de ATP de Azure**.</span><span class="sxs-lookup"><span data-stu-id="620ed-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span>
  
   ![Imagen of_the información sobre la solicitud de integración de ATP de Azure donde debe seleccionar el vínculo habilitar la integración de datos de ATP de Azure](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="620ed-199">Si no aparece este mensaje, puede significar que ya se ha habilitado la integración de datos de ATP de Azure.</span><span class="sxs-lookup"><span data-stu-id="620ed-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="620ed-200">Sin embargo, si no está seguro, póngase en contacto con su administrador de TI para confirmarlo.</span><span class="sxs-lookup"><span data-stu-id="620ed-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="620ed-201">Vaya a **configuración**, active el botón de alternancia **integración de ATP de Azure** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="620ed-201">Go to **Settings**, turn on the **Azure ATP integration** toggle, then click **Save**.</span></span> 

   ![Página de configuración de of_the de imágenes donde debe activar el botón de alternancia integración de ATP de Azure y, a continuación, haga clic en guardar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="620ed-203">Para las nuevas instancias de ATP de Azure, este cambio de integración se activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="620ed-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="620ed-204">Confirme que la integración de ATP de Azure se haya habilitado antes de continuar con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="620ed-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="620ed-205">En la configuración de detección en la nube, seleccione **integración de Microsoft defender ATP**y, a continuación, habilite la integración.</span><span class="sxs-lookup"><span data-stu-id="620ed-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="620ed-206">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="620ed-206">Click **Save**.</span></span>

   ![Imagen of_the página ATP de Microsoft defender en la que la casilla bloquear aplicaciones no autorizadas de la integración de ATP de Microsoft defender está seleccionada.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="620ed-209">En configuración de detección en la nube, seleccione **enriquecimiento de usuario**y, a continuación, habilite la integración con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="620ed-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Imagen de la sección enriquecimiento de usuario donde está seleccionada la casilla enriquecer los identificadores de usuario detectados con nombres de usuario de Azure Active Directory](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="620ed-211">Configurar la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="620ed-211">Configure Microsoft Defender Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="620ed-212">Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="620ed-212">Skip this step if you've already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="620ed-213">Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **más recursos**  >  **centro de seguridad de Microsoft defender**.</span><span class="sxs-lookup"><span data-stu-id="620ed-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="620ed-214">Haga clic en **Open** (Abrir).</span><span class="sxs-lookup"><span data-stu-id="620ed-214">Click **Open**.</span></span>

   ![Imagen of_Microsoft defender Security Center Option en la página del centro de seguridad de Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="620ed-216">Siga el Asistente para la protección contra amenazas avanzada de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="620ed-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="620ed-217">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="620ed-217">Click **Next**.</span></span> 

   ![Imagen of_the página del asistente de bienvenida del centro de seguridad de Microsoft defender](../../media/mtp-eval-59.png)

3. <span data-ttu-id="620ed-219">Elija en función de la ubicación de almacenamiento de datos preferida, la Directiva de retención de datos, el tamaño de la organización y las características de vista previa.</span><span class="sxs-lookup"><span data-stu-id="620ed-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Imagen of_the página para seleccionar su país de almacenamiento de datos, la Directiva de retención y el tamaño de la organización.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="620ed-222">No puede cambiar algunos de los valores, como la ubicación de almacenamiento de datos, más adelante.</span><span class="sxs-lookup"><span data-stu-id="620ed-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="620ed-223">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="620ed-223">Click **Next**.</span></span> 

4. <span data-ttu-id="620ed-224">Haga clic en **continuar** y se aprovisionará el inquilino ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="620ed-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>

   ![Imagen of_the página que le pide que haga clic en el botón continuar para crear su instancia de nube](../../media/mtp-eval-61.png)

5. <span data-ttu-id="620ed-226">Incorpore los puntos de conexión a través de directivas de grupo, Microsoft Endpoint Manager o mediante la ejecución de un script local a ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="620ed-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="620ed-227">Para simplificar, esta guía usa el script local.</span><span class="sxs-lookup"><span data-stu-id="620ed-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="620ed-228">Haga clic en **Descargar paquete** y copie el script de incorporación en los extremos.</span><span class="sxs-lookup"><span data-stu-id="620ed-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Imagen of_page le pregunta si desea hacer clic en el botón Descargar paquete para copiar el script de incorporación en el extremo o los extremos](../../media/mtp-eval-62.png)

7. <span data-ttu-id="620ed-230">En el punto de conexión, ejecute el script de incorporación como administrador y elija Y.</span><span class="sxs-lookup"><span data-stu-id="620ed-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Image of_the CommandLine donde se ejecuta el script de incorporación y elija y para continuar.](../../media/mtp-eval-63.png)

8. <span data-ttu-id="620ed-232">Enhorabuena, ha incorporado el primer punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="620ed-232">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the CommandLine donde recibirá la confirmación de que ha incorporado el primer punto de conexión.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="620ed-235">Copie-pegue la prueba de detección desde el Asistente para ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="620ed-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>

   ![Imagen of_the ejecute un paso de prueba de detección en el que debe hacer clic en copiar para copiar el script de prueba de detección que debe pegar en el símbolo del sistema](../../media/mtp-eval-65.png)

10. <span data-ttu-id="620ed-237">Copie el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="620ed-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Image of_command prompt donde debe copiar el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo](../../media/mtp-eval-66.png)

11. <span data-ttu-id="620ed-239">Seleccione **empezar a usar ATP de Microsoft defender** desde el asistente.</span><span class="sxs-lookup"><span data-stu-id="620ed-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>

    ![Imagen of_the mensaje de confirmación del asistente donde debe hacer clic en empezar a usar ATP de Microsoft defender](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="620ed-241">Visite el [centro de seguridad de Microsoft defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="620ed-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="620ed-242">Vaya a **configuración** y, a continuación, seleccione **características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="620ed-242">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Menú de configuración del centro de seguridad de imágenes of_Microsoft defender donde debe seleccionar características avanzadas](../../media/mtp-eval-68.png)

13. <span data-ttu-id="620ed-244">Active la integración con la **protección contra amenazas avanzada de Azure**.</span><span class="sxs-lookup"><span data-stu-id="620ed-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  

    ![Características avanzadas del centro de seguridad de imágenes of_Microsoft defender, opción de protección contra amenazas avanzada de Azure para alternar que debe activar](../../media/mtp-eval-69.png)

14. <span data-ttu-id="620ed-246">Active la integración con la **inteligencia sobre amenazas de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="620ed-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Características avanzadas del centro de seguridad de imágenes of_Microsoft defender, Office 365 Threat Intelligence opción para alternar la activación](../../media/mtp-eval-70.png)

15. <span data-ttu-id="620ed-248">Active la integración con **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="620ed-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft defender Security Center Advanced Security Features, Microsoft Cloud App Security opción alternar la activación](../../media/mtp-eval-71.png)

16. <span data-ttu-id="620ed-250">Desplácese hacia abajo y haga clic en **Guardar preferencias** para confirmar las nuevas integraciones.</span><span class="sxs-lookup"><span data-stu-id="620ed-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Botón de preferencias de of_Save de imagen en el que debe hacer clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a><span data-ttu-id="620ed-252">Iniciar el servicio de Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="620ed-252">Start the Microsoft Threat Protection service</span></span>

>[!NOTE]
><span data-ttu-id="620ed-253">A partir del 1 de junio de 2020, Microsoft habilita automáticamente las características de protección contra amenazas de Microsoft para todos los inquilinos elegibles.</span><span class="sxs-lookup"><span data-stu-id="620ed-253">Starting June 1, 2020, Microsoft automatically enables Microsoft Threat Protection features for all eligible tenants.</span></span> <span data-ttu-id="620ed-254">Consulte este [artículo de la comunidad tecnológica de Microsoft sobre la elegibilidad de licencias](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="620ed-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="620ed-255">Vaya al [centro de seguridad 365 de Microsoft](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="620ed-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="620ed-256">Vaya a **configuración** y, a continuación, seleccione **protección contra amenazas de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="620ed-256">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>

![<span data-ttu-id="620ed-257">Imagen of_Microsoft captura de pantalla de la opción de protección contra amenazas de la página Configuración del centro de seguridad 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="620ed-257">Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="620ed-258">Para obtener una guía más completa, consulte [activar la protección contra amenazas de Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="620ed-258">For a more comprehensive guidance, see [Turn on Microsoft Threat Protection](mtp-enable.md).</span></span> 

<span data-ttu-id="620ed-259">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="620ed-259">Congratulations!</span></span> <span data-ttu-id="620ed-260">Acaba de crear su entorno de prueba de Microsoft Threat Protection o un entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="620ed-260">You've just created your Microsoft Threat Protection trial lab or pilot environment!</span></span> <span data-ttu-id="620ed-261">Ahora puede familiarizarse con la interfaz de usuario de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="620ed-261">Now you can familiarize yourself with the Microsoft Threat Protection user interface!</span></span> <span data-ttu-id="620ed-262">Vea lo que puede aprender de la siguiente guía interactiva de Microsoft Threat Protection y sepa cómo usar cada panel para las tareas de la operación de seguridad diaria.</span><span class="sxs-lookup"><span data-stu-id="620ed-262">See what you can learn from the following Microsoft Threat Protection interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="620ed-263">A continuación, puede simular un ataque y ver cómo las capacidades cruzadas del producto detectan, crean alertas y responden automáticamente a un ataque de archivos no deseados en un extremo.</span><span class="sxs-lookup"><span data-stu-id="620ed-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="620ed-264">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="620ed-264">Next step</span></span>
|<span data-ttu-id="620ed-265">![Fase de simulación de ataques](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="620ed-265">![Attack simulation phase](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="620ed-266">Fase de simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="620ed-266">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="620ed-267">Ejecute la simulación de ataques para su entorno piloto de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="620ed-267">Run the attack simulation for your Microsoft Threat Protection pilot environment.</span></span>
|:-------|:-----|
