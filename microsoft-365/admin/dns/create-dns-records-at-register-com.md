---
title: Crear registros DNS en Register.com para Office 365
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Register.com para Office 365.
ms.openlocfilehash: 0210c03a48112d9cc517ae15f879db3b40eb8c94
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42354141"
---
# <a name="create-dns-records-at-registercom-for-office-365"></a><span data-ttu-id="68d4d-103">Crear registros DNS en Register.com para Office 365</span><span class="sxs-lookup"><span data-stu-id="68d4d-103">Create DNS records at Register.com for Office 365</span></span>

 <span data-ttu-id="68d4d-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="68d4d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="68d4d-105">Si Register.com es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="68d4d-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="68d4d-106">Estos son los registros principales que agregar.</span><span class="sxs-lookup"><span data-stu-id="68d4d-106">These are the main records to add.</span></span> <span data-ttu-id="68d4d-107">Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="68d4d-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="68d4d-108">Agregar un registro TXT en Register.com para comprobar que es el propietario del dominio</span><span class="sxs-lookup"><span data-stu-id="68d4d-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="68d4d-109">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="68d4d-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="68d4d-110">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="68d4d-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="68d4d-111">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="68d4d-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="68d4d-112">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="68d4d-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="68d4d-113">Después de agregar estos registros a Register.com, el dominio estará configurado para funcionar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68d4d-113">After you add these records at Register.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="68d4d-114">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="68d4d-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="68d4d-115">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="68d4d-115">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="68d4d-116">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="68d4d-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="68d4d-117">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="68d4d-117">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="68d4d-118">Agregar un registro TXT en Register.com para comprobar que es el propietario del dominio</span><span class="sxs-lookup"><span data-stu-id="68d4d-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="68d4d-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="68d4d-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="68d4d-p103">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="68d4d-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68d4d-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="68d4d-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="68d4d-124">Siga los pasos siguientes o [vea el vídeo (empieza en 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="68d4d-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="68d4d-125">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="68d4d-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="68d4d-126">Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="68d4d-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="68d4d-127">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="68d4d-128">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="68d4d-129">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="68d4d-130">Desplácese hacia abajo hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros txt (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="68d4d-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="68d4d-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="68d4d-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="68d4d-132">**Host Name**</span></span> <br/> |<span data-ttu-id="68d4d-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="68d4d-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="68d4d-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="68d4d-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="68d4d-135">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="68d4d-135">**Note:** This is an example.</span></span> <span data-ttu-id="68d4d-136">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68d4d-136">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="68d4d-137">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="68d4d-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="68d4d-138">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="68d4d-139">En la página siguiente, seleccione **continuar** de nuevo para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="68d4d-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="68d4d-140">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="68d4d-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="68d4d-141">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="68d4d-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="68d4d-142">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="68d4d-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="68d4d-143">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="68d4d-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="68d4d-144">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="68d4d-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="68d4d-145">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="68d4d-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="68d4d-146">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="68d4d-147">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="68d4d-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="68d4d-148">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="68d4d-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="68d4d-149">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="68d4d-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="68d4d-150">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="68d4d-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="68d4d-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="68d4d-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="68d4d-152">Siga los pasos siguientes o [vea el vídeo (empieza en 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="68d4d-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="68d4d-153">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="68d4d-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="68d4d-154">Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="68d4d-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="68d4d-155">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="68d4d-156">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="68d4d-157">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="68d4d-158">Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros de intercambio de correo**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Seleccionar Editar registros de intercambio de correo](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="68d4d-160">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="68d4d-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="68d4d-161">(Elija el valor **prioridad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="68d4d-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="68d4d-162">\*\*\*\*Nombre de host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="68d4d-163">\*\*\*\*Prioridad\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="68d4d-164">\*\*\*\*Servidor de correo\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="68d4d-165">Alta</span><span class="sxs-lookup"><span data-stu-id="68d4d-165">High</span></span>  <br/> <span data-ttu-id="68d4d-166">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="68d4d-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="68d4d-167">*\< clave-de-dominio \>*  . mail.protection.outlook.com    </span><span class="sxs-lookup"><span data-stu-id="68d4d-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="68d4d-168">**Nota:** Obtenga la \<*clave-de-dominio*\> desde su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68d4d-168">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> <br> [<span data-ttu-id="68d4d-169">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="68d4d-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copie y pegue el valor de la tabla](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="68d4d-171">Si se muestran otros registros MX en la lista, seleccione todos los registros que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="68d4d-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="68d4d-173">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-173">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="68d4d-175">En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="68d4d-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccione continuar.](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="68d4d-177">Agregar los registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="68d4d-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="68d4d-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="68d4d-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="68d4d-179">Siga los pasos siguientes o [vea el vídeo (empieza en 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="68d4d-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="68d4d-180">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="68d4d-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="68d4d-181">Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="68d4d-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="68d4d-182">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="68d4d-183">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="68d4d-184">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="68d4d-185">Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros de alias de dominio**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Seleccione Editar registros de alias de dominio](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="68d4d-187">Seleccione **Agregar más alias de dominio**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-187">Select **Add more domain aliases**.</span></span>
    
    ![Seleccione Agregar alias de dominios](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="68d4d-189">Agregar los registros CNAME necesarios.</span><span class="sxs-lookup"><span data-stu-id="68d4d-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="68d4d-190">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="68d4d-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="68d4d-191">\*\*\*\*Primer campo (sin etiqueta)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="68d4d-192">\*\*\*\*Señala a\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="68d4d-193">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="68d4d-193">autodiscover</span></span>  <br/> |<span data-ttu-id="68d4d-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="68d4d-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="68d4d-195">sip</span><span class="sxs-lookup"><span data-stu-id="68d4d-195">sip</span></span>  <br/> |<span data-ttu-id="68d4d-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="68d4d-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="68d4d-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="68d4d-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="68d4d-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="68d4d-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="68d4d-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="68d4d-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="68d4d-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="68d4d-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="68d4d-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="68d4d-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="68d4d-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="68d4d-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Copiar y pegar los valores DNS de la tabla](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="68d4d-204">Una vez que haya agregado todos los registros CNAME que necesita, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="68d4d-206">En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="68d4d-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccione continuar.](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="68d4d-208">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="68d4d-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="68d4d-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="68d4d-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="68d4d-210">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="68d4d-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="68d4d-211">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="68d4d-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="68d4d-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="68d4d-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="68d4d-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="68d4d-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="68d4d-214">Siga los pasos siguientes o [vea el vídeo (empieza en 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="68d4d-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="68d4d-215">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="68d4d-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="68d4d-216">Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="68d4d-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="68d4d-217">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="68d4d-218">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="68d4d-219">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="68d4d-220">Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros txt (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Seleccionar Editar registros TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="68d4d-222">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="68d4d-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="68d4d-223">\*\*\*\*Nombre de host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="68d4d-224">\*\*\*\*Registro TXT\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="68d4d-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="68d4d-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="68d4d-226">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="68d4d-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Copiar y pegar los valores de la tabla](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="68d4d-228">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-228">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="68d4d-230">En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="68d4d-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccione continuar.](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="68d4d-232">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="68d4d-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="68d4d-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="68d4d-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="68d4d-234">Siga los pasos siguientes o [vea el vídeo (empieza en 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="68d4d-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="68d4d-p112">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/). Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="68d4d-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="68d4d-237">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="68d4d-238">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="68d4d-239">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="68d4d-240">Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Seleccionar Editar registros SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="68d4d-242">Agregue el primero de los dos registros SRV:</span><span class="sxs-lookup"><span data-stu-id="68d4d-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="68d4d-243">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="68d4d-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="68d4d-244">(Elija el valor **prioridad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="68d4d-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="68d4d-245">\*\*\*\*Servicio\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="68d4d-246">\*\*\*\*Puerto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="68d4d-247">\*\*\*\*Nombre\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="68d4d-248">\*\*\*\*Prioridad\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="68d4d-249">\*\*\*\*Grosor\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="68d4d-250">\*\*\*\*Puerto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="68d4d-251">\*\*\*\*Destino\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68d4d-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="68d4d-252">_sip</span><span class="sxs-lookup"><span data-stu-id="68d4d-252">_sip</span></span>  <br/> |<span data-ttu-id="68d4d-253">_tls</span><span class="sxs-lookup"><span data-stu-id="68d4d-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="68d4d-254">Máximo</span><span class="sxs-lookup"><span data-stu-id="68d4d-254">High</span></span>  <br/> |<span data-ttu-id="68d4d-255">1</span><span class="sxs-lookup"><span data-stu-id="68d4d-255">1</span></span>  <br/> |<span data-ttu-id="68d4d-256">443</span><span class="sxs-lookup"><span data-stu-id="68d4d-256">443</span></span>  <br/> |<span data-ttu-id="68d4d-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="68d4d-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="68d4d-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="68d4d-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="68d4d-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="68d4d-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="68d4d-260">Máximo</span><span class="sxs-lookup"><span data-stu-id="68d4d-260">High</span></span>  <br/> |<span data-ttu-id="68d4d-261">1</span><span class="sxs-lookup"><span data-stu-id="68d4d-261">1</span></span>  <br/> |<span data-ttu-id="68d4d-262">5061</span><span class="sxs-lookup"><span data-stu-id="68d4d-262">5061</span></span>  <br/> |<span data-ttu-id="68d4d-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="68d4d-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Copiar y pegar los valores de la tabla](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="68d4d-265">Seleccione **Agregar más registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-265">Select **Add more SRV records**.</span></span>
    
    ![Seleccione Agregar más registros SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="68d4d-267">Agregue el segundo registro SRV:</span><span class="sxs-lookup"><span data-stu-id="68d4d-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="68d4d-268">Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="68d4d-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="68d4d-269">Una vez que haya agregado los dos registros SRV, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="68d4d-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="68d4d-271">En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="68d4d-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccione continuar.](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="68d4d-273">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="68d4d-273">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="68d4d-274">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="68d4d-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="68d4d-275">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="68d4d-275">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
