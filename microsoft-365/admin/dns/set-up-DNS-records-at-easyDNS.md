---
title: Crear registros DNS en easyDNS para Microsoft
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en easyDNS para Microsoft.
ms.openlocfilehash: 24f477d240af936975141c53d382e114a24c0ac5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400237"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="f669e-103">Crear registros DNS en easyDNS para Microsoft</span><span class="sxs-lookup"><span data-stu-id="f669e-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="f669e-104">[Consulte preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md) si no encuentra lo que está buscando.</span><span class="sxs-lookup"><span data-stu-id="f669e-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f669e-105">Deberá agregar todos los registros DNS siguientes al sitio web del registrador para enrutar el correo a Microsoft, usar su dominio para Teams y Skype empresarial, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="f669e-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="f669e-106">Nota: Actualmente, los registros SRV no están disponibles en todos los paquetes del servicio de easyDNS.</span><span class="sxs-lookup"><span data-stu-id="f669e-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="f669e-107">Es posible que necesite actualizar a un nivel de servicio superior con easyDNS para agregar los registros SRV necesarios para Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="f669e-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="f669e-108">Comprobar que es el propietario del dominio con un registro TXT</span><span class="sxs-lookup"><span data-stu-id="f669e-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="f669e-109">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="f669e-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="f669e-110">En el encabezado **todos los dominios** , seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="f669e-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="f669e-111">En el encabezado **registros txt** , selecciona el botón Editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="f669e-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="f669e-112">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="f669e-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="f669e-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="f669e-113">**Host**</span></span>|<span data-ttu-id="f669e-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="f669e-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="f669e-115">MS = msXXXXXXXX (use el valor que se proporciona en la página de dominios del centro de administración)</span><span class="sxs-lookup"><span data-stu-id="f669e-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="f669e-116">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f669e-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="f669e-117">Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f669e-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="f669e-118">Espere unos minutos antes de continuar, para que el registro que acaba de crear pueda propagarse a través de Internet y sea detectado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f669e-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="f669e-119">Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.</span><span class="sxs-lookup"><span data-stu-id="f669e-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="f669e-120">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="f669e-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="f669e-121">En la página **Dominios**, elija el dominio que está verificando.</span><span class="sxs-lookup"><span data-stu-id="f669e-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="f669e-122">En la página **configuración** , seleccione **Iniciar configuración.**</span><span class="sxs-lookup"><span data-stu-id="f669e-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="f669e-123">En la página**verificar dominio**, seleccione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="f669e-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="f669e-124">Agregar un registro MX para redirigir el correo electrónico a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f669e-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="f669e-125">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="f669e-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="f669e-126">En el encabezado **todos los dominios** , seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="f669e-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="f669e-127">En el encabezado **registros MX** , selecciona el botón Editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="f669e-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="f669e-128">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="f669e-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="f669e-129">**CORREO PARA LA ZONA**</span><span class="sxs-lookup"><span data-stu-id="f669e-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="f669e-130">**SERVIDOR DE CORREO**</span><span class="sxs-lookup"><span data-stu-id="f669e-130">**MAIL SERVER**</span></span>|<span data-ttu-id="f669e-131">**DISTINGUIR**</span><span class="sxs-lookup"><span data-stu-id="f669e-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f669e-132">\<domain-key\>. mail.protection.outlook.com (obtener su \<domain-key\> valor de la página de dominios del centro de administración)</span><span class="sxs-lookup"><span data-stu-id="f669e-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="f669e-133">comprendi</span><span class="sxs-lookup"><span data-stu-id="f669e-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="f669e-134">Si desea guardar los demás registros MX para fines de copia de seguridad, cópielos en algún lugar.</span><span class="sxs-lookup"><span data-stu-id="f669e-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="f669e-135">Antes de continuar, elimine todos los demás registros MX.</span><span class="sxs-lookup"><span data-stu-id="f669e-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="f669e-136">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f669e-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="f669e-137">Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f669e-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="f669e-138">Agregar los registros CNAME necesarios</span><span class="sxs-lookup"><span data-stu-id="f669e-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="f669e-139">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="f669e-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="f669e-140">En el encabezado **todos los dominios** , seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="f669e-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="f669e-141">En el encabezado **registros CNAME/alias** , selecciona el botón Editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="f669e-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="f669e-142">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="f669e-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="f669e-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="f669e-143">**HOST**</span></span>|<span data-ttu-id="f669e-144">**Address (debe terminar con un ".")**</span><span class="sxs-lookup"><span data-stu-id="f669e-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f669e-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f669e-145">autodiscover</span></span>  <br/> |<span data-ttu-id="f669e-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f669e-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="f669e-147">sip</span><span class="sxs-lookup"><span data-stu-id="f669e-147">sip</span></span>  <br/> |<span data-ttu-id="f669e-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f669e-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="f669e-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f669e-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f669e-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f669e-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="f669e-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f669e-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f669e-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="f669e-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="f669e-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f669e-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f669e-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f669e-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="f669e-155">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f669e-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="f669e-156">Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f669e-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f669e-157">Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f669e-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="f669e-158">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="f669e-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="f669e-159">En el encabezado **todos los dominios** , seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="f669e-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="f669e-160">En el encabezado **registros txt** , selecciona el botón Editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="f669e-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="f669e-161">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="f669e-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="f669e-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="f669e-162">**Host**</span></span>|<span data-ttu-id="f669e-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="f669e-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="f669e-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f669e-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="f669e-165">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f669e-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="f669e-166">Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f669e-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="f669e-167">Agregar los dos registros SRV necesarios para Microsoft</span><span class="sxs-lookup"><span data-stu-id="f669e-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="f669e-168">Nota: Actualmente, los registros SRV no están disponibles en easyDNS ' dominio más nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="f669e-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="f669e-169">Es posible que necesite actualizar a un nivel de servicio superior con easyDNS para agregar registros SRV</span><span class="sxs-lookup"><span data-stu-id="f669e-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="f669e-170">Vaya a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e inicie sesión con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="f669e-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="f669e-171">En el encabezado **todos los dominios** , seleccione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="f669e-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="f669e-172">En el encabezado **registros SRV** , selecciona el botón Editar (icono de llave inglesa).</span><span class="sxs-lookup"><span data-stu-id="f669e-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="f669e-173">Escriba los siguientes registros en los campos de texto:</span><span class="sxs-lookup"><span data-stu-id="f669e-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="f669e-174">**SERVICIO**</span><span class="sxs-lookup"><span data-stu-id="f669e-174">**SERVICE**</span></span>|<span data-ttu-id="f669e-175">**Protocolo**</span><span class="sxs-lookup"><span data-stu-id="f669e-175">**PROTO**</span></span>|<span data-ttu-id="f669e-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="f669e-176">**HOST**</span></span>|<span data-ttu-id="f669e-177">**PRIORIDAD**</span><span class="sxs-lookup"><span data-stu-id="f669e-177">**PRI**</span></span>|<span data-ttu-id="f669e-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="f669e-178">**WGT**</span></span>|<span data-ttu-id="f669e-179">**PUERTO**</span><span class="sxs-lookup"><span data-stu-id="f669e-179">**PORT**</span></span>|<span data-ttu-id="f669e-180">**DESTINO (debe terminar con ".")**</span><span class="sxs-lookup"><span data-stu-id="f669e-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="f669e-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f669e-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f669e-182">_sip</span><span class="sxs-lookup"><span data-stu-id="f669e-182">_sip</span></span>  <br/> |<span data-ttu-id="f669e-183">TLS</span><span class="sxs-lookup"><span data-stu-id="f669e-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="f669e-184">100</span><span class="sxs-lookup"><span data-stu-id="f669e-184">100</span></span>  <br/> |<span data-ttu-id="f669e-185">1 </span><span class="sxs-lookup"><span data-stu-id="f669e-185">1</span></span>  <br/> |<span data-ttu-id="f669e-186">443</span><span class="sxs-lookup"><span data-stu-id="f669e-186">443</span></span>  <br/> |<span data-ttu-id="f669e-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f669e-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="f669e-188">1800</span><span class="sxs-lookup"><span data-stu-id="f669e-188">1800</span></span>  <br/> |
    |<span data-ttu-id="f669e-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f669e-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="f669e-190">TCP</span><span class="sxs-lookup"><span data-stu-id="f669e-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="f669e-191">100</span><span class="sxs-lookup"><span data-stu-id="f669e-191">100</span></span>  <br/> |<span data-ttu-id="f669e-192">1 </span><span class="sxs-lookup"><span data-stu-id="f669e-192">1</span></span>  <br/> |<span data-ttu-id="f669e-193">5061</span><span class="sxs-lookup"><span data-stu-id="f669e-193">5061</span></span>  <br/> |<span data-ttu-id="f669e-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f669e-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="f669e-195">1800</span><span class="sxs-lookup"><span data-stu-id="f669e-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="f669e-196">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f669e-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="f669e-197">Asegúrese de que el registro sea correcto y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f669e-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

