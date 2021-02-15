---
title: Configurar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender
description: Obtenga acceso al Centro de seguridad de Microsoft 365 y configure su entorno de laboratorio de prueba de Microsoft 365 Defender
keywords: Configuración de prueba de Protección contra amenazas de Microsoft, configuración piloto de Protección contra amenazas de Microsoft, probar Protección contra amenazas de Microsoft, configuración del laboratorio de evaluación de Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932987"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="e7085-104">Configurar el entorno de laboratorio de prueba de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7085-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e7085-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e7085-105">**Applies to:**</span></span>
- <span data-ttu-id="e7085-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7085-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="e7085-107">Crear un entorno piloto o laboratorio de prueba de Microsoft 365 Defender e implementarlo es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="e7085-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="e7085-108">[![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="e7085-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="e7085-109">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="e7085-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![Fase 2: Configurar](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="e7085-111">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="e7085-111">Phase 2: Set up</span></span> |<span data-ttu-id="e7085-112">[![Fase 3: Incorporación](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="e7085-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="e7085-113">Fase 3: Incorporación</span><span class="sxs-lookup"><span data-stu-id="e7085-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="e7085-114">[![Volver al piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="e7085-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="e7085-115">Volver al libro de reproducción piloto</span><span class="sxs-lookup"><span data-stu-id="e7085-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="e7085-116">*¡Estás aquí!*</span><span class="sxs-lookup"><span data-stu-id="e7085-116">*You are here!*</span></span>  | | |


<span data-ttu-id="e7085-117">Actualmente está en la fase de configuración.</span><span class="sxs-lookup"><span data-stu-id="e7085-117">You're currently in the set up phase.</span></span> <span data-ttu-id="e7085-118">Siga los pasos iniciales para acceder al Centro de seguridad de Microsoft 365 y, a continuación, configure el entorno de prueba o piloto.</span><span class="sxs-lookup"><span data-stu-id="e7085-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="e7085-119">Regístrese para obtener una suscripción a Office 365 o Azure Active Directory para generar un inquilino *.onmicrosoft.com* que puede usar para registrarse en su licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e7085-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="e7085-120">Si ya tiene una suscripción existente de Office 365 o Azure Active Directory, puede omitir los pasos de creación de inquilinos piloto o de prueba de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e7085-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="e7085-121">En esta fase, se te guiará a:</span><span class="sxs-lookup"><span data-stu-id="e7085-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="e7085-122">Crear un inquilino de prueba de Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e7085-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="e7085-123">Habilitar la suscripción de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7085-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="e7085-124">Crear un inquilino de prueba de Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e7085-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="e7085-125">Si ya tiene una suscripción existente de Office 365 o Azure Active Directory, puede omitir los pasos de creación de inquilinos de prueba de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e7085-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="e7085-126">Vaya al [portal de productos de Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) y seleccione Prueba **gratuita.**</span><span class="sxs-lookup"><span data-stu-id="e7085-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Imagen of_Office de prueba gratuita 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="e7085-128">Complete el registro de prueba especificando su dirección de correo electrónico (personal o corporativa).</span><span class="sxs-lookup"><span data-stu-id="e7085-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="e7085-129">Haga clic **en Configurar cuenta.**</span><span class="sxs-lookup"><span data-stu-id="e7085-129">Click **Set up account**.</span></span>

   ![Página de of_Office configuración de registro de prueba de 365 E5](../../media/mtp-eval-10.png)

3. <span data-ttu-id="e7085-131">Rellene el nombre, los apellidos, el número de teléfono de la empresa, el nombre de la compañía, el tamaño de la compañía y el país o región.</span><span class="sxs-lookup"><span data-stu-id="e7085-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Imagen of_Office página de configuración de registro de prueba de 365 E5 que solicita el nombre, el teléfono y los detalles de la empresa](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="e7085-133">El país o la región que establezca aquí determina la región del centro de datos en la que se hospedará Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7085-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="e7085-134">Elija su preferencia de verificación: a través de un mensaje de texto o una llamada.</span><span class="sxs-lookup"><span data-stu-id="e7085-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="e7085-135">Haga clic **en Enviar código de verificación.**</span><span class="sxs-lookup"><span data-stu-id="e7085-135">Click **Send Verification Code**.</span></span> 

   ![Imagen of_Office página de configuración de registro de prueba de 365 E5 que solicita la preferencia de verificación](../../media/mtp-eval-12.png)

5. <span data-ttu-id="e7085-137">Establezca el nombre de dominio personalizado para su inquilino y, a continuación, haga clic **en Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="e7085-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Página of_Office configuración de registro de prueba de 365 E5 en la que puede configurar el nombre de dominio personalizado](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="e7085-139">Configure la primera identidad, que será un administrador global del inquilino.</span><span class="sxs-lookup"><span data-stu-id="e7085-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="e7085-140">Rellene el **nombre y** la **contraseña.**</span><span class="sxs-lookup"><span data-stu-id="e7085-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="e7085-141">Haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="e7085-141">Click **Sign up**.</span></span>

   ![Página of_Office configuración de registro de prueba de 365 E5 en la que puede establecer su identidad empresarial](../../media/mtp-eval-14.png)

7. <span data-ttu-id="e7085-143">Haga **clic en Ir al programa de** instalación para completar el aprovisionamiento de inquilinos de prueba de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e7085-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Imagen de la página de configuración del registro de prueba de Office 365 E5 en la que se le pide que haga clic en el botón Ir a la instalación](../../media/mtp-eval-15.png)

8. <span data-ttu-id="e7085-145">Conecte su dominio corporativo al inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7085-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="e7085-146">[Opcional] Elija **Conectar un dominio que ya posee** y escriba su nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="e7085-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="e7085-147">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7085-147">Click **Next**.</span></span>

   ![Imagen of_Office página de instalación de 365 E5 donde debe personalizar el inicio de sesión y el correo electrónico](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="e7085-149">Agregue un registro TXT o MX para validar la propiedad del dominio.</span><span class="sxs-lookup"><span data-stu-id="e7085-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="e7085-150">Una vez que haya agregado el registro TXT o MX a su dominio, seleccione **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="e7085-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Imagen of_Office página de instalación de 365 E5 donde debe agregar un registro TXT de MX para comprobar el dominio](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="e7085-152">[Opcional] Cree más cuentas de usuario para su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="e7085-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="e7085-153">Puede omitir este paso haciendo clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7085-153">You can skip this step by clicking **Next**.</span></span>

    ![Página of_Office configuración de 365 E5 en la que puede agregar más usuarios](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="e7085-155">[Opcional] Descargue las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="e7085-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="e7085-156">Haga **clic en** Siguiente para omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="e7085-156">Click **Next** to skip this step.</span></span> 

    ![Imagen of_Office página 365 E5 donde puede instalar las aplicaciones de Office](../../media/mtp-eval-19.png)

12. <span data-ttu-id="e7085-158">[Opcional] Migrar mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e7085-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="e7085-159">De nuevo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="e7085-159">Again, you can skip this step.</span></span>

    ![Imagen of_Office 365 E5 donde puede establecer si desea migrar mensajes de correo electrónico o no](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="e7085-161">Elija servicios en línea.</span><span class="sxs-lookup"><span data-stu-id="e7085-161">Choose online services.</span></span> <span data-ttu-id="e7085-162">Seleccione **Exchange y** haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="e7085-162">Select **Exchange** and click **Next**.</span></span> 

    ![Imagen of_Office 365 E5 donde puede elegir los servicios en línea](../../media/mtp-eval-21.png)

14. <span data-ttu-id="e7085-164">Agregue registros MX, CNAME y TXT al dominio.</span><span class="sxs-lookup"><span data-stu-id="e7085-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="e7085-165">Cuando se complete, seleccione **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="e7085-165">When completed, select **Verify**.</span></span>

    ![Imagen of_Office 365 E5 aquí puede agregar los registros DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="e7085-167">Enhorabuena, ha completado el aprovisionamiento de su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7085-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Página de of_Office de finalización de instalación de 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="e7085-169">Habilitar la suscripción de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7085-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="e7085-170">Registrarse para obtener una versión de prueba le ofrece 25 licencias de usuario para usarlas durante un mes.</span><span class="sxs-lookup"><span data-stu-id="e7085-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="e7085-171">Consulta [Probar o comprar una suscripción a M365 para](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e7085-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="e7085-172">En el Centro de administración de [Microsoft 365,](https://admin.microsoft.com/)haga clic en **Facturación** y, a continuación, vaya **a Servicios de compra.**</span><span class="sxs-lookup"><span data-stu-id="e7085-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="e7085-173">Seleccione **Microsoft 365 E5 y** haga clic en Iniciar prueba **gratuita.**</span><span class="sxs-lookup"><span data-stu-id="e7085-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Página de of_Microsoft 365 E5 Start free trial](../../media/mtp-eval-24.png)

3. <span data-ttu-id="e7085-175">Elija su preferencia de verificación: a través de un mensaje de texto o una llamada.</span><span class="sxs-lookup"><span data-stu-id="e7085-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="e7085-176">Una vez que lo haya decidido, escriba el número de teléfono, seleccione **Enviarme** texto o **Llamarme** en función de su selección.</span><span class="sxs-lookup"><span data-stu-id="e7085-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Imagen of_Microsoft 365 E5 Página de prueba gratuita que pide detalles de contacto para enviar código para demostrar que no es un robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="e7085-178">Escribe el código de verificación y haz clic **en Iniciar la prueba gratuita.**</span><span class="sxs-lookup"><span data-stu-id="e7085-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Imagen of_Microsoft 365 E5 Página de prueba gratuita en la que puedes rellenar el código de verificación que el sistema envió para demostrar que no eres un robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="e7085-180">Haga **clic en Probar ahora** para confirmar la versión de prueba de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e7085-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Imagen of_Microsoft página de prueba gratuita inicio 365 E5 en la que debería reloj el botón Probar ahora para iniciar](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="e7085-182">Vaya a los usuarios activos del Centro de administración de **Microsoft 365.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="e7085-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="e7085-183">Seleccione su cuenta de usuario, **seleccione** Administrar licencias de producto y, a continuación, cambie la licencia de Office 365 E5 a **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="e7085-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="e7085-184">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e7085-184">Click **Save**.</span></span>

   ![Imagen of_Microsoft página del Centro de administración de 365 donde puede seleccionar la licencia de Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="e7085-186">Vuelva a seleccionar la cuenta de administrador global y, a continuación, haga **clic en Administrar nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="e7085-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Imagen of_Microsoft página del Centro de administración de 365 donde puede seleccionar Cuenta y, a continuación, Administrar nombre de usuario](../../media/mtp-eval-29.png)

8. <span data-ttu-id="e7085-188">[Opcional] Cambie el dominio de *onmicrosoft.com* a su propio dominio, en función de lo que haya elegido en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="e7085-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="e7085-189">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e7085-189">Click **Save changes**.</span></span>

   ![Imagen of_Microsoft página del Centro de administración de 365 donde puede cambiar su preferencia de dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="e7085-191">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e7085-191">Next step</span></span>
|[<span data-ttu-id="e7085-192">Fase 3: Configurar & incorporación</span><span class="sxs-lookup"><span data-stu-id="e7085-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="e7085-193">Configure cada pilar de Microsoft 365 Defender para su entorno piloto o laboratorio de prueba de Microsoft 365 Defender e incorpore los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="e7085-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
