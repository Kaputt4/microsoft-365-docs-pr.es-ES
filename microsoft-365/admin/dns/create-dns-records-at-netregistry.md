---
title: Crear registros DNS en Netregistry para Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Netregistry para Microsoft.
ms.openlocfilehash: 6aed84a4eaf95674358aa54986cfbb76edec2ef3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629316"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="e813a-103">Crear registros DNS en Netregistry para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e813a-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="e813a-104">[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md) si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="e813a-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e813a-105">Si Netregistry es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="e813a-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e813a-106">Estos son los registros principales que se deben agregar.</span><span class="sxs-lookup"><span data-stu-id="e813a-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="e813a-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="e813a-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="e813a-108">Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e813a-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="e813a-109">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e813a-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="e813a-110">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="e813a-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="e813a-111">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e813a-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="e813a-112">Después de agregar estos registros a Netregistry, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e813a-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="e813a-113">Para obtener más información sobre WebHosting y DNS para sitios web con Microsoft, vea [usar un sitio web público con Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="e813a-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e813a-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e813a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e813a-117">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="e813a-117">Add a TXT record for verification</span></span>
<span data-ttu-id="e813a-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="e813a-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="e813a-119">Antes de usar el dominio con Microsoft, debemos asegurarnos de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="e813a-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="e813a-120">Su capacidad para iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS es la que se demuestre a Microsoft que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="e813a-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e813a-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="e813a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e813a-123">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="e813a-123">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="e813a-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e813a-124">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="e813a-126">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="e813a-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="e813a-128">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="e813a-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="e813a-130">En **Agregar un registro de zona**, elija **registro TXT** de la lista y, a continuación, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="e813a-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="e813a-132">Debe usar comillas antes y después de la entrada en el cuadro TXT.</span><span class="sxs-lookup"><span data-stu-id="e813a-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="e813a-133">En el **nuevo formulario de registro TXT** , escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e813a-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="e813a-134">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e813a-134">**Name**</span></span>|<span data-ttu-id="e813a-135">**TTL (SEG.)**</span><span class="sxs-lookup"><span data-stu-id="e813a-135">**TTL (SEC)**</span></span>|<span data-ttu-id="e813a-136">**TXT (apunta a la dirección o al valor)**</span><span class="sxs-lookup"><span data-stu-id="e813a-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="e813a-137">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="e813a-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="e813a-138">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e813a-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e813a-139">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="e813a-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="e813a-140">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e813a-140">**Note:** This is an example.</span></span> <span data-ttu-id="e813a-141">Use aquí su **destino específico o** el valor de dirección de destino de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e813a-141">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e813a-142">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="e813a-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="e813a-144">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="e813a-144">Select **Add record**.</span></span>
    
<span data-ttu-id="e813a-145">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará el registro.</span><span class="sxs-lookup"><span data-stu-id="e813a-145">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e813a-146">Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.</span><span class="sxs-lookup"><span data-stu-id="e813a-146">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e813a-147">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="e813a-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e813a-148">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="e813a-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e813a-149">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="e813a-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e813a-150">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="e813a-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e813a-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e813a-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e813a-154">Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e813a-154">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e813a-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="e813a-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="e813a-156">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="e813a-156">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="e813a-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e813a-157">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="e813a-159">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="e813a-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="e813a-161">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="e813a-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="e813a-163">En **registros de la zona actual**, quite los registros MX predeterminados seleccionando **quitar** junto a cada registro MX de la lista.</span><span class="sxs-lookup"><span data-stu-id="e813a-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="e813a-165">En **Agregar un registro de zona**, elija **registro MX** de la lista y, después, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="e813a-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="e813a-167">En el formulario **nuevo registro MX** , escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e813a-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="e813a-168">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e813a-168">**Name**</span></span>|<span data-ttu-id="e813a-169">**TTL (SEG.)**</span><span class="sxs-lookup"><span data-stu-id="e813a-169">**TTL (SEC)**</span></span>|<span data-ttu-id="e813a-170">**Exchange (apunta a la dirección o al valor)**</span><span class="sxs-lookup"><span data-stu-id="e813a-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="e813a-171">**¿Es el host completo?**</span><span class="sxs-lookup"><span data-stu-id="e813a-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="e813a-172">**Preferencia (prioridad)**</span><span class="sxs-lookup"><span data-stu-id="e813a-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e813a-173">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="e813a-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="e813a-174">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e813a-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="e813a-175">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="e813a-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e813a-176">**Nota:** Obtén tu \* \<clave\> de dominio\* de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e813a-176">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="e813a-177">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="e813a-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="e813a-178">(seleccione la casilla de verificación)</span><span class="sxs-lookup"><span data-stu-id="e813a-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="e813a-179">10 </span><span class="sxs-lookup"><span data-stu-id="e813a-179">10</span></span>  <br/> <span data-ttu-id="e813a-180">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="e813a-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="e813a-182">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="e813a-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e813a-184">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e813a-184">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e813a-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="e813a-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="e813a-186">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="e813a-186">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="e813a-187">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e813a-187">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="e813a-189">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="e813a-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="e813a-191">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="e813a-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="e813a-193">En **Agregar un registro de zona**, elija **registro CNAME** de la lista y, después, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="e813a-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="e813a-195">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e813a-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="e813a-196">**Name**</span><span class="sxs-lookup"><span data-stu-id="e813a-196">**Name**</span></span>|<span data-ttu-id="e813a-197">**Type**</span><span class="sxs-lookup"><span data-stu-id="e813a-197">**Type**</span></span>|<span data-ttu-id="e813a-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e813a-198">**TTL**</span></span>|<span data-ttu-id="e813a-199">**HOST (valor de punto o dirección)**</span><span class="sxs-lookup"><span data-stu-id="e813a-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e813a-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e813a-200">autodiscover</span></span>  <br/> |<span data-ttu-id="e813a-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="e813a-201">CNAME</span></span>  <br/> |<span data-ttu-id="e813a-202">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e813a-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e813a-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e813a-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="e813a-204">sip</span><span class="sxs-lookup"><span data-stu-id="e813a-204">sip</span></span>  <br/> |<span data-ttu-id="e813a-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="e813a-205">CNAME</span></span>  <br/> |<span data-ttu-id="e813a-206">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e813a-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e813a-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e813a-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e813a-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e813a-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e813a-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="e813a-209">CNAME</span></span>  <br/> |<span data-ttu-id="e813a-210">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e813a-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e813a-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e813a-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e813a-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e813a-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e813a-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="e813a-213">CNAME</span></span>  <br/> |<span data-ttu-id="e813a-214">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e813a-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e813a-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e813a-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="e813a-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e813a-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e813a-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="e813a-217">CNAME</span></span>  <br/> |<span data-ttu-id="e813a-218">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e813a-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e813a-219">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e813a-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="e813a-221">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="e813a-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="e813a-223">Repita los pasos anteriores para crear los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="e813a-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="e813a-224">Para cada registro, escriba (o copie y pegue) los valores de la siguiente fila de la tabla anterior en los cuadros para ese registro.</span><span class="sxs-lookup"><span data-stu-id="e813a-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e813a-225">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="e813a-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e813a-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="e813a-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e813a-227">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="e813a-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e813a-228">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="e813a-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e813a-229">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e813a-229">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e813a-230">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="e813a-230">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="e813a-231">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="e813a-231">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="e813a-232">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e813a-232">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="e813a-234">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="e813a-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="e813a-236">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="e813a-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="e813a-238">En **Agregar un registro de zona**, elija **registro TXT** de la lista y, a continuación, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="e813a-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="e813a-240">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e813a-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e813a-241">Debe usar comillas antes y después de la entrada en el cuadro TXT.</span><span class="sxs-lookup"><span data-stu-id="e813a-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="e813a-242">**Name**</span><span class="sxs-lookup"><span data-stu-id="e813a-242">**Name**</span></span>|<span data-ttu-id="e813a-243">**Type**</span><span class="sxs-lookup"><span data-stu-id="e813a-243">**Type**</span></span>|<span data-ttu-id="e813a-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e813a-244">**TTL**</span></span>|<span data-ttu-id="e813a-245">**Datos TXT (destino)**</span><span class="sxs-lookup"><span data-stu-id="e813a-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e813a-246">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="e813a-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="e813a-247">TXT</span><span class="sxs-lookup"><span data-stu-id="e813a-247">TXT</span></span>  <br/> |<span data-ttu-id="e813a-248">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e813a-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e813a-249">"v = spf1 include include SPF. Protection. Outlook. com-All"</span><span class="sxs-lookup"><span data-stu-id="e813a-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="e813a-250">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="e813a-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="e813a-252">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="e813a-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e813a-254">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="e813a-254">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e813a-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="e813a-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="e813a-256">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="e813a-256">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="e813a-257">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e813a-257">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="e813a-259">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="e813a-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="e813a-261">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="e813a-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="e813a-263">En **Agregar un registro de zona**, elija **registro SRV** en la lista y, a continuación, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="e813a-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="e813a-265">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e813a-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e813a-266">El campo nombre es una combinación del servicio (por ejemplo, _sip) y el protocolo (por ejemplo, _tls).</span><span class="sxs-lookup"><span data-stu-id="e813a-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="e813a-267">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e813a-267">**Type**</span></span>|<span data-ttu-id="e813a-268">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e813a-268">**Name**</span></span>|<span data-ttu-id="e813a-269">**TTL (SEG.)**</span><span class="sxs-lookup"><span data-stu-id="e813a-269">**TTL (SEC)**</span></span>|<span data-ttu-id="e813a-270">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="e813a-270">**Priority**</span></span>|<span data-ttu-id="e813a-271">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="e813a-271">**Weight**</span></span>|<span data-ttu-id="e813a-272">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="e813a-272">**Port**</span></span>|<span data-ttu-id="e813a-273">**Destino**</span><span class="sxs-lookup"><span data-stu-id="e813a-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e813a-274">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="e813a-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="e813a-275">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="e813a-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="e813a-276">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e813a-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e813a-277">100</span><span class="sxs-lookup"><span data-stu-id="e813a-277">100</span></span>  <br/> |<span data-ttu-id="e813a-278">1</span><span class="sxs-lookup"><span data-stu-id="e813a-278">1</span></span>  <br/> |<span data-ttu-id="e813a-279">443</span><span class="sxs-lookup"><span data-stu-id="e813a-279">443</span></span>  <br/> |<span data-ttu-id="e813a-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e813a-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e813a-281">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="e813a-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="e813a-282">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="e813a-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="e813a-283">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="e813a-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e813a-284">100</span><span class="sxs-lookup"><span data-stu-id="e813a-284">100</span></span>  <br/> |<span data-ttu-id="e813a-285">1</span><span class="sxs-lookup"><span data-stu-id="e813a-285">1</span></span>  <br/> |<span data-ttu-id="e813a-286">5061</span><span class="sxs-lookup"><span data-stu-id="e813a-286">5061</span></span>  <br/> |<span data-ttu-id="e813a-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e813a-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="e813a-289">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="e813a-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="e813a-291">Repita los pasos anteriores para crear el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="e813a-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="e813a-292">Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="e813a-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e813a-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e813a-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

