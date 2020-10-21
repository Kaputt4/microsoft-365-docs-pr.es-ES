---
title: Crear registros DNS en Register365 para Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Register365 para Microsoft.
ms.openlocfilehash: a4c66a4c16960332150a51779207defb00df3044
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645772"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="16b5e-103">Crear registros DNS en Register365 para Microsoft</span><span class="sxs-lookup"><span data-stu-id="16b5e-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="16b5e-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="16b5e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="16b5e-105">Si Register365 es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="16b5e-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="16b5e-106">Estos son los registros principales que es necesario agregar.</span><span class="sxs-lookup"><span data-stu-id="16b5e-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="16b5e-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="16b5e-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="16b5e-108">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="16b5e-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="16b5e-109">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="16b5e-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="16b5e-110">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="16b5e-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="16b5e-111">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="16b5e-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="16b5e-112">Después de agregar estos registros a Microsoft, su dominio estará configurado para trabajar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16b5e-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="16b5e-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="16b5e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="16b5e-116">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="16b5e-116">Add a TXT record for verification</span></span>
<span data-ttu-id="16b5e-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="16b5e-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="16b5e-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="16b5e-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16b5e-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="16b5e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="16b5e-p104">Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="16b5e-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="16b5e-125">En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="16b5e-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="16b5e-126">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-126">(You may have to scroll down.)</span></span>
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="16b5e-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="16b5e-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="16b5e-129">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="16b5e-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="16b5e-130">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="16b5e-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="16b5e-131">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="16b5e-132">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="16b5e-132">**Host name**</span></span>|<span data-ttu-id="16b5e-133">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="16b5e-133">**Type**</span></span>|<span data-ttu-id="16b5e-134">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="16b5e-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="16b5e-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="16b5e-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="16b5e-136">TXT</span><span class="sxs-lookup"><span data-stu-id="16b5e-136">TXT</span></span>  <br/> |<span data-ttu-id="16b5e-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="16b5e-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="16b5e-138">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="16b5e-138">**Note:** This is an example.</span></span> <span data-ttu-id="16b5e-139">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="16b5e-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="16b5e-140">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="16b5e-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="16b5e-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16b5e-142">Select **Save**.</span></span>
    
    <span data-ttu-id="16b5e-143">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-143">(You may have to scroll down.)</span></span>
    
    ![Seleccione Guardar.](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="16b5e-145">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="16b5e-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="16b5e-146">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="16b5e-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="16b5e-147">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="16b5e-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="16b5e-148">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="16b5e-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="16b5e-149">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="16b5e-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="16b5e-150">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="16b5e-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="16b5e-151">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="16b5e-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="16b5e-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="16b5e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="16b5e-155">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="16b5e-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="16b5e-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="16b5e-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="16b5e-p107">Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="16b5e-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="16b5e-160">En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="16b5e-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="16b5e-161">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-161">(You may have to scroll down.)</span></span>
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="16b5e-163">En la página **Add/Modify DNS Zone** (Agregar o modificar zona DNS), en la sección **Mail exchange records** (Registros Mail eXchange), en los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="16b5e-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="16b5e-164">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="16b5e-165">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="16b5e-165">**Host name**</span></span>|<span data-ttu-id="16b5e-166">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="16b5e-166">**Priority**</span></span>|<span data-ttu-id="16b5e-167">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="16b5e-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="16b5e-168">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="16b5e-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="16b5e-169">1</span><span class="sxs-lookup"><span data-stu-id="16b5e-169">1</span></span>  <br/> <span data-ttu-id="16b5e-170">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="16b5e-170">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="16b5e-171">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="16b5e-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="16b5e-172">**Nota:** Obtén tu  *\<domain-key\>*  cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16b5e-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="16b5e-173">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="16b5e-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="16b5e-175">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16b5e-175">Select **Save**.</span></span>
    
    <span data-ttu-id="16b5e-176">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-176">(You may have to scroll down.)</span></span>
    
    ![Seleccione Guardar.](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="16b5e-178">Si hay otros registros MX en la sección **Mail exchange records** (Registros Mail eXchange), elimínelos. Para hacerlo, selecciónelos y, después, pulse la tecla **Suprimir** en el teclado.</span><span class="sxs-lookup"><span data-stu-id="16b5e-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="16b5e-180">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16b5e-180">Select **Save**.</span></span>
    
    <span data-ttu-id="16b5e-181">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-181">(You may have to scroll down.)</span></span>
    
    ![Seleccione Guardar.](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="16b5e-183">Agregar los seis registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="16b5e-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="16b5e-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="16b5e-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="16b5e-p109">Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="16b5e-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="16b5e-188">En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="16b5e-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="16b5e-189">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-189">(You may have to scroll down.)</span></span>
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="16b5e-191">En la página **Add/Modify DNS Zone** (Agregar o modificar zona DNS), en la sección **A, CNAME, AAAA, TXT and NS records** (Registros A, CNAME, AAAA, TXT y NS), en los cuadros para los registros nuevos, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="16b5e-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="16b5e-192">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="16b5e-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="16b5e-193">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="16b5e-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="16b5e-194">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="16b5e-195">\*\*\*\*Nombre de host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16b5e-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="16b5e-196">\*\*\*\*Tipo\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16b5e-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="16b5e-197">\*\*\*\*Resultado\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="16b5e-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="16b5e-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="16b5e-198">autodiscover</span></span>  <br/> |<span data-ttu-id="16b5e-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="16b5e-199">CNAME</span></span>  <br/> |<span data-ttu-id="16b5e-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="16b5e-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="16b5e-201">sip</span><span class="sxs-lookup"><span data-stu-id="16b5e-201">sip</span></span>  <br/> |<span data-ttu-id="16b5e-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="16b5e-202">CNAME</span></span>  <br/> |<span data-ttu-id="16b5e-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16b5e-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="16b5e-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="16b5e-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="16b5e-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="16b5e-205">CNAME</span></span>  <br/> |<span data-ttu-id="16b5e-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16b5e-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="16b5e-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="16b5e-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="16b5e-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="16b5e-208">CNAME</span></span>  <br/> |<span data-ttu-id="16b5e-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="16b5e-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="16b5e-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="16b5e-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="16b5e-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="16b5e-211">CNAME</span></span>  <br/> |<span data-ttu-id="16b5e-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="16b5e-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="16b5e-214">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16b5e-214">Select **Save**.</span></span>
    
    ![Seleccione Guardar.](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="16b5e-216">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="16b5e-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="16b5e-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="16b5e-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="16b5e-218">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="16b5e-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="16b5e-219">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="16b5e-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="16b5e-220">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16b5e-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="16b5e-221">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="16b5e-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="16b5e-p111">Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="16b5e-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="16b5e-225">En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="16b5e-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="16b5e-226">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-226">(You may have to scroll down.)</span></span>
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="16b5e-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="16b5e-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="16b5e-229">(Elija el valor **Tipo** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="16b5e-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="16b5e-230">(Si necesita agregar una fila, seleccione **agregar registros a/CNAME (+)**).</span><span class="sxs-lookup"><span data-stu-id="16b5e-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="16b5e-231">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="16b5e-232">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="16b5e-232">**Host name**</span></span>|<span data-ttu-id="16b5e-233">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="16b5e-233">**Type**</span></span>|<span data-ttu-id="16b5e-234">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="16b5e-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="16b5e-235">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="16b5e-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="16b5e-236">TXT</span><span class="sxs-lookup"><span data-stu-id="16b5e-236">TXT</span></span>  <br/> |<span data-ttu-id="16b5e-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="16b5e-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="16b5e-238">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="16b5e-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Especificar valores en la página Agregar o modificar zona DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="16b5e-240">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16b5e-240">Select **Save**.</span></span>
    
    <span data-ttu-id="16b5e-241">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-241">(You may have to scroll down.)</span></span>
    
    ![Seleccione Guardar.](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="16b5e-243">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="16b5e-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="16b5e-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="16b5e-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="16b5e-p112">Para empezar, vaya a su página de dominios en Register365 a través de [este vínculo](https://admin.register365.com/dns/). Se le pedirá que inicie sesión primero .</span><span class="sxs-lookup"><span data-stu-id="16b5e-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![La página de inicio de sesión del Panel de control](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="16b5e-248">En la página **Panel**, busque el nombre del dominio que vaya a actualizar y, a continuación, elija **Configuración DNS** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="16b5e-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="16b5e-249">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-249">(You may have to scroll down.)</span></span>
    
    ![Selección de la configuración DNS en la lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="16b5e-251">En la página **Add/Modify DNS Zone** (Agregar o modificar zona DNS), en la sección **Service records** (Registros de servicio), en los cuadros de los registros nuevos, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="16b5e-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="16b5e-252">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="16b5e-253">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="16b5e-253">**Name**</span></span>|<span data-ttu-id="16b5e-254">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="16b5e-254">**Priority**</span></span>|<span data-ttu-id="16b5e-255">**Grosor**</span><span class="sxs-lookup"><span data-stu-id="16b5e-255">**Weight**</span></span>|<span data-ttu-id="16b5e-256">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="16b5e-256">**Port**</span></span>|<span data-ttu-id="16b5e-257">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="16b5e-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16b5e-258">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="16b5e-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="16b5e-259">100</span><span class="sxs-lookup"><span data-stu-id="16b5e-259">100</span></span>  <br/> |<span data-ttu-id="16b5e-260">1</span><span class="sxs-lookup"><span data-stu-id="16b5e-260">1</span></span>  <br/> |<span data-ttu-id="16b5e-261">443</span><span class="sxs-lookup"><span data-stu-id="16b5e-261">443</span></span>  <br/> |<span data-ttu-id="16b5e-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16b5e-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="16b5e-263">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="16b5e-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="16b5e-264">100</span><span class="sxs-lookup"><span data-stu-id="16b5e-264">100</span></span>  <br/> |<span data-ttu-id="16b5e-265">1</span><span class="sxs-lookup"><span data-stu-id="16b5e-265">1</span></span>  <br/> |<span data-ttu-id="16b5e-266">5061</span><span class="sxs-lookup"><span data-stu-id="16b5e-266">5061</span></span>  <br/> |<span data-ttu-id="16b5e-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="16b5e-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Introducción de valores en la sección de registros de servicio](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="16b5e-269">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="16b5e-269">Select **Save**.</span></span>
    
    <span data-ttu-id="16b5e-270">(Es posible que tenga que desplazarse hacia abajo).</span><span class="sxs-lookup"><span data-stu-id="16b5e-270">(You may have to scroll down.)</span></span>
    
    ![Seleccione Guardar.](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="16b5e-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="16b5e-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
