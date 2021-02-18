---
title: Simulador de ataques en Microsoft Defender para Office 365
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
description: Los administradores pueden aprender a usar el simulador de ataques para ejecutar ataques simulados de suplantación de identidad y contraseña en sus organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1e877900698d033cb99154b31e32fa04ff7d1010
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289586"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9b155-103">Simulador de ataques en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9b155-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9b155-104">**Se aplica a** [Microsoft Defender para Office 365 plan 2](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="9b155-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="9b155-105">Si su organización tiene Microsoft Defender para Office 365 Plan 2, que incluye capacidades de investigación y respuesta de [amenazas,](office-365-ti.md)puede usar el Simulador de ataques en el Centro de seguridad & Cumplimiento para ejecutar escenarios de ataque realistas en su organización.</span><span class="sxs-lookup"><span data-stu-id="9b155-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="9b155-106">Estos ataques simulados pueden ayudarte a identificar y encontrar usuarios vulnerables antes de que un ataque real repercuta en la línea inferior.</span><span class="sxs-lookup"><span data-stu-id="9b155-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="9b155-107">Lea este artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9b155-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="9b155-108">La experiencia del simulador de ataque v1 se ha cambiado al modo de solo lectura y se ha reemplazado por la formación del simulador de ataque que se describe en Introducción al entrenamiento [de simulación de ataques.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="9b155-108">Attack Simulator v1 experience has been switched to read-only mode and replaced by Attack simulator training that's described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
> <span data-ttu-id="9b155-109">Se ha deshabilitado la capacidad de iniciar nuevas simulaciones desde este sitio.</span><span class="sxs-lookup"><span data-stu-id="9b155-109">The ability to launch new simulations from this site has been disabled.</span></span> <span data-ttu-id="9b155-110">Sin embargo, aún puede tener acceso a los informes de simulaciones que se ejecutan durante un período de 90 días a partir del 24 de enero de 2021.</span><span class="sxs-lookup"><span data-stu-id="9b155-110">However, you can still access reports for simulations run for a period of 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9b155-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="9b155-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9b155-112">Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9b155-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="9b155-113">El simulador de ataques está disponible en **el simulador de** \> **ataques de administración de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="9b155-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="9b155-114">Vaya directamente al simulador de ataques, abra <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="9b155-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="9b155-115">Para obtener más información sobre la disponibilidad del Simulador de ataques en distintas suscripciones de Microsoft 365, vea la descripción del servicio de [Microsoft Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="9b155-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="9b155-116">Debe ser miembro de los grupos de roles **Administración** de la organización o **Administrador de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="9b155-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="9b155-117">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9b155-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="9b155-118">Tu cuenta debe configurarse para la autenticación multifactor (MFA) para crear y administrar campañas en el Simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="9b155-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="9b155-119">Para obtener instrucciones, [vea Configurar la autenticación multifactor.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="9b155-119">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="9b155-120">Las campañas de suplantación de identidad recopilarán y procesarán eventos durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="9b155-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="9b155-121">Los datos históricos de la campaña estarán disponibles hasta 90 días después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="9b155-122">La simulación de ataques y los datos relacionados con la formación se almacenan con otros datos de clientes para los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b155-122">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="9b155-123">Para obtener más información, [vea ubicaciones de datos de Microsoft 365.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="9b155-123">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="9b155-124">No hay ningún cmdlet de PowerShell correspondiente para el Simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="9b155-124">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="9b155-125">Campañas de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="9b155-125">Spear phishing campaigns</span></span>

<span data-ttu-id="9b155-126">*La suplantación* de identidad es un término genérico para los ataques de correo electrónico que intentan robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza.</span><span class="sxs-lookup"><span data-stu-id="9b155-126">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="9b155-127">La suplantación de identidad *(phishing)* es un ataque de suplantación de identidad dirigido que usa contenido centrado y personalizado que se adapta específicamente a los destinatarios de destino (normalmente, después de que el atacante los reconoce).</span><span class="sxs-lookup"><span data-stu-id="9b155-127">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="9b155-128">En el Simulador de ataques, hay disponibles dos tipos diferentes de campañas de suplantación de identidad de lanza:</span><span class="sxs-lookup"><span data-stu-id="9b155-128">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="9b155-129">**Phishing de punta (recolección de credenciales):** el ataque intenta convencer a los destinatarios para que haga clic en una dirección URL en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b155-129">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="9b155-130">Si hacen clic en el vínculo, se les pedirá que escriban sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="9b155-130">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="9b155-131">Si lo hacen, se les traslada a una de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="9b155-131">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="9b155-132">Una página predeterminada que explica que se trata de una prueba y ofrece sugerencias para reconocer mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="9b155-132">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Qué verán los usuarios si hacen clic en el vínculo de suplantación de identidad y escriben sus credenciales](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="9b155-134">Una página personalizada (URL) que especifique.</span><span class="sxs-lookup"><span data-stu-id="9b155-134">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="9b155-135">**Phishing de punta (datos adjuntos):** el ataque intenta convencer a los destinatarios para que abran un archivo adjunto .docx o .pdf en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b155-135">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="9b155-136">Los datos adjuntos contienen el mismo contenido del vínculo de suplantación de identidad predeterminado, pero la primera oración comienza con " , está viendo este mensaje como un mensaje de correo electrónico reciente que \<Display Name\> abrió...".</span><span class="sxs-lookup"><span data-stu-id="9b155-136">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="9b155-137">Actualmente, las campañas de suplantación de identidad de lanza en el simulador de ataques no expiran.</span><span class="sxs-lookup"><span data-stu-id="9b155-137">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="9b155-138">Crear una campaña de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="9b155-138">Create a spear phishing campaign</span></span>

<span data-ttu-id="9b155-139">Una parte importante de cualquier campaña de phishing de lanza es la apariencia del mensaje de correo electrónico que se envía a los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="9b155-139">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="9b155-140">Para crear y configurar el mensaje de correo electrónico, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="9b155-140">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="9b155-141">**Use una plantilla de correo electrónico** integrada: hay disponibles dos plantillas integradas: **Giveaway y** Payroll **Update**.</span><span class="sxs-lookup"><span data-stu-id="9b155-141">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="9b155-142">Puede personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="9b155-143">**Cree una plantilla de correo electrónico** reutilizable: después de crear y guardar la plantilla de correo electrónico, puede usarla de nuevo en futuras campañas de suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="9b155-143">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="9b155-144">Puede personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="9b155-145">**Cree el mensaje de correo electrónico en el** asistente: puede crear el mensaje de correo directamente en el asistente mientras crea e inicia la campaña de suplantación de identidad de lanza.</span><span class="sxs-lookup"><span data-stu-id="9b155-145">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="9b155-146">Paso 1 (opcional): Crear una plantilla de correo electrónico personalizada</span><span class="sxs-lookup"><span data-stu-id="9b155-146">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="9b155-147">Si va a usar una de las plantillas integradas o crear el mensaje de correo electrónico directamente en el asistente, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="9b155-147">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="9b155-148">En el Centro de seguridad & cumplimiento, vaya al simulador **de** \> **ataques de administración de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="9b155-148">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="9b155-149">En la **página Simular** ataques, en las secciones **Phishing (Recolección** de credenciales) o Phishing de lanza **(datos** adjuntos), haga clic en **Detalles de ataques.**</span><span class="sxs-lookup"><span data-stu-id="9b155-149">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="9b155-150">No importa dónde cree la plantilla.</span><span class="sxs-lookup"><span data-stu-id="9b155-150">It doesn't matter where you create the template.</span></span> <span data-ttu-id="9b155-151">Las opciones disponibles en la plantilla son las mismas para ambos tipos de ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="9b155-151">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="9b155-152">En la página **Detalles de** ataques que se  abre, en la sección **Plantillas** de suplantación de identidad, en el área Crear plantillas, haga clic en **Nueva plantilla.**</span><span class="sxs-lookup"><span data-stu-id="9b155-152">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="9b155-153">El **Asistente para configurar plantillas de** suplantación de identidad se inicia en un nuevo control desplegable.</span><span class="sxs-lookup"><span data-stu-id="9b155-153">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="9b155-154">En el **paso Inicio,** escriba un nombre para mostrar único para la plantilla y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9b155-154">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="9b155-155">En el paso **Configurar detalles de** correo electrónico, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9b155-155">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="9b155-156">**From (Name):** el nombre para mostrar que se usa para el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b155-156">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="9b155-157">**De (correo electrónico):** la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="9b155-157">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="9b155-158">**Dirección URL del servidor de inicio de** sesión de suplantación de identidad : haga clic en la lista desplegable y seleccione una de las direcciones URL disponibles en la lista.</span><span class="sxs-lookup"><span data-stu-id="9b155-158">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="9b155-159">Esta es la dirección URL en la que los usuarios estarán tentados a hacer clic.</span><span class="sxs-lookup"><span data-stu-id="9b155-159">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="9b155-160">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="9b155-160">The choices are:</span></span>

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
     > <span data-ttu-id="9b155-161">Un servicio de reputación de dirección URL puede identificar una o varias de estas direcciones URL como no seguras.</span><span class="sxs-lookup"><span data-stu-id="9b155-161">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="9b155-162">Compruebe la disponibilidad de la dirección URL en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="9b155-162">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="9b155-163">**Dirección URL de la página de** aterrizaje personalizada: escriba una página de aterrizaje opcional en la que se toman los usuarios si hacen clic en el vínculo de suplantación de identidad y escriben sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="9b155-163">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="9b155-164">Este vínculo reemplaza la página de aterrizaje predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9b155-164">This link replaces the default landing page.</span></span> <span data-ttu-id="9b155-165">Por ejemplo, si tiene formación interna de reconocimiento, puede especificar esa dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="9b155-165">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="9b155-166">**Categoría:** actualmente, no se usa esta configuración (se omite todo lo que escriba).</span><span class="sxs-lookup"><span data-stu-id="9b155-166">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="9b155-167">**Asunto:** el **campo Asunto** del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9b155-167">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="9b155-168">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9b155-168">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="9b155-169">En el **paso Redactar correo** electrónico, cree el cuerpo del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9b155-169">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="9b155-170">Puede usar la pestaña **Correo** electrónico (un editor HTML enriquecido) o la pestaña **Origen** (código HTML sin formato).</span><span class="sxs-lookup"><span data-stu-id="9b155-170">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="9b155-171">El formato HTML puede ser tan simple o complejo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9b155-171">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="9b155-172">Puede insertar imágenes y texto para mejorar la fiabilidad del mensaje en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9b155-172">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="9b155-173">`${username}` inserta el nombre del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9b155-173">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="9b155-174">`${loginserverurl}` inserta el valor de la dirección URL del servidor de inicio de **sesión de suplantación** de identidad del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="9b155-174">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="9b155-175">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9b155-175">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="9b155-176">En el paso **Confirmar,** haga clic **en Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9b155-176">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="9b155-177">Paso 2: Crear e iniciar la campaña de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="9b155-177">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="9b155-178">En el Centro de seguridad & cumplimiento, vaya al simulador **de** \> **ataques de administración de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="9b155-178">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="9b155-179">En la **página Simular ataques,** realiza una de las siguientes selecciones en función del tipo de campaña que quieras crear:</span><span class="sxs-lookup"><span data-stu-id="9b155-179">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="9b155-180">En la sección Phishing de lanza **(recolección** de credenciales), haga clic en **Iniciar** ataque o en Ataque de inicio **de detalles** de \> **ataque.**</span><span class="sxs-lookup"><span data-stu-id="9b155-180">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="9b155-181">En la sección Phishing de lanza **(datos adjuntos),** haga clic en **Iniciar** ataque o en Ataque de inicio **de detalles** de \> **ataque.**</span><span class="sxs-lookup"><span data-stu-id="9b155-181">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="9b155-182">El **Asistente para configurar ataques de** suplantación de identidad se inicia en un nuevo menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="9b155-182">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="9b155-183">En el **paso** Inicio, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9b155-183">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="9b155-184">En el **cuadro** Nombre, escriba un nombre para mostrar único para la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-184">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="9b155-185">No haga clic en **Usar plantilla** porque creará el mensaje de correo electrónico más adelante en el asistente.</span><span class="sxs-lookup"><span data-stu-id="9b155-185">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="9b155-186">Haga **clic en Usar plantilla** y seleccione una plantilla de correo electrónico integrada o personalizada.</span><span class="sxs-lookup"><span data-stu-id="9b155-186">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="9b155-187">Después de seleccionar la plantilla, **el** cuadro Nombre se rellena automáticamente en función de la plantilla, pero puede cambiar el nombre.</span><span class="sxs-lookup"><span data-stu-id="9b155-187">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9b155-188">![Página de inicio de suplantación de identidad](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="9b155-188">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="9b155-189">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9b155-189">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9b155-190">En el **paso Destinatarios de** destino, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9b155-190">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="9b155-191">Haga **clic en Libreta de** direcciones para seleccionar los destinatarios (usuarios o grupos) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-191">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="9b155-192">Cada destinatario de destino debe tener un buzón de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9b155-192">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="9b155-193">Si hace clic **en Filtrar** y **aplicar** sin especificar criterios de búsqueda, se devolverán todos los destinatarios y se agregarán a la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-193">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="9b155-194">Haga **clic en** Importar **y,** a continuación, importar archivos para importar un valor separado por comas (CSV) o un archivo de direcciones de correo electrónico separados por líneas.</span><span class="sxs-lookup"><span data-stu-id="9b155-194">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="9b155-195">Cada línea debe contener la dirección de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9b155-195">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="9b155-196">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9b155-196">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9b155-197">En el paso **Configurar detalles de** correo electrónico, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9b155-197">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="9b155-198">Si seleccionó una plantilla en el paso **Inicio,** la mayoría de estos valores ya están configurados, pero puede cambiarlos.</span><span class="sxs-lookup"><span data-stu-id="9b155-198">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="9b155-199">**From (Name):** el nombre para mostrar que se usa para el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b155-199">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="9b155-200">**De (correo electrónico):** la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="9b155-200">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="9b155-201">Puede escribir una dirección de correo electrónico real o falsa desde el dominio de correo electrónico de su organización o puede escribir una dirección de correo electrónico externa real o falsa.</span><span class="sxs-lookup"><span data-stu-id="9b155-201">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="9b155-202">Una dirección de correo electrónico de remitente válida de su organización realmente se resolverá en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9b155-202">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="9b155-203">**Dirección URL del servidor de inicio de** sesión de suplantación de identidad : haga clic en la lista desplegable y seleccione una de las direcciones URL disponibles en la lista.</span><span class="sxs-lookup"><span data-stu-id="9b155-203">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="9b155-204">Esta es la dirección URL en la que los usuarios estarán tentados a hacer clic.</span><span class="sxs-lookup"><span data-stu-id="9b155-204">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="9b155-205">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="9b155-205">The choices are:</span></span>

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
     > - <span data-ttu-id="9b155-206">Todas las direcciones URL son http intencionadamente, no https.</span><span class="sxs-lookup"><span data-stu-id="9b155-206">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="9b155-207">Un servicio de reputación de dirección URL puede identificar una o varias de estas direcciones URL como no seguras.</span><span class="sxs-lookup"><span data-stu-id="9b155-207">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="9b155-208">Compruebe la disponibilidad de la dirección URL en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="9b155-208">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="9b155-209">Debe seleccionar una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="9b155-209">You are required to select a URL.</span></span> <span data-ttu-id="9b155-210">Para **campañas de phishing (datos adjuntos),** puede quitar el vínculo del cuerpo del mensaje en  el siguiente paso (de lo contrario, el mensaje contendrá un vínculo y un archivo adjunto).</span><span class="sxs-lookup"><span data-stu-id="9b155-210">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="9b155-211">**Tipo de datos** adjuntos: esta configuración solo está disponible en las campañas **de phishing (datos adjuntos).**</span><span class="sxs-lookup"><span data-stu-id="9b155-211">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="9b155-212">Haga clic en la lista desplegable y seleccione **. DOCX** o **. PDF** de la lista.</span><span class="sxs-lookup"><span data-stu-id="9b155-212">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="9b155-213">**Nombre de los datos** adjuntos: esta configuración solo está disponible en las campañas **de phishing (datos adjuntos).**</span><span class="sxs-lookup"><span data-stu-id="9b155-213">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="9b155-214">Escriba un nombre de archivo para los datos adjuntos .docx o .pdf.</span><span class="sxs-lookup"><span data-stu-id="9b155-214">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="9b155-215">**Dirección URL de la página de** aterrizaje personalizada: escriba una página de aterrizaje opcional en la que se toman los usuarios si hacen clic en el vínculo de suplantación de identidad y escriben sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="9b155-215">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="9b155-216">Este vínculo reemplaza la página de aterrizaje predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9b155-216">This link replaces the default landing page.</span></span> <span data-ttu-id="9b155-217">Por ejemplo, si tiene formación interna de reconocimiento, puede especificar esa dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="9b155-217">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="9b155-218">**Asunto:** el **campo Asunto** del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9b155-218">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="9b155-219">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9b155-219">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="9b155-220">En el **paso Redactar correo** electrónico, cree el cuerpo del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9b155-220">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="9b155-221">Si seleccionó una plantilla en el paso **Inicio,** el cuerpo del mensaje ya está configurado, pero puede personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="9b155-221">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="9b155-222">Puede usar la pestaña **Correo** electrónico (un editor HTML enriquecido) o la pestaña **Origen** (código HTML sin formato).</span><span class="sxs-lookup"><span data-stu-id="9b155-222">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="9b155-223">El formato HTML puede ser tan simple o complejo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9b155-223">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="9b155-224">Puede insertar imágenes y texto para mejorar la fiabilidad del mensaje en el cliente de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9b155-224">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="9b155-225">`${username}` inserta el nombre del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9b155-225">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="9b155-226">`${loginserverurl}` inserta el valor de **la dirección URL del servidor de inicio de sesión de suplantación de** identidad .</span><span class="sxs-lookup"><span data-stu-id="9b155-226">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="9b155-227">En el caso de las campañas de **phishing (datos adjuntos),** debe quitar el  vínculo del cuerpo del mensaje (de lo contrario, el mensaje contendrá un vínculo y datos adjuntos, y los clics de vínculo no se realizarán en una campaña de datos adjuntos).</span><span class="sxs-lookup"><span data-stu-id="9b155-227">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9b155-228">![Cuerpo del correo electrónico de redacción](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="9b155-228">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="9b155-229">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9b155-229">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="9b155-230">En el **paso Confirmar,** haz clic **en Finalizar** para iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-230">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="9b155-231">El mensaje de suplantación de identidad se entrega a los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="9b155-231">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="9b155-232">Campañas de ataque de contraseña</span><span class="sxs-lookup"><span data-stu-id="9b155-232">Password attack campaigns</span></span>

<span data-ttu-id="9b155-233">Un *ataque de contraseña* intenta adivinar las contraseñas de las cuentas de usuario de una organización, normalmente después de que el atacante haya identificado una o más cuentas de usuario válidas.</span><span class="sxs-lookup"><span data-stu-id="9b155-233">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="9b155-234">En el Simulador de ataques, hay dos tipos diferentes de campañas de ataque de contraseñas disponibles para probar la complejidad de las contraseñas de los usuarios:</span><span class="sxs-lookup"><span data-stu-id="9b155-234">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="9b155-235">Contraseña de fuerza bruta (ataque  de **diccionario):** un ataque de fuerza bruta o diccionario usa un archivo de diccionario grande de contraseñas en una cuenta de usuario con la expectativa de que una de ellas funcione (muchas contraseñas en una cuenta). </span><span class="sxs-lookup"><span data-stu-id="9b155-235">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="9b155-236">Los bloqueos de contraseña incorrectos ayudan a disuadir los ataques de contraseña por fuerza bruta.</span><span class="sxs-lookup"><span data-stu-id="9b155-236">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="9b155-237">Para el ataque de diccionario, puede especificar una o varias contraseñas para probar (introducidas manualmente o en un archivo cargado) y puede especificar uno o varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="9b155-237">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="9b155-238">**Ataque de aspersión** de contraseña: un ataque de *aspersión* de contraseña usa la misma contraseña que se considera cuidadosamente en una lista de cuentas de usuario (una contraseña contra muchas cuentas).</span><span class="sxs-lookup"><span data-stu-id="9b155-238">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="9b155-239">Los ataques de aspersión de contraseña son más difíciles de detectar que los ataques de contraseña por fuerza bruta (la probabilidad de éxito aumenta cuando un atacante intenta una contraseña en decenas o cientos de cuentas sin el riesgo de que el usuario no pueda bloquear la contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="9b155-239">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="9b155-240">Para el ataque de aspersión de contraseña, solo puede especificar una contraseña para probar y puede especificar uno o varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="9b155-240">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="9b155-241">Los ataques de contraseña en el simulador de ataques pasan solicitudes de autenticación básicas de nombre de usuario y contraseña a un punto de conexión, por lo que también funcionan con otros métodos de autenticación (AD FS, sincronización de hash de contraseña, paso a través, PingFederate, etc.).</span><span class="sxs-lookup"><span data-stu-id="9b155-241">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="9b155-242">Para los usuarios que tienen mfa habilitado, incluso si el ataque de contraseña intenta su contraseña real, el  intento siempre se registrará como un error (es decir, los usuarios de MFA nunca aparecerán en el recuento de intentos correctos de la campaña).</span><span class="sxs-lookup"><span data-stu-id="9b155-242">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="9b155-243">Este es el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="9b155-243">This is the expected result.</span></span> <span data-ttu-id="9b155-244">MFA es un método principal para ayudar a proteger contra ataques de contraseña.</span><span class="sxs-lookup"><span data-stu-id="9b155-244">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="9b155-245">Crear e iniciar una campaña de ataque de contraseña</span><span class="sxs-lookup"><span data-stu-id="9b155-245">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="9b155-246">En el Centro de seguridad & cumplimiento, vaya al simulador **de** \> **ataques de administración de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="9b155-246">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="9b155-247">En la **página Simular ataques,** realiza una de las siguientes selecciones en función del tipo de campaña que quieras crear:</span><span class="sxs-lookup"><span data-stu-id="9b155-247">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="9b155-248">En la sección Contraseña de fuerza bruta **(ataque** de diccionario), haga clic en **Iniciar** ataque o en Ataque de inicio **de detalles** \> **del ataque.**</span><span class="sxs-lookup"><span data-stu-id="9b155-248">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="9b155-249">en la sección **Ataque de lanzamiento de contraseña,** haga clic en **Iniciar** ataque o en Ataque de inicio **de detalles** de \> **ataque.**</span><span class="sxs-lookup"><span data-stu-id="9b155-249">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="9b155-250">El **Asistente para configurar ataques de** contraseña se inicia en un nuevo menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="9b155-250">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="9b155-251">En el **paso Inicio,** escriba un nombre para mostrar único para la campaña y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="9b155-251">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="9b155-252">En el **paso Usuarios de** destino, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9b155-252">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="9b155-253">Haga **clic en Libreta de** direcciones para seleccionar los destinatarios (usuarios o grupos) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-253">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="9b155-254">Cada destinatario de destino debe tener un buzón de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9b155-254">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="9b155-255">Si hace clic **en Filtrar** y **aplicar** sin especificar criterios de búsqueda, se devolverán todos los destinatarios y se agregarán a la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-255">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="9b155-256">Haga **clic en** Importar **y,** a continuación, importar archivos para importar un valor separado por comas (CSV) o un archivo de direcciones de correo electrónico separados por líneas.</span><span class="sxs-lookup"><span data-stu-id="9b155-256">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="9b155-257">Cada línea debe contener la dirección de correo electrónico del destinatario.</span><span class="sxs-lookup"><span data-stu-id="9b155-257">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="9b155-258">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9b155-258">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9b155-259">En el paso **Elegir configuración de** ataque, elige qué hacer en función del tipo de campaña:</span><span class="sxs-lookup"><span data-stu-id="9b155-259">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="9b155-260">**Contraseña de fuerza bruta (ataque de diccionario):** siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9b155-260">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="9b155-261">**Escriba las contraseñas manualmente:** en el **cuadro Presione Entrar para agregar** una contraseña, escriba una contraseña y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="9b155-261">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="9b155-262">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9b155-262">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="9b155-263">**Cargar contraseñas desde un archivo de diccionario:** haga clic en Cargar para importar un archivo de texto existente que contenga una contraseña en cada línea y una última línea en blanco. </span><span class="sxs-lookup"><span data-stu-id="9b155-263">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="9b155-264">El archivo de texto debe tener un tamaño de 10 MB o menos y no puede contener más de 30000 contraseñas.</span><span class="sxs-lookup"><span data-stu-id="9b155-264">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="9b155-265">**Ataque de aspersión** de contraseña: en las **contraseñas que se usarán en** el cuadro de ataque, escriba una contraseña.</span><span class="sxs-lookup"><span data-stu-id="9b155-265">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="9b155-266">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9b155-266">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="9b155-267">En el **paso Confirmar,** haz clic **en Finalizar** para iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-267">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="9b155-268">Las contraseñas que especificó se probarán en los usuarios especificados.</span><span class="sxs-lookup"><span data-stu-id="9b155-268">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="9b155-269">Ver los resultados de la campaña</span><span class="sxs-lookup"><span data-stu-id="9b155-269">View campaign results</span></span>

<span data-ttu-id="9b155-270">Después de iniciar una campaña, puedes comprobar el progreso y los resultados en la página principal **simular ataques.**</span><span class="sxs-lookup"><span data-stu-id="9b155-270">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="9b155-271">Las campañas activas mostrarán una barra de estado, un valor de porcentaje completado y el recuento "(usuarios completados) de (total de usuarios)".</span><span class="sxs-lookup"><span data-stu-id="9b155-271">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="9b155-272">Al hacer **clic en el** botón Actualizar se actualizará el progreso de las campañas activas.</span><span class="sxs-lookup"><span data-stu-id="9b155-272">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="9b155-273">También puedes hacer clic en **Finalizar** para detener una campaña activa.</span><span class="sxs-lookup"><span data-stu-id="9b155-273">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="9b155-274">Cuando finaliza la campaña, el estado cambia a **Ataque completado.**</span><span class="sxs-lookup"><span data-stu-id="9b155-274">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="9b155-275">Puedes ver los resultados de la campaña mediante cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9b155-275">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="9b155-276">En la página **principal Simular ataques,** haz clic **en Ver informe** bajo el nombre de la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-276">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="9b155-277">En la página **principal Simular ataques,** haz clic **en Detalles de** ataque en la sección para el tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="9b155-277">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="9b155-278">En la **página Detalles de** ataque que se abre, selecciona la campaña en la sección Historial **de** ataques.</span><span class="sxs-lookup"><span data-stu-id="9b155-278">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="9b155-279">Cualquiera de las acciones anteriores te llevará a una página denominada **Detalles de ataque.**</span><span class="sxs-lookup"><span data-stu-id="9b155-279">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="9b155-280">La información disponible en esta página para cada tipo de campaña se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="9b155-280">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="9b155-281">Resultados de la campaña de phishing (recolección de credenciales)</span><span class="sxs-lookup"><span data-stu-id="9b155-281">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="9b155-282">La siguiente información está disponible en la página Detalles **de ataques** de cada campaña:</span><span class="sxs-lookup"><span data-stu-id="9b155-282">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="9b155-283">Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-283">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="9b155-284">**Total de usuarios dirigidos**</span><span class="sxs-lookup"><span data-stu-id="9b155-284">**Total users targeted**</span></span>

- <span data-ttu-id="9b155-285">**Intentos correctos:** el número de usuarios que han hecho clic en el vínculo y han **escrito** sus credenciales (cualquier *valor* de nombre de usuario y contraseña).</span><span class="sxs-lookup"><span data-stu-id="9b155-285">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="9b155-286">**Tasa de éxito general:** porcentaje calculado por **intentos correctos.** Total de usuarios a los que se  /  **ha dirigido .**</span><span class="sxs-lookup"><span data-stu-id="9b155-286">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="9b155-287">**Clic más rápido:** cuánto tiempo tardó el primer usuario en hacer clic en el vínculo después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-287">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="9b155-288">**Promedio de clic:** la suma de cuánto tiempo tardó todo el mundo en hacer clic en el vínculo dividido por el número de usuarios que hizo clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="9b155-288">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="9b155-289">**Porcentaje de éxito de** clic: porcentaje calculado por (número de usuarios que han hecho clic en el vínculo) / **Total de usuarios a los que se ha dirigido**.</span><span class="sxs-lookup"><span data-stu-id="9b155-289">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="9b155-290">**Credenciales más rápidas:** cuánto tiempo tardó el primer usuario en escribir sus credenciales después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-290">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="9b155-291">**Promedio de credenciales:** la suma del tiempo que todos tardaron en escribir sus credenciales divididas por el número de usuarios que especificaron sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="9b155-291">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="9b155-292">**Porcentaje de éxito de credenciales:** porcentaje calculado por (número de usuarios que especificaron sus credenciales) / **Total de usuarios a los** que se ha dirigido .</span><span class="sxs-lookup"><span data-stu-id="9b155-292">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="9b155-293">Gráfico de barras que muestra el vínculo en el que se **hizo** clic y los números **proporcionados por credenciales** por día.</span><span class="sxs-lookup"><span data-stu-id="9b155-293">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="9b155-294">Gráfico de círculo que muestra el vínculo en el que se **hizo** clic, **la** credencial proporcionada y los **porcentajes** ninguno de la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-294">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="9b155-295">La **sección Usuarios comprometidos** muestra los detalles de los usuarios que han hecho clic en el vínculo:</span><span class="sxs-lookup"><span data-stu-id="9b155-295">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="9b155-296">La dirección de correo electrónico del usuario</span><span class="sxs-lookup"><span data-stu-id="9b155-296">The user's email address</span></span>

  - <span data-ttu-id="9b155-297">Fecha y hora en que se hizo clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="9b155-297">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="9b155-298">La dirección IP del cliente.</span><span class="sxs-lookup"><span data-stu-id="9b155-298">The client IP address.</span></span>

  - <span data-ttu-id="9b155-299">Detalles sobre la versión del usuario de Windows y el explorador web.</span><span class="sxs-lookup"><span data-stu-id="9b155-299">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="9b155-300">Puede hacer clic **en Exportar** para exportar los resultados a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="9b155-300">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="9b155-301">Resultados de la campaña de phishing (datos adjuntos)</span><span class="sxs-lookup"><span data-stu-id="9b155-301">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="9b155-302">La siguiente información está disponible en la página Detalles **de ataques** de cada campaña:</span><span class="sxs-lookup"><span data-stu-id="9b155-302">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="9b155-303">Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-303">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="9b155-304">**Total de usuarios dirigidos**</span><span class="sxs-lookup"><span data-stu-id="9b155-304">**Total users targeted**</span></span>

- <span data-ttu-id="9b155-305">**Intentos** correctos: el número de usuarios que abrieron, descargaron y abrieron los datos adjuntos (la vista previa no cuenta).</span><span class="sxs-lookup"><span data-stu-id="9b155-305">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="9b155-306">**Tasa de éxito general:** porcentaje calculado por **intentos correctos.** Total de usuarios a los que se  /  **ha dirigido .**</span><span class="sxs-lookup"><span data-stu-id="9b155-306">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="9b155-307">**Tiempo de apertura de datos adjuntos más** rápido: cuánto tiempo tardó el primer usuario en abrir los datos adjuntos después de iniciar la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-307">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="9b155-308">**Tiempo medio de** apertura de datos adjuntos: la suma del tiempo que todos tardaron en abrir los datos adjuntos dividido por el número de usuarios que abrieron los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="9b155-308">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="9b155-309">**Tasa de éxito de** apertura de datos adjuntos: porcentaje calculado por (número de usuarios que abrieron los datos adjuntos) / **Total de usuarios a los** que se ha dirigido .</span><span class="sxs-lookup"><span data-stu-id="9b155-309">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="9b155-310">Resultados de la campaña de fuerza bruta de contraseña (ataque de diccionario)</span><span class="sxs-lookup"><span data-stu-id="9b155-310">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="9b155-311">La siguiente información está disponible en la página Detalles **de ataques** de cada campaña:</span><span class="sxs-lookup"><span data-stu-id="9b155-311">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="9b155-312">Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-312">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="9b155-313">**Total de usuarios dirigidos**</span><span class="sxs-lookup"><span data-stu-id="9b155-313">**Total users targeted**</span></span>

- <span data-ttu-id="9b155-314">**Intentos** correctos: el número de usuarios que se encontraron con una de las contraseñas especificadas.</span><span class="sxs-lookup"><span data-stu-id="9b155-314">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="9b155-315">**Tasa de éxito general:** porcentaje calculado por **intentos correctos.** Total de usuarios a los que se  /  **ha dirigido .**</span><span class="sxs-lookup"><span data-stu-id="9b155-315">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="9b155-316">En **la sección Usuarios en peligro** se enumeran las direcciones de correo electrónico de los usuarios afectados.</span><span class="sxs-lookup"><span data-stu-id="9b155-316">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="9b155-317">Puede hacer clic **en Exportar** para exportar los resultados a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="9b155-317">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="9b155-318">Resultados de la campaña de ataques por aspersión de contraseñas</span><span class="sxs-lookup"><span data-stu-id="9b155-318">Password spray attack campaign results</span></span>

<span data-ttu-id="9b155-319">La siguiente información está disponible en la página Detalles **de ataques** de cada campaña:</span><span class="sxs-lookup"><span data-stu-id="9b155-319">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="9b155-320">Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.</span><span class="sxs-lookup"><span data-stu-id="9b155-320">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="9b155-321">**Total de usuarios dirigidos**</span><span class="sxs-lookup"><span data-stu-id="9b155-321">**Total users targeted**</span></span>

- <span data-ttu-id="9b155-322">**Intentos** correctos: el número de usuarios que se encontraron con la contraseña especificada.</span><span class="sxs-lookup"><span data-stu-id="9b155-322">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="9b155-323">**Tasa de éxito general:** porcentaje calculado por **intentos correctos.** Total de usuarios a los que se  /  **ha dirigido .**</span><span class="sxs-lookup"><span data-stu-id="9b155-323">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
