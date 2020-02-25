---
title: Cambiar los servidores DNS para configurar Office 365 con Amazon Web Services (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Descubra cómo puede configurar Office 365 para administrar los registros DNS en Amazon Web Services (AWS). '
ms.openlocfilehash: 08deba83738ba0e530e719cd6fd57bee423df5e0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246765"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a><span data-ttu-id="43f2d-103">Cambiar los servidores DNS para configurar Office 365 con Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="43f2d-103">Change nameservers to set up Office 365 with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="43f2d-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="43f2d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="43f2d-p101">Siga estas instrucciones si quiere que Office 365 administre los registros DNS de Office 365 automáticamente. (Si lo prefiere, puede [administrar todos los registros DNS de Office 365 en AWS](create-dns-records-at-aws.md)).</span><span class="sxs-lookup"><span data-stu-id="43f2d-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="43f2d-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="43f2d-107">Add a TXT record for verification</span></span>

<span data-ttu-id="43f2d-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="43f2d-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43f2d-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="43f2d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="43f2d-p104">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="43f2d-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="43f2d-114">En la página **recursos** , seleccione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="43f2d-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="43f2d-115">En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="43f2d-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="43f2d-116">Seleccione **crear conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="43f2d-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="43f2d-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="43f2d-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="43f2d-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="43f2d-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="43f2d-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="43f2d-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43f2d-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="43f2d-121">**Name**</span></span> <br/> |<span data-ttu-id="43f2d-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="43f2d-122">**Type**</span></span> <br/> |<span data-ttu-id="43f2d-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="43f2d-123">**Alias**</span></span> <br/> |<span data-ttu-id="43f2d-124">**TTL (segundos)**</span><span class="sxs-lookup"><span data-stu-id="43f2d-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="43f2d-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="43f2d-125">**Value**</span></span> <br/> |<span data-ttu-id="43f2d-126">**Directiva de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="43f2d-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="43f2d-127">(Deje este campo en blanco)</span><span class="sxs-lookup"><span data-stu-id="43f2d-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="43f2d-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="43f2d-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="43f2d-129">No</span><span class="sxs-lookup"><span data-stu-id="43f2d-129">No</span></span>  <br/> |<span data-ttu-id="43f2d-130">300</span><span class="sxs-lookup"><span data-stu-id="43f2d-130">300</span></span>  <br/> |<span data-ttu-id="43f2d-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="43f2d-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="43f2d-132">**Nota:** Este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="43f2d-132">**Note:** This is an example.</span></span> <span data-ttu-id="43f2d-133">Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="43f2d-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="43f2d-134">¿Cómo puedo encontrarlo?</span><span class="sxs-lookup"><span data-stu-id="43f2d-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="43f2d-135">Simple</span><span class="sxs-lookup"><span data-stu-id="43f2d-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="43f2d-136">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="43f2d-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="43f2d-137">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="43f2d-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="43f2d-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="43f2d-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="43f2d-139">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="43f2d-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="43f2d-140">En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="43f2d-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="43f2d-141">En la página **dominios** , seleccione el dominio que desea comprobar.</span><span class="sxs-lookup"><span data-stu-id="43f2d-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="43f2d-142">En la página **configuración** , seleccione **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="43f2d-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="43f2d-143">En la página **comprobar dominio** , seleccione **comprobar**.</span><span class="sxs-lookup"><span data-stu-id="43f2d-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="43f2d-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="43f2d-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="43f2d-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="43f2d-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="43f2d-146">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="43f2d-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="43f2d-147">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="43f2d-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="43f2d-p108">Para completar la configuración del dominio con Office 365, debe cambiar los registros NS del dominio en su registrador de dominios para que apunten a los servidores DNS primario y secundario de Office 365. Esto configura Office 365 para actualizar los registros DNS del dominio. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="43f2d-p108">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="43f2d-p109">Si cambia los registros NS del dominio para que apunten a los servidores DNS de Office 365, esto afectará a todos los servicios que estén asociados actualmente con su dominio. Por ejemplo, todos los correos que se envíen a su dominio (como, por ejemplo, rob@ *su_dominio*  .com) comenzarán a llegar a Office 365 después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="43f2d-p109">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="43f2d-153">El siguiente procedimiento le mostrará cómo eliminar cualquier otro de los servidores de nombres no deseados de la lista, y también cómo agregar los servidores de nombres correctos si aún no aparecen.</span><span class="sxs-lookup"><span data-stu-id="43f2d-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="43f2d-154">> cuando haya completado los pasos de esta sección, los únicos servidores DNS que se deben enumerar son los cuatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="43f2d-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="43f2d-155">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="43f2d-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="43f2d-156">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="43f2d-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="43f2d-157">En la página **recursos** , seleccione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="43f2d-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="43f2d-158">En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="43f2d-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="43f2d-159">Seleccione el conjunto de registros **Servidor DNS**.</span><span class="sxs-lookup"><span data-stu-id="43f2d-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="43f2d-161">En el conjunto de registros **NS: servidor de nombres de dominio** del cuadro **Valor**, elimine todos los servidores de nombres al seleccionarlos todos y después presionar la tecla **Supr** en el teclado.</span><span class="sxs-lookup"><span data-stu-id="43f2d-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="43f2d-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="43f2d-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="43f2d-163">(Es decir, elimine solo los servidores DNS actuales que *no* tengan el nombre **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="43f2d-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="43f2d-165">En el área **TTL (segundos):** , seleccione **1H** (1 hora).</span><span class="sxs-lookup"><span data-stu-id="43f2d-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Seleccionar 1H para una hora](../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="43f2d-167">Aún en el conjunto de registros **NS: servidor de nombres**, en el cuadro **Valor**, escriba o copie y pegue el valor **Primera línea** de la tabla siguiente y después presione la tecla **Entrar** en el teclado y escriba o copie y pegue el siguiente valor **línea**.</span><span class="sxs-lookup"><span data-stu-id="43f2d-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="43f2d-168">Cada valor de servidor DNS  *debe*  estar en su propia línea dentro del cuadro **Valor**, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="43f2d-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="43f2d-169">**Primera línea**</span><span class="sxs-lookup"><span data-stu-id="43f2d-169">**First line**</span></span> <br/> |<span data-ttu-id="43f2d-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="43f2d-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="43f2d-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="43f2d-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="43f2d-172">**Segunda línea**</span><span class="sxs-lookup"><span data-stu-id="43f2d-172">**Second line**</span></span> <br/> |<span data-ttu-id="43f2d-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="43f2d-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="43f2d-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="43f2d-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="43f2d-175">**Tercera línea**</span><span class="sxs-lookup"><span data-stu-id="43f2d-175">**Third line**</span></span> <br/> |<span data-ttu-id="43f2d-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="43f2d-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="43f2d-177">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="43f2d-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="43f2d-178">**Cuarta línea**</span><span class="sxs-lookup"><span data-stu-id="43f2d-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="43f2d-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="43f2d-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="43f2d-180">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="43f2d-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Escriba o pegue el valor de la primera línea en el cuadro valor](../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="43f2d-182">Seleccione **Guardar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="43f2d-182">Select **Save Record Set**.</span></span>
    
    ![Seleccione Guardar conjunto de registros.](../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="43f2d-p113">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="43f2d-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
