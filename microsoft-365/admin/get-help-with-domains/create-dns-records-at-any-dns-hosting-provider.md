---
title: Agregar registros DNS para conectarse a su dominio
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: Aprenda a verificar su dominio y a crear registros DNS en cualquier proveedor de host DNS para Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: d6e8a5a0e23bf9bb9e302566a72b9e1cc6b7bff4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915655"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="ca978-103">Agregar registros DNS para conectarse a su dominio</span><span class="sxs-lookup"><span data-stu-id="ca978-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="ca978-104">Si ha comprado un dominio de un proveedor de host externo, puede conectarlo a Microsoft 365 actualizando los registros DNS de la cuenta del registrador.</span><span class="sxs-lookup"><span data-stu-id="ca978-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="ca978-105">Tras finalizar estos pasos, el dominio seguirá registrado en el host en el que compró el dominio, pero Microsoft 365 podrá usarlo para sus direcciones de correo electrónico (como usuario@sudominio.com) y otros servicios.</span><span class="sxs-lookup"><span data-stu-id="ca978-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="ca978-106">Si no agrega el dominio, los integrantes de la organización usarán el dominio onmicrosoft.com para las direcciones de correo electrónico hasta que lo agregue.</span><span class="sxs-lookup"><span data-stu-id="ca978-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="ca978-107">Es importante que agregue el dominio antes de agregar usuarios, para evitar tener que configurarlo dos veces.</span><span class="sxs-lookup"><span data-stu-id="ca978-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="ca978-108">[Consulte las preguntas frecuentes sobre los dominios](../setup/domains-faq.yml) si no encuentra lo que busca debajo.</span><span class="sxs-lookup"><span data-stu-id="ca978-108">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="ca978-109">Paso 1: Agregar un registro TXT o MX para comprobar que es el propietario del dominio</span><span class="sxs-lookup"><span data-stu-id="ca978-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="ca978-110">Se recomienda: comprobarlo con un registro TXT</span><span class="sxs-lookup"><span data-stu-id="ca978-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="ca978-111">En primer lugar, tiene que demostrar que es el propietario del dominio que quiere agregar a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca978-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="ca978-112">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com/) y seleccione **Mostrar todo** > **Configuración** > **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="ca978-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="ca978-113">En una nueva pestaña o ventana del explorador, inicie sesión en su proveedor de host DNS y, después, busque el lugar donde administra la configuración de DNS (por ejemplo, Configuración del archivo de zona, Administrar dominios, Administrador de dominios, Administrador de DNS).</span><span class="sxs-lookup"><span data-stu-id="ca978-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="ca978-114">Vaya a la página del administrador de DNS de su proveedor y agregue a su dominio el registro TXT indicado en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="ca978-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="ca978-115">Agregar este registro no afectará a su correo electrónico existente ni a otros servicios. Podrá quitarlo de forma segura una vez que su dominio se haya conectado a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca978-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="ca978-116">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ca978-116">Example:</span></span>
- <span data-ttu-id="ca978-117">Nombre TXT: `@`</span><span class="sxs-lookup"><span data-stu-id="ca978-117">TXT Name: `@`</span></span>
- <span data-ttu-id="ca978-118">Valor TXT: MS=ms######## (ID único del centro de administración)</span><span class="sxs-lookup"><span data-stu-id="ca978-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="ca978-119">TTL: `3600‎` (o el proveedor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="ca978-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="ca978-120">Guarde el registro, vuelva al centro de administración y, a continuación, seleccione **Comprobar**.</span><span class="sxs-lookup"><span data-stu-id="ca978-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="ca978-121">Por lo general, los cambios de registro tardan alrededor de 15 minutos en efectuarse, pero a veces puede tardar más.</span><span class="sxs-lookup"><span data-stu-id="ca978-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="ca978-122">Espere unos momentos y pruebe varias veces hasta detectar el cambio.</span><span class="sxs-lookup"><span data-stu-id="ca978-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="ca978-123">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="ca978-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="ca978-124">Comprobarlo con un registro MX</span><span class="sxs-lookup"><span data-stu-id="ca978-124">Verify with an MX record</span></span>

<span data-ttu-id="ca978-125">Si su registrador no permite agregar registros TXT, puede agregar un registro MX para comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="ca978-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="ca978-126">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com/) y seleccione **Mostrar todo** > **Configuración** > **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="ca978-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="ca978-127">En una nueva pestaña o ventana del explorador, inicie sesión en su proveedor de host DNS y, después, busque el lugar donde administra la configuración de DNS (por ejemplo, Configuración del archivo de zona, Administrar dominios, Administrador de dominios, Administrador de DNS).</span><span class="sxs-lookup"><span data-stu-id="ca978-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="ca978-128">Vaya a la página del administrador de DNS de su proveedor y agregue a su dominio el registro MX indicado en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="ca978-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="ca978-129">La **prioridad** de este registro MX debe ser la máxima de todos los registros MX existentes para el dominio.</span><span class="sxs-lookup"><span data-stu-id="ca978-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="ca978-130">De lo contrario, puede interferir con el envío y la recepción de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ca978-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="ca978-131">Debe eliminar estos registros tan pronto como se haya completado la comprobación del dominio.</span><span class="sxs-lookup"><span data-stu-id="ca978-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="ca978-132">Asegúrese de configurar los campos con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ca978-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="ca978-133">Tipo de registro: `MX`</span><span class="sxs-lookup"><span data-stu-id="ca978-133">Record Type: `MX`</span></span>
- <span data-ttu-id="ca978-134">Prioridad: defina la prioridad con el valor más alto posible, que suele ser `0`.</span><span class="sxs-lookup"><span data-stu-id="ca978-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="ca978-135">Nombre de host: `@`</span><span class="sxs-lookup"><span data-stu-id="ca978-135">Host Name: `@`</span></span>
- <span data-ttu-id="ca978-136">Dirección de destino: copie el valor del centro de administración y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="ca978-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="ca978-137">TTL: `3600‎` (o el proveedor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="ca978-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="ca978-138">Cuando Microsoft encuentre el registro MX correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="ca978-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="ca978-139">Paso 2: Agregar registros DNS para conectarse a los servicios de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ca978-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="ca978-140">En una nueva pestaña o ventana del explorador, inicie sesión en su proveedor de host DNS y busque el lugar donde administra la configuración de DNS (por ejemplo, Configuración del archivo de zona, Administrar dominios, Administrador de dominios, Administrador de DNS).</span><span class="sxs-lookup"><span data-stu-id="ca978-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="ca978-141">Agregará varios tipos de registros DNS en función de los servicios que quiera habilitar.</span><span class="sxs-lookup"><span data-stu-id="ca978-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="ca978-142">Agregar un registro MX para el correo electrónico (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="ca978-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="ca978-143">**Antes de empezar:** si los usuarios ya tienen correo electrónico en su dominio (por ejemplo, usuario@sudominio.com), cree sus cuentas en el centro de administración antes de configurar los registros MX.</span><span class="sxs-lookup"><span data-stu-id="ca978-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="ca978-144">De esta forma, seguirán recibiendo correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ca978-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="ca978-145">Cuando actualice el registro MX de su dominio, todo el correo electrónico nuevo de cualquiera que use su dominio pasará a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca978-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="ca978-146">Cualquier correo electrónico ya existente permanecerá en el host de correo electrónico actual, a menos que decida [migrar el correo electrónico y los contactos a Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span><span class="sxs-lookup"><span data-stu-id="ca978-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="ca978-147">Obtendrá la información del registro MX del asistente de configuración del dominio del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="ca978-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="ca978-148">En el sitio web del proveedor de host, agregue un nuevo registro MX.</span><span class="sxs-lookup"><span data-stu-id="ca978-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="ca978-149">Asegúrese de configurar los campos con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ca978-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="ca978-150">Tipo de registro: `MX`</span><span class="sxs-lookup"><span data-stu-id="ca978-150">Record Type: `MX`</span></span>
- <span data-ttu-id="ca978-151">Prioridad: defina la prioridad con el valor más alto posible, que suele ser `0`.</span><span class="sxs-lookup"><span data-stu-id="ca978-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="ca978-152">Nombre de host: `@`</span><span class="sxs-lookup"><span data-stu-id="ca978-152">Host Name: `@`</span></span>
- <span data-ttu-id="ca978-153">Dirección de destino: copie el valor del centro de administración y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="ca978-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="ca978-154">TTL: `3600‎` (o el proveedor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="ca978-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="ca978-155">Guarde el registro y, a continuación, quite cualquier otro registro MX.</span><span class="sxs-lookup"><span data-stu-id="ca978-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="ca978-156">Agregar registros CNAME para conectarse a otros servicios (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="ca978-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="ca978-157">Obtendrá la información de los registros CNAME del asistente de configuración del dominio del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="ca978-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="ca978-158">En el sitio web de su proveedor de host, agregue los registros CNAME para cada servicio al que quiera conectarse.</span><span class="sxs-lookup"><span data-stu-id="ca978-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="ca978-159">Asegúrese de configurar los campos con los siguientes valores para cada uno:</span><span class="sxs-lookup"><span data-stu-id="ca978-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="ca978-160">Tipo de registro: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="ca978-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="ca978-161">Host: pegue aquí los valores que copie del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="ca978-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="ca978-162">Dirección de destino: copie el valor del centro de administración y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="ca978-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="ca978-163">TTL: `3600‎` (o el proveedor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="ca978-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="ca978-164">Agregar un registro TXT para SPF para ayudar a prevenir correo electrónico no deseado (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="ca978-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="ca978-165">**Antes de empezar:** si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca978-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="ca978-166">En vez de eso, agregue los valores necesarios de Microsoft 365 para el registro actual en el sitio web de su proveedor de host, de modo que solo tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="ca978-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="ca978-167">En el sitio web de su proveedor de host, edite el registro SPF existente o cree un nuevo registro SPF.</span><span class="sxs-lookup"><span data-stu-id="ca978-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="ca978-168">Asegúrese de configurar los campos con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ca978-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="ca978-169">Tipo de registro: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="ca978-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="ca978-170">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="ca978-170">Host: `@`</span></span>
- <span data-ttu-id="ca978-171">Valor TXT: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="ca978-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="ca978-172">TTL: `3600‎` (o el proveedor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="ca978-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="ca978-173">Guarde el registro.</span><span class="sxs-lookup"><span data-stu-id="ca978-173">Save the record.</span></span>

<span data-ttu-id="ca978-174">Para validar el registro de SPF, use una de estas[herramientas de validación de SPF](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).</span><span class="sxs-lookup"><span data-stu-id="ca978-174">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="ca978-175">SPF está diseñado para ayudar a evitar la suplantación de identidad, pero hay técnicas de suplantación de identidad contra las que SPF no puede proteger.</span><span class="sxs-lookup"><span data-stu-id="ca978-175">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="ca978-176">Para protegerse de estos, una vez que haya configurado el SPF, también debe configurar DKIM y DMARC para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca978-176">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="ca978-177">Para comenzar, consulte [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio en Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) y[Usar DMARC para validar el correo electrónico en Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="ca978-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="ca978-178">Agregar registros SRV para servicios de comunicaciones (Teams, Skype Empresarial)</span><span class="sxs-lookup"><span data-stu-id="ca978-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="ca978-179">En el sitio web de su proveedor de host, agregue los registros SRV para cada servicio al que quiera conectarse.</span><span class="sxs-lookup"><span data-stu-id="ca978-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="ca978-180">Asegúrese de configurar los campos con los siguientes valores para cada uno:</span><span class="sxs-lookup"><span data-stu-id="ca978-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="ca978-181">Tipo de registro: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="ca978-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="ca978-182">Nombre: `@`</span><span class="sxs-lookup"><span data-stu-id="ca978-182">Name: `@`</span></span>
- <span data-ttu-id="ca978-183">Destino: copie el valor del centro de administración y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="ca978-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="ca978-184">Protocolo: copie el valor del centro de administración y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="ca978-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="ca978-185">Servicio: copie el valor del centro de administración y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="ca978-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="ca978-186">Prioridad: `100`</span><span class="sxs-lookup"><span data-stu-id="ca978-186">Priority: `100`</span></span>
- <span data-ttu-id="ca978-187">Peso: `1`</span><span class="sxs-lookup"><span data-stu-id="ca978-187">Weight: `1`</span></span>
- <span data-ttu-id="ca978-188">Puerto: copie el valor del centro de administración y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="ca978-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="ca978-189">TTL: `3600‎` (o el proveedor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="ca978-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="ca978-190">Guarde el registro.</span><span class="sxs-lookup"><span data-stu-id="ca978-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="ca978-191">Restricciones y soluciones alternativas para campos de registros SRV</span><span class="sxs-lookup"><span data-stu-id="ca978-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="ca978-192">Algunos proveedores de host imponen restricciones en los valores de los campos de los registros SRV.</span><span class="sxs-lookup"><span data-stu-id="ca978-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="ca978-193">Estas son algunas soluciones alternativas habituales para estas restricciones.</span><span class="sxs-lookup"><span data-stu-id="ca978-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="ca978-194">Nombre</span><span class="sxs-lookup"><span data-stu-id="ca978-194">Name</span></span>
<span data-ttu-id="ca978-195">Si el proveedor de host no permite configurar este campo en **@**, déjelo en blanco.</span><span class="sxs-lookup"><span data-stu-id="ca978-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="ca978-196">Use esta estrategia *solo* cuando el proveedor de host tiene campos separados para los valores de servicio y protocolo.</span><span class="sxs-lookup"><span data-stu-id="ca978-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="ca978-197">De lo contrario, consulte las notas de servicio y protocolo a continuación.</span><span class="sxs-lookup"><span data-stu-id="ca978-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="ca978-198">Servicio y protocolo</span><span class="sxs-lookup"><span data-stu-id="ca978-198">Service and Protocol</span></span>
<span data-ttu-id="ca978-199">Si el proveedor de host no ofrece estos campos para los registros SRV, debe especificar los valores de **Servicio** y **Protocolo** en el campo de **Nombre** del registro.</span><span class="sxs-lookup"><span data-stu-id="ca978-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="ca978-200">(Nota: dependiendo de su proveedor de host, el campo de **Nombre** puede llamarse de otra forma, como: **Host**, **Nombre de host** o **Subdominio**). Para agregar estos valores, cree una sola cadena, separando los valores con un punto.</span><span class="sxs-lookup"><span data-stu-id="ca978-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="ca978-201">Ejemplo: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="ca978-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="ca978-202">Prioridad, peso y puerto</span><span class="sxs-lookup"><span data-stu-id="ca978-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="ca978-203">Si el proveedor de host no ofrece estos campos para los registros SRV, debe especificarlos en el campo **Destino** del registro.</span><span class="sxs-lookup"><span data-stu-id="ca978-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="ca978-204">(Nota: en función de su proveedor de host, el campo **Destino** puede llamarse de otra forma, como: **Contenido**, **Dirección IP** o **Host de destino**).</span><span class="sxs-lookup"><span data-stu-id="ca978-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="ca978-205">Para agregar estos valores, cree una sola cadena, separando los valores con espacios y *en ocasiones con un punto* (si no está seguro, consulte con el proveedor).</span><span class="sxs-lookup"><span data-stu-id="ca978-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="ca978-206">Los valores deben ser incluidos en este orden: prioridad, peso, puerto, y destino.</span><span class="sxs-lookup"><span data-stu-id="ca978-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="ca978-207">Ejemplo 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="ca978-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="ca978-208">Ejemplo 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="ca978-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>