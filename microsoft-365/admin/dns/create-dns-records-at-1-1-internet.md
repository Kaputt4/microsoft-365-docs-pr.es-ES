---
title: Crear registros DNS en 1&1 IONOS para Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en 1&1 IONOS para Microsoft.
ms.openlocfilehash: 9e6994b1906293cb249bf64101deaeb94a033c81
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629772"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="92279-103">Crear registros DNS en 1&1 IONOS para Microsoft</span><span class="sxs-lookup"><span data-stu-id="92279-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="92279-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="92279-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="92279-105">Tenga en cuenta que 1&1 IONOS no permite que un dominio tenga un registro MX y un registro CNAME de detección automática de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="92279-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="92279-106">Esto limita las formas en que puede configurar Exchange Online para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92279-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="92279-107">Hay una solución alternativa, pero le recomendamos que la emplee **solo** si ya tiene experiencia con la creación de subdominios en 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="92279-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="92279-108">> si, a pesar de esta [limitación del servicio](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) , elige administrar sus propios registros DNS de Microsoft en 1&1 IONOS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.</span><span class="sxs-lookup"><span data-stu-id="92279-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="92279-109">Después de agregar estos registros a la 1&1 IONOS, su dominio estará configurado para trabajar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92279-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="92279-110">Para obtener más información sobre WebHosting y DNS para sitios web con Microsoft, vea [usar un sitio web público con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="92279-110">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="92279-111">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="92279-111">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="92279-112">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="92279-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="92279-113">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="92279-113">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="92279-114">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="92279-114">Add a TXT record for verification</span></span>

<span data-ttu-id="92279-115">Antes de usar el dominio con Microsoft, debemos asegurarnos de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="92279-115">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="92279-116">Su capacidad para iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS es la que se demuestre a Microsoft que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="92279-116">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="92279-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="92279-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="92279-119">Siga los pasos siguientes o [vea el vídeo (empieza en 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="92279-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="92279-120">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="92279-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="92279-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="92279-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="92279-122">Seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="92279-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="92279-123">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="92279-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="92279-124">En el área **configuración del dominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="92279-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="92279-125">En la sección **registros txt y SRV** , seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="92279-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="92279-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="92279-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="92279-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="92279-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="92279-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="92279-128">**Type**</span></span> <br/> |<span data-ttu-id="92279-129">**Prefijo**</span><span class="sxs-lookup"><span data-stu-id="92279-129">**Prefix**</span></span> <br/> |<span data-ttu-id="92279-130">**Valor de nombre**</span><span class="sxs-lookup"><span data-stu-id="92279-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="92279-131">TXT</span><span class="sxs-lookup"><span data-stu-id="92279-131">TXT</span></span>  <br/> |<span data-ttu-id="92279-132">(Deje este campo en blanco)</span><span class="sxs-lookup"><span data-stu-id="92279-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="92279-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="92279-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="92279-134">Nota: este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="92279-134">NOTE: This is an example.</span></span> <span data-ttu-id="92279-135">Use aquí su **destino específico o** el valor de dirección de destino de la tabla.</span><span class="sxs-lookup"><span data-stu-id="92279-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="92279-136">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="92279-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="92279-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92279-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="92279-138">Vuelva a seleccionar **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="92279-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="92279-139">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="92279-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="92279-140">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="92279-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="92279-141">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft 365 y pedirá a Microsoft 365 que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="92279-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="92279-142">Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.</span><span class="sxs-lookup"><span data-stu-id="92279-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="92279-143">En el centro de administración de Microsoft, vaya a la página de **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="92279-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="92279-144">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="92279-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="92279-145">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="92279-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="92279-146">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="92279-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="92279-147">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="92279-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="92279-148">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="92279-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="92279-149">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="92279-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="92279-150">Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft</span><span class="sxs-lookup"><span data-stu-id="92279-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="92279-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="92279-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="92279-152">Siga los pasos siguientes o [vea el vídeo (empieza en 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="92279-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="92279-153">Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="92279-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="92279-154">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="92279-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="92279-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="92279-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="92279-156">Seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="92279-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="92279-157">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="92279-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="92279-158">En el área **configuración del dominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="92279-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="92279-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span><span class="sxs-lookup"><span data-stu-id="92279-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="92279-160">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="92279-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="92279-161">![1&amp;1-BP-configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="92279-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="92279-162">Si ya aparecen registros MX en la lista, elimínelos seleccionando el registro y, después, presionando la tecla **Eliminar** del teclado.</span><span class="sxs-lookup"><span data-stu-id="92279-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="92279-163">(Si no hay ningún registro MX en la lista, continúe con el paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="92279-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="92279-164">![1&amp;1-BP-configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="92279-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="92279-165">En los cuadros para el registro **MX 1**, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="92279-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="92279-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="92279-166">**MX 1**</span></span>|<span data-ttu-id="92279-167">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="92279-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="92279-168">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="92279-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="92279-169">Nota: Obtén la \<clave\> de dominio de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92279-169">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="92279-170">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="92279-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="92279-171">10 </span><span class="sxs-lookup"><span data-stu-id="92279-171">10</span></span>  <br/> <span data-ttu-id="92279-172">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="92279-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 y 1-configurar 2 y 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="92279-174">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92279-174">Select **Save**.</span></span><br/><span data-ttu-id="92279-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="92279-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="92279-176">![1&amp;1-BP-configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="92279-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="92279-177">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="92279-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="92279-178">![Selección de sí en el cuadro de diálogo Editar configuración DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="92279-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="92279-179">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="92279-179">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="92279-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="92279-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="92279-181">1&1 IONOS requiere una solución alternativa para que pueda usar un registro MX junto con los registros CNAME necesarios para los servicios de correo electrónico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92279-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="92279-182">Para solucionar este problema, es necesario crear un conjunto de subdominios en 1&1 IONOS y asignarlos a registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="92279-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="92279-183">Asegúrese de que tiene al menos dos subdominios disponibles antes de iniciar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="92279-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="92279-184">Le recomendamos esta solución solo si ya tiene experiencia con la creación de subdominios en 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="92279-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="92279-185">Registros CNAME básicos</span><span class="sxs-lookup"><span data-stu-id="92279-185">Basic CNAME records</span></span>

<span data-ttu-id="92279-186">Siga los pasos siguientes o [vea el vídeo (empieza en 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="92279-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="92279-187">Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="92279-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="92279-188">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="92279-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="92279-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="92279-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="92279-190">Seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="92279-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="92279-191">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione **administrar subdominios**.</span><span class="sxs-lookup"><span data-stu-id="92279-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="92279-192">![1&amp;1-BP-configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="92279-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="92279-193">Ahora podrá crear dos subdominios y establecer un valor **Alias** para cada uno.</span><span class="sxs-lookup"><span data-stu-id="92279-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="92279-194">(Esto es necesario porque 1&1 IONOS admite solo un registro CNAME de nivel superior, pero Microsoft requiere varios registros CNAME).</span><span class="sxs-lookup"><span data-stu-id="92279-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="92279-195">En primer lugar, debe crear el subdominio Autodiscover.</span><span class="sxs-lookup"><span data-stu-id="92279-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="92279-196">En la sección **información general de subdominio** , seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="92279-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="92279-p113">En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).</span><span class="sxs-lookup"><span data-stu-id="92279-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="92279-200">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="92279-200">**Create Subdomain**</span></span>|<span data-ttu-id="92279-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="92279-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="92279-202">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="92279-202">autodiscover</span></span>  <br/> |<span data-ttu-id="92279-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="92279-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="92279-205">Seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="92279-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="92279-206">![1&amp;1-BP-configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="92279-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="92279-207">En la sección **información general de subdominio** , localice el subdominio **Autodiscover** que acaba de crear y, a continuación, seleccione el control **Panel (v)** para ese subdominio.</span><span class="sxs-lookup"><span data-stu-id="92279-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="92279-208">![1&amp;1-BP-configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="92279-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="92279-209">En el área **configuración de subdominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="92279-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="92279-210">![1&amp;1-BP-configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="92279-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="92279-211">En la sección **registros A/AAAA (direcciones IP)** , en el área **dirección IP (registro A)** , seleccione **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="92279-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="92279-212">![1&amp;1-BP-configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="92279-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="92279-213">En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="92279-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="92279-214">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="92279-214">**Create Subdomain**</span></span>|<span data-ttu-id="92279-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="92279-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="92279-216">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="92279-216">autodiscover</span></span>  <br/> |<span data-ttu-id="92279-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="92279-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="92279-219">Active la casilla del aviso de declinación de responsabilidades **Soy consciente**.</span><span class="sxs-lookup"><span data-stu-id="92279-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="92279-220">![1&amp;1-BP-configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="92279-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="92279-221">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92279-221">Select **Save**.</span></span><br/><span data-ttu-id="92279-222">![1&amp;1-BP-configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="92279-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="92279-223">Registros CNAME adicionales</span><span class="sxs-lookup"><span data-stu-id="92279-223">Additional CNAME records</span></span>

<span data-ttu-id="92279-p114">Los registros CNAME adicionales creados con el procedimiento siguiente habilitan servicios Skype Empresarial Online. Repetirá los mismos pasos que siguió para crear los dos registros anteriores CNAME.</span><span class="sxs-lookup"><span data-stu-id="92279-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="92279-226">Cree el tercer subdominio (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="92279-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="92279-227">En la sección **información general de subdominio** , seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="92279-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="92279-p115">En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).</span><span class="sxs-lookup"><span data-stu-id="92279-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="92279-230">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="92279-230">**Create Subdomain**</span></span>|<span data-ttu-id="92279-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="92279-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="92279-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="92279-232">lyncdiscover</span></span>   |<span data-ttu-id="92279-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="92279-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="92279-234">Seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="92279-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="92279-235">En la página **centro de dominios** , seleccione **administrar subdominios**.</span><span class="sxs-lookup"><span data-stu-id="92279-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="92279-236">En la sección **información general de subdominio** , busque el subdominio **lyncdiscover** que acaba de crear y, a continuación, seleccione el control **Panel (v)** para ese subdominio.</span><span class="sxs-lookup"><span data-stu-id="92279-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="92279-237">En el área **configuración de subdominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="92279-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="92279-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="92279-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="92279-239">En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="92279-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="92279-240">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="92279-240">**Create Subdomain**</span></span>|<span data-ttu-id="92279-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="92279-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="92279-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="92279-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="92279-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="92279-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="92279-244">Active la casilla de verificación **I-Aware** declinación de responsabilidades y, después, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92279-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="92279-245">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="92279-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="92279-246">Crear el cuarto subdominio (SIP):</span><span class="sxs-lookup"><span data-stu-id="92279-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="92279-247">En la sección **información general de subdominio** , seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="92279-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="92279-p116">En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).</span><span class="sxs-lookup"><span data-stu-id="92279-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="92279-250">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="92279-250">**Create Subdomain**</span></span>|<span data-ttu-id="92279-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="92279-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="92279-252">sip</span><span class="sxs-lookup"><span data-stu-id="92279-252">sip</span></span>  <br/> |<span data-ttu-id="92279-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="92279-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="92279-254">Seleccione **crear subdominio**.</span><span class="sxs-lookup"><span data-stu-id="92279-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="92279-255">En la página **centro de dominios** , seleccione **administrar subdominios**.</span><span class="sxs-lookup"><span data-stu-id="92279-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="92279-256">En la sección **información general de subdominio** , busque el subdominio **SIP** que acaba de crear y, a continuación, seleccione el control **Panel (v)** para ese subdominio.</span><span class="sxs-lookup"><span data-stu-id="92279-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="92279-257">En el área **configuración de subdominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="92279-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="92279-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="92279-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="92279-259">En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="92279-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="92279-260">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="92279-260">**Create Subdomain**</span></span>|<span data-ttu-id="92279-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="92279-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="92279-262">sip</span><span class="sxs-lookup"><span data-stu-id="92279-262">sip</span></span>  <br/> |<span data-ttu-id="92279-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="92279-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="92279-264">Active la casilla de verificación **I-Aware** declinación de responsabilidades y, después, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92279-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="92279-265">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="92279-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="92279-266">Registros CNAME necesarios para MDM</span><span class="sxs-lookup"><span data-stu-id="92279-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92279-267">Siga el procedimiento que ha usado para los otros cuatro registros CNAME, pero proporcione los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="92279-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="92279-268">**Crear subdominio**</span><span class="sxs-lookup"><span data-stu-id="92279-268">**Create Subdomain**</span></span>|<span data-ttu-id="92279-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="92279-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="92279-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="92279-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="92279-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="92279-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="92279-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="92279-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="92279-273">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="92279-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="92279-274">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="92279-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92279-275">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="92279-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="92279-276">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="92279-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="92279-277">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92279-277">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="92279-278">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="92279-278">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="92279-279">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="92279-279">Need examples?</span></span> <span data-ttu-id="92279-280">Consulte estos [registros del sistema de nombres de dominio externo para Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="92279-280">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="92279-281">Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="92279-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="92279-282">Siga los pasos siguientes o [vea el vídeo (empieza en 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="92279-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="92279-283">Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="92279-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="92279-284">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="92279-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="92279-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="92279-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="92279-286">Seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="92279-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="92279-287">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** (**v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="92279-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="92279-288">En el área **configuración del dominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="92279-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="92279-289">En la sección **registros txt y SRV** , seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="92279-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="92279-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="92279-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="92279-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="92279-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="92279-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="92279-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="92279-293">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="92279-293">**Type**</span></span>|<span data-ttu-id="92279-294">**Prefijo**</span><span class="sxs-lookup"><span data-stu-id="92279-294">**Prefix**</span></span>|<span data-ttu-id="92279-295">**Valor de nombre**</span><span class="sxs-lookup"><span data-stu-id="92279-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="92279-296">TXT</span><span class="sxs-lookup"><span data-stu-id="92279-296">TXT</span></span>  <br/> |<span data-ttu-id="92279-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="92279-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="92279-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="92279-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="92279-299">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="92279-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![Registro TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="92279-301">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92279-301">Select **Save**.</span></span><br/><span data-ttu-id="92279-302">![Agregar registro](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="92279-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="92279-303">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92279-303">Select **Save**.</span></span><br/><span data-ttu-id="92279-304">![Guardar registro](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="92279-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="92279-305">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="92279-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="92279-306">![Selección de sí en el cuadro de diálogo Editar configuración DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="92279-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="92279-307">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="92279-307">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="92279-308">Siga los pasos siguientes o [vea el vídeo (empieza en 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="92279-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="92279-309">Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="92279-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="92279-310">Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="92279-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="92279-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="92279-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="92279-312">Seleccione **administrar dominios**.</span><span class="sxs-lookup"><span data-stu-id="92279-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="92279-313">En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.</span><span class="sxs-lookup"><span data-stu-id="92279-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="92279-314">En el área **configuración del dominio** , seleccione **Editar configuración DNS**.</span><span class="sxs-lookup"><span data-stu-id="92279-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="92279-315">En la sección **registros txt y SRV** , seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="92279-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="92279-316">Agregue el primero de los dos registros SRV.</span><span class="sxs-lookup"><span data-stu-id="92279-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="92279-317">En el área **Agregar registro**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores que aparecen en la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="92279-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="92279-318">(Seleccione los valores **tipo** y **TTL** que se muestran en la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="92279-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="92279-319">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="92279-319">**Type**</span></span>|<span data-ttu-id="92279-320">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="92279-320">**Service**</span></span>|<span data-ttu-id="92279-321">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="92279-321">**Protocol**</span></span>|<span data-ttu-id="92279-322">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="92279-322">**Name**</span></span>|<span data-ttu-id="92279-323">**Host**</span><span class="sxs-lookup"><span data-stu-id="92279-323">**Host**</span></span>|<span data-ttu-id="92279-324">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="92279-324">**Priority**</span></span>|<span data-ttu-id="92279-325">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="92279-325">**Weight**</span></span>|<span data-ttu-id="92279-326">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="92279-326">**Port**</span></span>|<span data-ttu-id="92279-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="92279-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="92279-328">SRV</span><span class="sxs-lookup"><span data-stu-id="92279-328">SRV</span></span>  <br/> |<span data-ttu-id="92279-329">sip</span><span class="sxs-lookup"><span data-stu-id="92279-329">sip</span></span>  <br/> |<span data-ttu-id="92279-330">_tls</span><span class="sxs-lookup"><span data-stu-id="92279-330">tls</span></span>  <br/> |<span data-ttu-id="92279-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="92279-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="92279-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="92279-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="92279-333">100</span><span class="sxs-lookup"><span data-stu-id="92279-333">100</span></span>  <br/> |<span data-ttu-id="92279-334">1</span><span class="sxs-lookup"><span data-stu-id="92279-334">1</span></span>  <br/> |<span data-ttu-id="92279-335">443</span><span class="sxs-lookup"><span data-stu-id="92279-335">443</span></span>  <br/> |<span data-ttu-id="92279-336">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="92279-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="92279-337">SRV</span><span class="sxs-lookup"><span data-stu-id="92279-337">SRV</span></span>  <br/> |<span data-ttu-id="92279-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="92279-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="92279-339">tcp</span><span class="sxs-lookup"><span data-stu-id="92279-339">tcp</span></span>  <br/> |<span data-ttu-id="92279-340">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="92279-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="92279-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="92279-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="92279-342">100</span><span class="sxs-lookup"><span data-stu-id="92279-342">100</span></span>  <br/> |<span data-ttu-id="92279-343">1</span><span class="sxs-lookup"><span data-stu-id="92279-343">1</span></span>  <br/> |<span data-ttu-id="92279-344">5061</span><span class="sxs-lookup"><span data-stu-id="92279-344">5061</span></span>  <br/> |<span data-ttu-id="92279-345">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="92279-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="92279-347">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92279-347">Select **Save**.</span></span> <br/><span data-ttu-id="92279-348">![1&amp;1-BP-configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="92279-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="92279-349">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="92279-349">Select **Save**.</span></span> <br/><span data-ttu-id="92279-350">![1&amp;1-BP-configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="92279-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="92279-351">En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="92279-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="92279-352">![Selección de sí en el cuadro de diálogo Editar configuración DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="92279-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="92279-353">Agregue el otro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="92279-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="92279-354">En la sección **registros txt y SRV** , seleccione **Agregar registro**.</span><span class="sxs-lookup"><span data-stu-id="92279-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="92279-355">En el área **Agregar registro** , cree un registro con los valores de la otra fila de la tabla y, a continuación, vuelva a seleccionar **Agregar**, **Guardar**y **sí** para completar el registro.</span><span class="sxs-lookup"><span data-stu-id="92279-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="92279-356">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="92279-356">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="92279-357">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="92279-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="92279-358">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="92279-358">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
