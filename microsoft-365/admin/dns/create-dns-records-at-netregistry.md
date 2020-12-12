---
title: Crear registros DNS en Netregistry para Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Netregistry para Microsoft.
ms.openlocfilehash: 857645c685cce946b39a7c3dcadb0a45b43686cf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657808"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="31be2-103">Crear registros DNS en Netregistry para Microsoft</span><span class="sxs-lookup"><span data-stu-id="31be2-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="31be2-104">[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml) si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="31be2-104">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="31be2-105">Si Netregistry es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="31be2-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="31be2-106">Estos son los registros principales que se deben agregar.</span><span class="sxs-lookup"><span data-stu-id="31be2-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="31be2-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="31be2-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="31be2-108">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="31be2-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="31be2-109">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="31be2-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="31be2-110">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="31be2-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="31be2-111">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="31be2-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="31be2-112">Después de agregar estos registros a Netregistry, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31be2-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="31be2-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="31be2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="31be2-116">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="31be2-116">Add a TXT record for verification</span></span>
<span data-ttu-id="31be2-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="31be2-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="31be2-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="31be2-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="31be2-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="31be2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="31be2-122">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="31be2-122">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="31be2-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="31be2-123">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="31be2-125">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="31be2-125">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="31be2-127">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="31be2-127">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="31be2-129">En **Agregar un registro de zona**, elija **registro TXT** de la lista y, a continuación, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="31be2-129">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="31be2-131">Debe usar comillas antes y después de la entrada en el cuadro TXT.</span><span class="sxs-lookup"><span data-stu-id="31be2-131">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="31be2-132">En el **nuevo formulario de registro TXT** , escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="31be2-132">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="31be2-133">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="31be2-133">**Name**</span></span>|<span data-ttu-id="31be2-134">**TTL (SEG.)**</span><span class="sxs-lookup"><span data-stu-id="31be2-134">**TTL (SEC)**</span></span>|<span data-ttu-id="31be2-135">**TXT (apunta a la dirección o al valor)**</span><span class="sxs-lookup"><span data-stu-id="31be2-135">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="31be2-136">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="31be2-136">(leave blank)</span></span>  <br/> |<span data-ttu-id="31be2-137">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="31be2-137">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="31be2-138">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="31be2-138">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="31be2-139">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="31be2-139">**Note:** This is an example.</span></span> <span data-ttu-id="31be2-140">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="31be2-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="31be2-141">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="31be2-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="31be2-143">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="31be2-143">Select **Add record**.</span></span>
    
<span data-ttu-id="31be2-144">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="31be2-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="31be2-145">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="31be2-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="31be2-146">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="31be2-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="31be2-147">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="31be2-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="31be2-148">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="31be2-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="31be2-149">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="31be2-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="31be2-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="31be2-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="31be2-153">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="31be2-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="31be2-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="31be2-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="31be2-155">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="31be2-155">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="31be2-156">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="31be2-156">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="31be2-158">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="31be2-158">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="31be2-160">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="31be2-160">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="31be2-162">En **registros de la zona actual**, quite los registros MX predeterminados seleccionando **quitar** junto a cada registro MX de la lista.</span><span class="sxs-lookup"><span data-stu-id="31be2-162">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="31be2-164">En **Agregar un registro de zona**, elija **registro MX** de la lista y, después, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="31be2-164">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="31be2-166">En el formulario **nuevo registro MX** , escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="31be2-166">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="31be2-167">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="31be2-167">**Name**</span></span>|<span data-ttu-id="31be2-168">**TTL (SEG.)**</span><span class="sxs-lookup"><span data-stu-id="31be2-168">**TTL (SEC)**</span></span>|<span data-ttu-id="31be2-169">**Exchange (apunta a la dirección o al valor)**</span><span class="sxs-lookup"><span data-stu-id="31be2-169">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="31be2-170">**¿Es el host completo?**</span><span class="sxs-lookup"><span data-stu-id="31be2-170">**Is host fully qualified?**</span></span>|<span data-ttu-id="31be2-171">**Preferencia (prioridad)**</span><span class="sxs-lookup"><span data-stu-id="31be2-171">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="31be2-172">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="31be2-172">(leave blank)</span></span>  <br/> |<span data-ttu-id="31be2-173">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="31be2-173">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="31be2-174">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="31be2-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="31be2-175">**Nota:** Obtén tu  *\<domain-key\>*  cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31be2-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="31be2-176">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="31be2-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="31be2-177">(seleccione la casilla de verificación)</span><span class="sxs-lookup"><span data-stu-id="31be2-177">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="31be2-178">10 </span><span class="sxs-lookup"><span data-stu-id="31be2-178">10</span></span>  <br/> <span data-ttu-id="31be2-179">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="31be2-179">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="31be2-181">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="31be2-181">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="31be2-183">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="31be2-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="31be2-184"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="31be2-184"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="31be2-185">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="31be2-185">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="31be2-186">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="31be2-186">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="31be2-188">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="31be2-188">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="31be2-190">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="31be2-190">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="31be2-192">En  **Agregar un registro de zona**, elija **registro CNAME** de la lista y, después, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="31be2-192">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="31be2-194">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="31be2-194">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="31be2-195">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="31be2-195">**Name**</span></span>|<span data-ttu-id="31be2-196">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="31be2-196">**Type**</span></span>|<span data-ttu-id="31be2-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="31be2-197">**TTL**</span></span>|<span data-ttu-id="31be2-198">**HOST (valor de punto o dirección)**</span><span class="sxs-lookup"><span data-stu-id="31be2-198">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="31be2-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="31be2-199">autodiscover</span></span>  <br/> |<span data-ttu-id="31be2-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="31be2-200">CNAME</span></span>  <br/> |<span data-ttu-id="31be2-201">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="31be2-201">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="31be2-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="31be2-202">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="31be2-203">sip</span><span class="sxs-lookup"><span data-stu-id="31be2-203">sip</span></span>  <br/> |<span data-ttu-id="31be2-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="31be2-204">CNAME</span></span>  <br/> |<span data-ttu-id="31be2-205">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="31be2-205">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="31be2-206">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="31be2-206">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="31be2-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="31be2-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="31be2-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="31be2-208">CNAME</span></span>  <br/> |<span data-ttu-id="31be2-209">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="31be2-209">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="31be2-210">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="31be2-210">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="31be2-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="31be2-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="31be2-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="31be2-212">CNAME</span></span>  <br/> |<span data-ttu-id="31be2-213">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="31be2-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="31be2-214">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="31be2-214">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="31be2-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="31be2-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="31be2-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="31be2-216">CNAME</span></span>  <br/> |<span data-ttu-id="31be2-217">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="31be2-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="31be2-218">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="31be2-218">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="31be2-220">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="31be2-220">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="31be2-222">Repita los pasos anteriores para crear los otros cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="31be2-222">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="31be2-223">Para cada registro, escriba (o copie y pegue) los valores de la siguiente fila de la tabla anterior en los cuadros para ese registro.</span><span class="sxs-lookup"><span data-stu-id="31be2-223">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="31be2-224">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="31be2-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="31be2-225"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="31be2-225"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="31be2-226">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="31be2-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="31be2-227">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="31be2-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="31be2-228">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31be2-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="31be2-229">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="31be2-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="31be2-230">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="31be2-230">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="31be2-231">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="31be2-231">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="31be2-233">Junto al dominio que quiera administrar, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="31be2-233">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="31be2-235">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="31be2-235">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="31be2-237">En **Agregar un registro de zona**, elija **registro TXT** de la lista y, a continuación, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="31be2-237">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="31be2-239">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="31be2-239">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="31be2-240">Debe usar comillas antes y después de la entrada en el cuadro TXT.</span><span class="sxs-lookup"><span data-stu-id="31be2-240">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="31be2-241">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="31be2-241">**Name**</span></span>|<span data-ttu-id="31be2-242">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="31be2-242">**Type**</span></span>|<span data-ttu-id="31be2-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="31be2-243">**TTL**</span></span>|<span data-ttu-id="31be2-244">**Datos TXT (destino)**</span><span class="sxs-lookup"><span data-stu-id="31be2-244">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="31be2-245">(se deja en blanco)</span><span class="sxs-lookup"><span data-stu-id="31be2-245">(leave blank)</span></span>  <br/> |<span data-ttu-id="31be2-246">TXT</span><span class="sxs-lookup"><span data-stu-id="31be2-246">TXT</span></span>  <br/> |<span data-ttu-id="31be2-247">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="31be2-247">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="31be2-248">"v = spf1 include include SPF. Protection. Outlook. com-All"</span><span class="sxs-lookup"><span data-stu-id="31be2-248">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="31be2-249">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="31be2-249">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="31be2-251">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="31be2-251">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="31be2-253">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="31be2-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="31be2-254"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="31be2-254"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="31be2-255">Para empezar, vaya a su página de dominios en Netregistry a través de [este vínculo](https://theconsole.netregistry.com.au/).</span><span class="sxs-lookup"><span data-stu-id="31be2-255">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="31be2-256">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="31be2-256">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="31be2-258">Junto al dominio que quiera administrar, seleccione  **administrar**.</span><span class="sxs-lookup"><span data-stu-id="31be2-258">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="31be2-260">Seleccione **Administrador de zonas**.</span><span class="sxs-lookup"><span data-stu-id="31be2-260">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="31be2-262">En  **Agregar un registro de zona**, elija **registro SRV** en la lista y, a continuación, seleccione **crear nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="31be2-262">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="31be2-264">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="31be2-264">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="31be2-265">El campo nombre es una combinación del servicio (por ejemplo, _sip) y el protocolo (por ejemplo, _tls).</span><span class="sxs-lookup"><span data-stu-id="31be2-265">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="31be2-266">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="31be2-266">**Type**</span></span>|<span data-ttu-id="31be2-267">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="31be2-267">**Name**</span></span>|<span data-ttu-id="31be2-268">**TTL (SEG.)**</span><span class="sxs-lookup"><span data-stu-id="31be2-268">**TTL (SEC)**</span></span>|<span data-ttu-id="31be2-269">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="31be2-269">**Priority**</span></span>|<span data-ttu-id="31be2-270">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="31be2-270">**Weight**</span></span>|<span data-ttu-id="31be2-271">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="31be2-271">**Port**</span></span>|<span data-ttu-id="31be2-272">**Destino**</span><span class="sxs-lookup"><span data-stu-id="31be2-272">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="31be2-273">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="31be2-273">SRV (service)</span></span>  <br/> |<span data-ttu-id="31be2-274">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="31be2-274">_sip._tls</span></span>  <br/> |<span data-ttu-id="31be2-275">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="31be2-275">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="31be2-276">100</span><span class="sxs-lookup"><span data-stu-id="31be2-276">100</span></span>  <br/> |<span data-ttu-id="31be2-277">1 </span><span class="sxs-lookup"><span data-stu-id="31be2-277">1</span></span>  <br/> |<span data-ttu-id="31be2-278">443</span><span class="sxs-lookup"><span data-stu-id="31be2-278">443</span></span>  <br/> |<span data-ttu-id="31be2-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="31be2-279">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="31be2-280">SRV (servicio)</span><span class="sxs-lookup"><span data-stu-id="31be2-280">SRV (service)</span></span>  <br/> |<span data-ttu-id="31be2-281">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="31be2-281">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="31be2-282">3600 (segundos)</span><span class="sxs-lookup"><span data-stu-id="31be2-282">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="31be2-283">100</span><span class="sxs-lookup"><span data-stu-id="31be2-283">100</span></span>  <br/> |<span data-ttu-id="31be2-284">1 </span><span class="sxs-lookup"><span data-stu-id="31be2-284">1</span></span>  <br/> |<span data-ttu-id="31be2-285">5061</span><span class="sxs-lookup"><span data-stu-id="31be2-285">5061</span></span>  <br/> |<span data-ttu-id="31be2-286">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="31be2-286">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="31be2-288">Seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="31be2-288">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="31be2-290">Repita los pasos anteriores para crear el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="31be2-290">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="31be2-291">Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="31be2-291">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="31be2-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="31be2-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

