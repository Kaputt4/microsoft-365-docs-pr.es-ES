---
title: Crear registros DNS en 1&1 IONOS para Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at 1&1 IONOS for Microsoft.
ms.openlocfilehash: 8e2deab05b5ef8d8f22993d2bfdd032999ed9c39
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658001"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="9e040-103">Crear registros DNS en 1&1 IONOS para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e040-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="9e040-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="9e040-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="9e040-105">Tenga en cuenta que 1&1 IONOS no permite que un dominio tenga un registro MX y un registro CNAME de detección automática de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="9e040-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="9e040-106">Esto limita las formas en que puede configurar Exchange Online para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e040-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="9e040-107">Hay una solución alternativa, pero  se recomienda emplearla solo si ya tiene experiencia en la creación de subdominios en 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="9e040-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="9e040-108">> Si, a [](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) pesar de esta limitación de servicio, decide administrar sus propios registros DNS de Microsoft en 1 ionos&1, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, entre otros.</span><span class="sxs-lookup"><span data-stu-id="9e040-108">> If despite this [service limitation](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="9e040-109">Después de agregar estos registros a 1&1 IONOS, el dominio se configurará para funcionar con los servicios Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e040-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="9e040-110">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="9e040-110">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9e040-111">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="9e040-111">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9e040-112">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e040-112">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9e040-113">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="9e040-113">Add a TXT record for verification</span></span>

<span data-ttu-id="9e040-p103">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="9e040-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e040-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="9e040-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="9e040-118">Siga los pasos siguientes o [vea el vídeo (empieza en 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="9e040-118">Follow the steps below or [watch the video (start at 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
1. <span data-ttu-id="9e040-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="9e040-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="9e040-120">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9e040-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="9e040-121">Seleccione **Administrar dominios.**</span><span class="sxs-lookup"><span data-stu-id="9e040-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="9e040-122">En la **página Centro de** dominio, busque el dominio que desea actualizar y, a continuación, seleccione el control **panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="9e040-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="9e040-123">En el **área Configuración del** dominio, seleccione Editar configuración **dns.**</span><span class="sxs-lookup"><span data-stu-id="9e040-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="9e040-124">En la **sección Registros TXT y SRV,** seleccione Agregar **registro.**</span><span class="sxs-lookup"><span data-stu-id="9e040-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="9e040-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9e040-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9e040-126">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="9e040-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="9e040-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9e040-127">**Type**</span></span> <br/> |<span data-ttu-id="9e040-128">**Prefijo**</span><span class="sxs-lookup"><span data-stu-id="9e040-128">**Prefix**</span></span> <br/> |<span data-ttu-id="9e040-129">**Valor de nombre**</span><span class="sxs-lookup"><span data-stu-id="9e040-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="9e040-130">TXT</span><span class="sxs-lookup"><span data-stu-id="9e040-130">TXT</span></span>  <br/> |<span data-ttu-id="9e040-131">(Deje este campo en blanco)</span><span class="sxs-lookup"><span data-stu-id="9e040-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="9e040-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9e040-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9e040-133">NOTA: Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9e040-133">NOTE: This is an example.</span></span> <span data-ttu-id="9e040-134">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="9e040-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="9e040-135">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="9e040-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="9e040-136">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e040-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="9e040-137">Seleccione **Guardar de** nuevo.</span><span class="sxs-lookup"><span data-stu-id="9e040-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="9e040-138">En el cuadro de diálogo Editar configuración **DNS,** seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="9e040-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="9e040-139">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="9e040-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9e040-140">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="9e040-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="9e040-141">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="9e040-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9e040-142">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="9e040-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9e040-143">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="9e040-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9e040-144">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="9e040-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9e040-145">En la página **Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="9e040-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e040-146">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="9e040-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9e040-147">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="9e040-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9e040-148">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e040-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9e040-149">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e040-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9e040-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9e040-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="9e040-151">Siga los pasos siguientes o [vea el vídeo (empieza en 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="9e040-151">Follow the steps below or [watch the video (start at 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e040-152">Si se registró con 1und1.de, [inicie sesión aquí.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="9e040-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="9e040-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="9e040-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="9e040-154">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9e040-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="9e040-155">Seleccione **Administrar dominios.**</span><span class="sxs-lookup"><span data-stu-id="9e040-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="9e040-156">En la **página Centro de** dominio, busque el dominio que desea actualizar y, a continuación, seleccione el control **panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="9e040-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="9e040-157">En el **área Configuración del** dominio, seleccione Editar configuración **dns.**</span><span class="sxs-lookup"><span data-stu-id="9e040-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="9e040-158">En la **sección Registros MX,** en el área Agente de intercambio **de correo (registro MX),** seleccione **Otro servidor de correo.**</span><span class="sxs-lookup"><span data-stu-id="9e040-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="9e040-159">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="9e040-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="9e040-160">![1 &amp; 1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="9e040-161">Si ya aparecen registros MX en la lista, elimínelos seleccionando el registro y, después, presionando la tecla **Eliminar** del teclado.</span><span class="sxs-lookup"><span data-stu-id="9e040-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="9e040-162">(Si no hay ningún registro MX en la lista, continúe con el paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="9e040-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="9e040-163">![1 &amp; 1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="9e040-164">En los cuadros para el registro **MX 1**, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e040-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="9e040-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="9e040-165">**MX 1**</span></span>|<span data-ttu-id="9e040-166">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="9e040-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="9e040-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e040-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="9e040-168">NOTA: Obtenga su \<domain-key\> cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e040-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="9e040-169">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="9e040-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="9e040-170">10  </span><span class="sxs-lookup"><span data-stu-id="9e040-170">10</span></span>  <br/> <span data-ttu-id="9e040-171">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="9e040-171">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | 
    
    ![1 y 1: configurar 2 y 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="9e040-173">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e040-173">Select **Save**.</span></span><br/><span data-ttu-id="9e040-174">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="9e040-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="9e040-175">![1 &amp; 1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="9e040-176">En el cuadro de diálogo Editar configuración **DNS,** seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="9e040-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="9e040-177">![Selección de Sí en el cuadro de diálogo Editar configuración DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9e040-178">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e040-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9e040-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9e040-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="9e040-180">1&1 IONOS requiere una solución alternativa para poder usar un registro MX junto con los registros CNAME necesarios para los servicios de correo electrónico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e040-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="9e040-181">Esta solución alternativa requiere crear un conjunto de subdominios en 1&1 IONOS y asignarlos a registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="9e040-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9e040-182">Asegúrese de que tiene al menos dos subdominios disponibles antes de iniciar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9e040-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="9e040-183">Se recomienda esta solución solo si ya tiene experiencia en la creación de subdominios en 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="9e040-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="9e040-184">Registros CNAME básicos</span><span class="sxs-lookup"><span data-stu-id="9e040-184">Basic CNAME records</span></span>

<span data-ttu-id="9e040-185">Siga los pasos siguientes o [vea el vídeo (empieza en 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="9e040-185">Follow the steps below or [watch the video (start at 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e040-186">Si se registró con 1und1.de, [inicie sesión aquí.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="9e040-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="9e040-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="9e040-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="9e040-188">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9e040-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="9e040-189">Seleccione **Administrar dominios.**</span><span class="sxs-lookup"><span data-stu-id="9e040-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="9e040-190">En la **página Centro de** dominio, busque el dominio que desea actualizar y, a continuación, seleccione Administrar **subdominios**.</span><span class="sxs-lookup"><span data-stu-id="9e040-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="9e040-191">![1 &amp; 1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="9e040-192">Ahora podrá crear dos subdominios y establecer un valor **Alias** para cada uno.</span><span class="sxs-lookup"><span data-stu-id="9e040-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="9e040-193">(Esto es necesario porque 1&1 IONOS solo admite un registro CNAME de nivel superior, pero Microsoft requiere varios registros CNAME).</span><span class="sxs-lookup"><span data-stu-id="9e040-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="9e040-194">En primer lugar, debe crear el subdominio Autodiscover.</span><span class="sxs-lookup"><span data-stu-id="9e040-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="9e040-195">En la **sección Información general del subdominio,** seleccione Crear **subdominio.**</span><span class="sxs-lookup"><span data-stu-id="9e040-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="9e040-p113">En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).</span><span class="sxs-lookup"><span data-stu-id="9e040-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="9e040-199">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="9e040-199">**Create Subdomain**</span></span>|<span data-ttu-id="9e040-200">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9e040-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9e040-201">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="9e040-201">autodiscover</span></span>  <br/> |<span data-ttu-id="9e040-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e040-202">autodiscover.outlook.com</span></span>   | 

    ![1 &amp; 1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="9e040-204">Seleccione **Crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="9e040-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="9e040-205">![1 &amp; 1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="9e040-206">En la **sección Información general del** subdominio, busque el subdominio de detección automática que acaba de crear y, a continuación, seleccione el control panel **(v)** para ese subdominio. </span><span class="sxs-lookup"><span data-stu-id="9e040-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="9e040-207">![1 &amp; 1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="9e040-208">En el **área Configuración del subdominio,** seleccione Editar **configuración dns.**</span><span class="sxs-lookup"><span data-stu-id="9e040-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="9e040-209">![1 &amp; 1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="9e040-210">En la **sección Registros A/AAAA (direcciones IP),** en el área Dirección **IP (Registro A),** seleccione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="9e040-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="9e040-211">![1 &amp; 1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="9e040-212">En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e040-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="9e040-213">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="9e040-213">**Create Subdomain**</span></span>|<span data-ttu-id="9e040-214">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9e040-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9e040-215">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="9e040-215">autodiscover</span></span>  <br/> |<span data-ttu-id="9e040-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e040-216">autodiscover.outlook.com</span></span>   |

    ![1 &amp; 1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="9e040-218">Active la casilla del aviso de declinación de responsabilidades **Soy consciente**.</span><span class="sxs-lookup"><span data-stu-id="9e040-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="9e040-219">![1 &amp; 1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="9e040-220">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e040-220">Select **Save**.</span></span><br/><span data-ttu-id="9e040-221">![1 &amp; 1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="9e040-222">Registros CNAME adicionales</span><span class="sxs-lookup"><span data-stu-id="9e040-222">Additional CNAME records</span></span>

<span data-ttu-id="9e040-p114">Los registros CNAME adicionales creados con el procedimiento siguiente habilitan servicios Skype Empresarial Online. Repetirá los mismos pasos que siguió para crear los dos registros anteriores CNAME.</span><span class="sxs-lookup"><span data-stu-id="9e040-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="9e040-225">Cree el tercer subdominio (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="9e040-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="9e040-226">En la **sección Información general del subdominio,** seleccione Crear **subdominio.**</span><span class="sxs-lookup"><span data-stu-id="9e040-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="9e040-p115">En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).</span><span class="sxs-lookup"><span data-stu-id="9e040-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="9e040-229">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="9e040-229">**Create Subdomain**</span></span>|<span data-ttu-id="9e040-230">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9e040-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9e040-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9e040-231">lyncdiscover</span></span>   |<span data-ttu-id="9e040-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e040-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="9e040-233">Seleccione **Crear subdominio.**</span><span class="sxs-lookup"><span data-stu-id="9e040-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="9e040-234">En la **página Centro de dominio,** seleccione **Administrar subdominios**.</span><span class="sxs-lookup"><span data-stu-id="9e040-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="9e040-235">En la **sección Información general del** subdominio, busque el subdominio **lyncdiscover** que acaba de crear y, a continuación, seleccione el control **panel (v)** para ese subdominio.</span><span class="sxs-lookup"><span data-stu-id="9e040-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="9e040-236">En el **área Configuración del subdominio,** seleccione Editar **configuración dns.**</span><span class="sxs-lookup"><span data-stu-id="9e040-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="9e040-237">En la **sección Registros A/AAAA (direcciones IP),** en el área Dirección **IP (Registro A),** seleccione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="9e040-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="9e040-238">En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e040-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="9e040-239">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="9e040-239">**Create Subdomain**</span></span>|<span data-ttu-id="9e040-240">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9e040-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9e040-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9e040-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9e040-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e040-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="9e040-243">Active la casilla para el aviso de **declinación** de responsabilidades I am aware y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e040-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="9e040-244">En el cuadro de diálogo Editar configuración **DNS,** seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="9e040-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="9e040-245">Crear el cuarto subdominio (SIP):</span><span class="sxs-lookup"><span data-stu-id="9e040-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="9e040-246">En la **sección Información general del subdominio,** seleccione Crear **subdominio.**</span><span class="sxs-lookup"><span data-stu-id="9e040-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="9e040-p116">En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).</span><span class="sxs-lookup"><span data-stu-id="9e040-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="9e040-249">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="9e040-249">**Create Subdomain**</span></span>|<span data-ttu-id="9e040-250">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9e040-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9e040-251">sip</span><span class="sxs-lookup"><span data-stu-id="9e040-251">sip</span></span>  <br/> |<span data-ttu-id="9e040-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e040-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="9e040-253">Seleccione **Crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="9e040-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="9e040-254">En la **página Centro de dominio,** seleccione **Administrar subdominios**.</span><span class="sxs-lookup"><span data-stu-id="9e040-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="9e040-255">En la **sección Información general del** subdominio, busque el subdominio **sip** que acaba de crear y, a continuación, seleccione el control **panel (v)** para ese subdominio.</span><span class="sxs-lookup"><span data-stu-id="9e040-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="9e040-256">En el **área Configuración del subdominio,** seleccione Editar **configuración dns.**</span><span class="sxs-lookup"><span data-stu-id="9e040-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="9e040-257">En la **sección Registros A/AAAA (direcciones IP),** en el área Dirección **IP (Registro A),** seleccione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="9e040-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="9e040-258">En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e040-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="9e040-259">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="9e040-259">**Create Subdomain**</span></span>|<span data-ttu-id="9e040-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9e040-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9e040-261">sip</span><span class="sxs-lookup"><span data-stu-id="9e040-261">sip</span></span>  <br/> |<span data-ttu-id="9e040-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e040-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="9e040-263">Active la casilla para el aviso de **declinación** de responsabilidades I am aware y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e040-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="9e040-264">En el cuadro de diálogo Editar configuración **DNS,** seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="9e040-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="9e040-265">Registros CNAME necesarios para MDM</span><span class="sxs-lookup"><span data-stu-id="9e040-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e040-266">Siga el procedimiento que ha usado para los otros cuatro registros CNAME, pero proporcione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e040-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="9e040-267">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="9e040-267">**Create Subdomain**</span></span>|<span data-ttu-id="9e040-268">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9e040-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e040-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9e040-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9e040-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9e040-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="9e040-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9e040-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9e040-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9e040-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9e040-273">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="9e040-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e040-274">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="9e040-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9e040-275">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="9e040-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9e040-276">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e040-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9e040-277">En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *de*  SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="9e040-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="9e040-278">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="9e040-278">Need examples?</span></span> <span data-ttu-id="9e040-279">Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="9e040-279">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="9e040-280">Para validar el registro de SPF, puede usar una de estas herramientas de[validación de SPF.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="9e040-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
<span data-ttu-id="9e040-281">Siga los pasos siguientes o [vea el vídeo (empieza en 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="9e040-281">Follow the steps below or [watch the video (start at 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e040-282">Si se registró con 1und1.de, [inicie sesión aquí.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="9e040-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="9e040-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="9e040-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="9e040-284">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9e040-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="9e040-285">Seleccione **Administrar dominios.**</span><span class="sxs-lookup"><span data-stu-id="9e040-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="9e040-286">En la **página Centro de** dominio, busque el dominio que desea actualizar y, a continuación, seleccione el control **panel** (**v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="9e040-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="9e040-287">En el **área Configuración del** dominio, seleccione Editar configuración **dns.**</span><span class="sxs-lookup"><span data-stu-id="9e040-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="9e040-288">En la **sección Registros TXT y SRV,** seleccione Agregar **registro.**</span><span class="sxs-lookup"><span data-stu-id="9e040-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="9e040-289">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="9e040-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="9e040-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9e040-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="9e040-291">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="9e040-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="9e040-292">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9e040-292">**Type**</span></span>|<span data-ttu-id="9e040-293">**Prefijo**</span><span class="sxs-lookup"><span data-stu-id="9e040-293">**Prefix**</span></span>|<span data-ttu-id="9e040-294">**Valor de nombre**</span><span class="sxs-lookup"><span data-stu-id="9e040-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9e040-295">TXT</span><span class="sxs-lookup"><span data-stu-id="9e040-295">TXT</span></span>  <br/> |<span data-ttu-id="9e040-296">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="9e040-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9e040-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9e040-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9e040-298">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="9e040-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![Registro TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="9e040-300">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e040-300">Select **Save**.</span></span><br/><span data-ttu-id="9e040-301">![Agregar registro](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="9e040-302">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e040-302">Select **Save**.</span></span><br/><span data-ttu-id="9e040-303">![Guardar registro](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="9e040-304">En el cuadro de diálogo Editar configuración **DNS,** seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="9e040-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="9e040-305">![Selección de Sí en el cuadro de diálogo Editar configuración DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9e040-306">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e040-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="9e040-307">Siga los pasos siguientes o [vea el vídeo (empieza en 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="9e040-307">Follow the steps below or [watch the video (start at 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e040-308">Si se registró con 1und1.de, [inicie sesión aquí.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="9e040-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="9e040-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="9e040-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="9e040-310">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9e040-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="9e040-311">Seleccione **Administrar dominios.**</span><span class="sxs-lookup"><span data-stu-id="9e040-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="9e040-312">En la **página Centro de** dominio, busque el dominio que desea actualizar y, a continuación, seleccione el control **panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="9e040-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="9e040-313">En el **área Configuración del** dominio, seleccione Editar configuración **dns.**</span><span class="sxs-lookup"><span data-stu-id="9e040-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="9e040-314">En la **sección Registros TXT y SRV,** seleccione Agregar **registro.**</span><span class="sxs-lookup"><span data-stu-id="9e040-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="9e040-315">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="9e040-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="9e040-316">En el área **Agregar registro**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores que aparecen en la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e040-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="9e040-317">(Elija los **valores tipo** **y TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="9e040-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9e040-318">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9e040-318">**Type**</span></span>|<span data-ttu-id="9e040-319">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="9e040-319">**Service**</span></span>|<span data-ttu-id="9e040-320">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="9e040-320">**Protocol**</span></span>|<span data-ttu-id="9e040-321">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9e040-321">**Name**</span></span>|<span data-ttu-id="9e040-322">**Host**</span><span class="sxs-lookup"><span data-stu-id="9e040-322">**Host**</span></span>|<span data-ttu-id="9e040-323">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="9e040-323">**Priority**</span></span>|<span data-ttu-id="9e040-324">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="9e040-324">**Weight**</span></span>|<span data-ttu-id="9e040-325">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="9e040-325">**Port**</span></span>|<span data-ttu-id="9e040-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e040-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e040-327">SRV</span><span class="sxs-lookup"><span data-stu-id="9e040-327">SRV</span></span>  <br/> |<span data-ttu-id="9e040-328">sip</span><span class="sxs-lookup"><span data-stu-id="9e040-328">sip</span></span>  <br/> |<span data-ttu-id="9e040-329">_tls</span><span class="sxs-lookup"><span data-stu-id="9e040-329">tls</span></span>  <br/> |<span data-ttu-id="9e040-330">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="9e040-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9e040-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e040-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9e040-332">100</span><span class="sxs-lookup"><span data-stu-id="9e040-332">100</span></span>  <br/> |<span data-ttu-id="9e040-333">1 </span><span class="sxs-lookup"><span data-stu-id="9e040-333">1</span></span>  <br/> |<span data-ttu-id="9e040-334">443</span><span class="sxs-lookup"><span data-stu-id="9e040-334">443</span></span>  <br/> |<span data-ttu-id="9e040-335">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="9e040-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="9e040-336">SRV</span><span class="sxs-lookup"><span data-stu-id="9e040-336">SRV</span></span>  <br/> |<span data-ttu-id="9e040-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9e040-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="9e040-338">tcp</span><span class="sxs-lookup"><span data-stu-id="9e040-338">tcp</span></span>  <br/> |<span data-ttu-id="9e040-339">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="9e040-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9e040-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e040-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="9e040-341">100</span><span class="sxs-lookup"><span data-stu-id="9e040-341">100</span></span>  <br/> |<span data-ttu-id="9e040-342">1 </span><span class="sxs-lookup"><span data-stu-id="9e040-342">1</span></span>  <br/> |<span data-ttu-id="9e040-343">5061</span><span class="sxs-lookup"><span data-stu-id="9e040-343">5061</span></span>  <br/> |<span data-ttu-id="9e040-344">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="9e040-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1 &amp; 1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="9e040-346">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e040-346">Select **Save**.</span></span> <br/><span data-ttu-id="9e040-347">![1 &amp; 1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="9e040-348">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e040-348">Select **Save**.</span></span> <br/><span data-ttu-id="9e040-349">![1 &amp; 1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="9e040-350">En el cuadro de diálogo Editar configuración **DNS,** seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="9e040-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="9e040-351">![Selección de Sí en el cuadro de diálogo Editar configuración DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="9e040-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="9e040-352">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="9e040-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="9e040-353">En la **sección Registros TXT y SRV,** seleccione Agregar **registro.**</span><span class="sxs-lookup"><span data-stu-id="9e040-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="9e040-354">En el **área Agregar** registro, cree un registro con los valores de la otra fila de la tabla y, a continuación, vuelva a seleccionar **Agregar** **,** Guardar y **Sí** para completar el registro.</span><span class="sxs-lookup"><span data-stu-id="9e040-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="9e040-355">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="9e040-355">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9e040-356">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="9e040-356">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9e040-357">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e040-357">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
