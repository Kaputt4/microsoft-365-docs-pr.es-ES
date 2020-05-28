---
title: Cambiar los servidores DNS para configurar Microsoft con soluciones de red
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Aprenda a configurar su dominio personalizado de Microsoft con soluciones de red si desea que Microsoft administre sus registros DNS. '
ms.openlocfilehash: 4a7c1eaab132b0ab41a62ba62d87956ccfafc014
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400610"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a><span data-ttu-id="5e7d4-103">Cambiar los servidores DNS para configurar Microsoft con soluciones de red</span><span class="sxs-lookup"><span data-stu-id="5e7d4-103">Change nameservers to set up Microsoft with Network Solutions</span></span>

 <span data-ttu-id="5e7d4-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="5e7d4-105">Siga estas instrucciones si desea que Microsoft administre los registros DNS por usted.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="5e7d4-106">(Si lo prefiere, puede [administrar todos los registros DNS de Microsoft en soluciones de red](create-dns-records-at-network-solutions.md)).</span><span class="sxs-lookup"><span data-stu-id="5e7d4-106">(If you prefer, you can [manage all your Microsoft DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="5e7d4-107">Agregar un registro TXT en Network Solutions para comprobar que es el propietario del dominio</span><span class="sxs-lookup"><span data-stu-id="5e7d4-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="5e7d4-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e7d4-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="5e7d4-112">Siga los pasos siguientes o [vea el vídeo (empieza en 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5e7d4-112">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5e7d4-p104">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5e7d4-115">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="5e7d4-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="5e7d4-117">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="5e7d4-119">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-119">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="5e7d4-121">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="5e7d4-122">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5e7d4-122">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="5e7d4-124">Desplácese hacia abajo hasta la sección **texto (registros txt)** y, a continuación, seleccione **Editar registros txt**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Seleccionar Editar registros TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="5e7d4-126">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="5e7d4-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-127">**Host**</span></span>|<span data-ttu-id="5e7d4-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-128">**TTL**</span></span>|<span data-ttu-id="5e7d4-129">**Texto**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="5e7d4-130">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="5e7d4-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="5e7d4-131">3600</span><span class="sxs-lookup"><span data-stu-id="5e7d4-131">3600</span></span>  <br/> |<span data-ttu-id="5e7d4-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5e7d4-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5e7d4-133">**Nota**: este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-133">**Note**: This is an example.</span></span> <span data-ttu-id="5e7d4-134">Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="5e7d4-135">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="5e7d4-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Escribir o pegar valores en los cuadros para el nuevo registro](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="5e7d4-137">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-137">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="5e7d4-139">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-139">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="5e7d4-141">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5e7d4-142">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="5e7d4-143">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5e7d4-144">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5e7d4-145">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5e7d4-146">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5e7d4-147">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5e7d4-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5e7d4-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="5e7d4-151">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="5e7d4-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="5e7d4-152">Para completar la configuración de su dominio con Microsoft, debe cambiar los registros NS de su dominio en su registrador de dominios para que apunten a los servidores de nombres principal y secundario de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-152">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="5e7d4-153">Esto configura a Microsoft para que actualice los registros DNS del dominio por usted.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-153">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="5e7d4-154">Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-154">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5e7d4-155">Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft, se ven afectados todos los servicios que están actualmente asociados a su dominio.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-155">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="5e7d4-156">Por ejemplo, todos los mensajes de correo electrónico enviados a su dominio (como rob@ *your_domain* . com) empezarán a llegar a Microsoft después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-156">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
<span data-ttu-id="5e7d4-157">¿Está preparado para cambiar los registros NS para que Microsoft pueda configurar el dominio?</span><span class="sxs-lookup"><span data-stu-id="5e7d4-157">Ready to change your NS records so Microsoft can set up your domain?</span></span> <span data-ttu-id="5e7d4-158">Siga los pasos siguientes o [vea el vídeo (empieza en 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5e7d4-158">Follow the steps below or [watch the video (start at 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="5e7d4-159">Cuando haya completado los pasos de esta sección, los *únicos* servidores de nombres que se deben enumerar son los cuatro siguientes: **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**y **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="5e7d4-160">En el procedimiento siguiente se muestra cómo eliminar cualquier otro servidor de nombres que no desee de la lista y también cómo agregar estos cuatro servidores DNS  *correctos*  , si aún no están en la lista.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="5e7d4-161">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="5e7d4-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="5e7d4-162">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5e7d4-163">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="5e7d4-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="5e7d4-165">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="5e7d4-167">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-167">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="5e7d4-169">Seleccione **mover DNS**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="5e7d4-171">Dependiendo de si ya existen o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e7d4-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="5e7d4-172">Si aún **NO** se muestran servidores DNS en la lista, [Si aún NO se muestran servidores DNS en la lista](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="5e7d4-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="5e7d4-173">Si **YA** se muestran servidores DNS en la lista, [Si ya existen servidores de nombres enumerados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="5e7d4-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="5e7d4-174">Si aún NO se muestran servidores DNS en la lista</span><span class="sxs-lookup"><span data-stu-id="5e7d4-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="5e7d4-175">En la página **dominios** , en la sección **especificar servidores de nombres de dominio** , seleccione **Agregar más servidores de nombres**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="5e7d4-177">En la página **Nombres de dominio**, escriba (o copie y pegue) los valores de servidores DNS de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="5e7d4-178">**Servidor DNS 1**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="5e7d4-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5e7d4-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5e7d4-180">**Servidor DNS 2**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="5e7d4-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5e7d4-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5e7d4-182">**Servidor DNS 2**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="5e7d4-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5e7d4-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5e7d4-184">**Servidor DNS 2**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="5e7d4-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5e7d4-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="5e7d4-187">Seleccione **mover DNS**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="5e7d4-189">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="5e7d4-191">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-191">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="5e7d4-192">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-192">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="5e7d4-193">Si ya existen servidores de nombres enumerados</span><span class="sxs-lookup"><span data-stu-id="5e7d4-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="5e7d4-p113">Siga estos pasos  *solo*  si tiene servidores de nombres distintos de los cuatro servidores de nombres  *correctos*  . (Es decir, elimine  *solo*  los servidores de nombres actuales que  *no*  sean **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com** ).</span><span class="sxs-lookup"><span data-stu-id="5e7d4-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="5e7d4-196">Si la lista contiene otros servidores DNS, elimínelos (para hacerlo, selecciónelos y, después, presione la tecla **Suprimir** en el teclado).</span><span class="sxs-lookup"><span data-stu-id="5e7d4-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![NetworkSolutions-BP-redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="5e7d4-198">Seleccione **Agregar más servidores de nombres**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="5e7d4-200">En la página **Nombres de dominio**, escriba (o copie y pegue) los valores de servidores DNS de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="5e7d4-201">**Servidor DNS 1**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="5e7d4-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5e7d4-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5e7d4-203">**Servidor DNS 2**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="5e7d4-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5e7d4-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5e7d4-205">**Servidor de nombres 3**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="5e7d4-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5e7d4-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="5e7d4-207">**Servidor de nombres 4**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="5e7d4-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="5e7d4-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="5e7d4-210">Seleccione **mover DNS**.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="5e7d4-212">Seleccione **Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="5e7d4-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="5e7d4-214">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-214">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="5e7d4-215">El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="5e7d4-215">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
