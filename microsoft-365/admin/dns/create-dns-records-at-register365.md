---
title: Crear registros DNS en Register365 para Office 365
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Register365 para Office 365.
ms.openlocfilehash: 66c5c29d533b6897280ff99c449988c160022cf8
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211091"
---
# <a name="create-dns-records-at-register365-for-office-365"></a><span data-ttu-id="6350a-103">Crear registros DNS en Register365 para Office 365</span><span class="sxs-lookup"><span data-stu-id="6350a-103">Create DNS records at Register365 for Office 365</span></span>

 <span data-ttu-id="6350a-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="6350a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6350a-105">Si Register365 es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="6350a-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="6350a-106">Estos son los registros principales que es necesario agregar.</span><span class="sxs-lookup"><span data-stu-id="6350a-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="6350a-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="6350a-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="6350a-108">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="6350a-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="6350a-109">Agregar los seis registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="6350a-109">Add the six CNAME records that are required for Office 365</span></span>](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="6350a-110">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="6350a-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="6350a-111">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="6350a-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="6350a-112">Después de agregar estos registros a Office 365, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6350a-112">After you add these records at Office 365, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="6350a-113">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="6350a-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="6350a-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6350a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6350a-117">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="6350a-117">Add a TXT record for verification</span></span>
<span data-ttu-id="6350a-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6350a-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6350a-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="6350a-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6350a-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="6350a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6350a-p104">Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="6350a-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="6350a-126">En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6350a-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="6350a-127">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-127">(You may have to scroll down.)</span></span>
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="6350a-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6350a-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6350a-130">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6350a-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="6350a-131">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="6350a-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="6350a-132">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="6350a-133">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="6350a-133">**Host name**</span></span>|<span data-ttu-id="6350a-134">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6350a-134">**Type**</span></span>|<span data-ttu-id="6350a-135">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="6350a-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="6350a-136">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6350a-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6350a-137">TXT</span><span class="sxs-lookup"><span data-stu-id="6350a-137">TXT</span></span>  <br/> |<span data-ttu-id="6350a-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6350a-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6350a-139">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6350a-139">**Note:** This is an example.</span></span> <span data-ttu-id="6350a-140">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6350a-140">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="6350a-141">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="6350a-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="6350a-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6350a-143">Select **Save**.</span></span>
    
    <span data-ttu-id="6350a-144">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-144">(You may have to scroll down.)</span></span>
    
    ![Seleccione Guardar](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="6350a-146">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="6350a-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6350a-147">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="6350a-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="6350a-148">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="6350a-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6350a-149">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="6350a-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6350a-150">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="6350a-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6350a-151">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="6350a-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6350a-152">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="6350a-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6350a-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6350a-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="6350a-156">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="6350a-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="6350a-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6350a-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="6350a-p107">Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="6350a-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="6350a-161">En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6350a-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="6350a-162">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-162">(You may have to scroll down.)</span></span>
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="6350a-164">En la página **Add/Modify DNS Zone** (Agregar o modificar zona DNS), en la sección **Mail exchange records** (Registros Mail eXchange), en los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6350a-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6350a-165">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="6350a-166">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="6350a-166">**Host name**</span></span>|<span data-ttu-id="6350a-167">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="6350a-167">**Priority**</span></span>|<span data-ttu-id="6350a-168">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="6350a-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="6350a-169">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="6350a-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6350a-170">1</span><span class="sxs-lookup"><span data-stu-id="6350a-170">1</span></span>  <br/> <span data-ttu-id="6350a-171">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="6350a-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="6350a-172">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="6350a-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6350a-173">**Nota:** Obtenga la \* \<clave\> de dominio\* de su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6350a-173">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="6350a-174">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="6350a-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="6350a-176">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6350a-176">Select **Save**.</span></span>
    
    <span data-ttu-id="6350a-177">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-177">(You may have to scroll down.)</span></span>
    
    ![Seleccione Guardar](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="6350a-179">Si hay otros registros MX en la sección **Mail exchange records** (Registros Mail eXchange), elimínelos. Para hacerlo, selecciónelos y, después, pulse la tecla **Suprimir** en el teclado.</span><span class="sxs-lookup"><span data-stu-id="6350a-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="6350a-181">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6350a-181">Select **Save**.</span></span>
    
    <span data-ttu-id="6350a-182">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-182">(You may have to scroll down.)</span></span>
    
    ![Seleccione Guardar](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="6350a-184">Agregar los seis registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="6350a-184">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="6350a-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6350a-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="6350a-p109">Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="6350a-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="6350a-189">En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6350a-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="6350a-190">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-190">(You may have to scroll down.)</span></span>
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="6350a-192">En la página **Add/Modify DNS Zone** (Agregar o modificar zona DNS), en la sección **A, CNAME, AAAA, TXT and NS records** (Registros A, CNAME, AAAA, TXT y NS), en los cuadros para los registros nuevos, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6350a-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6350a-193">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6350a-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="6350a-194">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="6350a-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="6350a-195">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="6350a-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="6350a-196">\*\*\*\*Nombre de host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6350a-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="6350a-197">\*\*\*\*Tipo\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6350a-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="6350a-198">\*\*\*\*Resultado\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6350a-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="6350a-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6350a-199">autodiscover</span></span>  <br/> |<span data-ttu-id="6350a-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="6350a-200">CNAME</span></span>  <br/> |<span data-ttu-id="6350a-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6350a-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="6350a-202">sip</span><span class="sxs-lookup"><span data-stu-id="6350a-202">sip</span></span>  <br/> |<span data-ttu-id="6350a-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="6350a-203">CNAME</span></span>  <br/> |<span data-ttu-id="6350a-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6350a-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6350a-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6350a-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6350a-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="6350a-206">CNAME</span></span>  <br/> |<span data-ttu-id="6350a-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6350a-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6350a-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6350a-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6350a-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="6350a-209">CNAME</span></span>  <br/> |<span data-ttu-id="6350a-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6350a-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="6350a-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6350a-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6350a-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="6350a-212">CNAME</span></span>  <br/> |<span data-ttu-id="6350a-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6350a-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="6350a-215">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6350a-215">Select **Save**.</span></span>
    
    ![Seleccione Guardar](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6350a-217">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="6350a-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6350a-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6350a-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6350a-219">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="6350a-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6350a-220">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="6350a-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6350a-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="6350a-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="6350a-222">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="6350a-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="6350a-p111">Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="6350a-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="6350a-226">En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6350a-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="6350a-227">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-227">(You may have to scroll down.)</span></span>
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="6350a-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6350a-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6350a-230">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6350a-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="6350a-231">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="6350a-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="6350a-232">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="6350a-233">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="6350a-233">**Host name**</span></span>|<span data-ttu-id="6350a-234">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6350a-234">**Type**</span></span>|<span data-ttu-id="6350a-235">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="6350a-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="6350a-236">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6350a-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6350a-237">TXT</span><span class="sxs-lookup"><span data-stu-id="6350a-237">TXT</span></span>  <br/> |<span data-ttu-id="6350a-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6350a-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="6350a-239">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="6350a-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="6350a-241">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6350a-241">Select **Save**.</span></span>
    
    <span data-ttu-id="6350a-242">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-242">(You may have to scroll down.)</span></span>
    
    ![Seleccione Guardar](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="6350a-244">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="6350a-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="6350a-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6350a-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="6350a-p112">Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="6350a-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="6350a-249">En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6350a-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="6350a-250">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-250">(You may have to scroll down.)</span></span>
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="6350a-252">En la página **Add/Modify DNS Zone** (Agregar o modificar zona DNS), en la sección **Service records** (Registros de servicio), en los cuadros de los registros nuevos, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6350a-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6350a-253">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="6350a-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="6350a-254">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6350a-254">**Name**</span></span>|<span data-ttu-id="6350a-255">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="6350a-255">**Priority**</span></span>|<span data-ttu-id="6350a-256">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="6350a-256">**Weight**</span></span>|<span data-ttu-id="6350a-257">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="6350a-257">**Port**</span></span>|<span data-ttu-id="6350a-258">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="6350a-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6350a-259">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="6350a-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="6350a-260">100</span><span class="sxs-lookup"><span data-stu-id="6350a-260">100</span></span>  <br/> |<span data-ttu-id="6350a-261">1</span><span class="sxs-lookup"><span data-stu-id="6350a-261">1</span></span>  <br/> |<span data-ttu-id="6350a-262">443</span><span class="sxs-lookup"><span data-stu-id="6350a-262">443</span></span>  <br/> |<span data-ttu-id="6350a-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6350a-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6350a-264">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="6350a-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="6350a-265">100</span><span class="sxs-lookup"><span data-stu-id="6350a-265">100</span></span>  <br/> |<span data-ttu-id="6350a-266">1</span><span class="sxs-lookup"><span data-stu-id="6350a-266">1</span></span>  <br/> |<span data-ttu-id="6350a-267">5061</span><span class="sxs-lookup"><span data-stu-id="6350a-267">5061</span></span>  <br/> |<span data-ttu-id="6350a-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6350a-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Introducción de valores en la sección de registros de servicio](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="6350a-270">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6350a-270">Select **Save**.</span></span>
    
    <span data-ttu-id="6350a-271">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6350a-271">(You may have to scroll down.)</span></span>
    
    ![Seleccione Guardar](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="6350a-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6350a-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
