---
title: Crear registros DNS en Amazon Web Services (AWS) para Microsoft
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en Amazon Web Services (AWS) para Microsoft.
ms.openlocfilehash: 12f9341ab381324266cf2da1ca6b5423df9973dd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910419"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="1f542-103">Crear registros DNS en Amazon Web Services (AWS) para Microsoft</span><span class="sxs-lookup"><span data-stu-id="1f542-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="1f542-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="1f542-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1f542-105">Si AWS es su proveedor de hospedaje DNS, siga los pasos descritos en este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Online para empresas, entre otros.</span><span class="sxs-lookup"><span data-stu-id="1f542-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="1f542-106">Después de agregar estos registros en AWS, el dominio se configurará para que funcione con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f542-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="1f542-107">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="1f542-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1f542-108">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="1f542-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1f542-109">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1f542-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1f542-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="1f542-110">Add a TXT record for verification</span></span>
<span data-ttu-id="1f542-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1f542-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1f542-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="1f542-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f542-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="1f542-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1f542-p104">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="1f542-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1f542-118">En la **página Recursos,** seleccione **Zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="1f542-118">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="1f542-119">En la **página Zonas hospedadas,** en la columna **Nombre** de dominio, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="1f542-119">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="1f542-120">Seleccione **Crear conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="1f542-120">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="1f542-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1f542-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1f542-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="1f542-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="1f542-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="1f542-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1f542-125">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1f542-125">**Name**</span></span> <br/> |<span data-ttu-id="1f542-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1f542-126">**Type**</span></span> <br/> |<span data-ttu-id="1f542-127">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1f542-127">**Alias**</span></span> <br/> |<span data-ttu-id="1f542-128">**TTL (segundos)**</span><span class="sxs-lookup"><span data-stu-id="1f542-128">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="1f542-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f542-129">**Value**</span></span> <br/> |<span data-ttu-id="1f542-130">**Directiva de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="1f542-130">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="1f542-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1f542-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1f542-132">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="1f542-132">TXT - Text</span></span>  <br/> |<span data-ttu-id="1f542-133">No</span><span class="sxs-lookup"><span data-stu-id="1f542-133">No</span></span>  <br/> |<span data-ttu-id="1f542-134">300</span><span class="sxs-lookup"><span data-stu-id="1f542-134">300</span></span>  <br/> |<span data-ttu-id="1f542-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1f542-135">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="1f542-136">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1f542-136">**Note:** This is an example.</span></span> <span data-ttu-id="1f542-137">Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f542-137">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="1f542-138">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="1f542-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1f542-139">Simple</span><span class="sxs-lookup"><span data-stu-id="1f542-139">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="1f542-140">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1f542-140">Select **Create**.</span></span>
    
7. <span data-ttu-id="1f542-141">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="1f542-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1f542-142">Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.</span><span class="sxs-lookup"><span data-stu-id="1f542-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="1f542-143">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="1f542-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1f542-144">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="1f542-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1f542-145">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="1f542-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="1f542-146">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="1f542-146">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="1f542-147">En la página **Verificar dominio**, elija **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="1f542-147">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1f542-148">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="1f542-148">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1f542-149">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="1f542-149">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1f542-150">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1f542-150">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="1f542-151">Agregar un registro MX para que el correo electrónico de su dominio se envíe a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f542-151">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="1f542-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1f542-152"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="1f542-p108">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="1f542-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1f542-155">En la **página Recursos,** seleccione **Zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="1f542-155">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="1f542-156">En la **página Zonas hospedadas,** en la columna **Nombre** de dominio, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="1f542-156">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="1f542-157">Seleccione **Crear conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="1f542-157">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="1f542-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1f542-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1f542-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="1f542-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="1f542-160">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1f542-160">**Name**</span></span>|<span data-ttu-id="1f542-161">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1f542-161">**Type**</span></span>|<span data-ttu-id="1f542-162">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1f542-162">**Alias**</span></span>|<span data-ttu-id="1f542-163">**TTL (segundos)**</span><span class="sxs-lookup"><span data-stu-id="1f542-163">**TTL (Seconds)**</span></span>|<span data-ttu-id="1f542-164">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f542-164">**Value**</span></span>|<span data-ttu-id="1f542-165">**Directiva de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="1f542-165">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1f542-166">(Deje este campo en blanco).</span><span class="sxs-lookup"><span data-stu-id="1f542-166">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1f542-167">MX - Registro de intercambio de correo</span><span class="sxs-lookup"><span data-stu-id="1f542-167">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="1f542-168">No</span><span class="sxs-lookup"><span data-stu-id="1f542-168">No</span></span>  <br/> |<span data-ttu-id="1f542-169">300</span><span class="sxs-lookup"><span data-stu-id="1f542-169">300</span></span>  <br/> |<span data-ttu-id="1f542-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1f542-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="1f542-p109">El 0 es el valor de prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  </span><span class="sxs-lookup"><span data-stu-id="1f542-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="1f542-173">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="1f542-173">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1f542-174">**Nota:** Obtenga el \<*domain-key*\> de su cuenta de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f542-174">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="1f542-175">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="1f542-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1f542-176">Simple</span><span class="sxs-lookup"><span data-stu-id="1f542-176">Simple</span></span>  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="1f542-178">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1f542-178">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="1f542-180">Si hay otros registros MX, quítelos.</span><span class="sxs-lookup"><span data-stu-id="1f542-180">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1f542-181">AWS almacena registros MX como un conjunto que puede contener varios registros.</span><span class="sxs-lookup"><span data-stu-id="1f542-181">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="1f542-182">**NO seleccione** **Eliminar conjunto de registros,** ya que se eliminarán todos los registros MX, incluido el que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="1f542-182">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="1f542-183">Use las siguientes instrucciones en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1f542-183">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="1f542-184">En primer lugar, seleccione el conjunto de registros MX.</span><span class="sxs-lookup"><span data-stu-id="1f542-184">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="1f542-186">A continuación, en el área **Editar conjunto de registros**, elimine cada registro MX obsoleto seleccionando la entrada en el cuadro **Valor** y, a continuación, pulse la tecla **Eliminar** de su teclado.</span><span class="sxs-lookup"><span data-stu-id="1f542-186">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="1f542-188">Seleccione **Guardar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="1f542-188">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="1f542-190">Agregar los cinco registros CNAME necesarios para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f542-190">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="1f542-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1f542-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="1f542-p112">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="1f542-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1f542-194">En la **página Recursos,** seleccione **Zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="1f542-194">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="1f542-195">En la **página Zonas hospedadas,** en la columna **Nombre** de dominio, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="1f542-195">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="1f542-196">Seleccione **Crear conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="1f542-196">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="1f542-197">Agregue el primer registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="1f542-197">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="1f542-198">En el área **Agregar conjunto de registros**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores a partir de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1f542-198">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="1f542-199">(Seleccione los valores **Tipo** y **Directiva de enrutamiento** que aparecen en las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="1f542-199">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="1f542-200">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1f542-200">**Name**</span></span>|<span data-ttu-id="1f542-201">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1f542-201">**Type**</span></span>|<span data-ttu-id="1f542-202">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1f542-202">**Alias**</span></span>|<span data-ttu-id="1f542-203">**TTL (segundos)**</span><span class="sxs-lookup"><span data-stu-id="1f542-203">**TTL (Seconds)**</span></span>|<span data-ttu-id="1f542-204">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f542-204">**Value**</span></span>|<span data-ttu-id="1f542-205">**Directiva de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="1f542-205">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1f542-206">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1f542-206">autodiscover</span></span>  <br/> |<span data-ttu-id="1f542-207">CNAME - nombre canónico</span><span class="sxs-lookup"><span data-stu-id="1f542-207">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="1f542-208">No</span><span class="sxs-lookup"><span data-stu-id="1f542-208">No</span></span>  <br/> |<span data-ttu-id="1f542-209">300</span><span class="sxs-lookup"><span data-stu-id="1f542-209">300</span></span>  <br/> |<span data-ttu-id="1f542-210">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1f542-210">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1f542-211">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="1f542-211">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1f542-212">Simple</span><span class="sxs-lookup"><span data-stu-id="1f542-212">Simple</span></span>  <br/> |
    |<span data-ttu-id="1f542-213">sip</span><span class="sxs-lookup"><span data-stu-id="1f542-213">sip</span></span>  <br/> |<span data-ttu-id="1f542-214">CNAME - nombre canónico</span><span class="sxs-lookup"><span data-stu-id="1f542-214">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="1f542-215">No</span><span class="sxs-lookup"><span data-stu-id="1f542-215">No</span></span>  <br/> |<span data-ttu-id="1f542-216">300</span><span class="sxs-lookup"><span data-stu-id="1f542-216">300</span></span>  <br/> |<span data-ttu-id="1f542-217">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1f542-217">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1f542-218">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="1f542-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1f542-219">Simple</span><span class="sxs-lookup"><span data-stu-id="1f542-219">Simple</span></span>  <br/> |
    |<span data-ttu-id="1f542-220">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1f542-220">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1f542-221">CNAME - nombre canónico</span><span class="sxs-lookup"><span data-stu-id="1f542-221">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="1f542-222">No</span><span class="sxs-lookup"><span data-stu-id="1f542-222">No</span></span>  <br/> |<span data-ttu-id="1f542-223">300</span><span class="sxs-lookup"><span data-stu-id="1f542-223">300</span></span>  <br/> |<span data-ttu-id="1f542-224">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1f542-224">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1f542-225">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="1f542-225">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1f542-226">Simple</span><span class="sxs-lookup"><span data-stu-id="1f542-226">Simple</span></span>  <br/> |
    |<span data-ttu-id="1f542-227">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1f542-227">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1f542-228">CNAME - nombre canónico</span><span class="sxs-lookup"><span data-stu-id="1f542-228">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="1f542-229">No</span><span class="sxs-lookup"><span data-stu-id="1f542-229">No</span></span>  <br/> |<span data-ttu-id="1f542-230">300</span><span class="sxs-lookup"><span data-stu-id="1f542-230">300</span></span>  <br/> |<span data-ttu-id="1f542-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1f542-231">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="1f542-232">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="1f542-232">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1f542-233">Simple</span><span class="sxs-lookup"><span data-stu-id="1f542-233">Simple</span></span>  <br/> |
    |<span data-ttu-id="1f542-234">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="1f542-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1f542-235">CNAME - nombre canónico</span><span class="sxs-lookup"><span data-stu-id="1f542-235">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="1f542-236">No</span><span class="sxs-lookup"><span data-stu-id="1f542-236">No</span></span>  <br/> |<span data-ttu-id="1f542-237">300</span><span class="sxs-lookup"><span data-stu-id="1f542-237">300</span></span>  <br/> |<span data-ttu-id="1f542-238">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1f542-238">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="1f542-239">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="1f542-239">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1f542-240">Simple</span><span class="sxs-lookup"><span data-stu-id="1f542-240">Simple</span></span>  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="1f542-242">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1f542-242">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="1f542-244">Agregue los otros cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1f542-244">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="1f542-245">En la **página Zonas hospedadas,** seleccione **Crear** conjunto de registros, cree un registro con los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar **Crear** para completar dicho registro.</span><span class="sxs-lookup"><span data-stu-id="1f542-245">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="1f542-246">Repita este proceso hasta que haya creado los cinco registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1f542-246">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1f542-247">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="1f542-247">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1f542-248"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1f542-248"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f542-249">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="1f542-249">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1f542-250">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="1f542-250">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1f542-251">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f542-251">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1f542-252">En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un único registro  *SPF*  que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="1f542-252">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="1f542-253">¿Necesita ejemplos?</span><span class="sxs-lookup"><span data-stu-id="1f542-253">Need examples?</span></span> <span data-ttu-id="1f542-254">Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="1f542-254">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="1f542-255">Para validar el registro SPF, puede usar una de estas herramientas[de validación de SPF](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="1f542-255">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="1f542-256">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="1f542-256">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="1f542-257">Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="1f542-257">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1f542-258">En la **página Recursos,** seleccione **Zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="1f542-258">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="1f542-259">En la **página Zonas hospedadas,** en la columna **Nombre** de dominio, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="1f542-259">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="1f542-260">Seleccione el conjunto de registros **TXT.**</span><span class="sxs-lookup"><span data-stu-id="1f542-260">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="1f542-p115">En el área **Editar conjunto de registros**, al final de la entrada actual del cuadro **Valor:** del registro existente, presione ENTRAR en el teclado para crear una línea; luego, en esa línea (en el valor existente), escriba o copie y pegue el valor de la tabla siguiente (puede ver un ejemplo en la ilustración que aparece debajo de la tabla).</span><span class="sxs-lookup"><span data-stu-id="1f542-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="1f542-264">**Valor:**</span><span class="sxs-lookup"><span data-stu-id="1f542-264">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="1f542-265">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1f542-265">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1f542-p116">(Las comillas necesarias por las instrucciones en pantalla aparecen automáticamente. No es necesario escribirlas manualmente).  </span><span class="sxs-lookup"><span data-stu-id="1f542-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="1f542-268">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="1f542-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="1f542-270">Seleccione **Guardar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="1f542-270">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="1f542-272">Agregar los dos registros SRV necesarios para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f542-272">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="1f542-273"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1f542-273"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="1f542-p117">Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.</span><span class="sxs-lookup"><span data-stu-id="1f542-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1f542-276">En la **página Recursos,** seleccione **Zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="1f542-276">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="1f542-277">En la **página Zonas hospedadas,** en la columna **Nombre** de dominio, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="1f542-277">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="1f542-278">Seleccione **Crear conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="1f542-278">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="1f542-279">Agregue el primer registro SRV.</span><span class="sxs-lookup"><span data-stu-id="1f542-279">Add the first SRV record:</span></span>
    
    <span data-ttu-id="1f542-280">En el área **Agregar conjunto de registros**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores a partir de la primera fila de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1f542-280">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="1f542-281">(Seleccione los valores **Tipo** y **Directiva de enrutamiento** que aparecen en las listas desplegables).</span><span class="sxs-lookup"><span data-stu-id="1f542-281">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="1f542-282">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1f542-282">**Name**</span></span>|<span data-ttu-id="1f542-283">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1f542-283">**Type**</span></span>|<span data-ttu-id="1f542-284">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1f542-284">**Alias**</span></span>|<span data-ttu-id="1f542-285">**TTL (segundos)**</span><span class="sxs-lookup"><span data-stu-id="1f542-285">**TTL (Seconds)**</span></span>|<span data-ttu-id="1f542-286">**Valor**</span><span class="sxs-lookup"><span data-stu-id="1f542-286">**Value**</span></span>|<span data-ttu-id="1f542-287">**Directiva de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="1f542-287">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1f542-288">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="1f542-288">_sip._tls</span></span>|<span data-ttu-id="1f542-289">SRV - Localizador de servicio</span><span class="sxs-lookup"><span data-stu-id="1f542-289">SRV - Service locator</span></span>|<span data-ttu-id="1f542-290">No</span><span class="sxs-lookup"><span data-stu-id="1f542-290">No</span></span>|<span data-ttu-id="1f542-291">300</span><span class="sxs-lookup"><span data-stu-id="1f542-291">300</span></span>|<span data-ttu-id="1f542-292">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1f542-292">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="1f542-293">**Este valor DEBE terminar con un punto (.)**></span><span class="sxs-lookup"><span data-stu-id="1f542-293">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="1f542-294">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="1f542-294">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="1f542-295">Simple</span><span class="sxs-lookup"><span data-stu-id="1f542-295">Simple</span></span>|
    |<span data-ttu-id="1f542-296">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="1f542-296">_sipfederationtls._tcp</span></span>|<span data-ttu-id="1f542-297">SRV - Localizador de servicio</span><span class="sxs-lookup"><span data-stu-id="1f542-297">SRV - Service locator</span></span>|<span data-ttu-id="1f542-298">No</span><span class="sxs-lookup"><span data-stu-id="1f542-298">No</span></span>|<span data-ttu-id="1f542-299">300</span><span class="sxs-lookup"><span data-stu-id="1f542-299">300</span></span>|<span data-ttu-id="1f542-300">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1f542-300">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="1f542-301">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="1f542-301">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="1f542-302">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="1f542-302">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="1f542-303">Simple</span><span class="sxs-lookup"><span data-stu-id="1f542-303">Simple</span></span>|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="1f542-305">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1f542-305">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="1f542-307">Para agregar el otro registro SRV:</span><span class="sxs-lookup"><span data-stu-id="1f542-307">To add the other SRV record:</span></span>
    
    <span data-ttu-id="1f542-308">En la **página Zonas hospedadas,** seleccione **Crear** conjunto de registros, cree un registro con los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar **Crear** para completar dicho registro.</span><span class="sxs-lookup"><span data-stu-id="1f542-308">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1f542-309">Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="1f542-309">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1f542-310">Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet.</span><span class="sxs-lookup"><span data-stu-id="1f542-310">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1f542-311">Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1f542-311">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
