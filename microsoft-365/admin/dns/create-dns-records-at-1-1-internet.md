---
title: Crear registros DNS en 1&1 IONOS para Office 365
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en 1&1 IONOS para Office 365.
ms.openlocfilehash: 88a46fa51ac3e259d617d6d6e1a3dbb189c1ee6d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246861"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a><span data-ttu-id="ca580-103">Crear registros DNS en 1&1 IONOS para Office 365</span><span class="sxs-lookup"><span data-stu-id="ca580-103">Create DNS records at 1&1 IONOS for Office 365</span></span>

 <span data-ttu-id="ca580-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="ca580-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="ca580-105">Tenga en cuenta que 1&1 IONOS no permite que un dominio tenga un registro MX y un registro CNAME de detección automática de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="ca580-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="ca580-106">Esto limita las formas en que puede configurar Exchange Online para Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca580-106">This limits the ways in which you can configure Exchange Online for Office 365.</span></span> <span data-ttu-id="ca580-107">Hay una solución alternativa, pero le recomendamos que la emplee **solo** si ya tiene experiencia con la creación de subdominios en 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="ca580-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="ca580-108">> si, a pesar de esta [limitación del servicio](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) , elige administrar sus propios registros DNS de Office 365 en 1&1 IONOS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="ca580-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Office 365 DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="ca580-109">Después de agregar estos registros a la 1&1 IONOS, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca580-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="ca580-110">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="ca580-110">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca580-111">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ca580-111">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ca580-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="ca580-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ca580-113">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ca580-113">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ca580-114">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="ca580-114">Add a TXT record for verification</span></span>

<span data-ttu-id="ca580-p103">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="ca580-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca580-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="ca580-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="ca580-119">Siga los pasos siguientes o [vea el vídeo (empieza en 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ca580-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ca580-120">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="ca580-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ca580-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ca580-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ca580-122">Seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="ca580-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ca580-123">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="ca580-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ca580-124">En el área **configuración del dominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="ca580-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ca580-125">En la sección **registros txt y SRV** , seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="ca580-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="ca580-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ca580-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ca580-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ca580-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="ca580-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ca580-128">**Type**</span></span> <br/> |<span data-ttu-id="ca580-129">**Prefijo**</span><span class="sxs-lookup"><span data-stu-id="ca580-129">**Prefix**</span></span> <br/> |<span data-ttu-id="ca580-130">**Valor de nombre**</span><span class="sxs-lookup"><span data-stu-id="ca580-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="ca580-131">TXT</span><span class="sxs-lookup"><span data-stu-id="ca580-131">TXT</span></span>  <br/> |<span data-ttu-id="ca580-132">(Deje este campo en blanco)</span><span class="sxs-lookup"><span data-stu-id="ca580-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="ca580-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ca580-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ca580-134">Nota: este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ca580-134">NOTE: This is an example.</span></span> <span data-ttu-id="ca580-135">Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca580-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="ca580-136">¿Cómo puedo encontrarlo?</span><span class="sxs-lookup"><span data-stu-id="ca580-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="ca580-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ca580-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="ca580-138">Vuelva a seleccionar **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="ca580-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="ca580-139">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="ca580-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="ca580-140">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="ca580-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ca580-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="ca580-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ca580-142">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="ca580-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ca580-143">En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="ca580-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ca580-144">En la página **dominios** , seleccione el dominio que desea comprobar.</span><span class="sxs-lookup"><span data-stu-id="ca580-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ca580-145">En la página **configuración** , seleccione **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="ca580-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ca580-146">En la página **comprobar dominio** , seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="ca580-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ca580-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ca580-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ca580-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="ca580-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ca580-149">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ca580-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="ca580-150">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="ca580-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="ca580-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ca580-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="ca580-152">Siga los pasos siguientes o [vea el vídeo (empieza en 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ca580-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca580-153">Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="ca580-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ca580-154">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="ca580-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ca580-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ca580-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ca580-156">Seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="ca580-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ca580-157">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="ca580-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ca580-158">En el área **configuración del dominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="ca580-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ca580-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span><span class="sxs-lookup"><span data-stu-id="ca580-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="ca580-160">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="ca580-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="ca580-161">![1&amp;1-BP-configure-2-1](../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-161">![1&amp;1-BP-Configure-2-1](../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="ca580-162">Si ya aparecen registros MX en la lista, elimínelos seleccionando el registro y, después, presionando la tecla **Eliminar** del teclado.</span><span class="sxs-lookup"><span data-stu-id="ca580-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="ca580-163">(Si no hay ningún registro MX en la lista, continúe con el paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="ca580-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="ca580-164">![1&amp;1-BP-configure-2-2](../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-164">![1&amp;1-BP-Configure-2-2](../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="ca580-165">En los cuadros para el registro **MX 1**, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca580-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="ca580-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="ca580-166">**MX 1**</span></span>|<span data-ttu-id="ca580-167">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="ca580-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="ca580-168">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="ca580-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="ca580-169">Nota: obtenga la \<clave\> de dominio de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca580-169">NOTE: Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="ca580-170">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="ca580-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ca580-171">10 </span><span class="sxs-lookup"><span data-stu-id="ca580-171">10</span></span>  <br/> <span data-ttu-id="ca580-172">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="ca580-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 y 1-configurar 2 y 3](../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="ca580-174">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ca580-174">Select **Save**.</span></span><br/><span data-ttu-id="ca580-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ca580-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="ca580-176">![1&amp;1-BP-configure-2-4](../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-176">![1&amp;1-BP-Configure-2-4](../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="ca580-177">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="ca580-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="ca580-178">![Selección de sí en el cuadro de diálogo Editar configuración DNS](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-178">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="ca580-179">Agregar los seis registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="ca580-179">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="ca580-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ca580-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="ca580-181">1&1 IONOS requiere una solución alternativa para que pueda usar un registro MX junto con los registros CNAME necesarios para los servicios de correo electrónico de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca580-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Office 365 email services.</span></span> <span data-ttu-id="ca580-182">Para solucionar este problema, es necesario crear un conjunto de subdominios en 1&1 IONOS y asignarlos a registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="ca580-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ca580-183">Asegúrese de que tiene al menos dos subdominios disponibles antes de iniciar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ca580-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="ca580-184">Le recomendamos esta solución solo si ya tiene experiencia con la creación de subdominios en 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="ca580-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="ca580-185">Registros CNAME básicos</span><span class="sxs-lookup"><span data-stu-id="ca580-185">Basic CNAME records</span></span>

<span data-ttu-id="ca580-186">Siga los pasos siguientes o [vea el vídeo (empieza en 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ca580-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca580-187">Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="ca580-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ca580-188">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="ca580-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ca580-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ca580-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ca580-190">Seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="ca580-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ca580-191">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione **administrar subdominios**.</span><span class="sxs-lookup"><span data-stu-id="ca580-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="ca580-192">![1&amp;1-BP-configure-3-0](../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-192">![1&amp;1-BP-Configure-3-0](../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="ca580-193">Ahora podrá crear dos subdominios y establecer un valor **Alias** para cada uno.</span><span class="sxs-lookup"><span data-stu-id="ca580-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="ca580-194">(Esto es necesario porque 1&1 IONOS admite solo un registro CNAME de nivel superior, pero Office 365 requiere varios registros CNAME).</span><span class="sxs-lookup"><span data-stu-id="ca580-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Office 365 requires several CNAME records.)</span></span><br/><span data-ttu-id="ca580-195">En primer lugar, debe crear el subdominio Autodiscover.</span><span class="sxs-lookup"><span data-stu-id="ca580-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="ca580-196">En la sección **información general de subdominio** , seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="ca580-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="ca580-p113">En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).</span><span class="sxs-lookup"><span data-stu-id="ca580-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="ca580-200">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="ca580-200">**Create Subdomain**</span></span>|<span data-ttu-id="ca580-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ca580-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ca580-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ca580-202">autodiscover</span></span>  <br/> |<span data-ttu-id="ca580-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ca580-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-configure-3-2](../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="ca580-205">Seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="ca580-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="ca580-206">![1&amp;1-BP-configure-3-3](../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-206">![1&amp;1-BP-Configure-3-3](../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="ca580-207">En la sección **información general de subdominio** , localice el subdominio **Autodiscover** que acaba de crear y, a continuación, seleccione el control **Panel (v)** para ese subdominio.</span><span class="sxs-lookup"><span data-stu-id="ca580-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="ca580-208">![1&amp;1-BP-configure-3-4](../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-208">![1&amp;1-BP-Configure-3-4](../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="ca580-209">En el área **configuración de subdominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="ca580-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="ca580-210">![1&amp;1-BP-configure-3-5](../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-210">![1&amp;1-BP-Configure-3-5](../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="ca580-211">En la sección **registros A/AAAA (direcciones IP)** , en el área **dirección IP (registro A)** , seleccione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ca580-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="ca580-212">![1&amp;1-BP-configure-3-6](../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-212">![1&amp;1-BP-Configure-3-6](../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="ca580-213">En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca580-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="ca580-214">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="ca580-214">**Create Subdomain**</span></span>|<span data-ttu-id="ca580-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ca580-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ca580-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ca580-216">autodiscover</span></span>  <br/> |<span data-ttu-id="ca580-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ca580-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-configure-3-7](../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="ca580-219">Active la casilla del aviso de declinación de responsabilidades **Soy consciente**.</span><span class="sxs-lookup"><span data-stu-id="ca580-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="ca580-220">![1&amp;1-BP-configure-3-8-1](../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-220">![1&amp;1-BP-Configure-3-8-1](../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="ca580-221">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ca580-221">Select **Save**.</span></span><br/><span data-ttu-id="ca580-222">![1&amp;1-BP-configure-3-8-2](../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-222">![1&amp;1-BP-Configure-3-8-2](../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="ca580-223">Registros CNAME adicionales</span><span class="sxs-lookup"><span data-stu-id="ca580-223">Additional CNAME records</span></span>

<span data-ttu-id="ca580-p114">Los registros CNAME adicionales creados con el procedimiento siguiente habilitan servicios Skype Empresarial Online. Repetirá los mismos pasos que siguió para crear los dos registros anteriores CNAME.</span><span class="sxs-lookup"><span data-stu-id="ca580-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="ca580-226">Cree el tercer subdominio (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="ca580-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="ca580-227">En la sección **información general de subdominio** , seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="ca580-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="ca580-p115">En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).</span><span class="sxs-lookup"><span data-stu-id="ca580-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="ca580-230">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="ca580-230">**Create Subdomain**</span></span>|<span data-ttu-id="ca580-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ca580-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ca580-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ca580-232">lyncdiscover</span></span>   |<span data-ttu-id="ca580-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca580-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="ca580-234">Seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="ca580-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="ca580-235">En la página **centro de dominios** , seleccione **administrar subdominios**.</span><span class="sxs-lookup"><span data-stu-id="ca580-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="ca580-236">En la sección **información general de subdominio** , busque el subdominio **lyncdiscover** que acaba de crear y, a continuación, seleccione el control **Panel (v)** para ese subdominio.</span><span class="sxs-lookup"><span data-stu-id="ca580-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="ca580-237">En el área **configuración de subdominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="ca580-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="ca580-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ca580-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="ca580-239">En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca580-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="ca580-240">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="ca580-240">**Create Subdomain**</span></span>|<span data-ttu-id="ca580-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ca580-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ca580-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ca580-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ca580-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca580-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="ca580-244">Active la casilla de verificación **I-Aware** declinación de responsabilidades y, después, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ca580-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="ca580-245">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="ca580-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="ca580-246">Crear el cuarto subdominio (SIP):</span><span class="sxs-lookup"><span data-stu-id="ca580-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="ca580-247">En la sección **información general de subdominio** , seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="ca580-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="ca580-p116">En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).</span><span class="sxs-lookup"><span data-stu-id="ca580-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="ca580-250">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="ca580-250">**Create Subdomain**</span></span>|<span data-ttu-id="ca580-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ca580-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ca580-252">sip</span><span class="sxs-lookup"><span data-stu-id="ca580-252">sip</span></span>  <br/> |<span data-ttu-id="ca580-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca580-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="ca580-254">Seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="ca580-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="ca580-255">En la página **centro de dominios** , seleccione **administrar subdominios**.</span><span class="sxs-lookup"><span data-stu-id="ca580-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="ca580-256">En la sección **información general de subdominio** , busque el subdominio **SIP** que acaba de crear y, a continuación, seleccione el control **Panel (v)** para ese subdominio.</span><span class="sxs-lookup"><span data-stu-id="ca580-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="ca580-257">En el área **configuración de subdominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="ca580-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="ca580-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ca580-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="ca580-259">En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca580-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="ca580-260">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="ca580-260">**Create Subdomain**</span></span>|<span data-ttu-id="ca580-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ca580-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ca580-262">sip</span><span class="sxs-lookup"><span data-stu-id="ca580-262">sip</span></span>  <br/> |<span data-ttu-id="ca580-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca580-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="ca580-264">Active la casilla de verificación **I-Aware** declinación de responsabilidades y, después, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ca580-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="ca580-265">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="ca580-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="ca580-266">Registros CNAME necesarios para MDM</span><span class="sxs-lookup"><span data-stu-id="ca580-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca580-267">Siga el procedimiento que ha usado para los otros cuatro registros CNAME, pero proporcione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca580-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="ca580-268">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="ca580-268">**Create Subdomain**</span></span>|<span data-ttu-id="ca580-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ca580-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ca580-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ca580-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ca580-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ca580-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="ca580-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ca580-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ca580-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ca580-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ca580-274">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="ca580-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca580-275">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="ca580-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ca580-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="ca580-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ca580-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca580-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="ca580-278">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="ca580-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="ca580-279">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="ca580-279">Need examples?</span></span> <span data-ttu-id="ca580-280">Consulte estos [registros del sistema de nombres de dominio externo para Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="ca580-280">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="ca580-281">Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="ca580-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="ca580-282">Siga los pasos siguientes o [vea el vídeo (empieza en 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ca580-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca580-283">Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="ca580-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ca580-284">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="ca580-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ca580-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ca580-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ca580-286">Seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="ca580-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ca580-287">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** (**v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="ca580-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ca580-288">En el área **configuración del dominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="ca580-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ca580-289">En la sección **registros txt y SRV** , seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="ca580-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="ca580-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ca580-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="ca580-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ca580-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="ca580-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ca580-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="ca580-293">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ca580-293">**Type**</span></span>|<span data-ttu-id="ca580-294">**Prefijo**</span><span class="sxs-lookup"><span data-stu-id="ca580-294">**Prefix**</span></span>|<span data-ttu-id="ca580-295">**Valor de nombre**</span><span class="sxs-lookup"><span data-stu-id="ca580-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ca580-296">TXT</span><span class="sxs-lookup"><span data-stu-id="ca580-296">TXT</span></span>  <br/> |<span data-ttu-id="ca580-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="ca580-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ca580-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ca580-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ca580-299">**Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.</span><span class="sxs-lookup"><span data-stu-id="ca580-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![Registro TXT](../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="ca580-301">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ca580-301">Select **Save**.</span></span><br/><span data-ttu-id="ca580-302">![Agregar registro](../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-302">![Add record](../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="ca580-303">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ca580-303">Select **Save**.</span></span><br/><span data-ttu-id="ca580-304">![Guardar registro](../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-304">![Save record](../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="ca580-305">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="ca580-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="ca580-306">![Selección de sí en el cuadro de diálogo Editar configuración DNS](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-306">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="ca580-307">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="ca580-307">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="ca580-308">Siga los pasos siguientes o [vea el vídeo (empieza en 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ca580-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca580-309">Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="ca580-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ca580-310">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="ca580-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ca580-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ca580-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ca580-312">Seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="ca580-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ca580-313">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="ca580-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ca580-314">En el área **configuración del dominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="ca580-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ca580-315">En la sección **registros txt y SRV** , seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="ca580-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="ca580-316">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="ca580-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="ca580-317">En el área **Agregar registro**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores que aparecen en la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca580-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="ca580-318">(Seleccione los valores **tipo** y **TTL** que se muestran en la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="ca580-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ca580-319">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ca580-319">**Type**</span></span>|<span data-ttu-id="ca580-320">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="ca580-320">**Service**</span></span>|<span data-ttu-id="ca580-321">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="ca580-321">**Protocol**</span></span>|<span data-ttu-id="ca580-322">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ca580-322">**Name**</span></span>|<span data-ttu-id="ca580-323">**Host**</span><span class="sxs-lookup"><span data-stu-id="ca580-323">**Host**</span></span>|<span data-ttu-id="ca580-324">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="ca580-324">**Priority**</span></span>|<span data-ttu-id="ca580-325">**Peso**</span><span class="sxs-lookup"><span data-stu-id="ca580-325">**Weight**</span></span>|<span data-ttu-id="ca580-326">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="ca580-326">**Port**</span></span>|<span data-ttu-id="ca580-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ca580-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ca580-328">SRV</span><span class="sxs-lookup"><span data-stu-id="ca580-328">SRV</span></span>  <br/> |<span data-ttu-id="ca580-329">sip</span><span class="sxs-lookup"><span data-stu-id="ca580-329">sip</span></span>  <br/> |<span data-ttu-id="ca580-330">_tls</span><span class="sxs-lookup"><span data-stu-id="ca580-330">tls</span></span>  <br/> |<span data-ttu-id="ca580-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="ca580-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ca580-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca580-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="ca580-333">100</span><span class="sxs-lookup"><span data-stu-id="ca580-333">100</span></span>  <br/> |<span data-ttu-id="ca580-334">1</span><span class="sxs-lookup"><span data-stu-id="ca580-334">1</span></span>  <br/> |<span data-ttu-id="ca580-335">443</span><span class="sxs-lookup"><span data-stu-id="ca580-335">443</span></span>  <br/> |<span data-ttu-id="ca580-336">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="ca580-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="ca580-337">SRV</span><span class="sxs-lookup"><span data-stu-id="ca580-337">SRV</span></span>  <br/> |<span data-ttu-id="ca580-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ca580-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="ca580-339">tcp</span><span class="sxs-lookup"><span data-stu-id="ca580-339">tcp</span></span>  <br/> |<span data-ttu-id="ca580-340">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="ca580-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ca580-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca580-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="ca580-342">100</span><span class="sxs-lookup"><span data-stu-id="ca580-342">100</span></span>  <br/> |<span data-ttu-id="ca580-343">1</span><span class="sxs-lookup"><span data-stu-id="ca580-343">1</span></span>  <br/> |<span data-ttu-id="ca580-344">5061</span><span class="sxs-lookup"><span data-stu-id="ca580-344">5061</span></span>  <br/> |<span data-ttu-id="ca580-345">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="ca580-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-configure-5-1](../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="ca580-347">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ca580-347">Select **Save**.</span></span> <br/><span data-ttu-id="ca580-348">![1&amp;1-BP-configure-5-2](../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-348">![1&amp;1-BP-Configure-5-2](../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="ca580-349">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ca580-349">Select **Save**.</span></span> <br/><span data-ttu-id="ca580-350">![1&amp;1-BP-configure-5-3](../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-350">![1&amp;1-BP-Configure-5-3](../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="ca580-351">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="ca580-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="ca580-352">![Selección de sí en el cuadro de diálogo Editar configuración DNS](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="ca580-352">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="ca580-353">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="ca580-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="ca580-354">En la sección **registros txt y SRV** , seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="ca580-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="ca580-355">En el área **Agregar registro** , cree un registro con los valores de la otra fila de la tabla y, a continuación, vuelva a seleccionar **Agregar**, **Guardar**y **sí** para completar el registro.</span><span class="sxs-lookup"><span data-stu-id="ca580-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="ca580-356">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ca580-356">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ca580-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="ca580-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ca580-358">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ca580-358">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
