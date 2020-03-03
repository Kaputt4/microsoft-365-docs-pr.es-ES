---
title: Crear registros DNS en Netregistry para Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Netregistry para Office 365.
ms.openlocfilehash: 91f802afccd337a97b23ca514c9d9921595abcd1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42348821"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a><span data-ttu-id="cc1b8-103">Crear registros DNS en Netregistry para Office 365</span><span class="sxs-lookup"><span data-stu-id="cc1b8-103">Create DNS records at Netregistry for Office 365</span></span>

<span data-ttu-id="cc1b8-104">[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md) si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cc1b8-105">Si Netregistry es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="cc1b8-106">Estos son los registros principales que se deben agregar.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="cc1b8-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="cc1b8-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="cc1b8-108">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="cc1b8-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [<span data-ttu-id="cc1b8-109">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="cc1b8-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="cc1b8-110">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="cc1b8-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="cc1b8-111">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="cc1b8-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="cc1b8-112">Después de agregar estos registros a Netregistry, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-112">After you add these records at Netregistry, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="cc1b8-113">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="cc1b8-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc1b8-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cc1b8-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cc1b8-117">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="cc1b8-117">Add a TXT record for verification</span></span>
<span data-ttu-id="cc1b8-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="cc1b8-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="cc1b8-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc1b8-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cc1b8-123">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="cc1b8-123">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="cc1b8-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-124">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="cc1b8-126">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="cc1b8-128">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="cc1b8-130">En **Agregar un registro de zona**, elija **registro TXT** de la lista y, a continuación, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="cc1b8-132">Debe usar comillas antes y después de la entrada en el cuadro TXT.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="cc1b8-133">En el **nuevo formulario de registro TXT** , escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="cc1b8-134">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-134">**Name**</span></span>|<span data-ttu-id="cc1b8-135">**TTL (SEG.)**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-135">**TTL (SEC)**</span></span>|<span data-ttu-id="cc1b8-136">**TXT (apunta a la dirección o al valor)**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="cc1b8-137">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="cc1b8-138">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cc1b8-139">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="cc1b8-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="cc1b8-140">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-140">**Note:** This is an example.</span></span> <span data-ttu-id="cc1b8-141">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="cc1b8-142">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="cc1b8-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="cc1b8-144">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-144">Select **Add record**.</span></span>
    
<span data-ttu-id="cc1b8-145">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="cc1b8-146">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cc1b8-147">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="cc1b8-148">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="cc1b8-149">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="cc1b8-150">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="cc1b8-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cc1b8-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="cc1b8-154">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="cc1b8-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="cc1b8-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="cc1b8-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="cc1b8-156">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="cc1b8-156">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="cc1b8-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-157">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="cc1b8-159">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="cc1b8-161">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="cc1b8-163">En **registros de la zona actual**, quite los registros MX predeterminados seleccionando **quitar** junto a cada registro MX de la lista.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="cc1b8-165">En **Agregar un registro de zona**, elija **registro MX** de la lista y, después, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="cc1b8-167">En el formulario **nuevo registro MX** , escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="cc1b8-168">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-168">**Name**</span></span>|<span data-ttu-id="cc1b8-169">**TTL (SEG.)**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-169">**TTL (SEC)**</span></span>|<span data-ttu-id="cc1b8-170">**Exchange (apunta a la dirección o al valor)**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="cc1b8-171">**¿Es el host completo?**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="cc1b8-172">**Preferencia (prioridad)**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cc1b8-173">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="cc1b8-174">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="cc1b8-175">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="cc1b8-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="cc1b8-176">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-176">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="cc1b8-177">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="cc1b8-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="cc1b8-178">(seleccione la casilla de verificación)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="cc1b8-179">10 </span><span class="sxs-lookup"><span data-stu-id="cc1b8-179">10</span></span>  <br/> <span data-ttu-id="cc1b8-180">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="cc1b8-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="cc1b8-182">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="cc1b8-184">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="cc1b8-184">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="cc1b8-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="cc1b8-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="cc1b8-186">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="cc1b8-186">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="cc1b8-187">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-187">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="cc1b8-189">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="cc1b8-191">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="cc1b8-193">En **Agregar un registro de zona**, elija **registro CNAME** de la lista y, después, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="cc1b8-195">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="cc1b8-196">**Name**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-196">**Name**</span></span>|<span data-ttu-id="cc1b8-197">**Type**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-197">**Type**</span></span>|<span data-ttu-id="cc1b8-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-198">**TTL**</span></span>|<span data-ttu-id="cc1b8-199">**HOST (valor de punto o dirección)**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cc1b8-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cc1b8-200">autodiscover</span></span>  <br/> |<span data-ttu-id="cc1b8-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc1b8-201">CNAME</span></span>  <br/> |<span data-ttu-id="cc1b8-202">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cc1b8-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cc1b8-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="cc1b8-204">sip</span><span class="sxs-lookup"><span data-stu-id="cc1b8-204">sip</span></span>  <br/> |<span data-ttu-id="cc1b8-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc1b8-205">CNAME</span></span>  <br/> |<span data-ttu-id="cc1b8-206">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cc1b8-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cc1b8-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cc1b8-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cc1b8-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cc1b8-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc1b8-209">CNAME</span></span>  <br/> |<span data-ttu-id="cc1b8-210">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cc1b8-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cc1b8-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cc1b8-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cc1b8-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cc1b8-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc1b8-213">CNAME</span></span>  <br/> |<span data-ttu-id="cc1b8-214">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cc1b8-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cc1b8-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="cc1b8-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cc1b8-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cc1b8-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc1b8-217">CNAME</span></span>  <br/> |<span data-ttu-id="cc1b8-218">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cc1b8-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cc1b8-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="cc1b8-221">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="cc1b8-223">Repita los pasos anteriores para crear los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="cc1b8-224">Para cada registro, escriba (o copie y pegue) los valores de la siguiente fila de la tabla anterior en los cuadros para ese registro.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cc1b8-225">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="cc1b8-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cc1b8-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="cc1b8-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc1b8-227">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cc1b8-228">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cc1b8-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="cc1b8-230">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="cc1b8-231">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="cc1b8-231">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="cc1b8-232">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-232">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="cc1b8-234">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="cc1b8-236">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="cc1b8-238">En **Agregar un registro de zona**, elija **registro TXT** de la lista y, a continuación, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="cc1b8-240">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cc1b8-241">Debe usar comillas antes y después de la entrada en el cuadro TXT.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="cc1b8-242">**Name**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-242">**Name**</span></span>|<span data-ttu-id="cc1b8-243">**Type**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-243">**Type**</span></span>|<span data-ttu-id="cc1b8-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-244">**TTL**</span></span>|<span data-ttu-id="cc1b8-245">**Datos TXT (destino)**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cc1b8-246">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="cc1b8-247">TXT</span><span class="sxs-lookup"><span data-stu-id="cc1b8-247">TXT</span></span>  <br/> |<span data-ttu-id="cc1b8-248">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cc1b8-249">"v = spf1 include include SPF. Protection. Outlook. com-All"</span><span class="sxs-lookup"><span data-stu-id="cc1b8-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="cc1b8-250">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="cc1b8-252">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="cc1b8-254">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="cc1b8-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="cc1b8-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="cc1b8-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="cc1b8-256">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="cc1b8-256">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="cc1b8-257">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-257">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="cc1b8-259">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="cc1b8-261">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="cc1b8-263">En **Agregar un registro de zona**, elija **registro SRV** en la lista y, a continuación, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="cc1b8-265">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cc1b8-266">El campo nombre es una combinación del servicio (por ejemplo, _sip) y el protocolo (por ejemplo, _tls).</span><span class="sxs-lookup"><span data-stu-id="cc1b8-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="cc1b8-267">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-267">**Type**</span></span>|<span data-ttu-id="cc1b8-268">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-268">**Name**</span></span>|<span data-ttu-id="cc1b8-269">**TTL (SEG.)**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-269">**TTL (SEC)**</span></span>|<span data-ttu-id="cc1b8-270">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-270">**Priority**</span></span>|<span data-ttu-id="cc1b8-271">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-271">**Weight**</span></span>|<span data-ttu-id="cc1b8-272">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-272">**Port**</span></span>|<span data-ttu-id="cc1b8-273">**Destino**</span><span class="sxs-lookup"><span data-stu-id="cc1b8-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cc1b8-274">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="cc1b8-275">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="cc1b8-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="cc1b8-276">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cc1b8-277">100</span><span class="sxs-lookup"><span data-stu-id="cc1b8-277">100</span></span>  <br/> |<span data-ttu-id="cc1b8-278">1</span><span class="sxs-lookup"><span data-stu-id="cc1b8-278">1</span></span>  <br/> |<span data-ttu-id="cc1b8-279">443</span><span class="sxs-lookup"><span data-stu-id="cc1b8-279">443</span></span>  <br/> |<span data-ttu-id="cc1b8-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cc1b8-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cc1b8-281">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="cc1b8-282">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="cc1b8-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="cc1b8-283">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="cc1b8-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="cc1b8-284">100</span><span class="sxs-lookup"><span data-stu-id="cc1b8-284">100</span></span>  <br/> |<span data-ttu-id="cc1b8-285">1</span><span class="sxs-lookup"><span data-stu-id="cc1b8-285">1</span></span>  <br/> |<span data-ttu-id="cc1b8-286">5061</span><span class="sxs-lookup"><span data-stu-id="cc1b8-286">5061</span></span>  <br/> |<span data-ttu-id="cc1b8-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cc1b8-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="cc1b8-289">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="cc1b8-291">Repita los pasos anteriores para crear el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="cc1b8-292">Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="cc1b8-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cc1b8-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cc1b8-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

