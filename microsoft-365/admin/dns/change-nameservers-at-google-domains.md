---
title: Cambiar los servidores de nombres para configurar Office 365 con Google Domains
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Obtenga información acerca de cómo puede configurar Office 365 para administrar los registros DNS de su dominio personalizado en Google Domains.
ms.openlocfilehash: f6faaa4a7b6540086752e88da2051a73450f4455
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351971"
---
# <a name="change-nameservers-to-set-up-office-365-with-google-domains"></a><span data-ttu-id="5062c-103">Cambiar los servidores de nombres para configurar Office 365 con Google Domains</span><span class="sxs-lookup"><span data-stu-id="5062c-103">Change nameservers to set up Office 365 with Google Domains</span></span>

 <span data-ttu-id="5062c-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="5062c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5062c-p101">Siga estas instrucciones si quiere que Office 365 administre los registros de DNS de Office 365. (Si lo prefiere, puede [administrar todos los registros de DNS de Office 365 en Google Domains](create-dns-records-at-google-domains.md)).</span><span class="sxs-lookup"><span data-stu-id="5062c-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5062c-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="5062c-107">Add a TXT record for verification</span></span>

<span data-ttu-id="5062c-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="5062c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5062c-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="5062c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5062c-112">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="5062c-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="5062c-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="5062c-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="5062c-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="5062c-114">To do so:</span></span>
    
1. <span data-ttu-id="5062c-115">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="5062c-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="5062c-116">Escriba sus credenciales de inicio de sesión y vuelva a seleccionar **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="5062c-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="5062c-117">En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="5062c-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5062c-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5062c-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5062c-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5062c-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="5062c-120">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5062c-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5062c-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="5062c-121">**Name**</span></span> <br/> |<span data-ttu-id="5062c-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="5062c-122">**Type**</span></span> <br/> |<span data-ttu-id="5062c-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5062c-123">**TTL**</span></span> <br/> |<span data-ttu-id="5062c-124">**Datos**</span><span class="sxs-lookup"><span data-stu-id="5062c-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="5062c-125">TXT</span><span class="sxs-lookup"><span data-stu-id="5062c-125">TXT</span></span>  <br/> |<span data-ttu-id="5062c-126">1H</span><span class="sxs-lookup"><span data-stu-id="5062c-126">1H</span></span>  <br/> |<span data-ttu-id="5062c-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5062c-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="5062c-128">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5062c-128">**Note:** This is an example.</span></span> <span data-ttu-id="5062c-129">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5062c-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="5062c-130">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="5062c-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="5062c-131">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5062c-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="5062c-132">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="5062c-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5062c-133">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="5062c-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5062c-134">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="5062c-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5062c-135">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="5062c-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5062c-136">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="5062c-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5062c-137">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="5062c-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5062c-138">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="5062c-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5062c-139">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="5062c-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5062c-140">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="5062c-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5062c-141">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5062c-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="5062c-142">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="5062c-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="5062c-p107">Para completar la configuración del dominio con Office 365, debe cambiar los registros NS del dominio en su registrador de dominios para que apunten a los servidores DNS primario y secundario de Office 365. Esto configura Office 365 para actualizar los registros DNS del dominio. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="5062c-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5062c-146">Si cambia los registros NS del dominio para que apunten a los servidores DNS de Office 365, esto afectará a todos los servicios que estén asociados actualmente con su dominio.</span><span class="sxs-lookup"><span data-stu-id="5062c-146">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="5062c-147">Por ejemplo, todo el correo electrónico enviado a su dominio (como rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="5062c-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="5062c-148">com) empezará a llegar a Office 365 después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="5062c-148">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5062c-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="5062c-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="5062c-150">> cuando haya completado los pasos de esta sección, los únicos servidores DNS que se deben enumerar son estos cuatro:</span><span class="sxs-lookup"><span data-stu-id="5062c-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="5062c-p110">Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:</span><span class="sxs-lookup"><span data-stu-id="5062c-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="5062c-154">Seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="5062c-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="5062c-155">Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.</span><span class="sxs-lookup"><span data-stu-id="5062c-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="5062c-156">En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="5062c-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5062c-157">En la página **Dominios**, en la sección **Servidores de nombres**, seleccione **Use servidores de nombres personalizados**.</span><span class="sxs-lookup"><span data-stu-id="5062c-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="5062c-159">Dependiendo de si ya existen o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5062c-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="5062c-160">Si aún **NO** se muestran servidores DNS en la lista, [Si aún NO se muestran servidores DNS en la lista](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="5062c-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="5062c-161">Si **YA** se muestran servidores DNS en la lista, [Si ya existen servidores de nombres enumerados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="5062c-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="5062c-162">Si aún NO se muestran servidores DNS en la lista</span><span class="sxs-lookup"><span data-stu-id="5062c-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="5062c-163">Agregue el primer servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="5062c-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="5062c-164">En la sección **Servidores de nombres**, en el cuadro **SERVIDOR DE NOMBRES**, escriba o copie y pegue el primer valor de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5062c-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="5062c-165">**Primer servidor de nombres**</span><span class="sxs-lookup"><span data-stu-id="5062c-165">**First name server**</span></span> <br/> |<span data-ttu-id="5062c-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5062c-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5062c-167">**Segundo servidor de nombres**</span><span class="sxs-lookup"><span data-stu-id="5062c-167">**Second name server**</span></span> <br/> |<span data-ttu-id="5062c-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5062c-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5062c-169">**Tercer servidor de nombres**</span><span class="sxs-lookup"><span data-stu-id="5062c-169">**Third name server**</span></span> <br/> |<span data-ttu-id="5062c-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5062c-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5062c-171">**Cuarto servidor de nombres**</span><span class="sxs-lookup"><span data-stu-id="5062c-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="5062c-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5062c-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="5062c-174">Seleccione el control **+ (agregar)** para crear una fila vacía.</span><span class="sxs-lookup"><span data-stu-id="5062c-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="5062c-176">Agregue los otros tres registros del servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="5062c-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="5062c-177">En la sección **servidores de nombres personalizados** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, a continuación, seleccione el control **+ (agregar)** para agregar otra fila.</span><span class="sxs-lookup"><span data-stu-id="5062c-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="5062c-178">Repita este proceso hasta que haya creado los cuatro registros de servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="5062c-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="5062c-179">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5062c-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="5062c-p111">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="5062c-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="5062c-183">Si ya existen servidores de nombres enumerados</span><span class="sxs-lookup"><span data-stu-id="5062c-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="5062c-184">Si en la lista se muestran otros servidores DNS, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5062c-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5062c-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="5062c-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="5062c-186">(Es decir, elimine solo los servidores DNS actuales que *no* tengan el nombre **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).</span><span class="sxs-lookup"><span data-stu-id="5062c-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="5062c-188">Elimine cada uno seleccionándolo y, después, presione la tecla **Eliminar** en el teclado.</span><span class="sxs-lookup"><span data-stu-id="5062c-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="5062c-190">Aún en la sección **Servidores de nombres**, en las filas **Servidor de nombres**, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5062c-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="5062c-191">**Primer servidor de nombres**</span><span class="sxs-lookup"><span data-stu-id="5062c-191">**First name server**</span></span> <br/> |<span data-ttu-id="5062c-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5062c-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5062c-193">**Segundo servidor de nombres**</span><span class="sxs-lookup"><span data-stu-id="5062c-193">**Second name server**</span></span> <br/> |<span data-ttu-id="5062c-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5062c-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5062c-195">**Tercer servidor de nombres**</span><span class="sxs-lookup"><span data-stu-id="5062c-195">**Third name server**</span></span> <br/> |<span data-ttu-id="5062c-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5062c-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5062c-197">**Cuarto servidor de nombres**</span><span class="sxs-lookup"><span data-stu-id="5062c-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="5062c-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5062c-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="5062c-200">Seleccione el control **+ (agregar)** para crear una fila vacía.</span><span class="sxs-lookup"><span data-stu-id="5062c-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="5062c-202">Agregue los otros dos registros del servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="5062c-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="5062c-203">En la sección **servidores de nombres personalizados** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, a continuación, seleccione el control **+ (agregar)** para agregar otra fila.</span><span class="sxs-lookup"><span data-stu-id="5062c-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="5062c-204">Repita este proceso hasta que haya creado los cuatro registros de servidor de nombres.</span><span class="sxs-lookup"><span data-stu-id="5062c-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="5062c-205">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5062c-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="5062c-p113">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="5062c-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
