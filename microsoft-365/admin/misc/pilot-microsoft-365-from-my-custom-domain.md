---
title: Prueba piloto de Microsoft 365 desde mi dominio personalizado
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información acerca de cómo probar la funcionalidad de correo electrónico de mi dominio personalizado en un buzón de Microsoft 365 usando solo dos cuentas de prueba.
ms.openlocfilehash: 8bb04edc9a7879edc2094f1fed667d5956174ea3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295039"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="03f35-103">Prueba piloto de Microsoft 365 desde mi dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="03f35-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="03f35-104">Puede realizar pruebas piloto de Microsoft 365 con estos requisitos y limitaciones:</span><span class="sxs-lookup"><span data-stu-id="03f35-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="03f35-105">Su proveedor de correo electrónico actual debe proporcionar el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="03f35-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="03f35-106">Debe administrar los registros DNS de Microsoft 365 en su proveedor de host DNS, en lugar de hacer que Microsoft 365 administre estos registros por usted.</span><span class="sxs-lookup"><span data-stu-id="03f35-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="03f35-107">Para obtener más información, vea [Agregar registros DNS para conectar su dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="03f35-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="03f35-108">La información de disponibilidad de los usuarios en el otro servidor de correo electrónico no está disponible.</span><span class="sxs-lookup"><span data-stu-id="03f35-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="03f35-109">Los administradores no pueden administrar todas las cuentas de usuario desde una sola ubicación.</span><span class="sxs-lookup"><span data-stu-id="03f35-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="03f35-110">Es posible que los usuarios no puedan usar el filtrado de correo no deseado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03f35-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="03f35-111">Configurar una prueba piloto de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03f35-111">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="03f35-112">Siga estos pasos para configurar una prueba piloto de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="03f35-112">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="03f35-113">Paso 1: iniciar sesión en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03f35-113">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="03f35-114">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="03f35-114">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="03f35-115">Seleccione **Configuración** > **Dominios** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="03f35-115">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="03f35-116">Paso 2: comprobar que es el propietario del dominio que quiere usar</span><span class="sxs-lookup"><span data-stu-id="03f35-116">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="03f35-117">En la página **Dominios**, seleccione **Agregar dominio**.</span><span class="sxs-lookup"><span data-stu-id="03f35-117">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="03f35-118">Escriba el nombre del dominio en el cuadro, seleccione **Usar este dominio** y, a continuación, seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="03f35-118">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="03f35-119">Seleccione los servicios que desee probar con su dominio, como el correo electrónico y la mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="03f35-119">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="03f35-120">En la página **Comprobar** dominio, siga las instrucciones paso a paso y, a continuación, haga clic en y **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="03f35-120">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="03f35-121">Se tarda entre unos minutos y 72 horas en que los cambios en el DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="03f35-121">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="03f35-122">Cuando la comprobación se realice correctamente, se le pedirá que modifique los registros de DNS.</span><span class="sxs-lookup"><span data-stu-id="03f35-122">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="03f35-123">Paso 3: marcar el dominio como compartido en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="03f35-123">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="03f35-124">En el Centro de administración de Exchange, en la sección **Flujo de correo**, seleccione **Dominios aceptados** y, a continuación, seleccione el dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="03f35-124">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="03f35-125">Haga doble clic para abrir la ventana y, a continuación, seleccione **retransmisión interna**.</span><span class="sxs-lookup"><span data-stu-id="03f35-125">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="03f35-126">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="03f35-126">Select **Save**.</span></span>

    <span data-ttu-id="03f35-127">Esta configuración puede tardar unos minutos en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="03f35-127">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="03f35-128">Paso 4: desbloquear el servidor de correo electrónico existente (opcional)</span><span class="sxs-lookup"><span data-stu-id="03f35-128">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="03f35-129">Microsoft 365 usa Exchange Online Protection (EOP) para la protección contra correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="03f35-129">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="03f35-130">EOP podría bloquear el servidor de correo existente si detecta un alto volumen de spam que el servidor de correo actual reenviará.</span><span class="sxs-lookup"><span data-stu-id="03f35-130">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="03f35-131">Si confía en la protección contra correo no deseado para su proveedor de correo electrónico, puede desbloquear el servidor de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03f35-131">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="03f35-132">Desbloquear el servidor de correo electrónico existente permite que el spam que llega a través del servidor original llegue a los buzones de Microsoft 365, por lo que no se puede evaluar la eficacia de Microsoft 365 para evitar el spam.</span><span class="sxs-lookup"><span data-stu-id="03f35-132">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="03f35-133">En el panel de navegación del Centro de administración de Exchange, seleccione **Protección**y, a continuación, seleccione **Filtro de conexión**.</span><span class="sxs-lookup"><span data-stu-id="03f35-133">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="03f35-134">En la **Lista de direcciones IP permitidas**, seleccione **+**, y agregue la dirección IP para el servidor de correo electrónico a su proveedor de correo electrónico actual.</span><span class="sxs-lookup"><span data-stu-id="03f35-134">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="03f35-135">Paso 5: crear cuentas de usuario y configurar la dirección de respuesta principal</span><span class="sxs-lookup"><span data-stu-id="03f35-135">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="03f35-136">En el Centro de administración de Microsoft 365 panel de navegación izquierdo, seleccione **Usuarios** > **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="03f35-136">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="03f35-137">Para crear dos cuentas de prueba, agregue dos usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="03f35-137">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="03f35-138">Para cada cuenta, seleccione **+ Agregar un usuario**, y rellene la información necesaria, incluyendo el método de contraseña que quiere probar.</span><span class="sxs-lookup"><span data-stu-id="03f35-138">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="03f35-139">Para asegurarse de que el correo electrónico de un usuario siga siendo el mismo, el campo **Nombre de usuario** tiene que coincidir con la dirección de correo electrónico actual del usuario.</span><span class="sxs-lookup"><span data-stu-id="03f35-139">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="03f35-140">Elija la licencia adecuada, haga clic en **Siguiente**y, después, haga clic en **Finalizar la agregación**.</span><span class="sxs-lookup"><span data-stu-id="03f35-140">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="03f35-141">Junto a **Nombre de usuario**, seleccione su nombre de dominio personalizado de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="03f35-141">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="03f35-142">Seleccione **Crear** > **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="03f35-142">Select **Create** > **Close**.</span></span>

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a><span data-ttu-id="03f35-143">Paso 6: \*\*configurar el correo para que fluya desde Microsoft 365 u Office 365 hacia el servidor de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="03f35-143">Step 6: \*\*Configure mail to flow from Microsoft 365 or Office 365 to Email server</span></span>

<span data-ttu-id="03f35-144">Para lograr esto, hay dos pasos:</span><span class="sxs-lookup"><span data-stu-id="03f35-144">There are two steps for this:</span></span>

1. <span data-ttu-id="03f35-145">Configurar el entorno de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="03f35-145">Configure your Microsoft 365 or Office 365 environment.</span></span>

2. <span data-ttu-id="03f35-146">Configurar un conector desde Microsoft 365 u Office 365 hacia su servidor de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="03f35-146">Set up a connector from Microsoft 365 or Office 365 to your email server.</span></span>

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a><span data-ttu-id="03f35-147">1. Configurar el entorno de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="03f35-147">1. Configure your Microsoft 365 or Office 365 environment</span></span>

<span data-ttu-id="03f35-148">Asegúrese de que ha realizado lo siguiente en Microsoft 365 u Office 365:</span><span class="sxs-lookup"><span data-stu-id="03f35-148">Make sure you have completed the following in Microsoft 365 or Office 365:</span></span>

1. <span data-ttu-id="03f35-149">Para configurar conectores, necesita permisos asignados antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="03f35-149">To set up connectors, you need permissions assigned before you can begin.</span></span> <span data-ttu-id="03f35-150">Para comprobar qué permisos necesita, consulte la entrada sobre conectores de Microsoft 365 y Office 365 en el tema [Permisos de características en EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop).</span><span class="sxs-lookup"><span data-stu-id="03f35-150">To check what permissions you need, see the Microsoft 365 and Office 365 connectors entry in the [Feature permissions in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop) topic.</span></span>

2. <span data-ttu-id="03f35-151">Si desea que EOP o Exchange Online retransmitan correo electrónico desde los servidores de correo electrónico a Internet, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="03f35-151">If you want EOP or Exchange Online to relay email from your email servers to the Internet, either:</span></span>

   - <span data-ttu-id="03f35-152">Use un certificado configurado con un nombre de sujeto que coincida con un dominio aceptado en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="03f35-152">Use a certificate configured with a subject name that matches an accepted domain in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="03f35-153">Se recomienda que el nombre común del certificado o el nombre alternativo del sujeto coincida con el dominio SMTP principal de la organización.</span><span class="sxs-lookup"><span data-stu-id="03f35-153">We recommend that your certificate's common name or subject alternative name matches the primary SMTP domain for your organization.</span></span> <span data-ttu-id="03f35-154">Para obtener más información, consulte [Requisitos previos para su entorno de correo electrónico local](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span><span class="sxs-lookup"><span data-stu-id="03f35-154">For details, see [Prerequisites for your on-premises email environment](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span></span>

   <span data-ttu-id="03f35-155">-O-</span><span class="sxs-lookup"><span data-stu-id="03f35-155">-OR-</span></span>

   - <span data-ttu-id="03f35-156">Asegúrese de que todos los dominios y subdominios del remitente de la organización estén configurados como dominios aceptados en Microsoft 365 y Office 365.</span><span class="sxs-lookup"><span data-stu-id="03f35-156">Make sure that all your organization sender domains and subdomains are configured as accepted domains in Microsoft 365 or Office 365.</span></span>

   <span data-ttu-id="03f35-157">Para obtener más información sobre la definición de dominios aceptados, consulte [Administrar los dominios aceptados en Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) y [Habilitar el flujo de correo para los subdominios en Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="03f35-157">For more information about defining accepted domains, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) and [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

3. <span data-ttu-id="03f35-158">Decida si desea usar reglas de flujo de correo (también conocidas como reglas de transporte) o nombres de dominio para entregar correo desde Microsoft 365 u Office 365 hacia los servidores de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="03f35-158">Decide whether you want to use mail flow rules (also known as transport rules) or domain names to deliver mail from Microsoft 365 or Office 365 to your email servers.</span></span> <span data-ttu-id="03f35-159">La mayoría de las empresas elige entregar el correo para todos los dominios aceptados.</span><span class="sxs-lookup"><span data-stu-id="03f35-159">Most businesses choose to deliver mail for all accepted domains.</span></span> <span data-ttu-id="03f35-160">Para obtener más información, consulte [Escenario: Enrutamiento de correo condicional en Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span><span class="sxs-lookup"><span data-stu-id="03f35-160">For more information, see [Scenario: Conditional mail routing in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span></span>

> [!NOTE]
> <span data-ttu-id="03f35-161">Puede configurar las reglas de flujo de correo tal y como se describen en [Acciones relacionadas con las reglas de flujo de correo de Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="03f35-161">You can set up mail flow rules as described in [Mail flow rule actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span> <span data-ttu-id="03f35-162">Por ejemplo, podría querer usar reglas de flujo de correo con conectores si actualmente su correo se dirigiera a través de listas de distribución hacia varios sitios.</span><span class="sxs-lookup"><span data-stu-id="03f35-162">For example, you might want to use mail flow rules with connectors if your mail is currently directed via distribution lists to multiple sites.</span></span>

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a><span data-ttu-id="03f35-163">2. Configurar un conector desde Microsoft 365 u Office 365 hacia su servidor de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="03f35-163">2. Set up a connector from Microsoft 365 or Office 365 to your email server</span></span>

<span data-ttu-id="03f35-164">Para crear un conector en Microsoft 365 u Office 365, haga clic en **Administración** y, luego, haga clic en **Exchange** para ir al Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="03f35-164">To create a connector in Microsoft 365 or Office 365, click **Admin**, and then click **Exchange** to go to the Exchange admin center.</span></span> <span data-ttu-id="03f35-165">A continuación, haga clic en **flujo de correo**, y en **conectores**.</span><span class="sxs-lookup"><span data-stu-id="03f35-165">Next, click **mail flow**, and click **connectors**.</span></span>

<span data-ttu-id="03f35-166">Configure los conectores con el asistente.</span><span class="sxs-lookup"><span data-stu-id="03f35-166">Set up connectors using the wizard.</span></span>

<span data-ttu-id="03f35-167">Para iniciar el asistente, haga clic en el símbolo más **+**.</span><span class="sxs-lookup"><span data-stu-id="03f35-167">To start the wizard, click the plus symbol **+**.</span></span> <span data-ttu-id="03f35-168">En la primera pantalla, elija **De** Office 365 y **Para** el servidor de correo electrónico de su organización.</span><span class="sxs-lookup"><span data-stu-id="03f35-168">On the first screen, choose **From** Office 365 and **To** Your Organization Mail server.</span></span>

<span data-ttu-id="03f35-169">Haga clic en **Siguiente**, y siga las instrucciones del asistente.</span><span class="sxs-lookup"><span data-stu-id="03f35-169">Click **Next**, and follow the instructions in the wizard.</span></span> <span data-ttu-id="03f35-170">Haga clic en los vínculos **Ayuda** o **Más información** si necesita más información.</span><span class="sxs-lookup"><span data-stu-id="03f35-170">Click the **Help** or **Learn More** links if you need more information.</span></span> <span data-ttu-id="03f35-171">El asistente le guiará a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="03f35-171">The wizard will guide you through setup.</span></span> <span data-ttu-id="03f35-172">Al final, asegúrese de que su conector se valida.</span><span class="sxs-lookup"><span data-stu-id="03f35-172">At the end, make sure your connector validates.</span></span> <span data-ttu-id="03f35-173">Si el conector no se valida, haga doble clic en el mensaje que se muestra para obtener más información, y consulte [Validar conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) para obtener ayuda con estos problemas.</span><span class="sxs-lookup"><span data-stu-id="03f35-173">If the connector does not validate, double-click the message displayed to get more information, and see [Validate connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) for help resolving issues.</span></span>



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="03f35-174">Paso 7: actualizar los registros DNS en su proveedor de host DNS</span><span class="sxs-lookup"><span data-stu-id="03f35-174">Step 7: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="03f35-175">Inicie sesión en el sitio web de su proveedor de host DNS y siga las instrucciones que encontrará en [Agregar registros DNS para conectar su dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="03f35-175">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="03f35-176">**Realice las dos siguientes excepciones:**</span><span class="sxs-lookup"><span data-stu-id="03f35-176">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="03f35-177">No cree un nuevo registro MX ni cambie su registro MX existente.</span><span class="sxs-lookup"><span data-stu-id="03f35-177">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="03f35-178">Si ya tiene un registro de Marco de Directivas de Remitente (SPF) para su anterior proveedor de correo electrónico, en lugar de crear un nuevo registro SPF (TXT) para Exchange Online, agregue "include:spf.protection.outlook.com" al registro TXT actual.</span><span class="sxs-lookup"><span data-stu-id="03f35-178">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="03f35-179">Por ejemplo, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="03f35-179">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="03f35-180">Si no tiene un registro de SPF, modifique el recomendado por Microsoft 365 para incluir el dominio de su proveedor de correo electrónico actual y agregue spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="03f35-180">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="03f35-181">Esto autoriza los mensajes salientes de ambos sistemas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="03f35-181">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="03f35-182">Paso 8: configurar el reenvío de correo electrónico en su proveedor actual</span><span class="sxs-lookup"><span data-stu-id="03f35-182">Step 8: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="03f35-183">En su proveedor de correo electrónico actual, configure el reenvío de las cuentas de correo electrónico de los usuarios a su dominio onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="03f35-183">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="03f35-184">Reenviar un buzón de correo del usuario A a usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="03f35-184">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="03f35-185">Reenviar el buzón de correo del usuario B a userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="03f35-185">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="03f35-186">Cuando finalice este paso, todo el correo electrónico enviado a usera@yourcompany.com y userb@yourcompany.com estará disponible en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03f35-186">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="03f35-187">Póngase en contacto con su proveedor de correo electrónico actual para ver los pasos detallados para configurar el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="03f35-187">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="03f35-188">No es necesario mantener una copia de los mensajes en el proveedor de correo electrónico actual.</span><span class="sxs-lookup"><span data-stu-id="03f35-188">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="03f35-189">La mayoría de los proveedores reenvían el correo electrónico dejando la dirección de respuesta del remitente intacta para que las respuestas pasen al remitente original.</span><span class="sxs-lookup"><span data-stu-id="03f35-189">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-9-test-mail-flow"></a><span data-ttu-id="03f35-190">Paso 9: comprobar el flujo de correo</span><span class="sxs-lookup"><span data-stu-id="03f35-190">Step 9: Test mail flow</span></span>

1. <span data-ttu-id="03f35-191">Inicie sesión en Outlook Web App con las credenciales del usuario A.</span><span class="sxs-lookup"><span data-stu-id="03f35-191">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="03f35-192">Realice estas pruebas:</span><span class="sxs-lookup"><span data-stu-id="03f35-192">Perform these tests:</span></span>

    - <span data-ttu-id="03f35-193">Pruebe el correo electrónico local de Microsoft enviando un correo electrónico, por ejemplo, al usuario B. El correo electrónico se entrega inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="03f35-193">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="03f35-194">En este escenario, el mensaje no se enruta al buzón del usuario B en su servidor original porque el buzón de Microsoft 365 es local.</span><span class="sxs-lookup"><span data-stu-id="03f35-194">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="03f35-195">Pruebe el correo electrónico para un usuario en el sistema de correo electrónico existente enviando un correo electrónico, por ejemplo, al usuario C. El correo electrónico se entrega en el buzón del usuario C en su servidor de correo original.</span><span class="sxs-lookup"><span data-stu-id="03f35-195">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="03f35-196">Compruebe que el reenvío se configuró correctamente desde una cuenta externa o desde una cuenta de correo electrónico del empleado en el sistema de correo electrónico existente.</span><span class="sxs-lookup"><span data-stu-id="03f35-196">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="03f35-197">Por ejemplo, desde la cuenta de servidor original del usuario C o de una cuenta de hotmail, envíe un correo electrónico al usuario A y compruebe que llega al buzón de Microsoft 365 para el usuario A.</span><span class="sxs-lookup"><span data-stu-id="03f35-197">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-10-move-mailbox-contents"></a><span data-ttu-id="03f35-198">Paso 10: mover contenido del buzón de correo</span><span class="sxs-lookup"><span data-stu-id="03f35-198">Step 10: Move mailbox contents</span></span>

<span data-ttu-id="03f35-199">Como va a mover solo dos usuarios de prueba, y el usuario A y el usuario B usan Outlook, puede mover el correo electrónico abriendo el archivo .PST antiguo en el nuevo perfil de Outlook y copie los mensajes, los elementos de calendario, los contactos, etc.</span><span class="sxs-lookup"><span data-stu-id="03f35-199">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="03f35-200">Para obtener más información, vea [Importar correo electrónico, contactos y calendario desde un archivo .pst de Outlook](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span><span class="sxs-lookup"><span data-stu-id="03f35-200">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="03f35-201">Una vez que se importan a las ubicaciones adecuadas en el buzón de correo de Microsoft 365, se puede acceder a ellos desde cualquier dispositivo y en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="03f35-201">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

<span data-ttu-id="03f35-202">Cuando haya más buzones involucrados, o si los empleados no están usando Outlook, puede usar las herramientas de migración disponibles en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="03f35-202">When more mailboxes are involved, or if employees are not using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="03f35-203">Para empezar, vaya al Centro de administración de Exchange y siga las instrucciones que encontrará en [Migrar el correo electrónico desde un servidor IMAP a los buzones de correo de Exchange Online](https://docs.microsoft.com/exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="03f35-203">To get started, go to Exchange admin center, and follow the directions in [Migrate Email from an IMAP Server to Exchange Online Mailboxes](https://docs.microsoft.com/exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes).</span></span>
