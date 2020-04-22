---
title: Simulador de ataque en ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Como administrador global, puede usar simulador de ataque para ejecutar escenarios de ataque realistas en su organización. Esto puede ayudarle a identificar y encontrar a los usuarios vulnerables antes de que un ataque real reconozca a su empresa.
ms.openlocfilehash: cac09ed48a46531ea2246f9c3ef798649dc73196
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638577"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="f9b70-104">Simulador de ataque en ATP</span><span class="sxs-lookup"><span data-stu-id="f9b70-104">Attack Simulator in ATP</span></span>

<span data-ttu-id="f9b70-105">**Resumen** Si es administrador global o administrador de seguridad y su organización tiene Office 365 Advanced Threat Protection Plan 2, que incluye la [investigación de amenazas y las capacidades de respuesta](office-365-ti.md), puede usar simulador de ataque para ejecutar escenarios de ataque realistas en su organización.</span><span class="sxs-lookup"><span data-stu-id="f9b70-105">**Summary** If you are a global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="f9b70-106">Esto puede ayudarle a identificar y buscar usuarios vulnerables antes de que un ataque real afecte a los resultados finales.</span><span class="sxs-lookup"><span data-stu-id="f9b70-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="f9b70-107">Lea este artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f9b70-107">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f9b70-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="f9b70-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f9b70-109">Para abrir el centro de seguridad & cumplimiento, vaya <https://protection.office.com/>a.</span><span class="sxs-lookup"><span data-stu-id="f9b70-109">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="f9b70-110">El simulador de ataques está disponible en **simulador de ataques**de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f9b70-110">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![Administración de amenazas: simulador de ataque](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="f9b70-112">Para obtener más información acerca de la disponibilidad de un simulador de ataque en distintas suscripciones de Microsoft 365, consulte [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="f9b70-112">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="f9b70-113">Debe ser miembro de los grupos de roles **Administración** de la organización o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="f9b70-113">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f9b70-114">Para obtener más información acerca de los grupos de roles en el centro de seguridad & cumplimiento, consulte [Permissions in the security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f9b70-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f9b70-115">La cuenta debe estar configurada para la autenticación multifactor (MFA) con el fin de crear y administrar campañas en el simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="f9b70-115">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="f9b70-116">Para obtener instrucciones, vea [set up multi-factor Authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="f9b70-116">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

<span data-ttu-id="f9b70-117">Para que un ataque se inicie correctamente, asegúrese de que la cuenta que usa para ejecutar ataques simulados esté usando la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="f9b70-117">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="f9b70-118">Además, debe ser administrador global o administrador de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f9b70-118">In addition, you must be a global administrator or a security administrator.</span></span> <span data-ttu-id="f9b70-119">(Para obtener más información acerca de los roles y los permisos, consulte [permisos en el centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md)).</span><span class="sxs-lookup"><span data-stu-id="f9b70-119">(To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

- <span data-ttu-id="f9b70-120">Las campañas de suplantación de identidad recopilarán y procesarán eventos durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="f9b70-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="f9b70-121">Los datos históricos de la campaña estarán disponibles hasta 90 días después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="f9b70-122">No hay cmdlets de PowerShell correspondientes para el simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="f9b70-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="f9b70-123">Campañas de "Spear phishing"</span><span class="sxs-lookup"><span data-stu-id="f9b70-123">Spear phishing campaigns</span></span>

<span data-ttu-id="f9b70-124">La *suplantación de identidad (phishing)* es un término genérico para los ataques de correo electrónico que intentan robar información confidencial en los mensajes que parecen ser de remitentes legítimos o de confianza.</span><span class="sxs-lookup"><span data-stu-id="f9b70-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="f9b70-125">La *suplantación de identidad (Spear phishing* ) es un ataque de suplantación de identidad (phishing) orientado a los destinatarios de destino (normalmente, después del reconocimiento de los destinatarios por parte del atacante).</span><span class="sxs-lookup"><span data-stu-id="f9b70-125">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="f9b70-126">Es administrador global o administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="f9b70-126">You are a global administrator or security administrator</span></span>

<span data-ttu-id="f9b70-127">En el simulador de ataque, hay disponibles dos tipos diferentes de campañas de "Spear phishing":</span><span class="sxs-lookup"><span data-stu-id="f9b70-127">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="f9b70-128">El [acceso condicional/autenticación multifactor](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) está activado, al menos para la cuenta de administrador global y los administradores de seguridad que van a usar el simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="f9b70-128">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="f9b70-129">(Idealmente, el acceso condicional/autenticación multifactor está activado para todos los usuarios de la organización).</span><span class="sxs-lookup"><span data-stu-id="f9b70-129">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

  - <span data-ttu-id="f9b70-130">Una página predeterminada en la que se explica que se trataba de una sola prueba y ofrece sugerencias para reconocer los mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="f9b70-130">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Qué ven los usuarios si hacen clic en el vínculo phishing y escriben sus credenciales](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="f9b70-132">Una página personalizada (URL) que especifique.</span><span class="sxs-lookup"><span data-stu-id="f9b70-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="f9b70-133">**Spear phishing (datos adjuntos)**: el ataque intenta convencer a los destinatarios para que abran un archivo adjunto. docx o. pdf en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9b70-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="f9b70-134">Los datos adjuntos incluyen el mismo contenido del vínculo de suplantación de identidad (phishing\<) predeterminado\>, pero la primera frase comienza por "nombre para mostrar, se ve este mensaje como un mensaje de correo electrónico reciente abierto...".</span><span class="sxs-lookup"><span data-stu-id="f9b70-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="f9b70-135">Actualmente, las campañas de suplantación de identidad de Spear en el simulador de ataque no expiran.</span><span class="sxs-lookup"><span data-stu-id="f9b70-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="f9b70-136">Crear una campaña de "Spear phishing"</span><span class="sxs-lookup"><span data-stu-id="f9b70-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="f9b70-137">Una parte importante de cualquier campaña de "Spear phishing" es la apariencia del mensaje de correo electrónico que se envía a los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="f9b70-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="f9b70-138">Para crear y configurar el mensaje de correo electrónico, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="f9b70-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="f9b70-139">**Usar una plantilla de correo electrónico integrada**: hay disponibles dos plantillas integradas: **Premio regalo** y **actualización de nóminas**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="f9b70-140">Puede personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="f9b70-141">**Cree una plantilla de correo electrónico reutilizable**: una vez que haya creado y guardado la plantilla de correo electrónico, puede usarla de nuevo en las campañas de suplantación de identidad de Spear futuras.</span><span class="sxs-lookup"><span data-stu-id="f9b70-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="f9b70-142">Puede personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="f9b70-143">**Crear el mensaje de correo electrónico en el asistente**: puede crear el mensaje de correo electrónico directamente en el asistente mientras crea e inicia la campaña de Spear phishing.</span><span class="sxs-lookup"><span data-stu-id="f9b70-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="f9b70-144">Paso 1 (opcional): crear una plantilla de correo electrónico personalizada</span><span class="sxs-lookup"><span data-stu-id="f9b70-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="f9b70-145">Si va a utilizar una de las plantillas integradas o va a crear el mensaje de correo electrónico directamente en el asistente, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="f9b70-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="f9b70-146">En el centro de seguridad & cumplimiento, vaya a **simulador de ataques**de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f9b70-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f9b70-147">En la página **Simulate Attacks** , en las secciones de **Spear phishing (credenciales cosecha)** o **Spear phishing (datos adjuntos)** , haga clic en **detalles de ataque**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="f9b70-148">No importa dónde cree la plantilla.</span><span class="sxs-lookup"><span data-stu-id="f9b70-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="f9b70-149">Las opciones disponibles en la plantilla son las mismas para ambos tipos de ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="f9b70-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="f9b70-150">En la **página Detalles del ataque** que se abre, en la sección plantillas de **suplantación de identidad** , en el área **crear plantillas** , haga clic en **nueva plantilla**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="f9b70-151">El Asistente para **Configurar plantillas de suplantación de identidad** se inicia en un nuevo flotante.</span><span class="sxs-lookup"><span data-stu-id="f9b70-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="f9b70-152">En el paso **iniciar** , escriba un nombre para mostrar único para la plantilla y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="f9b70-153">En el paso **configurar detalles de correo electrónico** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f9b70-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="f9b70-154">**From (nombre)**: el nombre para mostrar que se usa para el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9b70-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="f9b70-155">**From (email)**: la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="f9b70-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="f9b70-156">**Dirección URL del servidor de inicio de sesión de phishing**: haga clic en el menú desplegable y seleccione una de las direcciones URL disponibles de la lista.</span><span class="sxs-lookup"><span data-stu-id="f9b70-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="f9b70-157">Esta es la dirección URL a la que se verá tentado a los usuarios en hacer clic.</span><span class="sxs-lookup"><span data-stu-id="f9b70-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="f9b70-158">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="f9b70-158">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     > <ul><li><span data-ttu-id="f9b70-159">Todas las direcciones URL son intencionadamente http, no HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f9b70-159">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="f9b70-160">Un servicio de reputación de dirección URL puede identificar una o varias de estas direcciones URL como no seguras.</span><span class="sxs-lookup"><span data-stu-id="f9b70-160">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="f9b70-161">Compruebe la disponibilidad de la dirección URL en los exploradores Web admitidos antes de usar la dirección URL en una campaña de suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="f9b70-161">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="f9b70-162">**Dirección URL de la página de aterrizaje personalizada**: escriba una página de aterrizaje opcional en la que se tomen los usuarios si hacen clic en el vínculo phishing y escriben sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="f9b70-162">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="f9b70-163">Este vínculo reemplaza la página de aterrizaje predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f9b70-163">This link replaces the default landing page.</span></span> <span data-ttu-id="f9b70-164">Por ejemplo, si tiene un entrenamiento de conciencia interno, puede especificar esta dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="f9b70-164">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="f9b70-165">**Categoría**: Actualmente, no se usa esta configuración (se ignora cualquier cosa que haya escrito).</span><span class="sxs-lookup"><span data-stu-id="f9b70-165">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="f9b70-166">**Subject**: el campo **Subject** del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f9b70-166">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="f9b70-167">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-167">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f9b70-168">En el paso de **redacción de correo electrónico** , cree el cuerpo del mensaje del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f9b70-168">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="f9b70-169">Puede usar la pestaña **correo electrónico** (un editor HTML enriquecido) o la ficha **origen** (código HTML sin formato).</span><span class="sxs-lookup"><span data-stu-id="f9b70-169">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="f9b70-170">El formato HTML puede ser tan sencillo o complejo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f9b70-170">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="f9b70-171">Puede insertar imágenes y texto para mejorar la increíbleidad del mensaje en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="f9b70-171">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="f9b70-172">`${username}`inserta el nombre del destinatario.</span><span class="sxs-lookup"><span data-stu-id="f9b70-172">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="f9b70-173">`${loginserverurl}`inserta el valor de la **dirección URL del servidor de inicio de sesión de suplantación de identidad** del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="f9b70-173">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="f9b70-174">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-174">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f9b70-175">En el paso **confirmar** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-175">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="f9b70-176">Paso 2: crear e iniciar la campaña de suplantación de identidad de Spear</span><span class="sxs-lookup"><span data-stu-id="f9b70-176">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="f9b70-177">En el centro de seguridad & cumplimiento, vaya a **simulador de ataques**de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f9b70-177">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f9b70-178">En la página **simular ataques** , realice una de las siguientes selecciones en función del tipo de campaña que desee crear:</span><span class="sxs-lookup"><span data-stu-id="f9b70-178">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="f9b70-179">En la sección **Spear phishing (credenciales cosecha)** , haga clic en **iniciar ataque** o en **ataque de inicio**de detalles \> de **ataque** .</span><span class="sxs-lookup"><span data-stu-id="f9b70-179">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="f9b70-180">En la sección **Spear phishing (datos adjuntos)** , haga clic en **iniciar ataque** o en **ataque de inicio**de detalles \> de **ataque** .</span><span class="sxs-lookup"><span data-stu-id="f9b70-180">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="f9b70-181">El Asistente para **configurar un ataque de suplantación de identidad** se inicia en un nuevo flotante.</span><span class="sxs-lookup"><span data-stu-id="f9b70-181">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="f9b70-182">En el paso **iniciar** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f9b70-182">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f9b70-183">En el cuadro **nombre** , escriba un nombre para mostrar único para la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-183">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="f9b70-184">No haga clic en **Usar plantilla**, ya que creará el mensaje de correo electrónico más adelante en el asistente.</span><span class="sxs-lookup"><span data-stu-id="f9b70-184">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="f9b70-185">Haga clic en **Usar plantilla** y seleccione una plantilla de correo electrónico integrada o personalizada.</span><span class="sxs-lookup"><span data-stu-id="f9b70-185">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="f9b70-186">Una vez seleccionada la plantilla, el cuadro **nombre** se rellena automáticamente en función de la plantilla, pero puede cambiar el nombre.</span><span class="sxs-lookup"><span data-stu-id="f9b70-186">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Página de inicio de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="f9b70-188">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-188">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f9b70-189">En el paso **destinatarios de destino** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f9b70-189">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f9b70-190">Haga clic en **Libreta de direcciones** para seleccionar los destinatarios (usuarios o grupos) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-190">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="f9b70-191">Cada destinatario de destino debe tener un buzón de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f9b70-191">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="f9b70-192">Si hace clic en **filtrar** y **aplicar** sin especificar ningún criterio de búsqueda, todos los destinatarios se devuelven y se agregan a la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-192">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="f9b70-193">Haga clic en **importar** y, a continuación, en importar **archivo** para importar un archivo de valores separados por comas (CSV) o archivos separados por líneas de direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f9b70-193">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="f9b70-194">Cada línea debe contener la dirección de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="f9b70-194">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="f9b70-195">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-195">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f9b70-196">En el paso **configurar detalles de correo electrónico** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f9b70-196">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="f9b70-197">Si seleccionó una plantilla en el paso **iniciar** , la mayoría de estos valores ya están configurados, pero puede cambiarlos.</span><span class="sxs-lookup"><span data-stu-id="f9b70-197">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="f9b70-198">**From (nombre)**: el nombre para mostrar que se usa para el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9b70-198">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="f9b70-199">**From (email)**: la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="f9b70-199">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="f9b70-200">Puede escribir una dirección de correo electrónico real o falsa desde el dominio de correo electrónico de su organización o puede escribir una dirección de correo electrónico externa real o falsa.</span><span class="sxs-lookup"><span data-stu-id="f9b70-200">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="f9b70-201">Una dirección de correo electrónico de remitente válida de la organización se resolverá realmente en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="f9b70-201">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="f9b70-202">**Dirección URL del servidor de inicio de sesión de phishing**: haga clic en el menú desplegable y seleccione una de las direcciones URL disponibles de la lista.</span><span class="sxs-lookup"><span data-stu-id="f9b70-202">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="f9b70-203">Esta es la dirección URL a la que se verá tentado a los usuarios en hacer clic.</span><span class="sxs-lookup"><span data-stu-id="f9b70-203">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="f9b70-204">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="f9b70-204">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     > <ul><li><span data-ttu-id="f9b70-205">Todas las direcciones URL son intencionadamente http, no HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f9b70-205">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="f9b70-206">Un servicio de reputación de dirección URL puede identificar una o varias de estas direcciones URL como no seguras.</span><span class="sxs-lookup"><span data-stu-id="f9b70-206">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="f9b70-207">Compruebe la disponibilidad de la dirección URL en los exploradores Web admitidos antes de usar la dirección URL en una campaña de suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="f9b70-207">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="f9b70-208">Es necesario que seleccione una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="f9b70-208">You are required to select a URL.</span></span> <span data-ttu-id="f9b70-209">En el caso de las campañas de <b>"Spear phishing" (datos adjuntos)</b> , puede quitar el vínculo del cuerpo del mensaje en el paso siguiente (de lo contrario, el mensaje contendrá tanto un vínculo <b>como</b> datos adjuntos).</span><span class="sxs-lookup"><span data-stu-id="f9b70-209">For <b>Spear Phishing (Attachment)</b> campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link <b>and</b> an attachment).</span></span></li></ul>

   - <span data-ttu-id="f9b70-210">**Tipo de datos adjuntos**: esta configuración solo está disponible en las campañas de **"Spear phishing" (datos adjuntos)** .</span><span class="sxs-lookup"><span data-stu-id="f9b70-210">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="f9b70-211">Haga clic en la lista desplegable y seleccione **. DOCX** o **. PDF** de la lista.</span><span class="sxs-lookup"><span data-stu-id="f9b70-211">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="f9b70-212">**Nombre de datos adjuntos**: esta configuración solo está disponible en las campañas de **"Spear phishing" (datos adjuntos)** .</span><span class="sxs-lookup"><span data-stu-id="f9b70-212">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="f9b70-213">Escriba un nombre de archivo para los datos adjuntos. docx o. pdf.</span><span class="sxs-lookup"><span data-stu-id="f9b70-213">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="f9b70-214">**Dirección URL de la página de aterrizaje personalizada**: escriba una página de aterrizaje opcional en la que se tomen los usuarios si hacen clic en el vínculo phishing y escriben sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="f9b70-214">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="f9b70-215">Este vínculo reemplaza la página de aterrizaje predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f9b70-215">This link replaces the default landing page.</span></span> <span data-ttu-id="f9b70-216">Por ejemplo, si tiene un entrenamiento de conciencia interno, puede especificar esta dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="f9b70-216">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="f9b70-217">**Subject**: el campo **Subject** del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f9b70-217">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="f9b70-218">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-218">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f9b70-219">En el paso de **redacción de correo electrónico** , cree el cuerpo del mensaje del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f9b70-219">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="f9b70-220">Si seleccionó una plantilla en el paso **iniciar** , el cuerpo del mensaje ya está configurado, pero puede personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="f9b70-220">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="f9b70-221">Puede usar la pestaña **correo electrónico** (un editor HTML enriquecido) o la ficha **origen** (código HTML sin formato).</span><span class="sxs-lookup"><span data-stu-id="f9b70-221">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="f9b70-222">El formato HTML puede ser tan sencillo o complejo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f9b70-222">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="f9b70-223">Puede insertar imágenes y texto para mejorar la increíbleidad del mensaje en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="f9b70-223">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="f9b70-224">`${username}`inserta el nombre del destinatario.</span><span class="sxs-lookup"><span data-stu-id="f9b70-224">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="f9b70-225">`${loginserverurl}`inserta el valor **URL del servidor de inicio de sesión de suplantación de identidad** .</span><span class="sxs-lookup"><span data-stu-id="f9b70-225">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="f9b70-226">Para las campañas de **"Spear phishing" (datos adjuntos)** , debe quitar el vínculo del cuerpo del mensaje (de lo contrario, el mensaje contendrá tanto un vínculo **como** datos adjuntos y los clics de vínculo no se realizará el seguimiento en una campaña de datos adjuntos).</span><span class="sxs-lookup"><span data-stu-id="f9b70-226">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Crear cuerpo de correo electrónico](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="f9b70-228">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-228">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f9b70-229">En el paso **confirmar** , haga clic en **Finalizar** para iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-229">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="f9b70-230">El mensaje de suplantación de identidad se entrega a los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="f9b70-230">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="f9b70-231">Campañas de ataque con contraseña</span><span class="sxs-lookup"><span data-stu-id="f9b70-231">Password attack campaigns</span></span>

<span data-ttu-id="f9b70-232">Un *ataque de contraseña* intenta adivinar las contraseñas de las cuentas de usuario de una organización, normalmente después de que el atacante haya identificado una o varias cuentas de usuario válidas.</span><span class="sxs-lookup"><span data-stu-id="f9b70-232">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="f9b70-233">En el simulador de ataque, hay disponibles dos tipos diferentes de campañas para ataques con contraseña para que pueda probar la complejidad de las contraseñas de los usuarios:</span><span class="sxs-lookup"><span data-stu-id="f9b70-233">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="f9b70-234">**Contraseña de fuerza bruta (ataque de diccionario)**: una *fuerza bruta* o un ataque de *Diccionario* usa un archivo de Diccionario de gran tamaño de contraseñas en una cuenta de usuario con la esperanza de que uno de ellos trabaje (muchas contraseñas con una cuenta).</span><span class="sxs-lookup"><span data-stu-id="f9b70-234">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="f9b70-235">Los bloqueos de contraseñas incorrectos ayudan a impedir ataques de contraseñas de fuerza bruta.</span><span class="sxs-lookup"><span data-stu-id="f9b70-235">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="f9b70-236">Para el ataque de diccionario, puede especificar una o varias contraseñas para probarlas (especificadas manualmente o en un archivo cargado) y puede especificar uno o varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="f9b70-236">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="f9b70-237">**Ataque por pulverización de contraseñas**: un ataque *rociado de contraseñas* usa la misma contraseña cuidadosamente considerada con una lista de cuentas de usuario (una contraseña en muchas cuentas).</span><span class="sxs-lookup"><span data-stu-id="f9b70-237">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="f9b70-238">Los ataques por pulverización de contraseña son más difíciles de detectar que los ataques de fuerza bruta de contraseña (la probabilidad de que aumente el éxito cuando un atacante prueba una contraseña entre docenas o cientos de cuentas sin el riesgo de que se bloquee el bloqueo de contraseña incorrecto del usuario).</span><span class="sxs-lookup"><span data-stu-id="f9b70-238">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="f9b70-239">Para el ataque con aerosol de contraseña, solo puede especificar una contraseña para probar y puede especificar uno o varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="f9b70-239">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="f9b70-240">Los ataques de contraseñas en el simulador de ataque pasan las solicitudes de nombre de usuario y contraseña básicas de autenticación a un extremo, por lo que también funcionan con otros métodos de autenticación (AD FS, sincronización de hash de contraseña, paso a través, PingFederate, etc.).</span><span class="sxs-lookup"><span data-stu-id="f9b70-240">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="f9b70-241">Para los usuarios con la MFA habilitada, aunque el ataque de contraseña intente su contraseña real, el intento se registrará siempre como un error (es decir, los usuarios de MFA nunca aparecerán en el recuento **correcto de intentos** de la campaña).</span><span class="sxs-lookup"><span data-stu-id="f9b70-241">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="f9b70-242">Este es el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="f9b70-242">This is the expected result.</span></span> <span data-ttu-id="f9b70-243">MFA es un método principal para ayudar a proteger contra ataques de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="f9b70-243">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="f9b70-244">Crear e iniciar una campaña de ataque con contraseña</span><span class="sxs-lookup"><span data-stu-id="f9b70-244">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="f9b70-245">En el centro de seguridad & cumplimiento, vaya a **simulador de ataques**de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f9b70-245">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f9b70-246">En la página **simular ataques** , realice una de las siguientes selecciones en función del tipo de campaña que desee crear:</span><span class="sxs-lookup"><span data-stu-id="f9b70-246">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="f9b70-247">En la sección **contraseña de fuerza bruta (ataque de diccionario)** , haga clic en **iniciar ataque** o en **ataque de inicio**de detalles \> de **ataque** .</span><span class="sxs-lookup"><span data-stu-id="f9b70-247">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="f9b70-248">en la **sección ataque por pulverización de contraseña** , haga clic en **iniciar ataque** o en **ataque de inicio**de detalles \> de **ataque** .</span><span class="sxs-lookup"><span data-stu-id="f9b70-248">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="f9b70-249">El Asistente para **configurar un ataque de contraseña** comienza en un nuevo control flotante.</span><span class="sxs-lookup"><span data-stu-id="f9b70-249">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="f9b70-250">En el paso **iniciar** , escriba un nombre para mostrar único para la campaña y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-250">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="f9b70-251">En el paso **usuarios de destino** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f9b70-251">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f9b70-252">Haga clic en **Libreta de direcciones** para seleccionar los destinatarios (usuarios o grupos) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-252">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="f9b70-253">Cada destinatario de destino debe tener un buzón de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f9b70-253">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="f9b70-254">Si hace clic en **filtrar** y **aplicar** sin especificar ningún criterio de búsqueda, todos los destinatarios se devuelven y se agregan a la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-254">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="f9b70-255">Haga clic en **importar** y, a continuación, en importar **archivo** para importar un archivo de valores separados por comas (CSV) o archivos separados por líneas de direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f9b70-255">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="f9b70-256">Cada línea debe contener la dirección de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="f9b70-256">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="f9b70-257">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-257">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f9b70-258">En el paso **elegir configuración de ataque** , elija qué hacer en función del tipo de campaña:</span><span class="sxs-lookup"><span data-stu-id="f9b70-258">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="f9b70-259">**Contraseña de fuerza bruta (ataque de diccionario)**: realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9b70-259">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="f9b70-260">**Escriba las contraseñas manualmente**: en el cuadro **presione Entrar para agregar una contraseña** , escriba una contraseña y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="f9b70-260">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="f9b70-261">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f9b70-261">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="f9b70-262">**Cargar contraseñas desde un archivo de diccionario**: haga clic en **cargar** para importar un archivo de texto existente que contenga una contraseña en cada línea y una última línea en blanco.</span><span class="sxs-lookup"><span data-stu-id="f9b70-262">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="f9b70-263">El archivo de texto debe tener un tamaño de 10 MB o menos, y no puede contener más de 30000 contraseñas.</span><span class="sxs-lookup"><span data-stu-id="f9b70-263">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="f9b70-264">**Ataque por pulverizador de contraseña**: en **las contraseñas que se van a usar en el cuadro ataque** , escriba una contraseña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-264">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="f9b70-265">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-265">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f9b70-266">En el paso **confirmar** , haga clic en **Finalizar** para iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-266">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="f9b70-267">Las contraseñas especificadas se prueban en los usuarios especificados.</span><span class="sxs-lookup"><span data-stu-id="f9b70-267">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="f9b70-268">Ver los resultados de la campaña</span><span class="sxs-lookup"><span data-stu-id="f9b70-268">View campaign results</span></span>

<span data-ttu-id="f9b70-269">Después de iniciar una campaña, puede comprobar el progreso y los resultados en la Página principal de **ataques de simulación** .</span><span class="sxs-lookup"><span data-stu-id="f9b70-269">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="f9b70-270">Las campañas activas mostrarán una barra de estado, un valor porcentual completado y el recuento de (usuarios completados) de (total de usuarios) ".</span><span class="sxs-lookup"><span data-stu-id="f9b70-270">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="f9b70-271">Al hacer clic en el botón **Actualizar** se actualizará el progreso de las campañas activas.</span><span class="sxs-lookup"><span data-stu-id="f9b70-271">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="f9b70-272">También puede hacer clic en **Finalizar** para detener una campaña activa.</span><span class="sxs-lookup"><span data-stu-id="f9b70-272">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="f9b70-273">Una vez finalizada la campaña, el estado cambia a **ataque completado**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-273">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="f9b70-274">Puede ver los resultados de la campaña realizando una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9b70-274">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="f9b70-275">En la página principales **ataques de simulación** , haga clic en **Ver informe** bajo el nombre de la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-275">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="f9b70-276">En la página principales **ataques de simulación** , haga clic en detalles de **ataque** en la sección para el tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="f9b70-276">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="f9b70-277">En la página **detalles de ataque** que se abre, seleccione la campaña en la sección historial de **ataques** .</span><span class="sxs-lookup"><span data-stu-id="f9b70-277">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="f9b70-278">Cualquiera de las acciones anteriores le llevará a una página denominada **detalles del ataque**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-278">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="f9b70-279">La información disponible en esta página para cada tipo de campaña se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="f9b70-279">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="f9b70-280">Resultados de la campaña de Spear phishing (recopilación de credenciales)</span><span class="sxs-lookup"><span data-stu-id="f9b70-280">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="f9b70-281">La siguiente información está disponible en la página **detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="f9b70-281">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f9b70-282">La duración (fecha y hora de inicio y fecha de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-282">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f9b70-283">**Total de usuarios a los que se destina**</span><span class="sxs-lookup"><span data-stu-id="f9b70-283">**Total users targeted**</span></span>

- <span data-ttu-id="f9b70-284">**Intentos correctos**: el número de usuarios que hizo clic en el vínculo **y** escribió sus credenciales (*cualquier* valor de nombre de usuario y contraseña).</span><span class="sxs-lookup"><span data-stu-id="f9b70-284">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="f9b70-285">**Tasa general de éxito**: porcentaje calculado por el **Successful attempts** / **número total de usuarios a los**que se ha dirigido correctamente.</span><span class="sxs-lookup"><span data-stu-id="f9b70-285">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f9b70-286">**Clic más rápido**: Cuánto tiempo tardó el primer usuario en hacer clic en el vínculo después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-286">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="f9b70-287">**Promedio haga clic**en: cantidad de tiempo que tardó en hacer que todos los usuarios haga clic en el vínculo dividido por el número de usuarios que hizo clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="f9b70-287">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="f9b70-288">**Tasa de éxito**: un porcentaje calculado por (número de usuarios que hizo clic en el vínculo)/ **total de usuarios dirigidos**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-288">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="f9b70-289">**Credenciales más rápidas**: Cuánto tiempo tardó el primer usuario en escribir sus credenciales después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-289">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="f9b70-290">**Promedio de credenciales**: la suma de cuánto tiempo tardó en escribir sus credenciales dividida por el número de usuarios que escribieron sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="f9b70-290">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="f9b70-291">**Tasa de éxito**de la credencial: porcentaje calculado por (número de usuarios que han especificado sus credenciales)/ **total de usuarios a los**que se destina.</span><span class="sxs-lookup"><span data-stu-id="f9b70-291">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="f9b70-292">Gráfico de barras que muestra el **vínculo en** el que se hizo clic y los números de **credenciales especificados** por día.</span><span class="sxs-lookup"><span data-stu-id="f9b70-292">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="f9b70-293">Un gráfico circular que muestra el **vínculo en**el que se hizo clic, las **credenciales suministradas**y **ninguno** de los porcentajes de la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-293">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="f9b70-294">La sección **usuarios comprometidos** muestra los detalles de los usuarios que hacer clic en el vínculo:</span><span class="sxs-lookup"><span data-stu-id="f9b70-294">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="f9b70-295">La dirección de correo electrónico del usuario</span><span class="sxs-lookup"><span data-stu-id="f9b70-295">The user's email address</span></span>

  - <span data-ttu-id="f9b70-296">Fecha y hora en que hizo clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="f9b70-296">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="f9b70-297">La dirección IP del cliente.</span><span class="sxs-lookup"><span data-stu-id="f9b70-297">The client IP address.</span></span>

  - <span data-ttu-id="f9b70-298">Detalles sobre la versión del usuario de Windows y el explorador Web.</span><span class="sxs-lookup"><span data-stu-id="f9b70-298">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="f9b70-299">Puede hacer clic en **exportar** para exportar los resultados a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f9b70-299">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="f9b70-300">Resultados de la campaña de Spear phishing (datos adjuntos)</span><span class="sxs-lookup"><span data-stu-id="f9b70-300">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="f9b70-301">La siguiente información está disponible en la página **detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="f9b70-301">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f9b70-302">La duración (fecha y hora de inicio y fecha de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-302">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f9b70-303">**Total de usuarios a los que se destina**</span><span class="sxs-lookup"><span data-stu-id="f9b70-303">**Total users targeted**</span></span>

- <span data-ttu-id="f9b70-304">**Intentos correctos**: el número de usuarios que abrieron o descargaron y abrieron los datos adjuntos (la vista previa no cuenta).</span><span class="sxs-lookup"><span data-stu-id="f9b70-304">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="f9b70-305">**Tasa general de éxito**: porcentaje calculado por el **Successful attempts** / **número total de usuarios a los**que se ha dirigido correctamente.</span><span class="sxs-lookup"><span data-stu-id="f9b70-305">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f9b70-306">**Tiempo de apertura de datos adjuntos más rápido**: Cuánto tiempo tardó el primer usuario en abrir los datos adjuntos después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-306">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="f9b70-307">**Tiempo medio de apertura de datos adjuntos**: la suma de la duración de la apertura de los datos adjuntos por el número de usuarios que abrieron los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="f9b70-307">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="f9b70-308">**Tasa de éxito de apertura de datos adjuntos**: porcentaje calculado por (número de usuarios que abrieron los datos adjuntos)/ **total de usuarios dirigidos**.</span><span class="sxs-lookup"><span data-stu-id="f9b70-308">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="f9b70-309">Resultados de la campaña de contraseña de fuerza bruta (ataque de diccionario)</span><span class="sxs-lookup"><span data-stu-id="f9b70-309">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="f9b70-310">La siguiente información está disponible en la página **detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="f9b70-310">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f9b70-311">La duración (fecha y hora de inicio y fecha de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-311">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f9b70-312">**Total de usuarios a los que se destina**</span><span class="sxs-lookup"><span data-stu-id="f9b70-312">**Total users targeted**</span></span>

- <span data-ttu-id="f9b70-313">**Intentos correctos**: el número de usuarios que se encontraron que utilizaban una de las contraseñas especificadas.</span><span class="sxs-lookup"><span data-stu-id="f9b70-313">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="f9b70-314">**Tasa general de éxito**: porcentaje calculado por el **Successful attempts** / **número total de usuarios a los**que se ha dirigido correctamente.</span><span class="sxs-lookup"><span data-stu-id="f9b70-314">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f9b70-315">La sección **usuarios comprometidos** muestra las direcciones de correo electrónico de los usuarios afectados.</span><span class="sxs-lookup"><span data-stu-id="f9b70-315">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="f9b70-316">Puede hacer clic en **exportar** para exportar los resultados a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f9b70-316">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="f9b70-317">Resultados de la campaña de ataque con aerosol de contraseña</span><span class="sxs-lookup"><span data-stu-id="f9b70-317">Password spray attack campaign results</span></span>

<span data-ttu-id="f9b70-318">La siguiente información está disponible en la página **detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="f9b70-318">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f9b70-319">La duración (fecha y hora de inicio y fecha de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="f9b70-319">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f9b70-320">**Total de usuarios a los que se destina**</span><span class="sxs-lookup"><span data-stu-id="f9b70-320">**Total users targeted**</span></span>

- <span data-ttu-id="f9b70-321">**Intentos correctos**: el número de usuarios que se encontraron que usaban la contraseña especificada.</span><span class="sxs-lookup"><span data-stu-id="f9b70-321">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="f9b70-322">**Tasa general de éxito**: porcentaje calculado por el **Successful attempts** / **número total de usuarios a los**que se ha dirigido correctamente.</span><span class="sxs-lookup"><span data-stu-id="f9b70-322">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
