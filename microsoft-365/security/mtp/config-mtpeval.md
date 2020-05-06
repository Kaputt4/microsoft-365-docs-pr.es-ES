---
title: Configurar los pilares de la protección contra amenazas de Microsoft para el entorno de pruebas de prueba
description: Configurar los pilares de la protección contra amenazas de Microsoft, Office 365 ATP, Azure ATP, Microsoft Cloud App Security y Microsoft defender ATP para su entorno de laboratorio de prueba
keywords: configurar Microsoft Threat Protection prueba, configuración de prueba de protección contra amenazas de Microsoft, configurar los pilares de la protección contra amenazas de Microsoft, pilares de la protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049514"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="0e563-104">Configurar los pilares de la protección contra amenazas de Microsoft para el entorno de pruebas de prueba</span><span class="sxs-lookup"><span data-stu-id="0e563-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="0e563-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0e563-105">**Applies to:**</span></span>
- <span data-ttu-id="0e563-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0e563-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="0e563-107">La creación de un entorno de laboratorio de prueba de Microsoft Threat Protection y su implementación es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="0e563-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparar el entorno de laboratorio de prueba de Microsoft Threat Protection" />
      <br/><span data-ttu-id="0e563-109">Fase 1: preparación</a></span><span class="sxs-lookup"><span data-stu-id="0e563-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar el entorno de laboratorio de prueba de Microsoft Threat Protection" />
      <br/><span data-ttu-id="0e563-111">Fase 2: configuración</a></span><span class="sxs-lookup"><span data-stu-id="0e563-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurar cada pilar de protección contra amenazas de Microsoft para el entorno de laboratorio de prueba de Microsoft Threat Protection y los puntos de conexión incorporados" />
      <br/><span data-ttu-id="0e563-113">Fase 3: configurar & incorporado</a></span><span class="sxs-lookup"><span data-stu-id="0e563-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="0e563-114">Actualmente se encuentra en la fase de configuración.</span><span class="sxs-lookup"><span data-stu-id="0e563-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="0e563-115">La preparación es fundamental para todas las implementaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="0e563-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="0e563-116">En este artículo, se le guiará en los puntos que necesitará tener en cuenta a la hora de prepararse para implementar ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="0e563-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="0e563-117">Pilares de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0e563-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="0e563-118">La protección contra amenazas de Microsoft consta de cuatro pilares.</span><span class="sxs-lookup"><span data-stu-id="0e563-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="0e563-119">Aunque un pilar ya puede proporcionar valor a la seguridad de su organización de red, la habilitación de los cuatro pilares de la protección contra amenazas de Microsoft dará mayor valor a su organización.</span><span class="sxs-lookup"><span data-stu-id="0e563-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![Of_page de imagen](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="0e563-121">Esta sección le guiará para configurar:</span><span class="sxs-lookup"><span data-stu-id="0e563-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="0e563-122">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="0e563-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="0e563-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0e563-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="0e563-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0e563-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="0e563-125">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0e563-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="0e563-126">Configuración de la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="0e563-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="0e563-127">Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e563-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="0e563-128">Hay un módulo de PowerShell denominado analizador de configuración de la *protección contra amenazas avanzada de Office 365 (Orca)* que ayuda a determinar algunas de estas opciones.</span><span class="sxs-lookup"><span data-stu-id="0e563-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="0e563-129">Cuando se ejecuta como administrador en su espacio empresarial, Get-ORCAReport le ayudará a generar una evaluación de la configuración de protección contra correo electrónico no deseado, anti-phish y otros mensajes.</span><span class="sxs-lookup"><span data-stu-id="0e563-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="0e563-130">Puede descargar este módulo desde https://www.powershellgallery.com/packages/ORCA/.</span><span class="sxs-lookup"><span data-stu-id="0e563-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="0e563-131">Vaya a la**Directiva**de**Administración** > de amenazas [& cumplimiento del centro](https://protection.office.com/homepage) > de cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e563-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="0e563-132">![Of_page de imagen](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-132">![Image of_page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="0e563-133">Haga clic en **anti-phishing ATP**, seleccione **crear** y rellene el nombre y la descripción de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="0e563-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="0e563-134">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0e563-134">Click **Next**.</span></span>
<span data-ttu-id="0e563-135">![Of_page de imagen](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-135">![Image of_page](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="0e563-136">Edite la Directiva antiphishing de ATP avanzada.</span><span class="sxs-lookup"><span data-stu-id="0e563-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="0e563-137">Cambiar el **umbral de suplantación de identidad avanzado** a **2-agresivo**.</span><span class="sxs-lookup"><span data-stu-id="0e563-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="0e563-138">Haga clic en el menú desplegable **Agregar condición** y seleccione su dominio o dominios como dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="0e563-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="0e563-139">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0e563-139">Click **Next**.</span></span>
<span data-ttu-id="0e563-140">![Of_page de imagen](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-140">![Image of_page](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="0e563-141">Revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="0e563-141">Review your settings.</span></span> <span data-ttu-id="0e563-142">Haga clic en **crear esta directiva** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="0e563-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="0e563-143">![Of_page de imagen](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-143">![Image of_page](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="0e563-144">Seleccione **datos adjuntos seguros de ATP** y seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="0e563-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="0e563-145">![Of_page de imagen](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-145">![Image of_page](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="0e563-146">Haga clic en el icono + para crear una nueva Directiva de datos adjuntos seguros, aplíquela como dominio del destinatario en sus dominios.</span><span class="sxs-lookup"><span data-stu-id="0e563-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="0e563-147">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e563-147">Click **Save**.</span></span>
<span data-ttu-id="0e563-148">![Of_page de imagen](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-148">![Image of_page](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="0e563-149">A continuación, seleccione la Directiva de **vínculos seguros ATP** y haga clic en el icono de lápiz para editar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0e563-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="0e563-150">Asegúrese de que la opción no **realizar seguimiento cuando los usuarios hagan clic en vínculos seguros** no esté seleccionada, mientras que el resto de las opciones están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="0e563-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="0e563-151">Vea [configuración de vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0e563-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="0e563-152">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e563-152">Click **Save**.</span></span> 
<span data-ttu-id="0e563-153">![Of_page de imagen](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-153">![Image of_page](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="0e563-154">A continuación, seleccione la directiva **antimalware** , seleccione la opción predeterminada y elija el icono de lápiz.</span><span class="sxs-lookup"><span data-stu-id="0e563-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="0e563-155">Haga clic en **configuración** y seleccione **sí y use el texto de notificación predeterminado** para habilitar la **respuesta de detección de malware**.</span><span class="sxs-lookup"><span data-stu-id="0e563-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="0e563-156">Active el **filtro tipos de datos adjuntos comunes** en.</span><span class="sxs-lookup"><span data-stu-id="0e563-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="0e563-157">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e563-157">Click **Save**.</span></span>
<br><span data-ttu-id="0e563-158">![Of_page de imagen](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-158">![Image of_page](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="0e563-159">Vaya a [Office 365 Security & cumplimiento del centro](https://protection.office.com/homepage) > **Search** > de**Auditoría** búsqueda y active la auditoría.</span><span class="sxs-lookup"><span data-stu-id="0e563-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="0e563-160">![Of_page de imagen](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-160">![Image of_page](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="0e563-161">Integrar Office 365 ATP con Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="0e563-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="0e563-162">Vaya a [Office 365 Security & cumplimiento del centro](https://protection.office.com/homepage) > de**Administración** > **de amenazas y seleccione** **WDATP configuración** en la esquina superior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="0e563-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="0e563-163">En el cuadro de diálogo conexión ATP de Microsoft defender, Active **conectarse a ATP de Windows**.</span><span class="sxs-lookup"><span data-stu-id="0e563-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="0e563-164">![Of_page de imagen](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-164">![Image of_page](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="0e563-165">Configurar la protección contra amenazas avanzada de Azure</span><span class="sxs-lookup"><span data-stu-id="0e563-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="0e563-166">Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Azure</span><span class="sxs-lookup"><span data-stu-id="0e563-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="0e563-167">Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info) > seleccione **más recursos** > **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="0e563-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="0e563-168">![Of_page de imagen](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-168">![Image of_page](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="0e563-169">Haga clic en **crear** para iniciar el Asistente de Azure Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="0e563-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="0e563-170">![Of_page de imagen](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-170">![Image of_page](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="0e563-171">Elija **proporcionar un nombre de usuario y una contraseña para conectar con el bosque de Active**Directory.</span><span class="sxs-lookup"><span data-stu-id="0e563-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="0e563-172">![Of_page de imagen](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-172">![Image of_page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="0e563-173">Escriba sus credenciales locales de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0e563-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="0e563-174">Puede ser cualquier cuenta de usuario que tenga acceso de lectura a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0e563-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="0e563-175">![Of_page de imagen](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-175">![Image of_page](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="0e563-176">A continuación, seleccione **descargar la configuración del sensor** y transferir el archivo a su controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="0e563-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="0e563-177">![Of_page de imagen](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-177">![Image of_page](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="0e563-178">Ejecute la configuración del sensor ATP de Azure y comience a seguir el asistente.</span><span class="sxs-lookup"><span data-stu-id="0e563-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="0e563-179">![Of_page de imagen](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-179">![Image of_page](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="0e563-180">Haga clic en **siguiente** en el tipo de implementación de sensor.</span><span class="sxs-lookup"><span data-stu-id="0e563-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="0e563-181">![Of_page de imagen](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-181">![Image of_page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="0e563-182">Copie la clave de acceso, ya que tendrá que escribirla a continuación en el asistente.</span><span class="sxs-lookup"><span data-stu-id="0e563-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="0e563-183">![Of_page de imagen](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-183">![Image of_page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="0e563-184">Copie la clave de acceso en el asistente y haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="0e563-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="0e563-185">![Of_page de imagen](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-185">![Image of_page](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="0e563-186">Enhorabuena, ha configurado correctamente la protección contra amenazas avanzada de Azure en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="0e563-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="0e563-187">![Of_page de imagen](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-187">![Image of_page](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="0e563-188">En la sección configuración de ATP de Azure [Azure](https://go.microsoft.com/fwlink/?linkid=2040449) , seleccione **ATP de Windows Defender**y, a continuación, cambie el botón de alternancia a.</span><span class="sxs-lookup"><span data-stu-id="0e563-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="0e563-189">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e563-189">Click **Save**.</span></span> 
<span data-ttu-id="0e563-190">![Of_page de imagen](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-190">![Image of_page](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="0e563-191">Windows Defender ATP ha cambiado de marca como ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="0e563-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="0e563-192">Los cambios de personalización de marca en todos nuestros portales se están implementando para lograr coherencia.</span><span class="sxs-lookup"><span data-stu-id="0e563-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="0e563-193">Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0e563-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="0e563-194">Omita este paso si ya ha habilitado Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="0e563-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="0e563-195">Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info) > **más recursos** > **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="0e563-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="0e563-196">![Of_page de imagen](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-196">![Image of_page](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="0e563-197">En la solicitud de información para integrar ATP de Azure, seleccione **Habilitar la integración de datos de ATP de Azure**.</span><span class="sxs-lookup"><span data-stu-id="0e563-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="0e563-198">![Of_page de imagen](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-198">![Image of_page](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="0e563-199">Si no aparece este mensaje, puede significar que ya se ha habilitado la integración de datos de ATP de Azure.</span><span class="sxs-lookup"><span data-stu-id="0e563-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="0e563-200">Sin embargo, si no está seguro, póngase en contacto con su administrador de TI para confirmarlo.</span><span class="sxs-lookup"><span data-stu-id="0e563-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="0e563-201">Vaya a **configuración**, active la opción de alternancia de **Azure ATP Integration** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e563-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="0e563-202">![Of_page de imagen](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-202">![Image of_page](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="0e563-203">Para las nuevas instancias de ATP de Azure, este cambio de integración se activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0e563-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="0e563-204">Confirme que la integración de ATP de Azure se haya habilitado antes de continuar con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e563-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="0e563-205">En la configuración de detección en la nube, seleccione **integración de Microsoft defender ATP**y, a continuación, habilite la integración.</span><span class="sxs-lookup"><span data-stu-id="0e563-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="0e563-206">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e563-206">Click **Save**.</span></span>
<span data-ttu-id="0e563-207">![Of_page de imagen](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-207">![Image of_page](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="0e563-208">En configuración de detección en la nube, seleccione **enriquecimiento de usuario**y, a continuación, habilite la integración con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0e563-208">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="0e563-209">![Of_page de imagen](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-209">![Image of_page](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="0e563-210">Configurar la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="0e563-210">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="0e563-211">Omita este paso si ya ha habilitado la protección contra amenazas avanzada de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="0e563-211">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="0e563-212">Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info) > **más recursos** > **centro de seguridad de Microsoft defender**.</span><span class="sxs-lookup"><span data-stu-id="0e563-212">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="0e563-213">Haga clic en **Open** (Abrir).</span><span class="sxs-lookup"><span data-stu-id="0e563-213">Click **Open**.</span></span>
<br><span data-ttu-id="0e563-214">![Of_page de imagen](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-214">![Image of_page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="0e563-215">Siga el Asistente para la protección contra amenazas avanzada de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="0e563-215">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="0e563-216">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0e563-216">Click **Next**.</span></span> 
<br><span data-ttu-id="0e563-217">![Of_page de imagen](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-217">![Image of_page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="0e563-218">Elija en función de la ubicación de almacenamiento de datos preferida, la Directiva de retención de datos, el tamaño de la organización y las características de vista previa.</span><span class="sxs-lookup"><span data-stu-id="0e563-218">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="0e563-219">![Of_page de imagen](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-219">![Image of_page](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="0e563-220">No puede cambiar algunos de los valores, como la ubicación de almacenamiento de datos, más adelante.</span><span class="sxs-lookup"><span data-stu-id="0e563-220">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="0e563-221">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0e563-221">Click **Next**.</span></span> 

4. <span data-ttu-id="0e563-222">Haga clic en **continuar** y se aprovisionará el inquilino ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="0e563-222">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="0e563-223">![Of_page de imagen](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-223">![Image of_page](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="0e563-224">Incorpore los puntos de conexión a través de directivas de grupo, Microsoft Endpoint Manager o mediante la ejecución de un script local a ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="0e563-224">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="0e563-225">Para simplificar, esta guía usa el script local.</span><span class="sxs-lookup"><span data-stu-id="0e563-225">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="0e563-226">Haga clic en **Descargar paquete** y copie el script de incorporación en los extremos.</span><span class="sxs-lookup"><span data-stu-id="0e563-226">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="0e563-227">![Of_page de imagen](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-227">![Image of_page](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="0e563-228">En el punto de conexión, ejecute el script de incorporación como administrador y elija Y.</span><span class="sxs-lookup"><span data-stu-id="0e563-228">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="0e563-229">![Of_page de imagen](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-229">![Image of_page](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="0e563-230">Enhorabuena, ha incorporado el primer punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0e563-230">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![Of_page de imagen](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="0e563-232">Copie-pegue la prueba de detección desde el Asistente para ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="0e563-232">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="0e563-233">![Of_page de imagen](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-233">![Image of_page](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="0e563-234">Copie el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="0e563-234">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="0e563-235">![Of_page de imagen](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-235">![Image of_page](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="0e563-236">Seleccione **empezar a usar ATP de Microsoft defender** desde el asistente.</span><span class="sxs-lookup"><span data-stu-id="0e563-236">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="0e563-237">![Of_page de imagen](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-237">![Image of_page](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="0e563-238">Visite el [centro de seguridad de Microsoft defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="0e563-238">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="0e563-239">Vaya a **configuración** y, a continuación, seleccione **características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="0e563-239">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="0e563-240">![Of_page de imagen](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-240">![Image of_page](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="0e563-241">Active la integración con la **protección contra amenazas avanzada de Azure**.</span><span class="sxs-lookup"><span data-stu-id="0e563-241">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="0e563-242">![Of_page de imagen](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-242">![Image of_page](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="0e563-243">Active la integración con la **inteligencia sobre amenazas de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="0e563-243">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="0e563-244">![Of_page de imagen](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-244">![Image of_page](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="0e563-245">Active la integración con **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="0e563-245">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="0e563-246">![Of_page de imagen](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-246">![Image of_page](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="0e563-247">Desplácese hacia abajo y haga clic en **Guardar preferencias** para confirmar las nuevas integraciones.</span><span class="sxs-lookup"><span data-stu-id="0e563-247">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="0e563-248">![Of_page de imagen](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="0e563-248">![Image of_page](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="next-steps"></a><span data-ttu-id="0e563-249">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0e563-249">Next steps</span></span>
<span data-ttu-id="0e563-250">[Active la protección contra amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) y, a continuación, [genere una alerta de prueba](generate-test-alert.md).</span><span class="sxs-lookup"><span data-stu-id="0e563-250">[Turn on Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) and then [generate a test alert](generate-test-alert.md).</span></span>
