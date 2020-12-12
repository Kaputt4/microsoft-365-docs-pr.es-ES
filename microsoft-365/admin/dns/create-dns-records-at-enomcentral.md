---
title: Crear registros DNS en eNomCentral para Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en eNomCentral para Microsoft.
ms.openlocfilehash: e6e05b987a893da582ea7fb062eafe421861b970
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658116"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="c8e46-103">Crear registros DNS en eNomCentral para Microsoft</span><span class="sxs-lookup"><span data-stu-id="c8e46-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="c8e46-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="c8e46-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="c8e46-105">Si eNomCentral es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.</span><span class="sxs-lookup"><span data-stu-id="c8e46-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="c8e46-106">Después de agregar estos registros a eNomCentral, su dominio estará configurado para funcionar con los servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8e46-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e46-p101">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c8e46-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c8e46-110">Agregar un registro TXT para verificación</span><span class="sxs-lookup"><span data-stu-id="c8e46-110">Add a TXT record for verification</span></span>
<span data-ttu-id="c8e46-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c8e46-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c8e46-p102">Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="c8e46-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e46-p103">Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="c8e46-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="c8e46-116">Siga los pasos siguientes o [vea el vídeo (empieza en 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="c8e46-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="c8e46-p104">Para empezar, vaya a su página de dominios en eNom Central a través de [este vínculo](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="c8e46-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="c8e46-120">En **mis dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="c8e46-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="c8e46-122">En la lista desplegable **Administrar dominio**, elija **Registros de host**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. <span data-ttu-id="c8e46-124">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c8e46-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="c8e46-125">Elija el valor **tipo de registro** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c8e46-125">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="c8e46-126">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="c8e46-126">Host Name</span></span>|<span data-ttu-id="c8e46-127">Record Type</span><span class="sxs-lookup"><span data-stu-id="c8e46-127">Record Type</span></span>|<span data-ttu-id="c8e46-128">Address</span><span class="sxs-lookup"><span data-stu-id="c8e46-128">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="c8e46-129">TXT</span><span class="sxs-lookup"><span data-stu-id="c8e46-129">TXT</span></span>|<span data-ttu-id="c8e46-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c8e46-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c8e46-131">**Nota:** esto es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c8e46-131">**Note:** This is an example.</span></span> <span data-ttu-id="c8e46-132">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="c8e46-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="c8e46-133">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="c8e46-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. <span data-ttu-id="c8e46-135">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-135">Select **save**.</span></span>

   ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. <span data-ttu-id="c8e46-137">Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.</span><span class="sxs-lookup"><span data-stu-id="c8e46-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="c8e46-138">Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.</span><span class="sxs-lookup"><span data-stu-id="c8e46-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>

<span data-ttu-id="c8e46-139">Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.</span><span class="sxs-lookup"><span data-stu-id="c8e46-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="c8e46-140">En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="c8e46-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="c8e46-141">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="c8e46-141">On the **Domains** page, select the domain that you are verifying.</span></span>

3. <span data-ttu-id="c8e46-142">En la página de **Configuración**, elija **Iniciar configuración**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-142">On the **Setup** page, select **Start setup**.</span></span>

4. <span data-ttu-id="c8e46-143">En la página **verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-143">On the **Verify domain** page, select **Verify**.</span></span>

> [!NOTE]
> <span data-ttu-id="c8e46-p106">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c8e46-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c8e46-147">Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c8e46-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c8e46-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c8e46-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="c8e46-149">Siga los pasos siguientes o [vea el vídeo (empieza en 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="c8e46-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="c8e46-p107">Para empezar, vaya a su página de dominios en eNom Central a través de [este vínculo](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="c8e46-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="c8e46-153">En **mis dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="c8e46-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="c8e46-155">En la lista desplegable **Administrar dominio**, elija **Configuración de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>

   ![eNom-BP-configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. <span data-ttu-id="c8e46-157">En la lista desplegable **Selección de servicio**, elija **Usuario (MX)**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>

   ![eNom-BP-configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. <span data-ttu-id="c8e46-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c8e46-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="c8e46-160">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="c8e46-160">Host Name</span></span>|<span data-ttu-id="c8e46-161">Address</span><span class="sxs-lookup"><span data-stu-id="c8e46-161">Address</span></span>|<span data-ttu-id="c8e46-162">Pref.</span><span class="sxs-lookup"><span data-stu-id="c8e46-162">Pref</span></span>|
   |---|---|---|
   |@| <span data-ttu-id="c8e46-163">*\<domain-key\>*  . mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="c8e46-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="c8e46-164">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="c8e46-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="c8e46-165">**Nota:** Obtén tu  *\<domain-key\>*  cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8e46-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="c8e46-166">¿Cómo puedo encontrarla?</span><span class="sxs-lookup"><span data-stu-id="c8e46-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="c8e46-167">10 </span><span class="sxs-lookup"><span data-stu-id="c8e46-167">10</span></span>  <br/> <span data-ttu-id="c8e46-168">Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="c8e46-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span>|

   ![eNom-BP-configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. <span data-ttu-id="c8e46-170">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-170">Select **save**.</span></span>

   ![eNom-BP-configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. <span data-ttu-id="c8e46-172">Si hay otros registros MX, active las casillas de esos registros para seleccionarlos.</span><span class="sxs-lookup"><span data-stu-id="c8e46-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>

   ![eNom-BP-configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. <span data-ttu-id="c8e46-174">Seleccione **eliminar seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-174">Select **delete checked**.</span></span>

   ![eNom-BP-configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c8e46-176">Agregar los registros CNAME necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="c8e46-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c8e46-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c8e46-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="c8e46-178">Siga los pasos siguientes o [vea el vídeo (empieza en 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="c8e46-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="c8e46-p109">Para empezar, vaya a su página de dominios en eNom Central a través de [este vínculo](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="c8e46-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="c8e46-182">En **mis dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="c8e46-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="c8e46-184">En la lista desplegable **Administrar dominio**, elija **Registros de host**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="c8e46-186">Seleccione **nueva fila**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-186">Select **new row**.</span></span>

   ![eNom-BP-configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. <span data-ttu-id="c8e46-188">En los cuadros para los seis nuevos registros, escriba o copie y pegue los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="c8e46-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>

   <span data-ttu-id="c8e46-189">Elija el valor **tipo de registro** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c8e46-189">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="c8e46-190">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="c8e46-190">Host Name</span></span>|<span data-ttu-id="c8e46-191">Record Type</span><span class="sxs-lookup"><span data-stu-id="c8e46-191">Record Type</span></span>|<span data-ttu-id="c8e46-192">Address</span><span class="sxs-lookup"><span data-stu-id="c8e46-192">Address</span></span>|
   |---|---|---|
   |<span data-ttu-id="c8e46-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c8e46-193">autodiscover</span></span>|<span data-ttu-id="c8e46-194">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="c8e46-194">CNAME (Alias)</span></span>|<span data-ttu-id="c8e46-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="c8e46-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="c8e46-196">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="c8e46-196">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="c8e46-197">sip</span><span class="sxs-lookup"><span data-stu-id="c8e46-197">sip</span></span>|<span data-ttu-id="c8e46-198">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="c8e46-198">CNAME (Alias)</span></span>|<span data-ttu-id="c8e46-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c8e46-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c8e46-200">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="c8e46-200">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="c8e46-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c8e46-201">lyncdiscover</span></span>|<span data-ttu-id="c8e46-202">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="c8e46-202">CNAME (Alias)</span></span>|<span data-ttu-id="c8e46-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c8e46-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c8e46-204">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="c8e46-204">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="c8e46-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c8e46-205">enterpriseregistration</span></span>|<span data-ttu-id="c8e46-206">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="c8e46-206">CNAME (Alias)</span></span>|<span data-ttu-id="c8e46-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="c8e46-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="c8e46-208">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="c8e46-208">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="c8e46-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c8e46-209">enterpriseenrollment</span></span>|<span data-ttu-id="c8e46-210">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="c8e46-210">CNAME (Alias)</span></span>|<span data-ttu-id="c8e46-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c8e46-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="c8e46-212">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c8e46-212">**This value MUST end with a period (.)**</span></span>|

   ![eNom-BP-configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. <span data-ttu-id="c8e46-214">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-214">Select **save**.</span></span>

   ![eNom-BP-configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c8e46-216">Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="c8e46-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c8e46-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c8e46-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8e46-218">No puede tener más de un registro TXT para el SPF de un dominio.</span><span class="sxs-lookup"><span data-stu-id="c8e46-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c8e46-219">Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c8e46-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c8e46-220">Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8e46-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c8e46-221">En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="c8e46-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="c8e46-222">Siga los pasos siguientes o [vea el vídeo (empieza en 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="c8e46-222">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="c8e46-p111">Para empezar, vaya a su página de dominios en eNom Central a través de [este vínculo](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="c8e46-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="c8e46-226">En **mis dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="c8e46-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="c8e46-228">En la lista desplegable **Administrar dominio**, elija **Registros de host**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="c8e46-230">En los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c8e46-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="c8e46-231">Elija el valor **tipo de registro** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c8e46-231">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="c8e46-232">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="c8e46-232">Host Name</span></span>|<span data-ttu-id="c8e46-233">Record Type</span><span class="sxs-lookup"><span data-stu-id="c8e46-233">Record Type</span></span>|<span data-ttu-id="c8e46-234">Address</span><span class="sxs-lookup"><span data-stu-id="c8e46-234">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="c8e46-235">TXT</span><span class="sxs-lookup"><span data-stu-id="c8e46-235">TXT</span></span>|<span data-ttu-id="c8e46-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c8e46-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="c8e46-237">**Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.</span><span class="sxs-lookup"><span data-stu-id="c8e46-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>|

   ![eNom-BP-configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. <span data-ttu-id="c8e46-239">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-239">Select **save**.</span></span>

   ![eNom-BP-configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c8e46-241">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="c8e46-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c8e46-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c8e46-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="c8e46-243">Siga los pasos siguientes o [vea el vídeo (empieza en 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="c8e46-243">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="c8e46-p112">Para empezar, vaya a su página de dominios en eNom Central a través de [este vínculo](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Se le pedirá que primero inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="c8e46-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="c8e46-247">En **mis dominios**, seleccione el nombre del dominio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="c8e46-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="c8e46-249">En la lista desplegable **Administrar dominio**, elija **Registros de host**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="c8e46-251">A la derecha de **nueva fila**, seleccione **Agregar registro SRV o SPF**.</span><span class="sxs-lookup"><span data-stu-id="c8e46-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>

   ![eNom-BP-configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. <span data-ttu-id="c8e46-253">En los cuadros de los dos nuevos registros, escriba (o copie y pegue) los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c8e46-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="c8e46-254">Servicio</span><span class="sxs-lookup"><span data-stu-id="c8e46-254">Service</span></span>|<span data-ttu-id="c8e46-255">Protocolo</span><span class="sxs-lookup"><span data-stu-id="c8e46-255">Protocol</span></span>|<span data-ttu-id="c8e46-256">Priority</span><span class="sxs-lookup"><span data-stu-id="c8e46-256">Priority</span></span>|<span data-ttu-id="c8e46-257">Peso</span><span class="sxs-lookup"><span data-stu-id="c8e46-257">Weight</span></span>|<span data-ttu-id="c8e46-258">Puerto</span><span class="sxs-lookup"><span data-stu-id="c8e46-258">Port</span></span>|<span data-ttu-id="c8e46-259">Destino (nombre de host)</span><span class="sxs-lookup"><span data-stu-id="c8e46-259">Target (Hostname)</span></span>|
   |---|---|---|---|---|---|
   |<span data-ttu-id="c8e46-260">_sip</span><span class="sxs-lookup"><span data-stu-id="c8e46-260">_sip</span></span>|<span data-ttu-id="c8e46-261">_tls</span><span class="sxs-lookup"><span data-stu-id="c8e46-261">_tls</span></span>|<span data-ttu-id="c8e46-262">100</span><span class="sxs-lookup"><span data-stu-id="c8e46-262">100</span></span>|<span data-ttu-id="c8e46-263">1 </span><span class="sxs-lookup"><span data-stu-id="c8e46-263">1</span></span>|<span data-ttu-id="c8e46-264">443</span><span class="sxs-lookup"><span data-stu-id="c8e46-264">443</span></span>|<span data-ttu-id="c8e46-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c8e46-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c8e46-266">**Este valor DEBE terminar en punto (.)**</span><span class="sxs-lookup"><span data-stu-id="c8e46-266">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="c8e46-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c8e46-267">_sipfederationtls</span></span>|<span data-ttu-id="c8e46-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="c8e46-268">_tcp</span></span>|<span data-ttu-id="c8e46-269">100</span><span class="sxs-lookup"><span data-stu-id="c8e46-269">100</span></span>|<span data-ttu-id="c8e46-270">1 </span><span class="sxs-lookup"><span data-stu-id="c8e46-270">1</span></span>|<span data-ttu-id="c8e46-271">5061</span><span class="sxs-lookup"><span data-stu-id="c8e46-271">5061</span></span>|<span data-ttu-id="c8e46-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c8e46-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="c8e46-273">**Este valor DEBE terminar en punto (.).**</span><span class="sxs-lookup"><span data-stu-id="c8e46-273">**This value MUST end with a period (.)**</span></span>|

   ![eNom-BP-configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. <span data-ttu-id="c8e46-275">Seleccione **Guardar**</span><span class="sxs-lookup"><span data-stu-id="c8e46-275">Select **save**</span></span>

   ![eNom-BP-configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> <span data-ttu-id="c8e46-p113">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c8e46-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
