---
title: Crear registros DNS en Register.com para Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Register.com para Microsoft.
ms.openlocfilehash: 7a11fa248f2602eb02fe1242234d26584bd33fd2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780330"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="574c9-103">Crear registros DNS en Register.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="574c9-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="574c9-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="574c9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="574c9-105">Si Register.com es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="574c9-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="574c9-106">Estos son los registros principales que agregar.</span><span class="sxs-lookup"><span data-stu-id="574c9-106">These are the main records to add.</span></span> <span data-ttu-id="574c9-107">Siga los pasos siguientes o [vea el vídeo](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="574c9-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
- [<span data-ttu-id="574c9-108">Agregar un registro TXT en Register.com para comprobar que es el propietario del dominio</span><span class="sxs-lookup"><span data-stu-id="574c9-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="574c9-109">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="574c9-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="574c9-110">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="574c9-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="574c9-111">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="574c9-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="574c9-112">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="574c9-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="574c9-113">Después de agregar estos registros a Register.com, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="574c9-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="574c9-114">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="574c9-114">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="574c9-115">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="574c9-115">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="574c9-116">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="574c9-116">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="574c9-117">Agregar un registro TXT en Register.com para comprobar que es el propietario del dominio</span><span class="sxs-lookup"><span data-stu-id="574c9-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="574c9-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="574c9-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="574c9-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="574c9-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="574c9-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="574c9-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="574c9-121">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="574c9-121">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="574c9-122">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="574c9-122">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="574c9-123">Siga los pasos siguientes o [vea el vídeo (empieza en 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="574c9-123">Follow the steps below or [watch the video (start at 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="574c9-124">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="574c9-124">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="574c9-125">Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="574c9-125">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="574c9-126">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="574c9-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="574c9-127">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="574c9-128">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="574c9-129">Desplácese hacia abajo hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros txt (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="574c9-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="574c9-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="574c9-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="574c9-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="574c9-131">**Host Name**</span></span> <br/> |<span data-ttu-id="574c9-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="574c9-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="574c9-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="574c9-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="574c9-134">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="574c9-134">**Note:** This is an example.</span></span> <span data-ttu-id="574c9-135">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="574c9-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="574c9-136">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="574c9-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="574c9-137">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="574c9-138">En la página siguiente, seleccione **continuar** de nuevo para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="574c9-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="574c9-139">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="574c9-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="574c9-140">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="574c9-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="574c9-141">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="574c9-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="574c9-142">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="574c9-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="574c9-143">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="574c9-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="574c9-144">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="574c9-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="574c9-145">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="574c9-146">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="574c9-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="574c9-147">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="574c9-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="574c9-148">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="574c9-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="574c9-149">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="574c9-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="574c9-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="574c9-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="574c9-151">Siga los pasos siguientes o [vea el vídeo (empieza en 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="574c9-151">Follow the steps below or [watch the video (start at 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="574c9-152">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="574c9-152">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="574c9-153">Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="574c9-153">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="574c9-154">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="574c9-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="574c9-155">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="574c9-156">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="574c9-157">Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros de intercambio de correo**.</span><span class="sxs-lookup"><span data-stu-id="574c9-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Seleccionar Editar registros de intercambio de correo](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="574c9-159">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="574c9-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="574c9-160">(Elija el valor **prioridad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="574c9-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="574c9-161">\*\*\*\*Nombre de host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="574c9-162">\*\*\*\*Prioridad\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="574c9-163">\*\*\*\*Servidor de correo\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="574c9-164">Máximo</span><span class="sxs-lookup"><span data-stu-id="574c9-164">High</span></span>  <br/> <span data-ttu-id="574c9-165">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="574c9-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="574c9-166">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="574c9-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="574c9-167">**Nota:** Obtén tu \<*domain-key*\> cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="574c9-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="574c9-168">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="574c9-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copie y pegue el valor de la tabla](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="574c9-170">Si se muestran otros registros MX en la lista, seleccione todos los registros que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="574c9-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="574c9-172">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-172">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="574c9-174">En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="574c9-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccione continuar.](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="574c9-176">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="574c9-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="574c9-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="574c9-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="574c9-178">Siga los pasos siguientes o [vea el vídeo (empieza en 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="574c9-178">Follow the steps below or [watch the video (start at 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="574c9-179">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="574c9-179">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="574c9-180">Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="574c9-180">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="574c9-181">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="574c9-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="574c9-182">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="574c9-183">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="574c9-184">Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros de alias de dominio**.</span><span class="sxs-lookup"><span data-stu-id="574c9-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Seleccione Editar registros de alias de dominio](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="574c9-186">Seleccione **Agregar más alias de dominio**.</span><span class="sxs-lookup"><span data-stu-id="574c9-186">Select **Add more domain aliases**.</span></span>
    
    ![Seleccione Agregar alias de dominios](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="574c9-188">Agregar los registros CNAME necesarios.</span><span class="sxs-lookup"><span data-stu-id="574c9-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="574c9-189">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="574c9-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="574c9-190">\*\*\*\*Primer campo (sin etiqueta)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="574c9-191">\*\*\*\*Señala a\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="574c9-192">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="574c9-192">autodiscover</span></span>  <br/> |<span data-ttu-id="574c9-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="574c9-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="574c9-194">sip</span><span class="sxs-lookup"><span data-stu-id="574c9-194">sip</span></span>  <br/> |<span data-ttu-id="574c9-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="574c9-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="574c9-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="574c9-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="574c9-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="574c9-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="574c9-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="574c9-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="574c9-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="574c9-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="574c9-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="574c9-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="574c9-201">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="574c9-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Copiar y pegar los valores DNS de la tabla](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="574c9-203">Una vez que haya agregado todos los registros CNAME que necesita, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="574c9-205">En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="574c9-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccione continuar.](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="574c9-207">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="574c9-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="574c9-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="574c9-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="574c9-209">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="574c9-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="574c9-210">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="574c9-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="574c9-211">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="574c9-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="574c9-212">En vez de eso, agregue los valores necesarios de Microsoft para el registro actual, de modo que solo tenga un único registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="574c9-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="574c9-213">Siga los pasos siguientes o [vea el vídeo (empieza en 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="574c9-213">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="574c9-214">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="574c9-214">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="574c9-215">Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="574c9-215">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="574c9-216">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="574c9-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="574c9-217">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="574c9-218">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="574c9-219">Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros txt (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="574c9-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Seleccionar Editar registros TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="574c9-221">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="574c9-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="574c9-222">\*\*\*\*Nombre de host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="574c9-223">\*\*\*\*Registro TXT\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="574c9-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="574c9-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="574c9-225">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="574c9-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Copiar y pegar los valores de la tabla](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="574c9-227">Seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-227">Select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="574c9-229">En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="574c9-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccione continuar.](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="574c9-231">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="574c9-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="574c9-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="574c9-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="574c9-233">Siga los pasos siguientes o [vea el vídeo (empieza en 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="574c9-233">Follow the steps below or [watch the video (start at 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="574c9-234">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="574c9-234">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="574c9-235">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="574c9-235">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="574c9-236">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="574c9-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="574c9-237">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="574c9-238">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="574c9-239">Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="574c9-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Seleccionar Editar registros SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="574c9-241">Agregue el primero de los dos registros SRV:</span><span class="sxs-lookup"><span data-stu-id="574c9-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="574c9-242">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="574c9-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="574c9-243">(Elija el valor **prioridad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="574c9-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="574c9-244">\*\*\*\*Servicio\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="574c9-245">\*\*\*\*Puerto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="574c9-246">\*\*\*\*Nombre\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="574c9-247">\*\*\*\*Prioridad\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="574c9-248">\*\*\*\*Grosor\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="574c9-249">\*\*\*\*Puerto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="574c9-250">\*\*\*\*Destino\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="574c9-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="574c9-251">_sip</span><span class="sxs-lookup"><span data-stu-id="574c9-251">_sip</span></span>  <br/> |<span data-ttu-id="574c9-252">_tls</span><span class="sxs-lookup"><span data-stu-id="574c9-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="574c9-253">Máximo</span><span class="sxs-lookup"><span data-stu-id="574c9-253">High</span></span>  <br/> |<span data-ttu-id="574c9-254">1 </span><span class="sxs-lookup"><span data-stu-id="574c9-254">1</span></span>  <br/> |<span data-ttu-id="574c9-255">443</span><span class="sxs-lookup"><span data-stu-id="574c9-255">443</span></span>  <br/> |<span data-ttu-id="574c9-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="574c9-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="574c9-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="574c9-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="574c9-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="574c9-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="574c9-259">Máximo</span><span class="sxs-lookup"><span data-stu-id="574c9-259">High</span></span>  <br/> |<span data-ttu-id="574c9-260">1 </span><span class="sxs-lookup"><span data-stu-id="574c9-260">1</span></span>  <br/> |<span data-ttu-id="574c9-261">5061</span><span class="sxs-lookup"><span data-stu-id="574c9-261">5061</span></span>  <br/> |<span data-ttu-id="574c9-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="574c9-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Copiar y pegar los valores de la tabla](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="574c9-264">Seleccione **Agregar más registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="574c9-264">Select **Add more SRV records**.</span></span>
    
    ![Seleccione Agregar más registros SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="574c9-266">Agregue el segundo registro SRV:</span><span class="sxs-lookup"><span data-stu-id="574c9-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="574c9-267">Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="574c9-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="574c9-268">Una vez que haya agregado los dos registros SRV, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="574c9-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Seleccione continuar.](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="574c9-270">En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="574c9-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccione continuar.](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="574c9-272">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="574c9-272">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="574c9-273">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="574c9-273">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="574c9-274">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="574c9-274">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
