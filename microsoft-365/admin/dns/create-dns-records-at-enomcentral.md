---
title: Crear registros DNS en eNomCentral para Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en eNomCentral para Microsoft.
ms.openlocfilehash: c964729c052f5c0b61441f14ce15a167caa06b72
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780402"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="2b061-103">Crear registros DNS en eNomCentral para Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b061-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="2b061-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="2b061-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2b061-105">Si eNomCentral es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="2b061-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="2b061-106">Después de agregar estos registros a eNomCentral, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b061-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="2b061-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="2b061-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="2b061-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="2b061-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="2b061-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2b061-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2b061-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="2b061-110">Add a TXT record for verification</span></span>
<span data-ttu-id="2b061-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2b061-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2b061-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="2b061-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="2b061-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="2b061-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b061-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="2b061-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="2b061-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="2b061-115">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="2b061-116">Siga los pasos siguientes o [vea el vídeo (empieza en 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="2b061-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="2b061-117">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="2b061-117">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="2b061-118">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="2b061-118">You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="2b061-120">En **mis dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="2b061-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="2b061-122">En la lista desplegable **Administrar dominio**, elija **Registros de host**.</span><span class="sxs-lookup"><span data-stu-id="2b061-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="2b061-124">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b061-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="2b061-125">Elija el valor **tipo de registro** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2b061-125">Choose the **Record Type** value from the drop-down list.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="2b061-126">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2b061-126">**Host Name**</span></span> <br/> |<span data-ttu-id="2b061-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="2b061-127">**Record Type**</span></span> <br/> |<span data-ttu-id="2b061-128">**Address**</span><span class="sxs-lookup"><span data-stu-id="2b061-128">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="2b061-129">TXT</span><span class="sxs-lookup"><span data-stu-id="2b061-129">TXT</span></span>  <br/> |<span data-ttu-id="2b061-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2b061-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2b061-131">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2b061-131">**Note:** This is an example.</span></span> <span data-ttu-id="2b061-132">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="2b061-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="2b061-133">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="2b061-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="2b061-135">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b061-135">Select **save**.</span></span>
    
    ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="2b061-137">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="2b061-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2b061-138">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="2b061-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="2b061-139">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="2b061-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2b061-140">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="2b061-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="2b061-141">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="2b061-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="2b061-142">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="2b061-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="2b061-143">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="2b061-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="2b061-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="2b061-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="2b061-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="2b061-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="2b061-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2b061-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2b061-147">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b061-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2b061-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2b061-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="2b061-149">Siga los pasos siguientes o [vea el vídeo (empieza en 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="2b061-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="2b061-150">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="2b061-150">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="2b061-151">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="2b061-151">You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="2b061-153">En **mis dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="2b061-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="2b061-155">En la lista desplegable **Administrar dominio**, elija **Configuración de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="2b061-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="2b061-157">En la lista desplegable **Selección de servicio**, elija **Usuario (MX)**.</span><span class="sxs-lookup"><span data-stu-id="2b061-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="2b061-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2b061-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="2b061-160">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2b061-160">**Host Name**</span></span>|<span data-ttu-id="2b061-161">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="2b061-161">**Address**</span></span>|<span data-ttu-id="2b061-162">**Pref.**</span><span class="sxs-lookup"><span data-stu-id="2b061-162">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="2b061-163">*\<domain-key\>*. mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2b061-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="2b061-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2b061-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="2b061-165">**Nota:** Obtén tu *\<domain-key\>* cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b061-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="2b061-166">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="2b061-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="2b061-167">10  </span><span class="sxs-lookup"><span data-stu-id="2b061-167">10</span></span>  <br/> <span data-ttu-id="2b061-168">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="2b061-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
       
   ![eNom-BP-configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="2b061-170">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b061-170">Select **save**.</span></span>
    
    ![eNom-BP-configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="2b061-172">Si hay otros registros MX, active las casillas de esos registros para seleccionarlos.</span><span class="sxs-lookup"><span data-stu-id="2b061-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="2b061-174">Seleccione **eliminar seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="2b061-174">Select **delete checked**.</span></span>
    
    ![eNom-BP-configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2b061-176">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b061-176">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="2b061-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2b061-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="2b061-178">Siga los pasos siguientes o [vea el vídeo (empieza en 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="2b061-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="2b061-179">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="2b061-179">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="2b061-180">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="2b061-180">You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="2b061-182">En **mis dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="2b061-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="2b061-184">En la lista desplegable **Administrar dominio**, elija **Registros de host**.</span><span class="sxs-lookup"><span data-stu-id="2b061-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="2b061-186">Seleccione **nueva fila**.</span><span class="sxs-lookup"><span data-stu-id="2b061-186">Select **new row**.</span></span>
    
    ![eNom-BP-configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="2b061-188">En los cuadros para los seis nuevos registros, escriba o copie y pegue los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="2b061-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
<span data-ttu-id="2b061-189">Elija el valor **tipo de registro** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2b061-189">Choose the **Record Type** value from the drop-down list.</span></span>
        
    |<span data-ttu-id="2b061-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2b061-190">**Host Name**</span></span>|<span data-ttu-id="2b061-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="2b061-191">**Record Type**</span></span>|<span data-ttu-id="2b061-192">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="2b061-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2b061-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2b061-193">autodiscover</span></span>  <br/> |<span data-ttu-id="2b061-194">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="2b061-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="2b061-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2b061-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="2b061-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2b061-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2b061-197">sip</span><span class="sxs-lookup"><span data-stu-id="2b061-197">sip</span></span>  <br/> |<span data-ttu-id="2b061-198">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="2b061-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="2b061-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2b061-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2b061-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2b061-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2b061-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2b061-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2b061-202">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="2b061-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="2b061-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2b061-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2b061-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="2b061-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2b061-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2b061-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2b061-206">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="2b061-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="2b061-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="2b061-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="2b061-208">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="2b061-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2b061-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2b061-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2b061-210">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="2b061-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="2b061-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2b061-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="2b061-212">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="2b061-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="2b061-213">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b061-213">Select **save**.</span></span>
    
    ![eNom-BP-configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2b061-215">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2b061-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2b061-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2b061-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b061-217">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="2b061-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2b061-218">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="2b061-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2b061-219">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b061-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="2b061-220">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="2b061-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="2b061-221">Siga los pasos siguientes o [vea el vídeo (empieza en 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="2b061-221">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="2b061-222">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="2b061-222">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="2b061-223">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="2b061-223">You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="2b061-225">En **mis dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="2b061-225">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="2b061-227">En la lista desplegable **Administrar dominio**, elija **Registros de host**.</span><span class="sxs-lookup"><span data-stu-id="2b061-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="2b061-229">En los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b061-229">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
<span data-ttu-id="2b061-230">Elija el valor **tipo de registro** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2b061-230">Choose the **Record Type** value from the drop-down list.</span></span>
    
    |<span data-ttu-id="2b061-231">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2b061-231">**Host Name**</span></span>|<span data-ttu-id="2b061-232">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="2b061-232">**Record Type**</span></span>|<span data-ttu-id="2b061-233">**Address**</span><span class="sxs-lookup"><span data-stu-id="2b061-233">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2b061-234">TXT</span><span class="sxs-lookup"><span data-stu-id="2b061-234">TXT</span></span>  <br/> |<span data-ttu-id="2b061-235">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2b061-235">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="2b061-236">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="2b061-236">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="2b061-238">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b061-238">Select **save**.</span></span>
    
    ![eNom-BP-configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2b061-240">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b061-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2b061-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2b061-241"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="2b061-242">Siga los pasos siguientes o [vea el vídeo (empieza en 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="2b061-242">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="2b061-243">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="2b061-243">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="2b061-244">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="2b061-244">You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="2b061-246">En **mis dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="2b061-246">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="2b061-248">En la lista desplegable **Administrar dominio**, elija **Registros de host**.</span><span class="sxs-lookup"><span data-stu-id="2b061-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="2b061-250">A la derecha de **nueva fila**, seleccione **Agregar registro SRV o SPF**.</span><span class="sxs-lookup"><span data-stu-id="2b061-250">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="2b061-252">En los cuadros de los dos nuevos registros, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b061-252">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="2b061-253">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="2b061-253">**Service**</span></span>|<span data-ttu-id="2b061-254">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="2b061-254">**Protocol**</span></span>|<span data-ttu-id="2b061-255">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="2b061-255">**Priority**</span></span>|<span data-ttu-id="2b061-256">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="2b061-256">**Weight**</span></span>|<span data-ttu-id="2b061-257">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="2b061-257">**Port**</span></span>|<span data-ttu-id="2b061-258">**Destino          (nombre de host)**</span><span class="sxs-lookup"><span data-stu-id="2b061-258">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2b061-259">_sip</span><span class="sxs-lookup"><span data-stu-id="2b061-259">_sip</span></span>  <br/> |<span data-ttu-id="2b061-260">_tls</span><span class="sxs-lookup"><span data-stu-id="2b061-260">_tls</span></span>  <br/> |<span data-ttu-id="2b061-261">100</span><span class="sxs-lookup"><span data-stu-id="2b061-261">100</span></span>  <br/> |<span data-ttu-id="2b061-262">1 </span><span class="sxs-lookup"><span data-stu-id="2b061-262">1</span></span>  <br/> |<span data-ttu-id="2b061-263">443</span><span class="sxs-lookup"><span data-stu-id="2b061-263">443</span></span>  <br/> |<span data-ttu-id="2b061-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2b061-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2b061-265">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="2b061-265">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="2b061-266">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="2b061-266">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="2b061-267">_tcp</span><span class="sxs-lookup"><span data-stu-id="2b061-267">_tcp</span></span>  <br/> |<span data-ttu-id="2b061-268">100</span><span class="sxs-lookup"><span data-stu-id="2b061-268">100</span></span>  <br/> |<span data-ttu-id="2b061-269">1 </span><span class="sxs-lookup"><span data-stu-id="2b061-269">1</span></span>  <br/> |<span data-ttu-id="2b061-270">5061</span><span class="sxs-lookup"><span data-stu-id="2b061-270">5061</span></span>  <br/> |<span data-ttu-id="2b061-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2b061-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="2b061-272">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="2b061-272">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="2b061-274">Seleccione **Guardar**</span><span class="sxs-lookup"><span data-stu-id="2b061-274">Select **save**</span></span>
    
    ![eNom-BP-configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="2b061-276">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="2b061-276">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="2b061-277">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="2b061-277">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="2b061-278">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2b061-278">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

