---
title: Simulador de ataque en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar Attack Simulator para ejecutar ataques simulados de suplantación de identidad (phishing) y contraseñas en sus organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 03e6c0077f13c85bfd20ac0583b64ce29e2535a1
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878681"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6c6b8-103">Simulador de ataque en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6c6b8-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6c6b8-104">**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="6c6b8-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="6c6b8-105">Si su organización tiene Microsoft Defender para Office 365 Plan 2, que incluye capacidades de investigación de amenazas y [respuesta,](office-365-ti.md)puede usar attack simulator en el Centro de seguridad & cumplimiento para ejecutar escenarios de ataque realistas en su organización.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="6c6b8-106">Estos ataques simulados pueden ayudarte a identificar y encontrar usuarios vulnerables antes de que un ataque real impacte en la línea de fondo.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="6c6b8-107">Lea este artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="6c6b8-108">Attack Simulator, como se describe en este artículo,  ahora es de solo lectura y ha sido reemplazado por el entrenamiento de simulación de ataque en el nodo de colaboración **Email &** en el portal de Microsoft 365 Defender en <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="6c6b8-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="6c6b8-109">Para obtener más información, vea [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="6c6b8-110">Se ha deshabilitado la capacidad de iniciar nuevas simulaciones desde esta versión de Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="6c6b8-111">Sin embargo, todavía puede acceder a informes hasta el 24 de abril de 2021.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-111">However, you can still access reports until April 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6c6b8-112">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="6c6b8-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6c6b8-113">Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="6c6b8-114">El simulador de ataque está disponible en **el simulador de ataque de administración** de \> **amenazas.**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="6c6b8-115">Para ir directamente al simulador de ataque, abra <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="6c6b8-115">To go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="6c6b8-116">Para obtener más información acerca de la disponibilidad de Attack Simulator en diferentes Microsoft 365 suscripciones, vea [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="6c6b8-117">Debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="6c6b8-118">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="6c6b8-119">La cuenta debe configurarse para la autenticación multifactor (MFA) para crear y administrar campañas en Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="6c6b8-120">Para obtener instrucciones, vea [Configurar la autenticación multifactor](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="6c6b8-121">Attack Simulator solo funciona en buzones basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="6c6b8-122">Las campañas de suplantación de identidad recopilarán y procesarán eventos durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="6c6b8-123">Los datos históricos de la campaña estarán disponibles hasta 90 días después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="6c6b8-124">Los datos relacionados con la simulación de ataques y el aprendizaje se almacenan con otros datos de clientes para Microsoft 365 servicios.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="6c6b8-125">Para obtener más [información, vea Microsoft 365 de datos](../../enterprise/o365-data-locations.md).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-125">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span>

- <span data-ttu-id="6c6b8-126">No hay cmdlets de PowerShell correspondientes para Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="6c6b8-127">Campañas de suplantación de identidad de lanza</span><span class="sxs-lookup"><span data-stu-id="6c6b8-127">Spear phishing campaigns</span></span>

<span data-ttu-id="6c6b8-128">*Phishing* es un término genérico para ataques de correo electrónico que intentan robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="6c6b8-129">*El phishing* de lanza es un ataque de suplantación de identidad dirigido que usa contenido centrado y personalizado que se adapta específicamente a los destinatarios dirigidos (normalmente, después del reconocimiento de los destinatarios por parte del atacante).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="6c6b8-130">En Attack Simulator, hay disponibles dos tipos diferentes de campañas de suplantación de identidad de lanza:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="6c6b8-131">**Phishing de lanza (recolección de credenciales):** el ataque intenta convencer a los destinatarios para que haga clic en una dirección URL del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="6c6b8-132">Si hacen clic en el vínculo, se les pedirá que escriban sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="6c6b8-133">Si lo hacen, se les traslada a una de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="6c6b8-134">Una página predeterminada que explica que se trataba de una prueba y proporciona sugerencias para reconocer mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Qué ven los usuarios si hacen clic en el vínculo de suplantación de identidad (phishing) y escriben sus credenciales](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="6c6b8-136">Una página personalizada (DIRECCIÓN URL) que especifique.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="6c6b8-137">**Phishing de lanza (datos adjuntos):** el ataque intenta convencer a los destinatarios para que abran .docx o .pdf datos adjuntos en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="6c6b8-138">Los datos adjuntos contienen el mismo contenido del vínculo de suplantación de identidad predeterminado, pero la primera oración comienza por " , estás viendo este mensaje como un mensaje de correo electrónico reciente \<Display Name\> que has abierto...".</span><span class="sxs-lookup"><span data-stu-id="6c6b8-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="6c6b8-139">Actualmente, las campañas de suplantación de identidad de lanza en Attack Simulator no expiran.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="6c6b8-140">Crear una campaña de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6c6b8-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="6c6b8-141">Una parte importante de cualquier campaña de suplantación de identidad de lanza es la apariencia del mensaje de correo electrónico que se envía a los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="6c6b8-142">Para crear y configurar el mensaje de correo electrónico, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="6c6b8-143">**Use una plantilla de correo electrónico integrada:** hay disponibles dos plantillas integradas: **Entrega** de premios y **Actualización de nómina.**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="6c6b8-144">Puedes personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="6c6b8-145">**Crear una plantilla de correo electrónico** reutilizable: después de crear y guardar la plantilla de correo electrónico, puede usarla de nuevo en futuras campañas de suplantación de identidad de lanza.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="6c6b8-146">Puedes personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="6c6b8-147">**Cree el mensaje de correo electrónico en el** asistente: puede crear el mensaje de correo electrónico directamente en el asistente al crear e iniciar la campaña de suplantación de identidad de lanza.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="6c6b8-148">Paso 1 (opcional): crear una plantilla de correo electrónico personalizada</span><span class="sxs-lookup"><span data-stu-id="6c6b8-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="6c6b8-149">Si va a usar una de las plantillas integradas o crear el mensaje de correo electrónico directamente en el asistente, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="6c6b8-150">En el Centro de seguridad & cumplimiento, vaya al Simulador **de ataques de administración** de \> **amenazas.**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6c6b8-151">En la **página Simular** ataques, en las secciones **Phishing de lanza (recolección** de credenciales) o Phishing de lanza **(datos** adjuntos), haga clic en **Detalles de ataque**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="6c6b8-152">No importa dónde cree la plantilla.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="6c6b8-153">Las opciones disponibles en la plantilla son las mismas para ambos tipos de ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="6c6b8-154">En la página **Detalles de** ataque que se abre, en la sección Plantillas **de** suplantación de identidad, en el área Crear plantillas, haga clic **en Nueva plantilla**. </span><span class="sxs-lookup"><span data-stu-id="6c6b8-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="6c6b8-155">El **Asistente para configurar plantilla de suplantación** de identidad comienza en un nuevo control desplegable.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="6c6b8-156">En el **paso Inicio,** escriba un nombre para mostrar único para la plantilla y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="6c6b8-157">En el **paso Configurar detalles de correo** electrónico, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="6c6b8-158">**From (Name):** el nombre para mostrar que se usa para el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="6c6b8-159">**From (Email):** la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="6c6b8-160">Dirección URL del servidor de inicio de sesión **de phishing:** haga clic en la lista desplegable y seleccione una de las direcciones URL disponibles de la lista.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="6c6b8-161">Esta es la dirección URL en la que los usuarios tendrán la tentación de hacer clic.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="6c6b8-162">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-162">The choices are:</span></span>

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
     > <span data-ttu-id="6c6b8-163">Un servicio de reputación de direcciones URL puede identificar una o varias de estas direcciones URL como no seguras.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="6c6b8-164">Compruebe la disponibilidad de la dirección URL en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="6c6b8-165">**Dirección URL de página de aterrizaje** personalizada: escriba una página de aterrizaje opcional en la que los usuarios se toman si hacen clic en el vínculo de suplantación de identidad y escriben sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="6c6b8-166">Este vínculo reemplaza la página de aterrizaje predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-166">This link replaces the default landing page.</span></span> <span data-ttu-id="6c6b8-167">Por ejemplo, si tiene formación de reconocimiento interno, puede especificar esa dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="6c6b8-168">**Categoría:** actualmente, esta configuración no se usa (se omite cualquier cosa que escriba).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="6c6b8-169">**Asunto:** el **campo Asunto** del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="6c6b8-170">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6c6b8-171">En el **paso Redacción de correo** electrónico, cree el cuerpo del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="6c6b8-172">Puede usar la pestaña **Correo** electrónico (un editor HTML enriquecido) o la **pestaña** Origen (código HTML sin formato).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="6c6b8-173">El formato HTML puede ser tan simple o complejo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="6c6b8-174">Puede insertar imágenes y texto para mejorar la fiabilidad del mensaje en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="6c6b8-175">`${username}` inserta el nombre del destinatario.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="6c6b8-176">`${loginserverurl}` inserta el valor de la dirección URL del servidor de inicio de **sesión de phishing** del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="6c6b8-177">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6c6b8-178">En el **paso Confirmar,** haga clic **en Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="6c6b8-179">Paso 2: Crear e iniciar la campaña de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6c6b8-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="6c6b8-180">En el Centro de seguridad & cumplimiento, vaya al Simulador **de ataques de administración** de \> **amenazas.**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6c6b8-181">En la **página Simular ataques,** realice una de las siguientes selecciones en función del tipo de campaña que desee crear:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="6c6b8-182">En la **sección Phishing de lanza (recolección** de credenciales), haga clic **en Iniciar ataque** o haga clic en Ataque de inicio **detalles** de \> **ataque.**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="6c6b8-183">En la sección Phishing de lanza **(datos adjuntos),** haga clic **en Iniciar ataque** o haga clic en **Detalles de** ataque \> **Iniciar ataque**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="6c6b8-184">El **Asistente para configurar ataques de** suplantación de identidad comienza en un nuevo flyout.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="6c6b8-185">En el **paso** Inicio, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6c6b8-186">En el **cuadro** Nombre, escriba un nombre para mostrar único para la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="6c6b8-187">No haga clic en **Usar plantilla**, porque creará el mensaje de correo electrónico más adelante en el asistente.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="6c6b8-188">Haga **clic en Usar plantilla** y seleccione una plantilla de correo electrónico integrada o personalizada.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="6c6b8-189">Después de seleccionar la plantilla, **el** cuadro Nombre se rellena automáticamente en función de la plantilla, pero puede cambiar el nombre.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6c6b8-190">![Página de inicio de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="6c6b8-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="6c6b8-191">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6c6b8-192">En el **paso Destinatarios de** destino, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6c6b8-193">Haga **clic en Libreta de** direcciones para seleccionar los destinatarios (usuarios o grupos) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="6c6b8-194">Cada destinatario de destino debe tener un Exchange Online buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="6c6b8-195">Si hace clic **en Filtrar y** **aplicar** sin especificar un criterio de búsqueda, todos los destinatarios se devuelven y se agregan a la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="6c6b8-196">Haga **clic en** Importar **y,** a continuación, en Importar archivo para importar un valor separado por comas (CSV) o un archivo de direcciones de correo electrónico separados por líneas.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="6c6b8-197">Cada línea debe contener la dirección de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="6c6b8-198">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6c6b8-199">En el **paso Configurar detalles de correo** electrónico, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="6c6b8-200">Si seleccionó una plantilla en el paso **Inicio,** la mayoría de estos valores ya están configurados, pero puede cambiarlos.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="6c6b8-201">**From (Name):** el nombre para mostrar que se usa para el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="6c6b8-202">**From (Email):** la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="6c6b8-203">Puede escribir una dirección de correo electrónico real o falsa desde el dominio de correo electrónico de su organización o puede escribir una dirección de correo electrónico externa real o falsa.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="6c6b8-204">Una dirección de correo electrónico del remitente válida de su organización se resolverá realmente en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="6c6b8-205">Dirección URL del servidor de inicio de sesión **de phishing:** haga clic en la lista desplegable y seleccione una de las direcciones URL disponibles de la lista.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="6c6b8-206">Esta es la dirección URL en la que los usuarios tendrán la tentación de hacer clic.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="6c6b8-207">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-207">The choices are:</span></span>

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
     > - <span data-ttu-id="6c6b8-208">Todas las direcciones URL son http intencionadamente, no https.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="6c6b8-209">Un servicio de reputación de direcciones URL puede identificar una o varias de estas direcciones URL como no seguras.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="6c6b8-210">Compruebe la disponibilidad de la dirección URL en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="6c6b8-211">Es necesario seleccionar una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-211">You are required to select a URL.</span></span> <span data-ttu-id="6c6b8-212">En el caso de las campañas de **phishing (datos adjuntos),** puedes quitar el vínculo del  cuerpo del mensaje en el siguiente paso (de lo contrario, el mensaje contendrá un vínculo y un archivo adjunto).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="6c6b8-213">**Tipo de datos adjuntos:** esta configuración solo está disponible en campañas **de phishing de** lanza (datos adjuntos).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="6c6b8-214">Haga clic en la lista desplegable **y seleccione.DOCX** o **.PDF** de la lista.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="6c6b8-215">**Nombre de datos adjuntos:** esta configuración solo está disponible en campañas **de phishing (datos adjuntos)** de Lanza.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="6c6b8-216">Escriba un nombre de archivo para los .docx o .pdf datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="6c6b8-217">**Dirección URL de página de aterrizaje** personalizada: escriba una página de aterrizaje opcional en la que los usuarios se toman si hacen clic en el vínculo de suplantación de identidad y escriben sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="6c6b8-218">Este vínculo reemplaza la página de aterrizaje predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-218">This link replaces the default landing page.</span></span> <span data-ttu-id="6c6b8-219">Por ejemplo, si tiene formación de reconocimiento interno, puede especificar esa dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="6c6b8-220">**Asunto:** el **campo Asunto** del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="6c6b8-221">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6c6b8-222">En el **paso Redacción de correo** electrónico, cree el cuerpo del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="6c6b8-223">Si seleccionó una plantilla en el paso **Inicio,** el cuerpo del mensaje ya está configurado, pero puede personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="6c6b8-224">Puede usar la pestaña **Correo** electrónico (un editor HTML enriquecido) o la **pestaña** Origen (código HTML sin formato).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="6c6b8-225">El formato HTML puede ser tan simple o complejo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="6c6b8-226">Puede insertar imágenes y texto para mejorar la fiabilidad del mensaje en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="6c6b8-227">`${username}` inserta el nombre del destinatario.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="6c6b8-228">`${loginserverurl}`inserta el valor **de la dirección URL del servidor de inicio de sesión de phishing.**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="6c6b8-229">Para las campañas de suplantación de identidad **(datos adjuntos),** debes quitar el vínculo  del cuerpo del mensaje (de lo contrario, el mensaje contendrá un vínculo y un archivo adjunto, y los clics de vínculo no se realizarán en una campaña de datos adjuntos).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6c6b8-230">![Redacción del cuerpo del correo electrónico](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="6c6b8-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="6c6b8-231">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6c6b8-232">En el **paso Confirmar,** haga clic **en Finalizar** para iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="6c6b8-233">El mensaje de suplantación de identidad se entrega a los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="6c6b8-234">Campañas de ataque con contraseña</span><span class="sxs-lookup"><span data-stu-id="6c6b8-234">Password attack campaigns</span></span>

<span data-ttu-id="6c6b8-235">Un *ataque de contraseña* intenta adivinar las contraseñas de las cuentas de usuario de una organización, normalmente después de que el atacante haya identificado una o más cuentas de usuario válidas.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="6c6b8-236">En Attack Simulator, hay dos tipos diferentes de campañas de ataque con contraseña disponibles para probar la complejidad de las contraseñas de los usuarios:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="6c6b8-237">Contraseña de fuerza bruta (ataque  de **diccionario):** una fuerza bruta o un ataque de diccionario usa un archivo de diccionario grande de contraseñas en una cuenta de usuario con la esperanza de que una de ellas funcione (muchas contraseñas en una cuenta). </span><span class="sxs-lookup"><span data-stu-id="6c6b8-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="6c6b8-238">Los bloqueos incorrectos de contraseñas ayudan a disuadir los ataques de contraseña de fuerza bruta.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="6c6b8-239">Para el ataque de diccionario, puede especificar una o varias contraseñas para probar (introducidas manualmente o en un archivo cargado) y puede especificar uno o varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="6c6b8-240">**Ataque de spray de contraseña:** un ataque de *spray* de contraseña usa la misma contraseña cuidadosamente considerada en una lista de cuentas de usuario (una contraseña en muchas cuentas).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="6c6b8-241">Los ataques de spray de contraseñas son más difíciles de detectar que los ataques de contraseña de fuerza bruta (la probabilidad de éxito aumenta cuando un atacante intenta una contraseña en decenas o cientos de cuentas sin el riesgo de que se bloquee la contraseña incorrecta del usuario).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="6c6b8-242">Para el ataque de spray de contraseña, solo puede especificar una contraseña para probar y puede especificar uno o varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="6c6b8-243">Los ataques de contraseña en Attack Simulator pasan solicitudes de autenticación básicas de nombre de usuario y contraseña a un punto de conexión, por lo que también funcionan con otros métodos de autenticación (AD FS, sincronización de hash de contraseña, paso a través, PingFederate, etc.).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="6c6b8-244">Para los usuarios que tienen MFA habilitado, incluso si el ataque de contraseña intenta su contraseña real, el  intento siempre se registrará como un error (es decir, los usuarios de MFA nunca aparecerán en el recuento de intentos correctos de la campaña).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="6c6b8-245">Este es el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-245">This is the expected result.</span></span> <span data-ttu-id="6c6b8-246">MFA es un método principal para ayudar a proteger contra ataques de contraseña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="6c6b8-247">Crear e iniciar una campaña de ataque de contraseña</span><span class="sxs-lookup"><span data-stu-id="6c6b8-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="6c6b8-248">En el Centro de seguridad & cumplimiento, vaya al Simulador **de ataques de administración** de \> **amenazas.**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6c6b8-249">En la **página Simular ataques,** realice una de las siguientes selecciones en función del tipo de campaña que desee crear:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="6c6b8-250">En la sección Contraseña de fuerza bruta **(ataque** de diccionario), haga clic **en Iniciar ataque** o haga clic en **Detalles** de ataque \> **Iniciar ataque**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="6c6b8-251">en la **sección Ataque de spray de contraseña,** haga clic en Iniciar **ataque** o haga clic en **Detalles de** ataque Iniciar \> **ataque**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="6c6b8-252">El **Asistente para configurar ataque de** contraseña comienza en un nuevo menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="6c6b8-253">En el **paso Inicio,** escriba un nombre para mostrar único para la campaña y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="6c6b8-254">En el **paso Usuarios de** destino, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6c6b8-255">Haga **clic en Libreta de** direcciones para seleccionar los destinatarios (usuarios o grupos) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="6c6b8-256">Cada destinatario de destino debe tener un Exchange Online buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="6c6b8-257">Si hace clic **en Filtrar y** **aplicar** sin especificar un criterio de búsqueda, todos los destinatarios se devuelven y se agregan a la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="6c6b8-258">Haga **clic en** Importar **y,** a continuación, en Importar archivo para importar un valor separado por comas (CSV) o un archivo de direcciones de correo electrónico separados por líneas.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="6c6b8-259">Cada línea debe contener la dirección de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="6c6b8-260">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6c6b8-261">En el **paso Elegir configuración de** ataque, elija qué hacer en función del tipo de campaña:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="6c6b8-262">**Contraseña de fuerza bruta (ataque de diccionario):** realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="6c6b8-263">**Escribir contraseñas manualmente:** en el **cuadro Presione entrar para agregar** una contraseña, escriba una contraseña y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="6c6b8-264">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="6c6b8-265">**Upload contraseñas** de un archivo de diccionario: haga clic en **Upload** para importar un archivo de texto existente que contenga una contraseña en cada línea y una última línea en blanco.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="6c6b8-266">El archivo de texto debe tener 10 MB o menos de tamaño y no puede contener más de 30000 contraseñas.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="6c6b8-267">**Ataque de spray de** contraseña: en **las contraseñas que** se deben usar en el cuadro de ataque, escriba una contraseña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="6c6b8-268">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6c6b8-269">En el **paso Confirmar,** haga clic **en Finalizar** para iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="6c6b8-270">Las contraseñas que especificó se probarán en los usuarios que especificó.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="6c6b8-271">Ver los resultados de la campaña</span><span class="sxs-lookup"><span data-stu-id="6c6b8-271">View campaign results</span></span>

<span data-ttu-id="6c6b8-272">Después de iniciar una campaña, puedes comprobar el progreso y los resultados en la página **principal Simular ataques.**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="6c6b8-273">Las campañas activas mostrarán una barra de estado, un valor de porcentaje completado y el recuento "(usuarios completados) de (usuarios totales)".</span><span class="sxs-lookup"><span data-stu-id="6c6b8-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="6c6b8-274">Al hacer clic **en el** botón Actualizar se actualizará el progreso de las campañas activas.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="6c6b8-275">También puedes hacer clic en **Finalizar** para detener una campaña activa.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="6c6b8-276">Una vez finalizada la campaña, el estado cambia a **Ataque completado.**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="6c6b8-277">Para ver los resultados de la campaña, haga una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="6c6b8-278">En la página **principal Simular ataques,** haga clic en **Ver informe** bajo el nombre de la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="6c6b8-279">En la página **principal Simular ataques,** haga clic **en Detalles de** ataque en la sección para el tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="6c6b8-280">En la **página Detalles de** ataque que se abre, selecciona la campaña en la sección Historial **de** ataques.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="6c6b8-281">Cualquiera de las acciones anteriores te llevará a una página denominada **Detalles de ataque.**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="6c6b8-282">La información disponible en esta página para cada tipo de campaña se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="6c6b8-283">Resultados de campaña de phishing de lanza (recolección de credenciales)</span><span class="sxs-lookup"><span data-stu-id="6c6b8-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="6c6b8-284">La siguiente información está disponible en la página **Detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6c6b8-285">Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6c6b8-286">**Total de usuarios dirigidos**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-286">**Total users targeted**</span></span>

- <span data-ttu-id="6c6b8-287">**Intentos correctos:** el número de usuarios que hicieron clic en el **vínculo** e introdujeron sus credenciales *(cualquier valor* de nombre de usuario y contraseña).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="6c6b8-288">**Tasa de éxito general:** porcentaje calculado por **intentos correctos**  /  **Los usuarios totales destinados** a .</span><span class="sxs-lookup"><span data-stu-id="6c6b8-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6c6b8-289">**Haga clic más** rápido: cuánto tiempo tardó el primer usuario en hacer clic en el vínculo después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="6c6b8-290">**Promedio de clic:** la suma de cuánto tiempo tardó todo el mundo en hacer clic en el vínculo dividido por el número de usuarios que hicieron clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="6c6b8-291">**Haga clic en Tasa de** éxito: porcentaje calculado por (número de usuarios que han hecho clic en el vínculo) / Total de usuarios **dirigidos**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="6c6b8-292">**Credenciales más rápidas:** cuánto tiempo tardó el primer usuario en escribir sus credenciales después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="6c6b8-293">**Promedio de credenciales:** la suma del tiempo que todos tardaron en escribir sus credenciales divididas por el número de usuarios que introdujeron sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="6c6b8-294">**Tasa de éxito de credenciales:** porcentaje calculado por (número de usuarios que especificaron sus credenciales) / **Total de usuarios dirigidos**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="6c6b8-295">Gráfico de barras que muestra los números **de vínculos y** **credenciales proporcionados** por día.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="6c6b8-296">Gráfico de círculo que muestra los **porcentajes Vínculo hecho clic,** **Credencial** suministrada y **Ninguno** para la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="6c6b8-297">En **la sección Usuarios comprometidos** se enumeran los detalles de los usuarios que han hecho clic en el vínculo:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="6c6b8-298">La dirección de correo electrónico del usuario</span><span class="sxs-lookup"><span data-stu-id="6c6b8-298">The user's email address</span></span>

  - <span data-ttu-id="6c6b8-299">La fecha y hora en que hicieron clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="6c6b8-300">Dirección IP del cliente.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-300">The client IP address.</span></span>

  - <span data-ttu-id="6c6b8-301">Detalles sobre la versión del usuario de Windows explorador web.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="6c6b8-302">Puede hacer clic **en Exportar** para exportar los resultados a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="6c6b8-303">Resultados de campaña de phishing (datos adjuntos) de Spear</span><span class="sxs-lookup"><span data-stu-id="6c6b8-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="6c6b8-304">La siguiente información está disponible en la página **Detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6c6b8-305">Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6c6b8-306">**Total de usuarios dirigidos**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-306">**Total users targeted**</span></span>

- <span data-ttu-id="6c6b8-307">**Intentos correctos:** el número de usuarios que abrieron o descargaron y abrieron los datos adjuntos (la vista previa no cuenta).</span><span class="sxs-lookup"><span data-stu-id="6c6b8-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="6c6b8-308">**Tasa de éxito general:** porcentaje calculado por **intentos correctos**  /  **Los usuarios totales destinados** a .</span><span class="sxs-lookup"><span data-stu-id="6c6b8-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6c6b8-309">**Tiempo de apertura de datos adjuntos más** rápido: cuánto tiempo tardó el primer usuario en abrir los datos adjuntos después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="6c6b8-310">**Tiempo medio de apertura de** datos adjuntos: la suma de cuánto tiempo tardó todo el mundo en abrir los datos adjuntos dividido por el número de usuarios que abrieron los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="6c6b8-311">**Tasa de éxito de** apertura de datos adjuntos: porcentaje calculado por (número de usuarios que abrieron los datos adjuntos) / **Total de usuarios dirigidos**.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="6c6b8-312">Resultados de la campaña Fuerza bruta de contraseña (ataque de diccionario)</span><span class="sxs-lookup"><span data-stu-id="6c6b8-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="6c6b8-313">La siguiente información está disponible en la página **Detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6c6b8-314">Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6c6b8-315">**Total de usuarios dirigidos**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-315">**Total users targeted**</span></span>

- <span data-ttu-id="6c6b8-316">**Intentos correctos:** el número de usuarios que se encontró que estaban usando una de las contraseñas especificadas.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="6c6b8-317">**Tasa de éxito general:** porcentaje calculado por **intentos correctos**  /  **Los usuarios totales destinados** a .</span><span class="sxs-lookup"><span data-stu-id="6c6b8-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6c6b8-318">La **sección Usuarios en peligro** enumera las direcciones de correo electrónico de los usuarios afectados.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="6c6b8-319">Puede hacer clic **en Exportar** para exportar los resultados a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="6c6b8-320">Resultados de la campaña de ataque por spray de contraseña</span><span class="sxs-lookup"><span data-stu-id="6c6b8-320">Password spray attack campaign results</span></span>

<span data-ttu-id="6c6b8-321">La siguiente información está disponible en la página **Detalles de ataque** para cada campaña:</span><span class="sxs-lookup"><span data-stu-id="6c6b8-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6c6b8-322">Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6c6b8-323">**Total de usuarios dirigidos**</span><span class="sxs-lookup"><span data-stu-id="6c6b8-323">**Total users targeted**</span></span>

- <span data-ttu-id="6c6b8-324">**Intentos correctos:** el número de usuarios que se encontró que estaban usando la contraseña especificada.</span><span class="sxs-lookup"><span data-stu-id="6c6b8-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="6c6b8-325">**Tasa de éxito general:** porcentaje calculado por **intentos correctos**  /  **Los usuarios totales destinados** a .</span><span class="sxs-lookup"><span data-stu-id="6c6b8-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
