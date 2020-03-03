---
title: Crear registros DNS en Network Solutions para Office 365
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Network Solutions for Office 365.
ms.openlocfilehash: f94ad49f443e609aa28d634d05604601c7d5e576
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42348541"
---
# <a name="create-dns-records-at-network-solutions-for-office-365"></a><span data-ttu-id="e6535-103">Crear registros DNS en Network Solutions para Office 365</span><span class="sxs-lookup"><span data-stu-id="e6535-103">Create DNS records at Network Solutions for Office 365</span></span>

 <span data-ttu-id="e6535-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="e6535-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e6535-105">Si Network Solutions es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="e6535-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e6535-106">Estos son los registros principales que agregar.</span><span class="sxs-lookup"><span data-stu-id="e6535-106">These are the main records to add.</span></span> <span data-ttu-id="e6535-107">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e6535-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="e6535-108">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="e6535-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="e6535-109">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="e6535-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="e6535-110">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="e6535-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="e6535-111">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="e6535-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="e6535-112">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="e6535-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="e6535-113">Después de agregar estos registros a Network Solutions, el dominio estará configurado para funcionar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6535-113">After you add these records at Network Solutions, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="e6535-114">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="e6535-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e6535-p102">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e6535-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e6535-118">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="e6535-118">Add a TXT record for verification</span></span>
<span data-ttu-id="e6535-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e6535-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e6535-p103">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="e6535-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6535-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="e6535-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="e6535-124">Siga los pasos siguientes o [vea el vídeo (empieza en 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e6535-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="e6535-125">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="e6535-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="e6535-126">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="e6535-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e6535-127">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="e6535-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="e6535-129">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="e6535-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="e6535-131">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="e6535-131">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="e6535-133">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="e6535-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="e6535-134">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e6535-134">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="e6535-136">Desplácese hacia abajo hasta la sección **texto (registros txt)** y, a continuación, seleccione **Editar registros txt**.</span><span class="sxs-lookup"><span data-stu-id="e6535-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Seleccionar Editar registros TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="e6535-138">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6535-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="e6535-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="e6535-139">**Host**</span></span>|<span data-ttu-id="e6535-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e6535-140">**TTL**</span></span>|<span data-ttu-id="e6535-141">**Texto**</span><span class="sxs-lookup"><span data-stu-id="e6535-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="e6535-142">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="e6535-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="e6535-143">3600</span><span class="sxs-lookup"><span data-stu-id="e6535-143">3600</span></span>  <br/> |<span data-ttu-id="e6535-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e6535-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e6535-145">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e6535-145">**Note:** This is an example.</span></span> <span data-ttu-id="e6535-146">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6535-146">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="e6535-147">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="e6535-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Escribir o pegar valores en los cuadros para el nuevo registro](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="e6535-149">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="e6535-149">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="e6535-151">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e6535-151">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="e6535-153">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="e6535-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e6535-154">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="e6535-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="e6535-155">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="e6535-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="e6535-156">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="e6535-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e6535-157">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="e6535-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e6535-158">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="e6535-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e6535-159">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="e6535-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e6535-p107">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e6535-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="e6535-163">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="e6535-163">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="e6535-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e6535-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="e6535-165">Siga los pasos siguientes o [vea el vídeo (empieza en 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e6535-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="e6535-166">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="e6535-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="e6535-167">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="e6535-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e6535-168">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="e6535-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="e6535-170">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="e6535-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="e6535-172">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="e6535-172">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="e6535-174">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="e6535-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="e6535-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e6535-175">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="e6535-177">Desplácese hacia abajo hasta la sección **servidores de correo (registros MX)** y, a continuación, seleccione **Editar registros MX**.</span><span class="sxs-lookup"><span data-stu-id="e6535-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Seleccionar Editar registros MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="e6535-179">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6535-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="e6535-180">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="e6535-180">**Priority**</span></span>|<span data-ttu-id="e6535-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e6535-181">**TTL**</span></span>|<span data-ttu-id="e6535-182">**Servidor de correo**</span><span class="sxs-lookup"><span data-stu-id="e6535-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="e6535-183">10 </span><span class="sxs-lookup"><span data-stu-id="e6535-183">10</span></span>  <br/> <span data-ttu-id="e6535-184">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6535-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="e6535-185">3600</span><span class="sxs-lookup"><span data-stu-id="e6535-185">3600</span></span>  <br/> | <span data-ttu-id="e6535-186">*\<clave-de-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e6535-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e6535-187">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e6535-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="e6535-188">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6535-188">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span> [<span data-ttu-id="e6535-189">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="e6535-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Escribir o pegar valores en los cuadros para el nuevo registro](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="e6535-191">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="e6535-191">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="e6535-193">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e6535-193">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="e6535-195">Si hay otros registros MX, elimínelos todos (para hacerlo, seleccione **Eliminar** junto a cada registro).</span><span class="sxs-lookup"><span data-stu-id="e6535-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="e6535-197">Cuando estén todos seleccionados, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="e6535-197">When they are all selected, select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="e6535-199">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e6535-199">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="e6535-201">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="e6535-201">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="e6535-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e6535-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="e6535-203">Siga los pasos siguientes o [vea el vídeo (empieza en 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e6535-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="e6535-204">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="e6535-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="e6535-205">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="e6535-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e6535-206">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="e6535-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="e6535-208">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="e6535-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="e6535-210">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="e6535-210">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="e6535-212">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="e6535-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="e6535-213">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e6535-213">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="e6535-215">Desplácese hacia abajo hasta la sección **alias de host (registros CNAME)** y, a continuación, seleccione **Editar registros CNAME**.</span><span class="sxs-lookup"><span data-stu-id="e6535-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Seleccione Editar registros CNAME en alias de host](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="e6535-217">En los cuadros de los cuatro nuevos registros, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6535-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="e6535-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e6535-218">**Alias**</span></span>|<span data-ttu-id="e6535-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e6535-219">**TTL**</span></span>|<span data-ttu-id="e6535-220">**Referencia a nombre de host**</span><span class="sxs-lookup"><span data-stu-id="e6535-220">**Refers to Host Name**</span></span>|<span data-ttu-id="e6535-221">**Otro host          (seleccione el botón de opción **Otro host**)**</span><span class="sxs-lookup"><span data-stu-id="e6535-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e6535-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e6535-222">autodiscover</span></span>  <br/> |<span data-ttu-id="e6535-223">3600</span><span class="sxs-lookup"><span data-stu-id="e6535-223">3600</span></span>  <br/> |<span data-ttu-id="e6535-224">(Sin configuración)</span><span class="sxs-lookup"><span data-stu-id="e6535-224">(No setting)</span></span>  <br/> |<span data-ttu-id="e6535-225">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e6535-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="e6535-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e6535-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e6535-227">sip</span><span class="sxs-lookup"><span data-stu-id="e6535-227">sip</span></span>  <br/> |<span data-ttu-id="e6535-228">3600</span><span class="sxs-lookup"><span data-stu-id="e6535-228">3600</span></span>  <br/> |<span data-ttu-id="e6535-229">(Sin configuración)</span><span class="sxs-lookup"><span data-stu-id="e6535-229">(No setting)</span></span>  <br/> |<span data-ttu-id="e6535-230">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e6535-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e6535-231">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="e6535-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e6535-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e6535-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e6535-233">3600</span><span class="sxs-lookup"><span data-stu-id="e6535-233">3600</span></span>  <br/> |<span data-ttu-id="e6535-234">(Sin configuración)</span><span class="sxs-lookup"><span data-stu-id="e6535-234">(No setting)</span></span>  <br/> |<span data-ttu-id="e6535-235">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e6535-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e6535-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e6535-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e6535-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e6535-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e6535-238">3600</span><span class="sxs-lookup"><span data-stu-id="e6535-238">3600</span></span>  <br/> |<span data-ttu-id="e6535-239">(Sin configuración)</span><span class="sxs-lookup"><span data-stu-id="e6535-239">(No setting)</span></span>  <br/> |<span data-ttu-id="e6535-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e6535-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="e6535-241">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="e6535-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e6535-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e6535-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e6535-243">3600</span><span class="sxs-lookup"><span data-stu-id="e6535-243">3600</span></span>  <br/> |<span data-ttu-id="e6535-244">(Sin configuración)</span><span class="sxs-lookup"><span data-stu-id="e6535-244">(No setting)</span></span>  <br/> |<span data-ttu-id="e6535-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e6535-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="e6535-246">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e6535-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Escriba o pegue los valores de los nuevos registros](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="e6535-248">Una vez que haya agregado todos los registros CNAME que necesita, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="e6535-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="e6535-250">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e6535-250">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e6535-252">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="e6535-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e6535-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e6535-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6535-254">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="e6535-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e6535-255">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="e6535-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e6535-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6535-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="e6535-257">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="e6535-257">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="e6535-258">Siga los pasos siguientes o [vea el vídeo (empieza en 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e6535-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="e6535-259">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="e6535-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="e6535-260">Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="e6535-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e6535-261">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="e6535-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="e6535-263">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="e6535-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="e6535-265">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="e6535-265">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="e6535-267">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="e6535-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="e6535-268">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e6535-268">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="e6535-270">Desplácese hacia abajo hasta la sección **texto (registros txt)** y, a continuación, seleccione **Editar registros txt**.</span><span class="sxs-lookup"><span data-stu-id="e6535-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Seleccione Editar registros TXT en texto](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="e6535-272">En el cuadro para el nuevo registro, escriba o copie y pegue los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="e6535-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="e6535-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="e6535-273">**Host**</span></span>|<span data-ttu-id="e6535-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e6535-274">**TTL**</span></span>|<span data-ttu-id="e6535-275">**Texto**</span><span class="sxs-lookup"><span data-stu-id="e6535-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="e6535-276">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="e6535-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="e6535-277">3600</span><span class="sxs-lookup"><span data-stu-id="e6535-277">3600</span></span>  <br/> |<span data-ttu-id="e6535-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e6535-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e6535-279">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="e6535-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Escribir o pegar valores para el nuevo registro](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="e6535-281">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="e6535-281">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="e6535-283">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e6535-283">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="e6535-285">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="e6535-285">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="e6535-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e6535-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="e6535-287">Siga los pasos siguientes o [vea el vídeo (empieza en 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e6535-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="e6535-p113">Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="e6535-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e6535-290">Antes de seleccionar el botón de **Inicio de sesión** , elija **Administrar mis nombres de dominio** en la lista desplegable **iniciar sesión en:** .</span><span class="sxs-lookup"><span data-stu-id="e6535-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="e6535-292">Seleccione la casilla situada al lado del nombre del dominio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="e6535-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="e6535-294">Seleccione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="e6535-294">Select **Edit DNS**.</span></span>
    
    ![Seleccione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="e6535-296">Seleccione **administrar registros DNS avanzados**.</span><span class="sxs-lookup"><span data-stu-id="e6535-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="e6535-297">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e6535-297">(You may have to scroll down.)</span></span>
    
    ![Seleccione administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="e6535-299">Desplácese hacia abajo hasta la sección **servicio (registros SRV)** y, a continuación, seleccione **Editar registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="e6535-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Seleccione Editar registros SRV en servicio](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="e6535-301">En los cuadros de los dos nuevos registros, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e6535-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="e6535-302">(Elija los valores **Servicio** y **Protocolo** de las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="e6535-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e6535-303">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="e6535-303">**Service**</span></span>|<span data-ttu-id="e6535-304">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="e6535-304">**Protocol**</span></span>|<span data-ttu-id="e6535-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e6535-305">**TTL**</span></span>|<span data-ttu-id="e6535-306">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="e6535-306">**Priority**</span></span>|<span data-ttu-id="e6535-307">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="e6535-307">**Weight**</span></span>|<span data-ttu-id="e6535-308">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="e6535-308">**Port**</span></span>|<span data-ttu-id="e6535-309">**Destino**</span><span class="sxs-lookup"><span data-stu-id="e6535-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e6535-310">_sip</span><span class="sxs-lookup"><span data-stu-id="e6535-310">_sip</span></span>  <br/> |<span data-ttu-id="e6535-311">_tls</span><span class="sxs-lookup"><span data-stu-id="e6535-311">_tls</span></span>  <br/> |<span data-ttu-id="e6535-312">3600</span><span class="sxs-lookup"><span data-stu-id="e6535-312">3600</span></span>  <br/> |<span data-ttu-id="e6535-313">100</span><span class="sxs-lookup"><span data-stu-id="e6535-313">100</span></span>  <br/> |<span data-ttu-id="e6535-314">1</span><span class="sxs-lookup"><span data-stu-id="e6535-314">1</span></span>  <br/> |<span data-ttu-id="e6535-315">443</span><span class="sxs-lookup"><span data-stu-id="e6535-315">443</span></span>  <br/> |<span data-ttu-id="e6535-316">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e6535-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e6535-317">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="e6535-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e6535-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e6535-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="e6535-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="e6535-319">_tcp</span></span>  <br/> |<span data-ttu-id="e6535-320">3600</span><span class="sxs-lookup"><span data-stu-id="e6535-320">3600</span></span>  <br/> |<span data-ttu-id="e6535-321">100</span><span class="sxs-lookup"><span data-stu-id="e6535-321">100</span></span>  <br/> |<span data-ttu-id="e6535-322">1</span><span class="sxs-lookup"><span data-stu-id="e6535-322">1</span></span>  <br/> |<span data-ttu-id="e6535-323">5061</span><span class="sxs-lookup"><span data-stu-id="e6535-323">5061</span></span>  <br/> |<span data-ttu-id="e6535-324">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e6535-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="e6535-325">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e6535-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Escriba o pegue los valores de los nuevos registros](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="e6535-327">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="e6535-327">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="e6535-329">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e6535-329">Select **Save Changes**.</span></span>
    
    ![Seleccione Guardar cambios](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="e6535-p114">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e6535-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
