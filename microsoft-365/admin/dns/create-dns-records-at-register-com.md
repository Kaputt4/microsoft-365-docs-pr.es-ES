---
title: Crear registros DNS en Register.com para Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Register.com for Microsoft.
ms.openlocfilehash: dd2f3d516b5309fee85dd572470fe610ff277a68
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657597"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="a15ac-103">Crear registros DNS en Register.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a15ac-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="a15ac-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="a15ac-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a15ac-105">Si Register.com es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="a15ac-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a15ac-106">Estos son los registros principales que agregar.</span><span class="sxs-lookup"><span data-stu-id="a15ac-106">These are the main records to add.</span></span> <span data-ttu-id="a15ac-107">Siga los pasos siguientes o [vea el vídeo](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="a15ac-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
- [<span data-ttu-id="a15ac-108">Agregar un registro TXT en Register.com para comprobar que es el propietario del dominio</span><span class="sxs-lookup"><span data-stu-id="a15ac-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="a15ac-109">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a15ac-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="a15ac-110">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a15ac-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="a15ac-111">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="a15ac-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="a15ac-112">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a15ac-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="a15ac-113">Después de agregar estos registros a Register.com, el dominio se configurará para funcionar con los servicios Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a15ac-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="a15ac-114">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="a15ac-114">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a15ac-115">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="a15ac-115">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a15ac-116">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a15ac-116">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="a15ac-117">Agregar un registro TXT en Register.com para comprobar que es el propietario del dominio</span><span class="sxs-lookup"><span data-stu-id="a15ac-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="a15ac-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a15ac-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a15ac-p103">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="a15ac-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a15ac-p104">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="a15ac-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a15ac-123">Siga los pasos siguientes o [vea el vídeo (empieza en 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="a15ac-123">Follow the steps below or [watch the video (start at 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="a15ac-p105">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/). Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a15ac-p105">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="a15ac-126">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="a15ac-127">Seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="a15ac-128">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="a15ac-129">Desplácese hacia abajo hasta la **sección Configuración** técnica avanzada y, a continuación, seleccione Editar registros **TXT (SPF).**</span><span class="sxs-lookup"><span data-stu-id="a15ac-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="a15ac-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a15ac-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="a15ac-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a15ac-131">**Host Name**</span></span> <br/> |<span data-ttu-id="a15ac-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="a15ac-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="a15ac-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a15ac-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a15ac-134">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a15ac-134">**Note:** This is an example.</span></span> <span data-ttu-id="a15ac-135">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="a15ac-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="a15ac-136">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="a15ac-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="a15ac-137">Seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="a15ac-138">En la página siguiente, seleccione **Continuar de** nuevo para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a15ac-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="a15ac-139">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="a15ac-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a15ac-140">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="a15ac-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a15ac-141">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="a15ac-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a15ac-142">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="a15ac-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a15ac-143">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="a15ac-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="a15ac-144">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="a15ac-145">En la página **Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a15ac-146">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="a15ac-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a15ac-147">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="a15ac-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a15ac-148">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a15ac-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a15ac-149">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a15ac-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a15ac-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a15ac-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a15ac-151">Siga los pasos siguientes o [vea el vídeo (empieza en 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="a15ac-151">Follow the steps below or [watch the video (start at 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="a15ac-p108">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/). Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a15ac-p108">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="a15ac-154">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="a15ac-155">Seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="a15ac-156">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="a15ac-157">Desplácese hasta la **sección Configuración técnica** avanzada y, a continuación, seleccione Editar registros de intercambio de **correo.**</span><span class="sxs-lookup"><span data-stu-id="a15ac-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Seleccionar editar registros de exchanger de correo](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="a15ac-159">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a15ac-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a15ac-160">(Elija el **valor prioridad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="a15ac-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a15ac-161">\*\*\*\*Nombre de host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="a15ac-162">\*\*\*\*Prioridad\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="a15ac-163">\*\*\*\*Servidor de correo\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a15ac-164">Máximo</span><span class="sxs-lookup"><span data-stu-id="a15ac-164">High</span></span>  <br/> <span data-ttu-id="a15ac-165">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="a15ac-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="a15ac-166">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a15ac-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="a15ac-167">**Nota:** Obtenga la \<*domain-key*\> desde su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a15ac-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="a15ac-168">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="a15ac-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar y pegar el valor de la tabla](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="a15ac-170">Si se muestran otros registros MX en la lista, seleccione todos los registros que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="a15ac-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="a15ac-172">Seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-172">Select **Continue**.</span></span>
    
    ![Seleccionar Continuar](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="a15ac-174">En la página siguiente, seleccione **Continuar de** nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a15ac-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccionar Continuar](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a15ac-176">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a15ac-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a15ac-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a15ac-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a15ac-178">Siga los pasos siguientes o [vea el vídeo (empieza en 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="a15ac-178">Follow the steps below or [watch the video (start at 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="a15ac-p109">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/). Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a15ac-p109">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="a15ac-181">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="a15ac-182">Seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="a15ac-183">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="a15ac-184">Desplácese hasta la **sección Configuración técnica** avanzada y, a continuación, seleccione Editar registros de alias de **dominio.**</span><span class="sxs-lookup"><span data-stu-id="a15ac-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Seleccionar editar registros de alias de dominio](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="a15ac-186">Seleccione **Agregar más alias de dominio.**</span><span class="sxs-lookup"><span data-stu-id="a15ac-186">Select **Add more domain aliases**.</span></span>
    
    ![Seleccione Agregar más alias de dominios](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="a15ac-188">Agregar los registros CNAME necesarios.</span><span class="sxs-lookup"><span data-stu-id="a15ac-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="a15ac-189">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a15ac-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="a15ac-190">\*\*\*\*Primer campo (sin etiqueta)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="a15ac-191">\*\*\*\*Señala a\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a15ac-192">autodescubrir</span><span class="sxs-lookup"><span data-stu-id="a15ac-192">autodiscover</span></span>  <br/> |<span data-ttu-id="a15ac-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a15ac-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="a15ac-194">sip</span><span class="sxs-lookup"><span data-stu-id="a15ac-194">sip</span></span>  <br/> |<span data-ttu-id="a15ac-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a15ac-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="a15ac-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a15ac-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a15ac-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a15ac-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="a15ac-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a15ac-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a15ac-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a15ac-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="a15ac-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a15ac-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a15ac-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a15ac-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Copiar y pegar los valores DNS de la tabla](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="a15ac-203">Cuando haya agregado todos los registros CNAME que necesita, seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Seleccionar Continuar](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="a15ac-205">En la página siguiente, seleccione **Continuar de** nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a15ac-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccionar Continuar](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a15ac-207">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="a15ac-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a15ac-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a15ac-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a15ac-209">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="a15ac-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a15ac-210">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a15ac-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a15ac-211">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a15ac-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a15ac-212">En vez de eso, agregue los valores necesarios de Microsoft para el registro actual, de modo que solo tenga un único registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="a15ac-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="a15ac-213">Siga los pasos siguientes o [vea el vídeo (empieza en 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="a15ac-213">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="a15ac-p111">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/). Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a15ac-p111">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="a15ac-216">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="a15ac-217">Seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="a15ac-218">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="a15ac-219">Desplácese hasta la **sección Configuración técnica** avanzada y, a continuación, seleccione Editar registros TXT **(SPF).**</span><span class="sxs-lookup"><span data-stu-id="a15ac-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Seleccionar Editar registros TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="a15ac-221">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a15ac-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a15ac-222">\*\*\*\*Nombre de host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="a15ac-223">\*\*\*\*Registro TXT\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="a15ac-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a15ac-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a15ac-225">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="a15ac-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Copiar y pegar los valores de la tabla](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="a15ac-227">Seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-227">Select **Continue**.</span></span>
    
    ![Seleccionar Continuar](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="a15ac-229">En la página siguiente, seleccione **Continuar de** nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a15ac-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccionar Continuar](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a15ac-231">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="a15ac-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a15ac-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a15ac-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="a15ac-233">Siga los pasos siguientes o [vea el vídeo (empieza en 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="a15ac-233">Follow the steps below or [watch the video (start at 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="a15ac-p112">Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/). Se le pedirá que inicie sesión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a15ac-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="a15ac-236">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="a15ac-237">Seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="a15ac-238">Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="a15ac-239">Desplácese a la **sección Configuración técnica** avanzada y, a continuación, seleccione Editar registros **SRV.**</span><span class="sxs-lookup"><span data-stu-id="a15ac-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Seleccionar Editar registros SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="a15ac-241">Agregue el primero de los dos registros SRV:</span><span class="sxs-lookup"><span data-stu-id="a15ac-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="a15ac-242">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a15ac-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="a15ac-243">(Elija el **valor prioridad** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="a15ac-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a15ac-244">\*\*\*\*Servicio\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="a15ac-245">\*\*\*\*Puerto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="a15ac-246">\*\*\*\*Nombre\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="a15ac-247">\*\*\*\*Prioridad\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="a15ac-248">\*\*\*\*Grosor\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="a15ac-249">\*\*\*\*Puerto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="a15ac-250">\*\*\*\*Destino\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a15ac-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a15ac-251">_sip</span><span class="sxs-lookup"><span data-stu-id="a15ac-251">_sip</span></span>  <br/> |<span data-ttu-id="a15ac-252">_tls</span><span class="sxs-lookup"><span data-stu-id="a15ac-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="a15ac-253">Máximo</span><span class="sxs-lookup"><span data-stu-id="a15ac-253">High</span></span>  <br/> |<span data-ttu-id="a15ac-254">1 </span><span class="sxs-lookup"><span data-stu-id="a15ac-254">1</span></span>  <br/> |<span data-ttu-id="a15ac-255">443</span><span class="sxs-lookup"><span data-stu-id="a15ac-255">443</span></span>  <br/> |<span data-ttu-id="a15ac-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a15ac-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="a15ac-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a15ac-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a15ac-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="a15ac-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="a15ac-259">Máximo</span><span class="sxs-lookup"><span data-stu-id="a15ac-259">High</span></span>  <br/> |<span data-ttu-id="a15ac-260">1 </span><span class="sxs-lookup"><span data-stu-id="a15ac-260">1</span></span>  <br/> |<span data-ttu-id="a15ac-261">5061</span><span class="sxs-lookup"><span data-stu-id="a15ac-261">5061</span></span>  <br/> |<span data-ttu-id="a15ac-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a15ac-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Copiar y pegar los valores de la tabla](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="a15ac-264">Seleccione **Agregar más registros SRV.**</span><span class="sxs-lookup"><span data-stu-id="a15ac-264">Select **Add more SRV records**.</span></span>
    
    ![Seleccione Agregar más registros SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="a15ac-266">Agregue el segundo registro SRV:</span><span class="sxs-lookup"><span data-stu-id="a15ac-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="a15ac-267">Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.</span><span class="sxs-lookup"><span data-stu-id="a15ac-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="a15ac-268">Cuando haya agregado ambos registros SRV, seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="a15ac-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Seleccionar Continuar](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="a15ac-270">En la página siguiente, seleccione **Continuar de** nuevo para confirmar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a15ac-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Seleccionar Continuar](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="a15ac-272">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="a15ac-272">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a15ac-273">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="a15ac-273">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a15ac-274">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a15ac-274">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
