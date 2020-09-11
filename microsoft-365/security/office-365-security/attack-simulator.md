---
title: Simulador de ataque en ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar simulador de ataques para ejecutar ataques simulados de suplantación de identidad (phishing) y contraseña en sus organizaciones de Microsoft 365 E5 o ATP planeada 2.
ms.openlocfilehash: 9fc28cdecc07f5325918e3d5176e52d1051a626c
ms.sourcegitcommit: 2b8c3fc39a7cbd4ca35e98dca430d2470cd2c925
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47426998"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="98215-103">Simulador de ataque en ATP</span><span class="sxs-lookup"><span data-stu-id="98215-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="98215-104">Si su organización tiene el plan 2 de la protección contra amenazas avanzada (ATP) de Office 365, que incluye [capacidades de investigación y respuesta de amenazas](office-365-ti.md), puede usar simulador de ataques en el centro de seguridad & cumplimiento para ejecutar escenarios de ataque realistas en la organización.</span><span class="sxs-lookup"><span data-stu-id="98215-104">If your organization has Office 365 Advanced Threat Protection (ATP) Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="98215-105">Estos ataques simulados pueden ayudarle a identificar y encontrar a los usuarios vulnerables antes de que un ataque real afecte a su conclusión.</span><span class="sxs-lookup"><span data-stu-id="98215-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="98215-106">Lea este artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="98215-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="98215-107">La simulación de ataques y los datos relacionados con la formación se almacenan con otros datos de clientes para los servicios 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98215-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="98215-108">Para obtener más información, vea [ubicaciones de datos de Microsoft 365](/microsoft-365/enterprise/o365-data-locations).</span><span class="sxs-lookup"><span data-stu-id="98215-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="98215-109">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="98215-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="98215-110">Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="98215-110">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="98215-111">El simulador de ataques **Threat management** está disponible en \> **simulador de ataques**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="98215-111">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="98215-112">Vaya directamente a simulador de ataque, abrir <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="98215-112">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="98215-113">Para obtener más información acerca de la disponibilidad de un simulador de ataque en distintas suscripciones de Microsoft 365, consulte [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="98215-113">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="98215-114">Debe ser miembro de los grupos de roles **Administración** de la organización o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="98215-114">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="98215-115">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="98215-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="98215-116">La cuenta debe estar configurada para la autenticación multifactor (MFA) con el fin de crear y administrar campañas en el simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="98215-116">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="98215-117">Para obtener instrucciones, vea [set up multi-factor Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="98215-117">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="98215-118">Las campañas de suplantación de identidad recopilarán y procesarán eventos durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="98215-118">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="98215-119">Los datos históricos de la campaña estarán disponibles hasta 90 días después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-119">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="98215-120">No hay cmdlets de PowerShell correspondientes para el simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="98215-120">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="98215-121">Campañas de "Spear phishing"</span><span class="sxs-lookup"><span data-stu-id="98215-121">Spear phishing campaigns</span></span>

<span data-ttu-id="98215-122">La *suplantación de identidad (phishing)* es un término genérico para los ataques de correo electrónico que intentan robar información confidencial en los mensajes que parecen ser de remitentes legítimos o de confianza.</span><span class="sxs-lookup"><span data-stu-id="98215-122">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="98215-123">La *suplantación de identidad (Spear phishing* ) es un ataque de suplantación de identidad (phishing) dirigido que usa contenido centrado y personalizado que está específicamente adaptado a los destinatarios de destino (normalmente, después del reconocimiento de los destinatarios por parte del atacante).</span><span class="sxs-lookup"><span data-stu-id="98215-123">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="98215-124">En el simulador de ataque, hay disponibles dos tipos diferentes de campañas de "Spear phishing":</span><span class="sxs-lookup"><span data-stu-id="98215-124">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="98215-125">**Spear phishing (cosecha de credenciales)**: el ataque intenta convencer a los destinatarios para que haga clic en una dirección URL del mensaje.</span><span class="sxs-lookup"><span data-stu-id="98215-125">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="98215-126">Si hacen clic en el vínculo, se les pedirá que escriban sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="98215-126">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="98215-127">Si es así, se toman en una de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="98215-127">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="98215-128">Una página predeterminada que explica que se trataba de una sola prueba y ofrece sugerencias para reconocer los mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="98215-128">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Qué ven los usuarios si hacen clic en el vínculo phishing y escriben sus credenciales](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="98215-130">Una página personalizada (URL) que especifique.</span><span class="sxs-lookup"><span data-stu-id="98215-130">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="98215-131">**Spear phishing (datos adjuntos)**: el ataque intenta convencer a los destinatarios para que abran un archivo adjunto. docx o. pdf en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="98215-131">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="98215-132">Los datos adjuntos incluyen el mismo contenido del vínculo de suplantación de identidad (phishing) predeterminado, pero la primera frase comienza por " \<Display Name\> , está viendo este mensaje como un mensaje de correo electrónico reciente que ha abierto...".</span><span class="sxs-lookup"><span data-stu-id="98215-132">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="98215-133">Actualmente, las campañas de suplantación de identidad de Spear en el simulador de ataque no expiran.</span><span class="sxs-lookup"><span data-stu-id="98215-133">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="98215-134">Crear una campaña de "Spear phishing"</span><span class="sxs-lookup"><span data-stu-id="98215-134">Create a spear phishing campaign</span></span>

<span data-ttu-id="98215-135">Una parte importante de cualquier campaña de "Spear phishing" es la apariencia del mensaje de correo electrónico que se envía a los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="98215-135">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="98215-136">Para crear y configurar el mensaje de correo electrónico, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="98215-136">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="98215-137">**Usar una plantilla de correo electrónico integrada**: hay disponibles dos plantillas integradas: **Premio regalo** y **actualización de nóminas**.</span><span class="sxs-lookup"><span data-stu-id="98215-137">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="98215-138">Puede personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-138">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="98215-139">**Cree una plantilla de correo electrónico reutilizable**: una vez que haya creado y guardado la plantilla de correo electrónico, puede usarla de nuevo en las campañas de suplantación de identidad de Spear futuras.</span><span class="sxs-lookup"><span data-stu-id="98215-139">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="98215-140">Puede personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="98215-141">**Crear el mensaje de correo electrónico en el asistente**: puede crear el mensaje de correo electrónico directamente en el asistente mientras crea e inicia la campaña de Spear phishing.</span><span class="sxs-lookup"><span data-stu-id="98215-141">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="98215-142">Paso 1 (opcional): crear una plantilla de correo electrónico personalizada</span><span class="sxs-lookup"><span data-stu-id="98215-142">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="98215-143">Si va a utilizar una de las plantillas integradas o va a crear el mensaje de correo electrónico directamente en el asistente, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="98215-143">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="98215-144">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **simulador de ataques**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="98215-144">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="98215-145">En la página **Simulate Attacks** , en las secciones de **Spear phishing (credenciales cosecha)** o **Spear phishing (datos adjuntos)** , haga clic en **detalles de ataque**.</span><span class="sxs-lookup"><span data-stu-id="98215-145">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="98215-146">No importa dónde cree la plantilla.</span><span class="sxs-lookup"><span data-stu-id="98215-146">It doesn't matter where you create the template.</span></span> <span data-ttu-id="98215-147">Las opciones disponibles en la plantilla son las mismas para ambos tipos de ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="98215-147">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="98215-148">En la **página Detalles del ataque** que se abre, en la sección plantillas de **suplantación de identidad** , en el área **crear plantillas** , haga clic en **nueva plantilla**.</span><span class="sxs-lookup"><span data-stu-id="98215-148">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="98215-149">El Asistente para **Configurar plantillas de suplantación de identidad** se inicia en un nuevo flotante.</span><span class="sxs-lookup"><span data-stu-id="98215-149">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="98215-150">En el paso **iniciar** , escriba un nombre para mostrar único para la plantilla y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98215-150">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="98215-151">En el paso **configurar detalles de correo electrónico** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="98215-151">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="98215-152">**From (nombre)**: el nombre para mostrar que se usa para el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="98215-152">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="98215-153">**From (email)**: la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="98215-153">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="98215-154">**Dirección URL del servidor de inicio de sesión de phishing**: haga clic en el menú desplegable y seleccione una de las direcciones URL disponibles de la lista.</span><span class="sxs-lookup"><span data-stu-id="98215-154">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="98215-155">Esta es la dirección URL a la que se verá tentado a los usuarios en hacer clic.</span><span class="sxs-lookup"><span data-stu-id="98215-155">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="98215-156">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="98215-156">The choices are:</span></span>

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
     >
     > - <span data-ttu-id="98215-157">Todas las direcciones URL son intencionadamente http, no HTTPS.</span><span class="sxs-lookup"><span data-stu-id="98215-157">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="98215-158">Un servicio de reputación de dirección URL puede identificar una o varias de estas direcciones URL como no seguras.</span><span class="sxs-lookup"><span data-stu-id="98215-158">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="98215-159">Compruebe la disponibilidad de la dirección URL en los exploradores Web admitidos antes de usar la dirección URL en una campaña de suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="98215-159">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="98215-160">**Dirección URL de la página de aterrizaje personalizada**: escriba una página de aterrizaje opcional en la que se tomen los usuarios si hacen clic en el vínculo phishing y escriben sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="98215-160">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="98215-161">Este vínculo reemplaza la página de aterrizaje predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98215-161">This link replaces the default landing page.</span></span> <span data-ttu-id="98215-162">Por ejemplo, si tiene un entrenamiento de conciencia interno, puede especificar esta dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="98215-162">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="98215-163">**Categoría**: Actualmente, no se usa esta configuración (se ignora cualquier cosa que haya escrito).</span><span class="sxs-lookup"><span data-stu-id="98215-163">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="98215-164">**Subject**: el campo **Subject** del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="98215-164">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="98215-165">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98215-165">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="98215-166">En el paso de **redacción de correo electrónico** , cree el cuerpo del mensaje del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="98215-166">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="98215-167">Puede usar la pestaña **correo electrónico** (un editor HTML enriquecido) o la ficha **origen** (código HTML sin formato).</span><span class="sxs-lookup"><span data-stu-id="98215-167">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="98215-168">El formato HTML puede ser tan sencillo o complejo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="98215-168">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="98215-169">Puede insertar imágenes y texto para mejorar la increíbleidad del mensaje en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="98215-169">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="98215-170">`${username}` inserta el nombre del destinatario.</span><span class="sxs-lookup"><span data-stu-id="98215-170">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="98215-171">`${loginserverurl}` inserta el valor de la **dirección URL del servidor de inicio de sesión de suplantación de identidad** del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="98215-171">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="98215-172">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98215-172">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="98215-173">En el paso **confirmar** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="98215-173">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="98215-174">Paso 2: crear e iniciar la campaña de suplantación de identidad de Spear</span><span class="sxs-lookup"><span data-stu-id="98215-174">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="98215-175">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **simulador de ataques**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="98215-175">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="98215-176">En la página **simular ataques** , realice una de las siguientes selecciones en función del tipo de campaña que desee crear:</span><span class="sxs-lookup"><span data-stu-id="98215-176">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="98215-177">En la sección **Spear phishing (credenciales cosecha)** , haga clic en **iniciar ataque** o en ataque de inicio de **detalles de ataque** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="98215-177">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="98215-178">En la sección **Spear phishing (datos adjuntos)** , haga clic en **iniciar ataque** o en ataque de inicio de **detalles de ataque** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="98215-178">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="98215-179">El Asistente para **configurar un ataque de suplantación de identidad** se inicia en un nuevo flotante.</span><span class="sxs-lookup"><span data-stu-id="98215-179">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="98215-180">En el paso **iniciar** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="98215-180">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="98215-181">En el cuadro **nombre** , escriba un nombre para mostrar único para la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-181">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="98215-182">No haga clic en **Usar plantilla**, ya que creará el mensaje de correo electrónico más adelante en el asistente.</span><span class="sxs-lookup"><span data-stu-id="98215-182">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="98215-183">Haga clic en **Usar plantilla** y seleccione una plantilla de correo electrónico integrada o personalizada.</span><span class="sxs-lookup"><span data-stu-id="98215-183">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="98215-184">Una vez seleccionada la plantilla, el cuadro **nombre** se rellena automáticamente en función de la plantilla, pero puede cambiar el nombre.</span><span class="sxs-lookup"><span data-stu-id="98215-184">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Página de inicio de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="98215-186">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98215-186">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="98215-187">En el paso **destinatarios de destino** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="98215-187">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="98215-188">Haga clic en **Libreta de direcciones** para seleccionar los destinatarios (usuarios o grupos) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-188">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="98215-189">Cada destinatario de destino debe tener un buzón de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="98215-189">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="98215-190">Si hace clic en **filtrar** y **aplicar** sin especificar ningún criterio de búsqueda, todos los destinatarios se devuelven y se agregan a la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-190">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="98215-191">Haga clic en **importar** y, a continuación, en importar **archivo** para importar un archivo de valores separados por comas (CSV) o archivos separados por líneas de direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="98215-191">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="98215-192">Cada línea debe contener la dirección de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="98215-192">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="98215-193">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98215-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="98215-194">En el paso **configurar detalles de correo electrónico** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="98215-194">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="98215-195">Si seleccionó una plantilla en el paso **iniciar** , la mayoría de estos valores ya están configurados, pero puede cambiarlos.</span><span class="sxs-lookup"><span data-stu-id="98215-195">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="98215-196">**From (nombre)**: el nombre para mostrar que se usa para el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="98215-196">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="98215-197">**From (email)**: la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="98215-197">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="98215-198">Puede escribir una dirección de correo electrónico real o falsa desde el dominio de correo electrónico de su organización o puede escribir una dirección de correo electrónico externa real o falsa.</span><span class="sxs-lookup"><span data-stu-id="98215-198">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="98215-199">Una dirección de correo electrónico de remitente válida de la organización se resolverá realmente en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="98215-199">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="98215-200">**Dirección URL del servidor de inicio de sesión de phishing**: haga clic en el menú desplegable y seleccione una de las direcciones URL disponibles de la lista.</span><span class="sxs-lookup"><span data-stu-id="98215-200">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="98215-201">Esta es la dirección URL a la que se verá tentado a los usuarios en hacer clic.</span><span class="sxs-lookup"><span data-stu-id="98215-201">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="98215-202">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="98215-202">The choices are:</span></span>

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
     >
     > - <span data-ttu-id="98215-203">Todas las direcciones URL son intencionadamente http, no HTTPS.</span><span class="sxs-lookup"><span data-stu-id="98215-203">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="98215-204">Un servicio de reputación de dirección URL puede identificar una o varias de estas direcciones URL como no seguras.</span><span class="sxs-lookup"><span data-stu-id="98215-204">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="98215-205">Compruebe la disponibilidad de la dirección URL en los exploradores Web admitidos antes de usar la dirección URL en una campaña de suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="98215-205">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="98215-206">Es necesario que seleccione una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="98215-206">You are required to select a URL.</span></span> <span data-ttu-id="98215-207">En el caso de las campañas de **"Spear phishing" (datos adjuntos)** , puede quitar el vínculo del cuerpo del mensaje en el paso siguiente (de lo contrario, el mensaje contendrá tanto un vínculo **como** datos adjuntos).</span><span class="sxs-lookup"><span data-stu-id="98215-207">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="98215-208">**Tipo de datos adjuntos**: esta configuración solo está disponible en las campañas de **"Spear phishing" (datos adjuntos)** .</span><span class="sxs-lookup"><span data-stu-id="98215-208">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="98215-209">Haga clic en la lista desplegable y seleccione **. DOCX** o **. PDF** de la lista.</span><span class="sxs-lookup"><span data-stu-id="98215-209">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="98215-210">**Nombre de datos adjuntos**: esta configuración solo está disponible en las campañas de **"Spear phishing" (datos adjuntos)** .</span><span class="sxs-lookup"><span data-stu-id="98215-210">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="98215-211">Escriba un nombre de archivo para los datos adjuntos. docx o. pdf.</span><span class="sxs-lookup"><span data-stu-id="98215-211">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="98215-212">**Dirección URL de la página de aterrizaje personalizada**: escriba una página de aterrizaje opcional en la que se tomen los usuarios si hacen clic en el vínculo phishing y escriben sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="98215-212">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="98215-213">Este vínculo reemplaza la página de aterrizaje predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98215-213">This link replaces the default landing page.</span></span> <span data-ttu-id="98215-214">Por ejemplo, si tiene un entrenamiento de conciencia interno, puede especificar esta dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="98215-214">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="98215-215">**Subject**: el campo **Subject** del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="98215-215">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="98215-216">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98215-216">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="98215-217">En el paso de **redacción de correo electrónico** , cree el cuerpo del mensaje del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="98215-217">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="98215-218">Si seleccionó una plantilla en el paso **iniciar** , el cuerpo del mensaje ya está configurado, pero puede personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="98215-218">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="98215-219">Puede usar la pestaña **correo electrónico** (un editor HTML enriquecido) o la ficha **origen** (código HTML sin formato).</span><span class="sxs-lookup"><span data-stu-id="98215-219">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="98215-220">El formato HTML puede ser tan sencillo o complejo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="98215-220">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="98215-221">Puede insertar imágenes y texto para mejorar la increíbleidad del mensaje en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="98215-221">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="98215-222">`${username}` inserta el nombre del destinatario.</span><span class="sxs-lookup"><span data-stu-id="98215-222">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="98215-223">`${loginserverurl}` inserta el valor **URL del servidor de inicio de sesión de suplantación de identidad** .</span><span class="sxs-lookup"><span data-stu-id="98215-223">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="98215-224">Para las campañas de **"Spear phishing" (datos adjuntos)** , debe quitar el vínculo del cuerpo del mensaje (de lo contrario, el mensaje contendrá tanto un vínculo **como** datos adjuntos y los clics de vínculo no se realizará el seguimiento en una campaña de datos adjuntos).</span><span class="sxs-lookup"><span data-stu-id="98215-224">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Crear cuerpo de correo electrónico](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="98215-226">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98215-226">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="98215-227">En el paso **confirmar** , haga clic en **Finalizar** para iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-227">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="98215-228">El mensaje de suplantación de identidad se entrega a los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="98215-228">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="98215-229">Campañas de ataque con contraseña</span><span class="sxs-lookup"><span data-stu-id="98215-229">Password attack campaigns</span></span>

<span data-ttu-id="98215-230">Un *ataque de contraseña* intenta adivinar las contraseñas de las cuentas de usuario de una organización, normalmente después de que el atacante haya identificado una o varias cuentas de usuario válidas.</span><span class="sxs-lookup"><span data-stu-id="98215-230">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="98215-231">En el simulador de ataque, hay disponibles dos tipos diferentes de campañas para ataques con contraseña para que pueda probar la complejidad de las contraseñas de los usuarios:</span><span class="sxs-lookup"><span data-stu-id="98215-231">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="98215-232">**Contraseña de fuerza bruta (ataque de diccionario)**: una *fuerza bruta* o un ataque de *Diccionario* usa un archivo de Diccionario de gran tamaño de contraseñas en una cuenta de usuario con la esperanza de que uno de ellos trabaje (muchas contraseñas con una cuenta).</span><span class="sxs-lookup"><span data-stu-id="98215-232">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="98215-233">Los bloqueos de contraseñas incorrectos ayudan a impedir ataques de contraseñas de fuerza bruta.</span><span class="sxs-lookup"><span data-stu-id="98215-233">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="98215-234">Para el ataque de diccionario, puede especificar una o varias contraseñas para probarlas (especificadas manualmente o en un archivo cargado) y puede especificar uno o varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="98215-234">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="98215-235">**Ataque por pulverización de contraseñas**: un ataque *rociado de contraseñas* usa la misma contraseña cuidadosamente considerada con una lista de cuentas de usuario (una contraseña en muchas cuentas).</span><span class="sxs-lookup"><span data-stu-id="98215-235">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="98215-236">Los ataques por pulverización de contraseña son más difíciles de detectar que los ataques de fuerza bruta de contraseña (la probabilidad de que aumente el éxito cuando un atacante prueba una contraseña entre docenas o cientos de cuentas sin el riesgo de que se bloquee el bloqueo de contraseña incorrecto del usuario).</span><span class="sxs-lookup"><span data-stu-id="98215-236">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="98215-237">Para el ataque con aerosol de contraseña, solo puede especificar una contraseña para probar y puede especificar uno o varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="98215-237">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="98215-238">Los ataques de contraseñas en el simulador de ataque pasan las solicitudes de nombre de usuario y contraseña básicas de autenticación a un extremo, por lo que también funcionan con otros métodos de autenticación (AD FS, sincronización de hash de contraseña, paso a través, PingFederate, etc.).</span><span class="sxs-lookup"><span data-stu-id="98215-238">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="98215-239">Para los usuarios con la MFA habilitada, aunque el ataque de contraseña intente su contraseña real, el intento se registrará siempre como un error (es decir, los usuarios de MFA nunca aparecerán en el recuento **correcto de intentos** de la campaña).</span><span class="sxs-lookup"><span data-stu-id="98215-239">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="98215-240">Este es el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="98215-240">This is the expected result.</span></span> <span data-ttu-id="98215-241">MFA es un método principal para ayudar a proteger contra ataques de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="98215-241">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="98215-242">Crear e iniciar una campaña de ataque con contraseña</span><span class="sxs-lookup"><span data-stu-id="98215-242">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="98215-243">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **simulador de ataques**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="98215-243">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="98215-244">En la página **simular ataques** , realice una de las siguientes selecciones en función del tipo de campaña que desee crear:</span><span class="sxs-lookup"><span data-stu-id="98215-244">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="98215-245">En la sección **contraseña de fuerza bruta (ataque de diccionario)** , haga clic en **iniciar ataque** o en ataque de inicio de **detalles de ataque** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="98215-245">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="98215-246">en la sección **ataque por pulverización de contraseña** , haga clic en **iniciar ataque** o en ataque de inicio de **detalles de ataque** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="98215-246">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="98215-247">El Asistente para **configurar un ataque de contraseña** comienza en un nuevo control flotante.</span><span class="sxs-lookup"><span data-stu-id="98215-247">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="98215-248">En el paso **iniciar** , escriba un nombre para mostrar único para la campaña y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98215-248">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="98215-249">En el paso **usuarios de destino** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="98215-249">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="98215-250">Haga clic en **Libreta de direcciones** para seleccionar los destinatarios (usuarios o grupos) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-250">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="98215-251">Cada destinatario de destino debe tener un buzón de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="98215-251">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="98215-252">Si hace clic en **filtrar** y **aplicar** sin especificar ningún criterio de búsqueda, todos los destinatarios se devuelven y se agregan a la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-252">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="98215-253">Haga clic en **importar** y, a continuación, en importar **archivo** para importar un archivo de valores separados por comas (CSV) o archivos separados por líneas de direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="98215-253">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="98215-254">Cada línea debe contener la dirección de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="98215-254">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="98215-255">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98215-255">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="98215-256">En el paso **elegir configuración de ataque** , elija qué hacer en función del tipo de campaña:</span><span class="sxs-lookup"><span data-stu-id="98215-256">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="98215-257">**Contraseña de fuerza bruta (ataque de diccionario)**: realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="98215-257">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="98215-258">**Escriba las contraseñas manualmente**: en el cuadro **presione Entrar para agregar una contraseña** , escriba una contraseña y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="98215-258">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="98215-259">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="98215-259">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="98215-260">**Cargar contraseñas desde un archivo de diccionario**: haga clic en **cargar** para importar un archivo de texto existente que contenga una contraseña en cada línea y una última línea en blanco.</span><span class="sxs-lookup"><span data-stu-id="98215-260">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="98215-261">El archivo de texto debe tener un tamaño de 10 MB o menos, y no puede contener más de 30000 contraseñas.</span><span class="sxs-lookup"><span data-stu-id="98215-261">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="98215-262">**Ataque por pulverizador de contraseña**: en **las contraseñas que se van a usar en el cuadro ataque** , escriba una contraseña.</span><span class="sxs-lookup"><span data-stu-id="98215-262">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="98215-263">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98215-263">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="98215-264">En el paso **confirmar** , haga clic en **Finalizar** para iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-264">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="98215-265">Las contraseñas especificadas se prueban en los usuarios especificados.</span><span class="sxs-lookup"><span data-stu-id="98215-265">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="98215-266">Ver los resultados de la campaña</span><span class="sxs-lookup"><span data-stu-id="98215-266">View campaign results</span></span>

<span data-ttu-id="98215-267">Después de iniciar una campaña, puede comprobar el progreso y los resultados en la Página principal de **ataques de simulación** .</span><span class="sxs-lookup"><span data-stu-id="98215-267">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="98215-268">Las campañas activas mostrarán una barra de estado, un valor porcentual completado y el recuento de (usuarios completados) de (total de usuarios) ".</span><span class="sxs-lookup"><span data-stu-id="98215-268">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="98215-269">Al hacer clic en el botón **Actualizar** se actualizará el progreso de las campañas activas.</span><span class="sxs-lookup"><span data-stu-id="98215-269">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="98215-270">También puede hacer clic en **Finalizar** para detener una campaña activa.</span><span class="sxs-lookup"><span data-stu-id="98215-270">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="98215-271">Una vez finalizada la campaña, el estado cambia a **ataque completado**.</span><span class="sxs-lookup"><span data-stu-id="98215-271">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="98215-272">Puede ver los resultados de la campaña realizando una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="98215-272">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="98215-273">En la página principales **ataques de simulación** , haga clic en **Ver informe** bajo el nombre de la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-273">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="98215-274">En la página principales **ataques de simulación** , haga clic en detalles de **ataque** en la sección para el tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="98215-274">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="98215-275">En la página **detalles de ataque** que se abre, seleccione la campaña en la sección historial de **ataques** .</span><span class="sxs-lookup"><span data-stu-id="98215-275">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="98215-276">Cualquiera de las acciones anteriores le llevará a una página denominada **detalles del ataque**.</span><span class="sxs-lookup"><span data-stu-id="98215-276">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="98215-277">La información disponible en esta página para cada tipo de campaña se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="98215-277">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="98215-278">Resultados de la campaña de Spear phishing (recopilación de credenciales)</span><span class="sxs-lookup"><span data-stu-id="98215-278">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="98215-279">La siguiente información está disponible en la página **detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="98215-279">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="98215-280">La duración (fecha y hora de inicio y fecha de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-280">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="98215-281">**Total de usuarios a los que se destina**</span><span class="sxs-lookup"><span data-stu-id="98215-281">**Total users targeted**</span></span>

- <span data-ttu-id="98215-282">**Intentos correctos**: el número de usuarios que hizo clic en el vínculo **y** escribió sus credenciales (*cualquier* valor de nombre de usuario y contraseña).</span><span class="sxs-lookup"><span data-stu-id="98215-282">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="98215-283">**Tasa general de éxito**: porcentaje calculado por el **Successful attempts**  /  **número total de usuarios a los**que se ha dirigido correctamente.</span><span class="sxs-lookup"><span data-stu-id="98215-283">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="98215-284">**Clic más rápido**: Cuánto tiempo tardó el primer usuario en hacer clic en el vínculo después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-284">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="98215-285">**Promedio haga clic**en: cantidad de tiempo que tardó en hacer que todos los usuarios haga clic en el vínculo dividido por el número de usuarios que hizo clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="98215-285">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="98215-286">**Tasa de éxito**: un porcentaje calculado por (número de usuarios que hizo clic en el vínculo)/ **total de usuarios dirigidos**.</span><span class="sxs-lookup"><span data-stu-id="98215-286">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="98215-287">**Credenciales más rápidas**: Cuánto tiempo tardó el primer usuario en escribir sus credenciales después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-287">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="98215-288">**Promedio de credenciales**: la suma de cuánto tiempo tardó en escribir sus credenciales dividida por el número de usuarios que escribieron sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="98215-288">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="98215-289">**Tasa de éxito**de la credencial: porcentaje calculado por (número de usuarios que han especificado sus credenciales)/ **total de usuarios a los**que se destina.</span><span class="sxs-lookup"><span data-stu-id="98215-289">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="98215-290">Gráfico de barras que muestra el **vínculo en** el que se hizo clic y los números de **credenciales especificados** por día.</span><span class="sxs-lookup"><span data-stu-id="98215-290">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="98215-291">Un gráfico circular que muestra el **vínculo en**el que se hizo clic, las **credenciales suministradas**y **ninguno** de los porcentajes de la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-291">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="98215-292">La sección **usuarios comprometidos** muestra los detalles de los usuarios que hacer clic en el vínculo:</span><span class="sxs-lookup"><span data-stu-id="98215-292">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="98215-293">La dirección de correo electrónico del usuario</span><span class="sxs-lookup"><span data-stu-id="98215-293">The user's email address</span></span>

  - <span data-ttu-id="98215-294">Fecha y hora en que hizo clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="98215-294">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="98215-295">La dirección IP del cliente.</span><span class="sxs-lookup"><span data-stu-id="98215-295">The client IP address.</span></span>

  - <span data-ttu-id="98215-296">Detalles sobre la versión del usuario de Windows y el explorador Web.</span><span class="sxs-lookup"><span data-stu-id="98215-296">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="98215-297">Puede hacer clic en **exportar** para exportar los resultados a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="98215-297">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="98215-298">Resultados de la campaña de Spear phishing (datos adjuntos)</span><span class="sxs-lookup"><span data-stu-id="98215-298">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="98215-299">La siguiente información está disponible en la página **detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="98215-299">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="98215-300">La duración (fecha y hora de inicio y fecha de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-300">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="98215-301">**Total de usuarios a los que se destina**</span><span class="sxs-lookup"><span data-stu-id="98215-301">**Total users targeted**</span></span>

- <span data-ttu-id="98215-302">**Intentos correctos**: el número de usuarios que abrieron o descargaron y abrieron los datos adjuntos (la vista previa no cuenta).</span><span class="sxs-lookup"><span data-stu-id="98215-302">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="98215-303">**Tasa general de éxito**: porcentaje calculado por el **Successful attempts**  /  **número total de usuarios a los**que se ha dirigido correctamente.</span><span class="sxs-lookup"><span data-stu-id="98215-303">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="98215-304">**Tiempo de apertura de datos adjuntos más rápido**: Cuánto tiempo tardó el primer usuario en abrir los datos adjuntos después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-304">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="98215-305">**Tiempo medio de apertura de datos adjuntos**: la suma de la duración de la apertura de los datos adjuntos por el número de usuarios que abrieron los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="98215-305">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="98215-306">**Tasa de éxito de apertura de datos adjuntos**: porcentaje calculado por (número de usuarios que abrieron los datos adjuntos)/ **total de usuarios dirigidos**.</span><span class="sxs-lookup"><span data-stu-id="98215-306">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="98215-307">Resultados de la campaña de contraseña de fuerza bruta (ataque de diccionario)</span><span class="sxs-lookup"><span data-stu-id="98215-307">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="98215-308">La siguiente información está disponible en la página **detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="98215-308">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="98215-309">La duración (fecha y hora de inicio y fecha de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-309">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="98215-310">**Total de usuarios a los que se destina**</span><span class="sxs-lookup"><span data-stu-id="98215-310">**Total users targeted**</span></span>

- <span data-ttu-id="98215-311">**Intentos correctos**: el número de usuarios que se encontraron que utilizaban una de las contraseñas especificadas.</span><span class="sxs-lookup"><span data-stu-id="98215-311">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="98215-312">**Tasa general de éxito**: porcentaje calculado por el **Successful attempts**  /  **número total de usuarios a los**que se ha dirigido correctamente.</span><span class="sxs-lookup"><span data-stu-id="98215-312">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="98215-313">La sección **usuarios comprometidos** muestra las direcciones de correo electrónico de los usuarios afectados.</span><span class="sxs-lookup"><span data-stu-id="98215-313">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="98215-314">Puede hacer clic en **exportar** para exportar los resultados a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="98215-314">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="98215-315">Resultados de la campaña de ataque con aerosol de contraseña</span><span class="sxs-lookup"><span data-stu-id="98215-315">Password spray attack campaign results</span></span>

<span data-ttu-id="98215-316">La siguiente información está disponible en la página **detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="98215-316">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="98215-317">La duración (fecha y hora de inicio y fecha de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="98215-317">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="98215-318">**Total de usuarios a los que se destina**</span><span class="sxs-lookup"><span data-stu-id="98215-318">**Total users targeted**</span></span>

- <span data-ttu-id="98215-319">**Intentos correctos**: el número de usuarios que se encontraron que usaban la contraseña especificada.</span><span class="sxs-lookup"><span data-stu-id="98215-319">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="98215-320">**Tasa general de éxito**: porcentaje calculado por el **Successful attempts**  /  **número total de usuarios a los**que se ha dirigido correctamente.</span><span class="sxs-lookup"><span data-stu-id="98215-320">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
