---
title: Configurar el laboratorio Microsoft 365 Defender prueba o el entorno piloto
description: Access Microsoft 365 Security Center y, a continuación, configure el entorno Microsoft 365 Defender laboratorio de prueba
keywords: Microsoft 365 Defender de prueba, Microsoft 365 Defender piloto, pruebe Microsoft 365 Defender, Microsoft 365 Defender de laboratorio de evaluación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454738"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a><span data-ttu-id="08cef-104">Configurar la prueba Microsoft 365 Defender en un entorno de laboratorio</span><span class="sxs-lookup"><span data-stu-id="08cef-104">Set up your Microsoft 365 Defender trial in a lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="08cef-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="08cef-105">**Applies to:**</span></span>
- <span data-ttu-id="08cef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08cef-106">Microsoft 365 Defender</span></span> 

<span data-ttu-id="08cef-107">En este tema se le guía para configurar un entorno de laboratorio dedicado.</span><span class="sxs-lookup"><span data-stu-id="08cef-107">This topic guides you to set up a dedicated lab environment.</span></span> <span data-ttu-id="08cef-108">Para obtener información sobre cómo configurar una versión de prueba en producción, consulte la nueva Guía de evaluación [y Microsoft 365 Defender](eval-overview.md) prueba.</span><span class="sxs-lookup"><span data-stu-id="08cef-108">For information on setting up a trial in production, see the new [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) guide.</span></span> 

## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="08cef-109">Crear un inquilino Office 365 E5 de prueba</span><span class="sxs-lookup"><span data-stu-id="08cef-109">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="08cef-110">Si ya tiene una suscripción Office 365 o Azure Active Directory, puede omitir los pasos de creación Office 365 E5 inquilino de prueba.</span><span class="sxs-lookup"><span data-stu-id="08cef-110">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="08cef-111">Vaya al portal [Office 365 E5 producto y](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) seleccione Prueba **gratuita**.</span><span class="sxs-lookup"><span data-stu-id="08cef-111">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Página of_Office prueba gratuita de 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="08cef-113">Complete el registro de prueba especificando su dirección de correo electrónico (personal o corporativa).</span><span class="sxs-lookup"><span data-stu-id="08cef-113">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="08cef-114">Haga **clic en Configurar cuenta**.</span><span class="sxs-lookup"><span data-stu-id="08cef-114">Click **Set up account**.</span></span>

   ![Página of_Office configuración de registro de prueba de 365 E5](../../media/mtp-eval-10.png)

3. <span data-ttu-id="08cef-116">Rellene el nombre, el apellido, el número de teléfono de empresa, el nombre de la empresa, el tamaño de la empresa y el país o región.</span><span class="sxs-lookup"><span data-stu-id="08cef-116">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Página of_Office configuración de registro de prueba de 365 E5 que pide detalles de nombre, teléfono y empresa](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="08cef-118">El país o región que establezca aquí determina la región del centro de datos que Office 365 se hospedará.</span><span class="sxs-lookup"><span data-stu-id="08cef-118">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="08cef-119">Elija su preferencia de verificación: a través de un mensaje de texto o una llamada.</span><span class="sxs-lookup"><span data-stu-id="08cef-119">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="08cef-120">Haga clic **en Enviar código de verificación**.</span><span class="sxs-lookup"><span data-stu-id="08cef-120">Click **Send Verification Code**.</span></span> 

   ![Página of_Office configuración de registro de prueba 365 E5 que pide preferencia de verificación](../../media/mtp-eval-12.png)

5. <span data-ttu-id="08cef-122">Establezca el nombre de dominio personalizado para el inquilino y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="08cef-122">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Página of_Office configuración de registro de prueba de 365 E5 donde puede configurar el nombre de dominio personalizado](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="08cef-124">Configure la primera identidad, que será un administrador global para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="08cef-124">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="08cef-125">Rellene Nombre **y** **contraseña.**</span><span class="sxs-lookup"><span data-stu-id="08cef-125">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="08cef-126">Haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="08cef-126">Click **Sign up**.</span></span>

   ![Página of_Office configuración de registro de prueba de 365 E5 donde puede establecer su identidad empresarial](../../media/mtp-eval-14.png)

7. <span data-ttu-id="08cef-128">Haga **clic en Ir al programa de** instalación para completar el aprovisionamiento Office 365 E5 inquilino de prueba.</span><span class="sxs-lookup"><span data-stu-id="08cef-128">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Imagen de la Office 365 E5 de configuración de registro de prueba que pide hacer clic en El botón Ir a la instalación](../../media/mtp-eval-15.png)

8. <span data-ttu-id="08cef-130">Conectar el dominio corporativo al Office 365 empresarial.</span><span class="sxs-lookup"><span data-stu-id="08cef-130">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="08cef-131">[Opcional] Elija **Conectar dominio que ya posee** y escriba el nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="08cef-131">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="08cef-132">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="08cef-132">Click **Next**.</span></span>

   ![Página of_Office configuración de 365 E5 donde debes personalizar el inicio de sesión y el correo electrónico](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="08cef-134">Agregue un registro TXT o MX para validar la propiedad del dominio.</span><span class="sxs-lookup"><span data-stu-id="08cef-134">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="08cef-135">Una vez que haya agregado el registro TXT o MX al dominio, seleccione **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="08cef-135">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Página de of_Office de instalación de 365 E5 donde debe agregar un registro TXT de MX para comprobar su dominio](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="08cef-137">[Opcional] Cree más cuentas de usuario para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="08cef-137">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="08cef-138">Puede omitir este paso haciendo clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="08cef-138">You can skip this step by clicking **Next**.</span></span>

    ![Página de of_Office de instalación de 365 E5 donde puede agregar más usuarios](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="08cef-140">[Opcional] Descarga Office aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="08cef-140">[Optional] Download Office apps.</span></span> <span data-ttu-id="08cef-141">Haga **clic en** Siguiente para omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="08cef-141">Click **Next** to skip this step.</span></span> 

    ![Página of_Office 365 E5 donde puedes instalar las aplicaciones Office aplicaciones](../../media/mtp-eval-19.png)

12. <span data-ttu-id="08cef-143">[Opcional] Migrar mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="08cef-143">[Optional] Migrate email messages.</span></span> <span data-ttu-id="08cef-144">De nuevo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="08cef-144">Again, you can skip this step.</span></span>

    ![Imagen of_Office 365 E5 donde puede establecer si desea migrar mensajes de correo electrónico o no](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="08cef-146">Elija servicios en línea.</span><span class="sxs-lookup"><span data-stu-id="08cef-146">Choose online services.</span></span> <span data-ttu-id="08cef-147">Seleccione **Exchange** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="08cef-147">Select **Exchange** and click **Next**.</span></span> 

    ![Imagen of_Office 365 E5 donde puede elegir sus servicios en línea](../../media/mtp-eval-21.png)

14. <span data-ttu-id="08cef-149">Agregue registros MX, CNAME y TXT al dominio.</span><span class="sxs-lookup"><span data-stu-id="08cef-149">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="08cef-150">Cuando se complete, seleccione **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="08cef-150">When completed, select **Verify**.</span></span>

    ![Image of_Office 365 E5 aquí puede agregar los registros DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="08cef-152">Enhorabuena, ha completado el aprovisionamiento de su Office 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="08cef-152">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Página de of_Office de finalización de instalación de 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="08cef-154">Habilitar Microsoft 365 de prueba</span><span class="sxs-lookup"><span data-stu-id="08cef-154">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="08cef-155">Registrarse para una versión de prueba le ofrece 25 licencias de usuario para usarlas durante un mes.</span><span class="sxs-lookup"><span data-stu-id="08cef-155">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="08cef-156">Consulta [Probar o comprar una suscripción a M365](../../commerce/try-or-buy-microsoft-365.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="08cef-156">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="08cef-157">En [Administración de Microsoft 365, haga](https://admin.microsoft.com/)clic en **Facturación** y, a continuación, vaya a **Servicios de compra.**</span><span class="sxs-lookup"><span data-stu-id="08cef-157">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="08cef-158">Seleccione **Microsoft 365 E5** y haga clic **en Iniciar prueba gratuita.**</span><span class="sxs-lookup"><span data-stu-id="08cef-158">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Página of_Microsoft 365 E5 Start free trial](../../media/mtp-eval-24.png)

3. <span data-ttu-id="08cef-160">Elija su preferencia de verificación: a través de un mensaje de texto o una llamada.</span><span class="sxs-lookup"><span data-stu-id="08cef-160">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="08cef-161">Una vez que haya decidido, escriba el número de teléfono, seleccione **Enviarme** un mensaje de texto o **Llamarme** según la selección.</span><span class="sxs-lookup"><span data-stu-id="08cef-161">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="08cef-163">Escriba el código de verificación y haga clic **en Iniciar la prueba gratuita.**</span><span class="sxs-lookup"><span data-stu-id="08cef-163">Enter the verification code and click **Start your free trial**.</span></span>

   ![Imagen of_Microsoft 365 E5 Página de prueba gratuita inicio donde puede rellenar el código de verificación que el sistema envió para demostrar que no es un robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="08cef-165">Haga **clic en Probar ahora** para confirmar la Microsoft 365 E5 prueba.</span><span class="sxs-lookup"><span data-stu-id="08cef-165">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Imagen of_Microsoft 365 E5 Página de prueba gratuita inicio donde debería reloj el botón Probar ahora para iniciarse](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="08cef-167">Vaya al centro **de Administración de Microsoft 365 usuarios**  >    >  **activos.**</span><span class="sxs-lookup"><span data-stu-id="08cef-167">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="08cef-168">Seleccione su cuenta de usuario, seleccione **Administrar licencias de productos** y, a continuación, cambie la licencia de Office 365 E5 a **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="08cef-168">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="08cef-169">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="08cef-169">Click **Save**.</span></span>

   ![Página of_Microsoft centro de administración de 365 donde puede seleccionar Microsoft 365 E5 licencia](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="08cef-171">Vuelva a seleccionar la cuenta de administrador global y, a continuación, **haga clic en Administrar nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="08cef-171">Select the global administrator account again then click **Manage username**.</span></span>

   ![Imagen of_Microsoft página del Centro de administración de 365, donde puede seleccionar Cuenta y, a continuación, Administrar nombre de usuario](../../media/mtp-eval-29.png)

8. <span data-ttu-id="08cef-173">[Opcional] Cambie el dominio de *onmicrosoft.com* a su propio dominio, en función de lo que haya elegido en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="08cef-173">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="08cef-174">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="08cef-174">Click **Save changes**.</span></span>

   ![Página of_Microsoft centro de administración de 365 donde puede cambiar su preferencia de dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="08cef-176">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="08cef-176">Next step</span></span>
|[<span data-ttu-id="08cef-177">Fase 3: Configurar & incorporación</span><span class="sxs-lookup"><span data-stu-id="08cef-177">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="08cef-178">Configure cada Microsoft 365 Defender para su entorno Microsoft 365 Defender prueba o entorno piloto e incorpore los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="08cef-178">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
