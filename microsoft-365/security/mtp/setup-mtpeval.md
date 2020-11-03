---
title: Configurar el entorno piloto o el laboratorio de prueba de Microsoft 365 defender
description: Obtenga acceso al centro de seguridad 365 de Microsoft y, a continuación, configure el entorno de prueba de Microsoft 365 defender
keywords: Programa de instalación de Microsoft Threat Protection Trial, Microsoft Threat Protection Pilot Setup, pruebe Microsoft Threat Protection, instalación del laboratorio de evaluación de Microsoft Threat Protection
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
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 47f4ceeebd50784b1880a028ebe2698012c406da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844829"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="da089-104">Configurar el entorno del laboratorio de prueba de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="da089-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="da089-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="da089-105">**Applies to:**</span></span>
- <span data-ttu-id="da089-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="da089-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="da089-107">La creación de un entorno de prueba de Microsoft 365 defender o un entorno piloto y su implementación es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="da089-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Preparar el entorno piloto o el laboratorio de evaluación de Microsoft 365 defender" />
      <br/><span data-ttu-id="da089-109">Fase 1: preparación </a></span><span class="sxs-lookup"><span data-stu-id="da089-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Configurar el entorno piloto o el laboratorio de prueba de Microsoft 365 defender" />
      <br/><span data-ttu-id="da089-111">Fase 2: configuración </a></span><span class="sxs-lookup"><span data-stu-id="da089-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints" title="
Configure cada pilar de Microsoft 365 defender para su laboratorio de prueba de Microsoft 365 defender o entorno piloto y incorpore los puntos de conexión." />
      <br/><span data-ttu-id="da089-113">Fase 3: configurar & incorporado </a></span><span class="sxs-lookup"><span data-stu-id="da089-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="da089-114">Actualmente está en la fase de configuración.</span><span class="sxs-lookup"><span data-stu-id="da089-114">You're currently in the set up phase.</span></span> <span data-ttu-id="da089-115">Siga los pasos iniciales para acceder al centro de seguridad 365 de Microsoft y, a continuación, configure el entorno de prueba o el entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="da089-115">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="da089-116">Regístrese para obtener una suscripción de Office 365 o Azure Active Directory para generar un inquilino *. onmicrosoft.com* que puede usar para registrarse en su licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="da089-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="da089-117">Si ya tiene una suscripción a Office 365 o Azure Active Directory existente, puede omitir los pasos de creación del inquilino de prueba de Office 365 E5 o piloto.</span><span class="sxs-lookup"><span data-stu-id="da089-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="da089-118">En esta fase, se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="da089-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="da089-119">Crear un inquilino de prueba de Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="da089-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="da089-120">Habilitar la suscripción de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da089-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="da089-121">Crear un inquilino de prueba de Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="da089-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="da089-122">Si ya tiene una suscripción a Office 365 o Azure Active Directory existente, puede omitir los pasos de creación de inquilinos de prueba de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="da089-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="da089-123">Vaya al [portal de producto de Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) y seleccione **prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="da089-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Página de prueba gratuita de Image of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="da089-125">Para completar el registro de prueba, escriba su dirección de correo electrónico (personal o Corporate).</span><span class="sxs-lookup"><span data-stu-id="da089-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="da089-126">Haga clic en **configurar cuenta**.</span><span class="sxs-lookup"><span data-stu-id="da089-126">Click **Set up account**.</span></span>

   ![Página de configuración de registro de prueba de of_Office de Image 365 E5](../../media/mtp-eval-10.png)

3. <span data-ttu-id="da089-128">Escriba su nombre, apellidos, número de teléfono del trabajo, nombre de la compañía, tamaño de la compañía y país o región.</span><span class="sxs-lookup"><span data-stu-id="da089-128">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Página de configuración del registro de prueba de of_Office de la imagen de 365 E5 que solicita el nombre, el teléfono y los detalles de la compañía](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="da089-130">El país o la región que establezca aquí determina la región del centro de datos donde se hospedará Office 365.</span><span class="sxs-lookup"><span data-stu-id="da089-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="da089-131">Elija su preferencia de comprobación: mediante un mensaje de texto o una llamada.</span><span class="sxs-lookup"><span data-stu-id="da089-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="da089-132">Haga clic en **Enviar código de verificación**.</span><span class="sxs-lookup"><span data-stu-id="da089-132">Click **Send Verification Code**.</span></span> 

   ![Página de configuración del registro de prueba de of_Office de imagen de 365 E5 que solicita preferencia de comprobación](../../media/mtp-eval-12.png)

5. <span data-ttu-id="da089-134">Establezca el nombre de dominio personalizado para el inquilino y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da089-134">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Página de configuración de registro de prueba de 365 E5 de Image of_Office E5, donde puede configurar su nombre de dominio personalizado](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="da089-136">Configure la primera identidad, que será un administrador global del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="da089-136">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="da089-137">Escriba un **nombre** y una **contraseña**.</span><span class="sxs-lookup"><span data-stu-id="da089-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="da089-138">Haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="da089-138">Click **Sign up**.</span></span>

   ![Página de configuración de registro de prueba de 365 E5 de Image of_Office E5, donde puede configurar la identidad de la empresa](../../media/mtp-eval-14.png)

7. <span data-ttu-id="da089-140">Haga clic en **ir al programa de instalación** para completar el aprovisionamiento de inquilino de prueba de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="da089-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Imagen de la página de configuración del registro de prueba de Office 365 E5 solicitando hacer clic en el botón de configuración de Go](../../media/mtp-eval-15.png)

8. <span data-ttu-id="da089-142">Conecte el dominio corporativo al inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="da089-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="da089-143">Opcional Elija **conectar un dominio que ya posee** y escriba el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="da089-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="da089-144">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da089-144">Click **Next**.</span></span>

   ![Página de instalación de Image of_Office 365 E5 donde debe personalizar el inicio de sesión y el correo electrónico](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="da089-146">Agregue un registro TXT o MX para validar la propiedad del dominio.</span><span class="sxs-lookup"><span data-stu-id="da089-146">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="da089-147">Una vez que haya agregado el registro TXT o MX a su dominio, seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="da089-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Página de instalación de Image of_Office 365 E5 donde debe agregar un TXT del registro MX para comprobar su dominio](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="da089-149">Opcional Cree más cuentas de usuario para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="da089-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="da089-150">Puede omitir este paso haciendo clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da089-150">You can skip this step by clicking **Next**.</span></span>

    ![Página de instalación de Image of_Office 365 E5 donde puede agregar más usuarios](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="da089-152">Opcional Descargue las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="da089-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="da089-153">Haga clic en **siguiente** para omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="da089-153">Click **Next** to skip this step.</span></span> 

    ![Página de imagen of_Office 365 E5 donde puede instalar las aplicaciones de Office](../../media/mtp-eval-19.png)

12. <span data-ttu-id="da089-155">Opcional Migrar mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="da089-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="da089-156">De nuevo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="da089-156">Again, you can skip this step.</span></span>

    ![Image of_Office 365 E5 donde puede establecer si desea migrar los mensajes de correo electrónico o no.](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="da089-158">Elija servicios en línea.</span><span class="sxs-lookup"><span data-stu-id="da089-158">Choose online services.</span></span> <span data-ttu-id="da089-159">Seleccione **Exchange** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da089-159">Select **Exchange** and click **Next**.</span></span> 

    ![Image of_Office 365 E5 donde puede elegir sus servicios en línea](../../media/mtp-eval-21.png)

14. <span data-ttu-id="da089-161">Agregue los registros MX, CNAME y TXT a su dominio.</span><span class="sxs-lookup"><span data-stu-id="da089-161">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="da089-162">Una vez completada, seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="da089-162">When completed, select **Verify**.</span></span>

    ![Image of_Office 365 E5 aquí puede agregar sus registros DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="da089-164">Enhorabuena, ha completado el aprovisionamiento de su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="da089-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Página de confirmación de finalización de la instalación de Image of_Office 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="da089-166">Habilitar la suscripción de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da089-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="da089-167">Al registrarse para obtener una prueba, se le da 25 licencias de usuario para usarla durante un mes.</span><span class="sxs-lookup"><span data-stu-id="da089-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="da089-168">Consulte [probar o comprar una suscripción a M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="da089-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="da089-169">En [centro de administración de 365 de Microsoft](https://admin.microsoft.com/), haga clic en **facturación** y navegue a **servicios de compra**.</span><span class="sxs-lookup"><span data-stu-id="da089-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="da089-170">Seleccione **Microsoft 365 E5** y haga clic en **iniciar prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="da089-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Página de prueba de inicio gratuito de Image of_Microsoft 365 E5](../../media/mtp-eval-24.png)

3. <span data-ttu-id="da089-172">Elija su preferencia de comprobación: mediante un mensaje de texto o una llamada.</span><span class="sxs-lookup"><span data-stu-id="da089-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="da089-173">Una vez que haya decidido, escriba el número de teléfono, seleccione **texto me** o **llámeme** en función de la selección.</span><span class="sxs-lookup"><span data-stu-id="da089-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 página de prueba gratuita de inicio para solicitar detalles de contacto para enviar código para demostrar que no es un robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="da089-175">Escriba el código de verificación y haga clic en **iniciar la versión de prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="da089-175">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 página de prueba gratuita de inicio, donde puede rellenar el código de verificación que el sistema ha enviado para demostrar que no es un robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="da089-177">Haga clic en **probar ahora** para confirmar la prueba de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="da089-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Página de prueba de inicio gratuita de Image of_Microsoft 365 E5 donde debe entrar en el botón probar ahora para iniciar](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="da089-179">Vaya a los usuarios activos del **centro de administración de Microsoft 365**  >  **Users**  >  **Active users**.</span><span class="sxs-lookup"><span data-stu-id="da089-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="da089-180">Seleccione su cuenta de usuario, seleccione **administrar licencias de producto** y, a continuación, intercambie la licencia de Office 365 E5 a **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="da089-180">Select your user account, select **Manage product licenses** , then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="da089-181">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="da089-181">Click **Save**.</span></span>

   ![Imagen of_Microsoft 365 página del centro de administración donde puede seleccionar la licencia de Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="da089-183">Seleccione la cuenta de administrador global de nuevo y haga clic en **administrar nombre de usuario**.</span><span class="sxs-lookup"><span data-stu-id="da089-183">Select the global administrator account again then click **Manage username**.</span></span>

   ![Imagen of_Microsoft 365 página del centro de administración donde puede seleccionar cuenta y, a continuación, administrar el nombre de usuario](../../media/mtp-eval-29.png)

8. <span data-ttu-id="da089-185">Opcional Cambie el dominio de *onmicrosoft.com* a su propio dominio, en función de lo que elija en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="da089-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="da089-186">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="da089-186">Click **Save changes**.</span></span>

   ![Imagen of_Microsoft 365 página del centro de administración donde puede cambiar su preferencia de dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="da089-188">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="da089-188">Next step</span></span>
|<span data-ttu-id="da089-189">![Fase 3: configurar & incorporado](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="da089-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="da089-190">Fase 3: configurar & incorporado</span><span class="sxs-lookup"><span data-stu-id="da089-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="da089-191">Configure cada pilar de Microsoft 365 defender para su laboratorio de prueba de Microsoft 365 defender o entorno piloto y incorpore los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="da089-191">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
