---
title: Crear registros DNS en Amazon Web Services (AWS) para Office 365
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Amazon Web Services (AWS) para Office 365.
ms.openlocfilehash: baba7bb7275303604d241166f4dc1d2af77b3f17
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351481"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-office-365"></a><span data-ttu-id="aa36a-103">Crear registros DNS en Amazon Web Services (AWS) para Office 365</span><span class="sxs-lookup"><span data-stu-id="aa36a-103">Create DNS records at Amazon Web Services (AWS) for Office 365</span></span>

 <span data-ttu-id="aa36a-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="aa36a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="aa36a-105">Si AWS es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype online para empresas, etc.</span><span class="sxs-lookup"><span data-stu-id="aa36a-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="aa36a-106">Después de agregar estos registros a AWS, su dominio estará configurado para trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa36a-106">After you add these records at AWS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="aa36a-107">Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="aa36a-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa36a-108">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="aa36a-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="aa36a-109">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="aa36a-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="aa36a-110">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="aa36a-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="aa36a-111">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="aa36a-111">Add a TXT record for verification</span></span>
<span data-ttu-id="aa36a-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="aa36a-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="aa36a-p102">Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="aa36a-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa36a-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="aa36a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="aa36a-117">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="aa36a-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="aa36a-118">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="aa36a-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="aa36a-119">En la página **recursos** , seleccione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="aa36a-120">En la página \* \* zonas hospedadas \* \*, en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="aa36a-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="aa36a-121">Seleccione **crear conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="aa36a-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="aa36a-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="aa36a-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="aa36a-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="aa36a-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="aa36a-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="aa36a-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="aa36a-126">**Name**</span></span> <br/> |<span data-ttu-id="aa36a-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="aa36a-127">**Type**</span></span> <br/> |<span data-ttu-id="aa36a-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="aa36a-128">**Alias**</span></span> <br/> |<span data-ttu-id="aa36a-129">**TTL (segundos)**</span><span class="sxs-lookup"><span data-stu-id="aa36a-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="aa36a-130">**Valor**</span><span class="sxs-lookup"><span data-stu-id="aa36a-130">**Value**</span></span> <br/> |<span data-ttu-id="aa36a-131">**Directiva de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="aa36a-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="aa36a-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="aa36a-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="aa36a-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="aa36a-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="aa36a-134">No</span><span class="sxs-lookup"><span data-stu-id="aa36a-134">No</span></span>  <br/> |<span data-ttu-id="aa36a-135">300</span><span class="sxs-lookup"><span data-stu-id="aa36a-135">300</span></span>  <br/> |<span data-ttu-id="aa36a-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="aa36a-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="aa36a-137">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aa36a-137">**Note:** This is an example.</span></span> <span data-ttu-id="aa36a-138">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa36a-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="aa36a-139">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="aa36a-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="aa36a-140">Simple</span><span class="sxs-lookup"><span data-stu-id="aa36a-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="aa36a-141">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="aa36a-142">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="aa36a-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="aa36a-143">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="aa36a-143">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="aa36a-144">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="aa36a-144">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="aa36a-145">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="aa36a-145">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="aa36a-146">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="aa36a-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="aa36a-147">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="aa36a-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="aa36a-148">En la página**Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="aa36a-149">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="aa36a-149">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="aa36a-150">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="aa36a-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="aa36a-151">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="aa36a-151">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="aa36a-152">Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365</span><span class="sxs-lookup"><span data-stu-id="aa36a-152">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="aa36a-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="aa36a-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="aa36a-p108">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="aa36a-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="aa36a-156">En la página **recursos** , seleccione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="aa36a-157">En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="aa36a-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="aa36a-158">Seleccione **crear conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="aa36a-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="aa36a-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="aa36a-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="aa36a-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="aa36a-161">**Name**</span><span class="sxs-lookup"><span data-stu-id="aa36a-161">**Name**</span></span>|<span data-ttu-id="aa36a-162">**Type**</span><span class="sxs-lookup"><span data-stu-id="aa36a-162">**Type**</span></span>|<span data-ttu-id="aa36a-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="aa36a-163">**Alias**</span></span>|<span data-ttu-id="aa36a-164">**TTL (segundos)**</span><span class="sxs-lookup"><span data-stu-id="aa36a-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="aa36a-165">**Valor**</span><span class="sxs-lookup"><span data-stu-id="aa36a-165">**Value**</span></span>|<span data-ttu-id="aa36a-166">**Directiva de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="aa36a-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="aa36a-167">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="aa36a-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="aa36a-168">MX - Registro de intercambio de correo</span><span class="sxs-lookup"><span data-stu-id="aa36a-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="aa36a-169">No</span><span class="sxs-lookup"><span data-stu-id="aa36a-169">No</span></span>  <br/> |<span data-ttu-id="aa36a-170">300</span><span class="sxs-lookup"><span data-stu-id="aa36a-170">300</span></span>  <br/> |<span data-ttu-id="aa36a-171">0  *\<clave-de-dominio\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="aa36a-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="aa36a-p109">El 0 es el valor de prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  </span><span class="sxs-lookup"><span data-stu-id="aa36a-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="aa36a-174">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="aa36a-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="aa36a-175">**Nota:** Obtenga la \<*clave-de-dominio*\> desde su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa36a-175">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="aa36a-176">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="aa36a-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="aa36a-177">Simple</span><span class="sxs-lookup"><span data-stu-id="aa36a-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="aa36a-179">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="aa36a-181">Si hay otros registros MX, quítelos.</span><span class="sxs-lookup"><span data-stu-id="aa36a-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="aa36a-182">AWS almacena registros MX como un conjunto que puede contener varios registros.</span><span class="sxs-lookup"><span data-stu-id="aa36a-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="aa36a-183">**No** seleccione **eliminar conjunto de registros**, ya que se eliminarán todos los registros MX, incluido el que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="aa36a-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="aa36a-184">Use las siguientes instrucciones en su lugar.</span><span class="sxs-lookup"><span data-stu-id="aa36a-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="aa36a-185">En primer lugar, seleccione el conjunto de registros MX.</span><span class="sxs-lookup"><span data-stu-id="aa36a-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="aa36a-187">A continuación, en el área **Editar conjunto de registros**, elimine cada registro MX obsoleto seleccionando la entrada en el cuadro **Valor** y, a continuación, pulse la tecla **Eliminar** de su teclado.</span><span class="sxs-lookup"><span data-stu-id="aa36a-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="aa36a-189">Seleccione **Guardar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="aa36a-191">Agregue los cinco registros CNAME necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="aa36a-191">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="aa36a-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="aa36a-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="aa36a-p112">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="aa36a-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="aa36a-195">En la página **recursos** , seleccione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="aa36a-196">En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="aa36a-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="aa36a-197">Seleccione **crear conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="aa36a-198">Agregue el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="aa36a-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="aa36a-199">En el área **Agregar conjunto de registros**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores a partir de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="aa36a-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="aa36a-200">(Seleccione los valores **Tipo** y **Directiva de enrutamiento** que aparecen en las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="aa36a-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="aa36a-201">**Name**</span><span class="sxs-lookup"><span data-stu-id="aa36a-201">**Name**</span></span>|<span data-ttu-id="aa36a-202">**Type**</span><span class="sxs-lookup"><span data-stu-id="aa36a-202">**Type**</span></span>|<span data-ttu-id="aa36a-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="aa36a-203">**Alias**</span></span>|<span data-ttu-id="aa36a-204">**TTL (segundos)**</span><span class="sxs-lookup"><span data-stu-id="aa36a-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="aa36a-205">**Valor**</span><span class="sxs-lookup"><span data-stu-id="aa36a-205">**Value**</span></span>|<span data-ttu-id="aa36a-206">**Directiva de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="aa36a-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="aa36a-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="aa36a-207">autodiscover</span></span>  <br/> |<span data-ttu-id="aa36a-208">CNAME - nombre canónico</span><span class="sxs-lookup"><span data-stu-id="aa36a-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="aa36a-209">No</span><span class="sxs-lookup"><span data-stu-id="aa36a-209">No</span></span>  <br/> |<span data-ttu-id="aa36a-210">300</span><span class="sxs-lookup"><span data-stu-id="aa36a-210">300</span></span>  <br/> |<span data-ttu-id="aa36a-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="aa36a-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="aa36a-212">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="aa36a-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aa36a-213">Simple</span><span class="sxs-lookup"><span data-stu-id="aa36a-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="aa36a-214">sip</span><span class="sxs-lookup"><span data-stu-id="aa36a-214">sip</span></span>  <br/> |<span data-ttu-id="aa36a-215">CNAME - nombre canónico</span><span class="sxs-lookup"><span data-stu-id="aa36a-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="aa36a-216">No</span><span class="sxs-lookup"><span data-stu-id="aa36a-216">No</span></span>  <br/> |<span data-ttu-id="aa36a-217">300</span><span class="sxs-lookup"><span data-stu-id="aa36a-217">300</span></span>  <br/> |<span data-ttu-id="aa36a-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aa36a-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="aa36a-219">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="aa36a-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aa36a-220">Simple</span><span class="sxs-lookup"><span data-stu-id="aa36a-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="aa36a-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="aa36a-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="aa36a-222">CNAME - nombre canónico</span><span class="sxs-lookup"><span data-stu-id="aa36a-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="aa36a-223">No</span><span class="sxs-lookup"><span data-stu-id="aa36a-223">No</span></span>  <br/> |<span data-ttu-id="aa36a-224">300</span><span class="sxs-lookup"><span data-stu-id="aa36a-224">300</span></span>  <br/> |<span data-ttu-id="aa36a-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aa36a-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="aa36a-226">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="aa36a-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aa36a-227">Simple</span><span class="sxs-lookup"><span data-stu-id="aa36a-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="aa36a-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="aa36a-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="aa36a-229">CNAME - nombre canónico</span><span class="sxs-lookup"><span data-stu-id="aa36a-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="aa36a-230">No</span><span class="sxs-lookup"><span data-stu-id="aa36a-230">No</span></span>  <br/> |<span data-ttu-id="aa36a-231">300</span><span class="sxs-lookup"><span data-stu-id="aa36a-231">300</span></span>  <br/> |<span data-ttu-id="aa36a-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="aa36a-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="aa36a-233">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="aa36a-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aa36a-234">Simple</span><span class="sxs-lookup"><span data-stu-id="aa36a-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="aa36a-235">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="aa36a-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="aa36a-236">CNAME - nombre canónico</span><span class="sxs-lookup"><span data-stu-id="aa36a-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="aa36a-237">No</span><span class="sxs-lookup"><span data-stu-id="aa36a-237">No</span></span>  <br/> |<span data-ttu-id="aa36a-238">300</span><span class="sxs-lookup"><span data-stu-id="aa36a-238">300</span></span>  <br/> |<span data-ttu-id="aa36a-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="aa36a-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="aa36a-240">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="aa36a-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="aa36a-241">Simple</span><span class="sxs-lookup"><span data-stu-id="aa36a-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="aa36a-243">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="aa36a-245">Agregue los otros cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="aa36a-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="aa36a-246">En la página **zonas hospedadas** , seleccione **crear conjunto de registros**, cree un registro con los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar **crear** para completar ese registro.</span><span class="sxs-lookup"><span data-stu-id="aa36a-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="aa36a-247">Repita este proceso hasta que haya creado los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="aa36a-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="aa36a-248">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="aa36a-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="aa36a-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="aa36a-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa36a-250">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="aa36a-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="aa36a-251">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="aa36a-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="aa36a-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa36a-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="aa36a-253">En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="aa36a-253">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="aa36a-254">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="aa36a-254">Need examples?</span></span> <span data-ttu-id="aa36a-255">Consulte los [Registros externos del sistema de nombres de dominio para Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="aa36a-255">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="aa36a-256">Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="aa36a-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="aa36a-257">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="aa36a-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="aa36a-258">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="aa36a-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="aa36a-259">En la página **recursos** , seleccione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="aa36a-260">En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="aa36a-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="aa36a-261">Seleccione el conjunto de registros **txt** .</span><span class="sxs-lookup"><span data-stu-id="aa36a-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="aa36a-p115">En el área **Editar conjunto de registros**, al final de la entrada actual del cuadro **Valor:** del registro existente, presione ENTRAR en el teclado para crear una línea; luego, en esa línea (en el valor existente), escriba o copie y pegue el valor de la tabla siguiente (puede ver un ejemplo en la ilustración que aparece debajo de la tabla).</span><span class="sxs-lookup"><span data-stu-id="aa36a-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="aa36a-265">**Valor:**</span><span class="sxs-lookup"><span data-stu-id="aa36a-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="aa36a-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="aa36a-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="aa36a-p116">(Las comillas necesarias por las instrucciones en pantalla aparecen automáticamente. No es necesario escribirlas manualmente).  </span><span class="sxs-lookup"><span data-stu-id="aa36a-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="aa36a-269">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="aa36a-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="aa36a-271">Seleccione **Guardar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="aa36a-273">Agregar los dos registros SRV necesarios para Office 365</span><span class="sxs-lookup"><span data-stu-id="aa36a-273">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="aa36a-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="aa36a-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="aa36a-p117">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="aa36a-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="aa36a-277">En la página **recursos** , seleccione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="aa36a-278">En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="aa36a-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="aa36a-279">Seleccione **crear conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="aa36a-280">Agregue el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="aa36a-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="aa36a-281">En el área **Agregar conjunto de registros**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores a partir de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="aa36a-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="aa36a-282">(Seleccione los valores **Tipo** y **Directiva de enrutamiento** que aparecen en las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="aa36a-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="aa36a-283">**Name**</span><span class="sxs-lookup"><span data-stu-id="aa36a-283">**Name**</span></span>|<span data-ttu-id="aa36a-284">**Type**</span><span class="sxs-lookup"><span data-stu-id="aa36a-284">**Type**</span></span>|<span data-ttu-id="aa36a-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="aa36a-285">**Alias**</span></span>|<span data-ttu-id="aa36a-286">**TTL (segundos)**</span><span class="sxs-lookup"><span data-stu-id="aa36a-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="aa36a-287">**Valor**</span><span class="sxs-lookup"><span data-stu-id="aa36a-287">**Value**</span></span>|<span data-ttu-id="aa36a-288">**Directiva de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="aa36a-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="aa36a-289">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="aa36a-289">_sip._tls</span></span>|<span data-ttu-id="aa36a-290">SRV - Localizador de servicio</span><span class="sxs-lookup"><span data-stu-id="aa36a-290">SRV - Service locator</span></span>|<span data-ttu-id="aa36a-291">No</span><span class="sxs-lookup"><span data-stu-id="aa36a-291">No</span></span>|<span data-ttu-id="aa36a-292">300</span><span class="sxs-lookup"><span data-stu-id="aa36a-292">300</span></span>|<span data-ttu-id="aa36a-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aa36a-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="aa36a-294">**Este valor debe terminar con un punto (.).**></span><span class="sxs-lookup"><span data-stu-id="aa36a-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="aa36a-295">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="aa36a-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="aa36a-296">Simple</span><span class="sxs-lookup"><span data-stu-id="aa36a-296">Simple</span></span>|
    |<span data-ttu-id="aa36a-297">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="aa36a-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="aa36a-298">SRV - Localizador de servicio</span><span class="sxs-lookup"><span data-stu-id="aa36a-298">SRV - Service locator</span></span>|<span data-ttu-id="aa36a-299">No</span><span class="sxs-lookup"><span data-stu-id="aa36a-299">No</span></span>|<span data-ttu-id="aa36a-300">300</span><span class="sxs-lookup"><span data-stu-id="aa36a-300">300</span></span>|<span data-ttu-id="aa36a-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aa36a-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="aa36a-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="aa36a-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="aa36a-303">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="aa36a-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="aa36a-304">Simple</span><span class="sxs-lookup"><span data-stu-id="aa36a-304">Simple</span></span>|
   
    ![AWS-BP-configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="aa36a-306">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="aa36a-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="aa36a-308">Para agregar el otro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="aa36a-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="aa36a-309">En la página **zonas hospedadas** , seleccione **crear conjunto de registros**, cree un registro con los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar **crear** para completar ese registro.</span><span class="sxs-lookup"><span data-stu-id="aa36a-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="aa36a-310">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="aa36a-310">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="aa36a-311">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="aa36a-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="aa36a-312">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="aa36a-312">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
