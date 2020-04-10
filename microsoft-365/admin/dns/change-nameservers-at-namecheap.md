---
title: Cambiar los servidores de nombres para configurar Office 365 con namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Aprenda a configurar su dominio personalizado de Office 365 con namecheap si quiere que Office 365 administre sus registros DNS. '
ms.openlocfilehash: 1130f8aca0f2d014d73f5a1b2e2edb2785a7c6b8
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212322"
---
# <a name="change-nameservers-to-set-up-office-365-with-namecheap"></a><span data-ttu-id="4d108-103">Cambiar los servidores de nombres para configurar Office 365 con namecheap</span><span class="sxs-lookup"><span data-stu-id="4d108-103">Change nameservers to set up Office 365 with Namecheap</span></span>

 <span data-ttu-id="4d108-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="4d108-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="4d108-105">Siga estas instrucciones si quiere que Office 365 administre automáticamente los registros DNS de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d108-105">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.</span></span> <span data-ttu-id="4d108-106">(Si lo prefiere, puede [administrar todos los registros DNS de Office 365 en namecheap](create-dns-records-at-namecheap.md)).</span><span class="sxs-lookup"><span data-stu-id="4d108-106">(If you prefer, you can [manage all your Office 365 DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4d108-107">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="4d108-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="4d108-108">Para empezar, vaya a su página de dominios en namecheap a través de [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="4d108-108">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="4d108-109">Se le pedirá que inicie sesión y continúe.</span><span class="sxs-lookup"><span data-stu-id="4d108-109">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="4d108-111">En la página de **aterrizaje** , en **cuenta**, elija **lista de dominios** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4d108-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="4d108-113">En la página **lista de dominios** , busque el nombre del dominio que desea editar y, a continuación, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="4d108-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="4d108-115">Seleccione **DNS avanzado**.</span><span class="sxs-lookup"><span data-stu-id="4d108-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="4d108-117">En la sección **registros de host** , seleccione **Agregar nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="4d108-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="4d108-119">En la lista desplegable **tipo** , seleccione **registro TXT**.</span><span class="sxs-lookup"><span data-stu-id="4d108-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4d108-120">La lista desplegable **tipo** aparece automáticamente cuando se selecciona **Agregar nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="4d108-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="4d108-122">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4d108-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4d108-123">(Elija el valor **TTL** de la lista desplegable).</span><span class="sxs-lookup"><span data-stu-id="4d108-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="4d108-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4d108-124">**Type**</span></span>|<span data-ttu-id="4d108-125">**Host**</span><span class="sxs-lookup"><span data-stu-id="4d108-125">**Host**</span></span>|<span data-ttu-id="4d108-126">**Valor**</span><span class="sxs-lookup"><span data-stu-id="4d108-126">**Value**</span></span>|<span data-ttu-id="4d108-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4d108-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d108-128">TXT</span><span class="sxs-lookup"><span data-stu-id="4d108-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="4d108-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4d108-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4d108-130">**Nota**: este es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4d108-130">**Note**: This is an example.</span></span> <span data-ttu-id="4d108-131">Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d108-131">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="4d108-132">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="4d108-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4d108-133">30 minutos</span><span class="sxs-lookup"><span data-stu-id="4d108-133">30 min</span></span>  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="4d108-135">Seleccione el control **Guardar cambios** (marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="4d108-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="4d108-137">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="4d108-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4d108-138">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.</span><span class="sxs-lookup"><span data-stu-id="4d108-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="4d108-139">Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="4d108-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4d108-140">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="4d108-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4d108-141">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="4d108-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4d108-142">En la página de **Configuración**, elija \*\* Iniciar configuración\*\*.</span><span class="sxs-lookup"><span data-stu-id="4d108-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4d108-143">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="4d108-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="4d108-p104">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4d108-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="4d108-147">Cambiar los registros del servidor de nombres (o NS) de su dominio</span><span class="sxs-lookup"><span data-stu-id="4d108-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="4d108-p105">Para completar la configuración del dominio con Office 365, debe cambiar los registros NS del dominio en su registrador de dominios para que apunten a los servidores DNS primario y secundario de Office 365. Esto configura Office 365 para actualizar los registros DNS del dominio. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.</span><span class="sxs-lookup"><span data-stu-id="4d108-p105">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4d108-p106">Si cambia los registros NS del dominio para que apunten a los servidores DNS de Office 365, esto afectará a todos los servicios que estén asociados actualmente con su dominio. Por ejemplo, todos los correos que se envíen a su dominio (como, por ejemplo, rob@ *su_dominio*  .com) comenzarán a llegar a Office 365 después de realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="4d108-p106">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="4d108-153">Cuando haya completado los pasos descritos en esta sección, los  *únicos*  servidores DNS que deben aparecer son estos cuatro: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  En el procedimiento siguiente se muestra cómo eliminar cualquier otro servidor de nombres que no desee de la lista y también cómo agregar estos cuatro servidores DNS  *correctos*  , si aún no están en la lista.</span><span class="sxs-lookup"><span data-stu-id="4d108-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="4d108-154">Para empezar, vaya a su página de dominios en namecheap a través de [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="4d108-154">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="4d108-155">Se le pedirá que inicie sesión y continúe.</span><span class="sxs-lookup"><span data-stu-id="4d108-155">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="4d108-157">En la página de **aterrizaje** , en **cuenta**, elija **lista de dominios** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4d108-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="4d108-159">En la página **lista de dominios** , busque el nombre del dominio que desea editar y, a continuación, seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="4d108-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="4d108-161">Seleccione **dominio**.</span><span class="sxs-lookup"><span data-stu-id="4d108-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="4d108-163">Busque la sección **servidores de nombres** y seleccione **personalizada** en la lista desplegable **namecheap predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="4d108-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="4d108-165">Dependiendo de si ya hay o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4d108-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="4d108-166">Si aún NO se muestran servidores DNS en la lista</span><span class="sxs-lookup"><span data-stu-id="4d108-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="4d108-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="4d108-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="4d108-168">Seleccione **Agregar NAMESERVER** dos veces para agregar dos filas nuevas.</span><span class="sxs-lookup"><span data-stu-id="4d108-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namecheap-BP-redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="4d108-170">En los cuadros **servidor de nombres** , escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4d108-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="4d108-171">**Servidor DNS 1**</span><span class="sxs-lookup"><span data-stu-id="4d108-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="4d108-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4d108-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4d108-173">**Servidor de nombres 2**</span><span class="sxs-lookup"><span data-stu-id="4d108-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="4d108-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4d108-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4d108-175">**Servidor DNS 3**</span><span class="sxs-lookup"><span data-stu-id="4d108-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="4d108-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4d108-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4d108-177">**Servidor DNS 4**</span><span class="sxs-lookup"><span data-stu-id="4d108-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="4d108-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4d108-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="4d108-180">Seleccione el control **Guardar** (marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="4d108-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="4d108-p108">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="4d108-p108">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="4d108-184">Si ya existen servidores de nombres enumerados</span><span class="sxs-lookup"><span data-stu-id="4d108-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="4d108-p109">Siga estos pasos  *solo*  si tiene servidores de nombres distintos de los cuatro servidores de nombres  *correctos*  . (Es decir, elimine  *solo*  los servidores de nombres actuales que  *no*  sean **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com** ).</span><span class="sxs-lookup"><span data-stu-id="4d108-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="4d108-187">Si en los cuadros **servidor de nombres** aparecen otros servidores DNS, elimínelos (para hacerlo, selecciónelos y, después, presione la tecla **suprimir** en el teclado).</span><span class="sxs-lookup"><span data-stu-id="4d108-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="4d108-189">Seleccione **Agregar NAMESERVER** dos veces para agregar dos filas nuevas.</span><span class="sxs-lookup"><span data-stu-id="4d108-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namecheap-BP-redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="4d108-191">En los cuadros **servidor de nombres** , escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4d108-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="4d108-192">**Servidor DNS 1**</span><span class="sxs-lookup"><span data-stu-id="4d108-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="4d108-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4d108-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4d108-194">**Servidor DNS 2**</span><span class="sxs-lookup"><span data-stu-id="4d108-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="4d108-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4d108-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4d108-196">**Servidor DNS 3**</span><span class="sxs-lookup"><span data-stu-id="4d108-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="4d108-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4d108-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4d108-198">**Servidor DNS 4**</span><span class="sxs-lookup"><span data-stu-id="4d108-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="4d108-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4d108-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="4d108-201">Seleccione el control **Guardar** (marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="4d108-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="4d108-p110">Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.</span><span class="sxs-lookup"><span data-stu-id="4d108-p110">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>
