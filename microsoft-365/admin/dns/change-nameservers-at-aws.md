---
title: Cambiar los servidores DNS para configurar Microsoft con Amazon Web Services (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Obtenga información sobre cómo configurar Microsoft para administrar los registros DNS en Amazon Web Services (AWS). '
ms.openlocfilehash: 6393ef3e0d9603f122685dd3e3904b653fda8c34
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630000"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a><span data-ttu-id="c1606-103">Cambiar los servidores DNS para configurar Microsoft con Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="c1606-103">Change nameservers to set up Microsoft with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="c1606-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="c1606-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c1606-105">Siga estas instrucciones si desea que Microsoft administre los registros DNS por usted.</span><span class="sxs-lookup"><span data-stu-id="c1606-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="c1606-106">(Si lo prefiere, puede [administrar todos los registros DNS de Microsoft en AWS](create-dns-records-at-aws.md)).</span><span class="sxs-lookup"><span data-stu-id="c1606-106">(If you prefer, you can [manage all your Microsoft DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c1606-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="c1606-107">Add a TXT record for verification</span></span>

<span data-ttu-id="c1606-108">Antes de usar el dominio con Microsoft, debemos asegurarnos de que es el propietario.</span><span class="sxs-lookup"><span data-stu-id="c1606-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="c1606-109">Su capacidad para iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS es la que se demuestre a Microsoft que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="c1606-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1606-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="c1606-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c1606-p104">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="c1606-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c1606-114">En la página **recursos** , seleccione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="c1606-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="c1606-115">En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="c1606-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="c1606-116">Seleccione **crear conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="c1606-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="c1606-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c1606-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c1606-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="c1606-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="c1606-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="c1606-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1606-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="c1606-121">**Name**</span></span> <br/> |<span data-ttu-id="c1606-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="c1606-122">**Type**</span></span> <br/> |<span data-ttu-id="c1606-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="c1606-123">**Alias**</span></span> <br/> |<span data-ttu-id="c1606-124">**TTL (segundos)**</span><span class="sxs-lookup"><span data-stu-id="c1606-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="c1606-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c1606-125">**Value**</span></span> <br/> |<span data-ttu-id="c1606-126">**Directiva de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="c1606-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="c1606-127">(Deje este campo en blanco)</span><span class="sxs-lookup"><span data-stu-id="c1606-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="c1606-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="c1606-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="c1606-129">No</span><span class="sxs-lookup"><span data-stu-id="c1606-129">No</span></span>  <br/> |<span data-ttu-id="c1606-130">300</span><span class="sxs-lookup"><span data-stu-id="c1606-130">300</span></span>  <br/> |<span data-ttu-id="c1606-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c1606-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="c1606-132">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c1606-132">**Note:** This is an example.</span></span> <span data-ttu-id="c1606-133">Use aquí su **destino específico o** el valor de dirección de destino de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c1606-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="c1606-134">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="c1606-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="c1606-135">Simple</span><span class="sxs-lookup"><span data-stu-id="c1606-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="c1606-136">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c1606-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="c1606-137">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="c1606-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c1606-138">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.</span><span class="sxs-lookup"><span data-stu-id="c1606-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="c1606-139">Cuando Microsoft encuentre el registro TXT correcto, se comprobará el dominio.</span><span class="sxs-lookup"><span data-stu-id="c1606-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c1606-140">En el centro de administración de Microsoft, vaya a la página de **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="c1606-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c1606-141">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="c1606-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c1606-142">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="c1606-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c1606-143">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="c1606-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c1606-144">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="c1606-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c1606-145">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="c1606-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c1606-146">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c1606-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="c1606-147">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="c1606-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="c1606-148">Para completar la configuración de su dominio con Microsoft, debe cambiar los registros NS de su dominio en su registrador de dominios para que apunten a los servidores de nombres principal y secundario de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1606-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="c1606-149">Esto configura a Microsoft para que actualice los registros DNS del dominio por usted.</span><span class="sxs-lookup"><span data-stu-id="c1606-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="c1606-150">Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="c1606-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c1606-151">Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft, se ven afectados todos los servicios que están actualmente asociados a su dominio.</span><span class="sxs-lookup"><span data-stu-id="c1606-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="c1606-152">Por ejemplo, todos los mensajes de correo electrónico enviados a su dominio (como rob@ *your_domain* . com) empezarán a llegar a Microsoft después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="c1606-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="c1606-153">El siguiente procedimiento le mostrará cómo eliminar cualquier otro de los servidores de nombres no deseados de la lista, y también cómo agregar los servidores de nombres correctos si aún no aparecen.</span><span class="sxs-lookup"><span data-stu-id="c1606-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="c1606-154">> cuando haya completado los pasos de esta sección, los únicos servidores DNS que se deben enumerar son los cuatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c1606-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="c1606-155">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="c1606-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="c1606-156">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="c1606-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c1606-157">En la página **recursos** , seleccione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="c1606-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="c1606-158">En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="c1606-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="c1606-159">Seleccione el conjunto de registros **Servidor DNS**.</span><span class="sxs-lookup"><span data-stu-id="c1606-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="c1606-161">En el conjunto de registros **NS: servidor de nombres de dominio** del cuadro **Valor**, elimine todos los servidores de nombres al seleccionarlos todos y después presionar la tecla **Supr** en el teclado.</span><span class="sxs-lookup"><span data-stu-id="c1606-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="c1606-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="c1606-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="c1606-163">(Es decir, elimine solo los servidores DNS actuales que *no* tengan el nombre **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="c1606-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="c1606-165">En el área **TTL (segundos):** , seleccione **1H** (1 hora).</span><span class="sxs-lookup"><span data-stu-id="c1606-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Seleccionar 1H para una hora](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="c1606-167">Aún en el conjunto de registros **NS: servidor de nombres**, en el cuadro **Valor**, escriba o copie y pegue el valor **Primera línea** de la tabla siguiente y después presione la tecla **Entrar** en el teclado y escriba o copie y pegue el siguiente valor **línea**.</span><span class="sxs-lookup"><span data-stu-id="c1606-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="c1606-168">Cada valor de servidor DNS  *debe*  estar en su propia línea dentro del cuadro **Valor**, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="c1606-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c1606-169">**Primera línea**</span><span class="sxs-lookup"><span data-stu-id="c1606-169">**First line**</span></span> <br/> |<span data-ttu-id="c1606-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="c1606-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="c1606-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c1606-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="c1606-172">**Segunda línea**</span><span class="sxs-lookup"><span data-stu-id="c1606-172">**Second line**</span></span> <br/> |<span data-ttu-id="c1606-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="c1606-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="c1606-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c1606-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="c1606-175">**Tercera línea**</span><span class="sxs-lookup"><span data-stu-id="c1606-175">**Third line**</span></span> <br/> |<span data-ttu-id="c1606-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="c1606-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="c1606-177">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c1606-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="c1606-178">**Cuarta línea**</span><span class="sxs-lookup"><span data-stu-id="c1606-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="c1606-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="c1606-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="c1606-180">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c1606-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Escriba o pegue el valor de la primera línea en el cuadro valor](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="c1606-182">Seleccione **Guardar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="c1606-182">Select **Save Record Set**.</span></span>
    
    ![Seleccione Guardar conjunto de registros.](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="c1606-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c1606-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="c1606-185">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="c1606-185">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
