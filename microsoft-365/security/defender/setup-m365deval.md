---
title: Configurar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender
description: Access Microsoft 365 Security Center y, a continuación, configure el entorno de laboratorio de prueba de Microsoft 365 Defender
keywords: Microsoft 365 Configuración de prueba de Defender, Microsoft 365 piloto de Defender, prueba Microsoft 365 Defender, Microsoft 365 laboratorio de evaluación de Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: ae81f6be0a83d5d0141f0f0c8c89f8f2207cc56c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935430"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="63343-104">Configurar el entorno de laboratorio Microsoft 365 prueba de Defender</span><span class="sxs-lookup"><span data-stu-id="63343-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="63343-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="63343-105">**Applies to:**</span></span>
- <span data-ttu-id="63343-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63343-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="63343-107">Crear un Microsoft 365 de prueba de Defender o un entorno piloto e implementarlo es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="63343-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="63343-108">[![Fase 1: Preparación](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="63343-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="63343-109">Fase 1: Preparación</span><span class="sxs-lookup"><span data-stu-id="63343-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |![Fase 2: Configuración](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="63343-111">Fase 2: Configuración</span><span class="sxs-lookup"><span data-stu-id="63343-111">Phase 2: Set up</span></span> |<span data-ttu-id="63343-112">[![Fase 3: Incorporación](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="63343-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span></span><br/>[<span data-ttu-id="63343-113">Fase 3: Incorporación</span><span class="sxs-lookup"><span data-stu-id="63343-113">Phase 3: Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="63343-114">[![Volver al piloto](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="63343-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="63343-115">Volver al libro de reproducción piloto</span><span class="sxs-lookup"><span data-stu-id="63343-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="63343-116">*¡Estás aquí!*</span><span class="sxs-lookup"><span data-stu-id="63343-116">*You are here!*</span></span>  | | |


<span data-ttu-id="63343-117">Actualmente está en la fase de configuración.</span><span class="sxs-lookup"><span data-stu-id="63343-117">You're currently in the set up phase.</span></span> <span data-ttu-id="63343-118">Siga los pasos iniciales para obtener acceso Microsoft 365 centro de seguridad y, a continuación, configure el entorno piloto o el laboratorio de prueba.</span><span class="sxs-lookup"><span data-stu-id="63343-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="63343-119">Registrarse para obtener una suscripción Office 365 o Azure Active Directory para generar un inquilino *.onmicrosoft.com* que pueda usar para registrarse en su Microsoft 365 E5 licencia.</span><span class="sxs-lookup"><span data-stu-id="63343-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="63343-120">Si ya tiene una suscripción Office 365 o Azure Active Directory, puede omitir los pasos de creación de Office 365 prueba o piloto de E5.</span><span class="sxs-lookup"><span data-stu-id="63343-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="63343-121">En esta fase, se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="63343-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="63343-122">Crear un inquilino Office 365 de prueba de E5</span><span class="sxs-lookup"><span data-stu-id="63343-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="63343-123">Habilitar Microsoft 365 de prueba</span><span class="sxs-lookup"><span data-stu-id="63343-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="63343-124">Crear un inquilino Office 365 de prueba de E5</span><span class="sxs-lookup"><span data-stu-id="63343-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="63343-125">Si ya tiene una suscripción Office 365 o Azure Active Directory, puede omitir los pasos de creación Office 365 inquilino de prueba de E5.</span><span class="sxs-lookup"><span data-stu-id="63343-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="63343-126">Vaya al portal [de productos Office 365 E5 y](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) seleccione Prueba **gratuita.**</span><span class="sxs-lookup"><span data-stu-id="63343-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Página of_Office prueba gratuita de 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="63343-128">Complete el registro de prueba especificando su dirección de correo electrónico (personal o corporativa).</span><span class="sxs-lookup"><span data-stu-id="63343-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="63343-129">Haga **clic en Configurar cuenta**.</span><span class="sxs-lookup"><span data-stu-id="63343-129">Click **Set up account**.</span></span>

   ![Página of_Office configuración de registro de prueba de 365 E5](../../media/mtp-eval-10.png)

3. <span data-ttu-id="63343-131">Rellene el nombre, el apellido, el número de teléfono de empresa, el nombre de la empresa, el tamaño de la empresa y el país o región.</span><span class="sxs-lookup"><span data-stu-id="63343-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Página of_Office configuración de registro de prueba de 365 E5 que pide detalles de nombre, teléfono y empresa](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="63343-133">El país o región que establezca aquí determina la región del centro de datos que Office 365 se hospedará.</span><span class="sxs-lookup"><span data-stu-id="63343-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="63343-134">Elija su preferencia de verificación: a través de un mensaje de texto o una llamada.</span><span class="sxs-lookup"><span data-stu-id="63343-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="63343-135">Haga clic **en Enviar código de verificación**.</span><span class="sxs-lookup"><span data-stu-id="63343-135">Click **Send Verification Code**.</span></span> 

   ![Página of_Office configuración de registro de prueba 365 E5 que pide preferencia de verificación](../../media/mtp-eval-12.png)

5. <span data-ttu-id="63343-137">Establezca el nombre de dominio personalizado para el inquilino y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="63343-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Página of_Office configuración de registro de prueba de 365 E5 donde puede configurar el nombre de dominio personalizado](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="63343-139">Configure la primera identidad, que será un administrador global para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="63343-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="63343-140">Rellene Nombre **y** **contraseña.**</span><span class="sxs-lookup"><span data-stu-id="63343-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="63343-141">Haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="63343-141">Click **Sign up**.</span></span>

   ![Página of_Office configuración de registro de prueba de 365 E5 donde puede establecer su identidad empresarial](../../media/mtp-eval-14.png)

7. <span data-ttu-id="63343-143">Haga **clic en Ir al programa de** instalación para completar Office 365 de inquilino de prueba de E5.</span><span class="sxs-lookup"><span data-stu-id="63343-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Imagen de la Office 365 de configuración de registro de prueba de E5 que pide hacer clic en El botón Ir a la instalación](../../media/mtp-eval-15.png)

8. <span data-ttu-id="63343-145">Conectar el dominio corporativo al Office 365 empresarial.</span><span class="sxs-lookup"><span data-stu-id="63343-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="63343-146">[Opcional] Elija **Conectar dominio que ya posee** y escriba el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="63343-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="63343-147">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="63343-147">Click **Next**.</span></span>

   ![Página of_Office configuración de 365 E5 donde debes personalizar el inicio de sesión y el correo electrónico](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="63343-149">Agregue un registro TXT o MX para validar la propiedad del dominio.</span><span class="sxs-lookup"><span data-stu-id="63343-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="63343-150">Una vez que haya agregado el registro TXT o MX al dominio, seleccione **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="63343-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Página de of_Office de instalación de 365 E5 donde debe agregar un registro TXT de MX para comprobar su dominio](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="63343-152">[Opcional] Cree más cuentas de usuario para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="63343-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="63343-153">Puede omitir este paso haciendo clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="63343-153">You can skip this step by clicking **Next**.</span></span>

    ![Página de of_Office de instalación de 365 E5 donde puede agregar más usuarios](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="63343-155">[Opcional] Descarga Office aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="63343-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="63343-156">Haga **clic en** Siguiente para omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="63343-156">Click **Next** to skip this step.</span></span> 

    ![Página of_Office 365 E5 donde puedes instalar las aplicaciones Office aplicaciones](../../media/mtp-eval-19.png)

12. <span data-ttu-id="63343-158">[Opcional] Migrar mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="63343-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="63343-159">De nuevo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="63343-159">Again, you can skip this step.</span></span>

    ![Imagen of_Office 365 E5 donde puede establecer si desea migrar mensajes de correo electrónico o no](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="63343-161">Elija servicios en línea.</span><span class="sxs-lookup"><span data-stu-id="63343-161">Choose online services.</span></span> <span data-ttu-id="63343-162">Seleccione **Exchange** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="63343-162">Select **Exchange** and click **Next**.</span></span> 

    ![Imagen of_Office 365 E5 donde puede elegir sus servicios en línea](../../media/mtp-eval-21.png)

14. <span data-ttu-id="63343-164">Agregue registros MX, CNAME y TXT al dominio.</span><span class="sxs-lookup"><span data-stu-id="63343-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="63343-165">Cuando se complete, seleccione **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="63343-165">When completed, select **Verify**.</span></span>

    ![Image of_Office 365 E5 aquí puede agregar los registros DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="63343-167">Enhorabuena, ha completado el aprovisionamiento de su Office 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="63343-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Página de of_Office de finalización de instalación de 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="63343-169">Habilitar Microsoft 365 de prueba</span><span class="sxs-lookup"><span data-stu-id="63343-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="63343-170">Registrarse para una versión de prueba le ofrece 25 licencias de usuario para usarlas durante un mes.</span><span class="sxs-lookup"><span data-stu-id="63343-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="63343-171">Consulta [Probar o comprar una suscripción a M365](../../commerce/try-or-buy-microsoft-365.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="63343-171">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="63343-172">En [Microsoft 365 de administración,](https://admin.microsoft.com/)haga clic en **Facturación** y, a continuación, vaya a **Servicios de compra.**</span><span class="sxs-lookup"><span data-stu-id="63343-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="63343-173">Seleccione **Microsoft 365 E5** y haga clic **en Iniciar prueba gratuita.**</span><span class="sxs-lookup"><span data-stu-id="63343-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Página of_Microsoft 365 E5 Start free trial](../../media/mtp-eval-24.png)

3. <span data-ttu-id="63343-175">Elija su preferencia de verificación: a través de un mensaje de texto o una llamada.</span><span class="sxs-lookup"><span data-stu-id="63343-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="63343-176">Una vez que haya decidido, escriba el número de teléfono, seleccione **Enviarme** un mensaje de texto o **Llamarme** según la selección.</span><span class="sxs-lookup"><span data-stu-id="63343-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="63343-178">Escriba el código de verificación y haga clic **en Iniciar la prueba gratuita.**</span><span class="sxs-lookup"><span data-stu-id="63343-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Imagen of_Microsoft 365 E5 Página de prueba gratuita inicio donde puede rellenar el código de verificación que el sistema envió para demostrar que no es un robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="63343-180">Haga **clic en Probar ahora** para confirmar la Microsoft 365 E5 prueba.</span><span class="sxs-lookup"><span data-stu-id="63343-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Imagen of_Microsoft 365 E5 Página de prueba gratuita inicio donde debería reloj el botón Probar ahora para iniciarse](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="63343-182">Vaya a la **página Microsoft 365 Usuarios activos** del Centro  >    >  **de administración.**</span><span class="sxs-lookup"><span data-stu-id="63343-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="63343-183">Seleccione su cuenta de usuario, seleccione **Administrar licencias** de productos y, a continuación, cambie la licencia de Office 365 E5 **a Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="63343-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="63343-184">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="63343-184">Click **Save**.</span></span>

   ![Página of_Microsoft centro de administración de 365 donde puede seleccionar Microsoft 365 E5 licencia](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="63343-186">Vuelva a seleccionar la cuenta de administrador global y, a continuación, **haga clic en Administrar nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="63343-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Imagen of_Microsoft página del Centro de administración de 365, donde puede seleccionar Cuenta y, a continuación, Administrar nombre de usuario](../../media/mtp-eval-29.png)

8. <span data-ttu-id="63343-188">[Opcional] Cambie el dominio de *onmicrosoft.com* a su propio dominio, en función de lo que haya elegido en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="63343-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="63343-189">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="63343-189">Click **Save changes**.</span></span>

   ![Página of_Microsoft centro de administración de 365 donde puede cambiar su preferencia de dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="63343-191">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="63343-191">Next step</span></span>
|[<span data-ttu-id="63343-192">Fase 3: Configurar & incorporación</span><span class="sxs-lookup"><span data-stu-id="63343-192">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="63343-193">Configure cada pilar Microsoft 365 Defender para su entorno piloto o laboratorio de prueba de Microsoft 365 Defender e incorpore los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="63343-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
