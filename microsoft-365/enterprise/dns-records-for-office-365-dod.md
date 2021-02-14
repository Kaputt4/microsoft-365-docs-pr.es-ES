---
title: Registros DNS para Office 365 DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Resumen: registros DNS para Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693839"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="ceddb-103">Registros DNS para Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="ceddb-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="ceddb-104">*Este artículo se aplica a Office 365 DoD y Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="ceddb-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="ceddb-105">Como parte de la incorporación a Office 365 DoD, tendrá que agregar los dominios SMTP y SIP a su inquilino de Servicios en línea.</span><span class="sxs-lookup"><span data-stu-id="ceddb-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="ceddb-106">Para ello, use el cmdlet New-MsolDomain azure AD PowerShell o el Portal de [Azure Government para](https://portal.azure.us) iniciar el proceso de agregar el dominio y demostrar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ceddb-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="ceddb-107">Una vez que haya agregado sus dominios a su inquilino y validado, use las siguientes instrucciones para agregar los registros DNS adecuados para los servicios siguientes.</span><span class="sxs-lookup"><span data-stu-id="ceddb-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="ceddb-108">Es posible que tenga que modificar la tabla siguiente para satisfacer las necesidades de su organización con respecto a los registros MX entrantes y los registros de Detección automática de Exchange existentes que tenga en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ceddb-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="ceddb-109">Recomendamos encarecidamente coordinar estos registros DNS con el equipo de mensajería para evitar interrupciones o entregas erróneas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ceddb-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="ceddb-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ceddb-110">Exchange Online</span></span>

| <span data-ttu-id="ceddb-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="ceddb-111">Type</span></span> | <span data-ttu-id="ceddb-112">Prioridad</span><span class="sxs-lookup"><span data-stu-id="ceddb-112">Priority</span></span> | <span data-ttu-id="ceddb-113">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="ceddb-113">Host name</span></span> | <span data-ttu-id="ceddb-114">Apunta a dirección o valor</span><span class="sxs-lookup"><span data-stu-id="ceddb-114">Points to address or value</span></span> | <span data-ttu-id="ceddb-115">TTL</span><span class="sxs-lookup"><span data-stu-id="ceddb-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="ceddb-116">MX</span><span class="sxs-lookup"><span data-stu-id="ceddb-116">MX</span></span> | <span data-ttu-id="ceddb-117">0</span><span class="sxs-lookup"><span data-stu-id="ceddb-117">0</span></span> | @ | <span data-ttu-id="ceddb-118">*tenant*.mail.protection.office365.us (consulta a continuación para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="ceddb-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="ceddb-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ceddb-119">1 Hour</span></span> |
| <span data-ttu-id="ceddb-120">TXT</span><span class="sxs-lookup"><span data-stu-id="ceddb-120">TXT</span></span> | - | @ | <span data-ttu-id="ceddb-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="ceddb-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="ceddb-122">1 hora</span><span class="sxs-lookup"><span data-stu-id="ceddb-122">1 Hour</span></span> |
| <span data-ttu-id="ceddb-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="ceddb-123">CNAME</span></span> | - | <span data-ttu-id="ceddb-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ceddb-124">autodiscover</span></span> | <span data-ttu-id="ceddb-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="ceddb-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="ceddb-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ceddb-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="ceddb-127">Registro de detección automática de Exchange</span><span class="sxs-lookup"><span data-stu-id="ceddb-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="ceddb-128">Si tiene una Exchange Server local, le recomendamos dejar el registro existente en su lugar mientras migra a Exchange Online y actualizar ese registro una vez que haya completado la migración.</span><span class="sxs-lookup"><span data-stu-id="ceddb-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="ceddb-129">Registro MX de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ceddb-129">Exchange Online MX Record</span></span>

<span data-ttu-id="ceddb-130">El valor del registro MX para los dominios aceptados sigue un formato estándar  como se indicó *anteriormente:* inquilino .mail.protection.office365.us, reemplazando el inquilino por la primera parte del nombre de inquilino predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ceddb-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="ceddb-131">Por ejemplo, si el nombre del inquilino es contoso.onmicrosoft.us, usaría contoso.mail.protection.office365.us **como** valor para el registro MX.</span><span class="sxs-lookup"><span data-stu-id="ceddb-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="ceddb-132">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ceddb-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="ceddb-133">Registros CNAME</span><span class="sxs-lookup"><span data-stu-id="ceddb-133">CNAME records</span></span>

| <span data-ttu-id="ceddb-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="ceddb-134">Type</span></span> | <span data-ttu-id="ceddb-135">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="ceddb-135">Host name</span></span> | <span data-ttu-id="ceddb-136">Apunta a dirección o valor</span><span class="sxs-lookup"><span data-stu-id="ceddb-136">Points to address or value</span></span> | <span data-ttu-id="ceddb-137">TTL</span><span class="sxs-lookup"><span data-stu-id="ceddb-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="ceddb-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="ceddb-138">CNAME</span></span> | <span data-ttu-id="ceddb-139">sip</span><span class="sxs-lookup"><span data-stu-id="ceddb-139">sip</span></span> | <span data-ttu-id="ceddb-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="ceddb-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="ceddb-141">1 hora</span><span class="sxs-lookup"><span data-stu-id="ceddb-141">1 Hour</span></span> |
| <span data-ttu-id="ceddb-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="ceddb-142">CNAME</span></span> | <span data-ttu-id="ceddb-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ceddb-143">lyncdiscover</span></span> | <span data-ttu-id="ceddb-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="ceddb-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="ceddb-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ceddb-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="ceddb-146">Registros SRV</span><span class="sxs-lookup"><span data-stu-id="ceddb-146">SRV records</span></span>

| <span data-ttu-id="ceddb-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="ceddb-147">Type</span></span> | <span data-ttu-id="ceddb-148">Servicio</span><span class="sxs-lookup"><span data-stu-id="ceddb-148">Service</span></span> | <span data-ttu-id="ceddb-149">Protocolo</span><span class="sxs-lookup"><span data-stu-id="ceddb-149">Protocol</span></span> | <span data-ttu-id="ceddb-150">Puerto</span><span class="sxs-lookup"><span data-stu-id="ceddb-150">Port</span></span> | <span data-ttu-id="ceddb-151">Peso</span><span class="sxs-lookup"><span data-stu-id="ceddb-151">Weight</span></span> | <span data-ttu-id="ceddb-152">Priority</span><span class="sxs-lookup"><span data-stu-id="ceddb-152">Priority</span></span> | <span data-ttu-id="ceddb-153">Nombre</span><span class="sxs-lookup"><span data-stu-id="ceddb-153">Name</span></span> | <span data-ttu-id="ceddb-154">Target</span><span class="sxs-lookup"><span data-stu-id="ceddb-154">Target</span></span> | <span data-ttu-id="ceddb-155">TTL</span><span class="sxs-lookup"><span data-stu-id="ceddb-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="ceddb-156">SRV</span><span class="sxs-lookup"><span data-stu-id="ceddb-156">SRV</span></span> | <span data-ttu-id="ceddb-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="ceddb-157">\_sip</span></span> | <span data-ttu-id="ceddb-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="ceddb-158">\_tls</span></span> | <span data-ttu-id="ceddb-159">443</span><span class="sxs-lookup"><span data-stu-id="ceddb-159">443</span></span> | <span data-ttu-id="ceddb-160">1 </span><span class="sxs-lookup"><span data-stu-id="ceddb-160">1</span></span> | <span data-ttu-id="ceddb-161">100</span><span class="sxs-lookup"><span data-stu-id="ceddb-161">100</span></span> | @ | <span data-ttu-id="ceddb-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="ceddb-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="ceddb-163">1 hora</span><span class="sxs-lookup"><span data-stu-id="ceddb-163">1 Hour</span></span> |
| <span data-ttu-id="ceddb-164">SRV</span><span class="sxs-lookup"><span data-stu-id="ceddb-164">SRV</span></span> | <span data-ttu-id="ceddb-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ceddb-165">\_sipfederationtls</span></span> | <span data-ttu-id="ceddb-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="ceddb-166">\_tcp</span></span> | <span data-ttu-id="ceddb-167">5061</span><span class="sxs-lookup"><span data-stu-id="ceddb-167">5061</span></span> | <span data-ttu-id="ceddb-168">1 </span><span class="sxs-lookup"><span data-stu-id="ceddb-168">1</span></span> | <span data-ttu-id="ceddb-169">100</span><span class="sxs-lookup"><span data-stu-id="ceddb-169">100</span></span> | @ | <span data-ttu-id="ceddb-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="ceddb-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="ceddb-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ceddb-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="ceddb-172">Registros DNS adicionales</span><span class="sxs-lookup"><span data-stu-id="ceddb-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ceddb-173">Si tiene un registro *CNAME msoid* existente en  la zona DNS, debe quitar el registro de DNS en este momento.</span><span class="sxs-lookup"><span data-stu-id="ceddb-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="ceddb-174">El registro msoid es incompatible con Aplicaciones de Microsoft 365 Enterprise *(anteriormente Office 365 ProPlus)* y evitará que la activación se haga correctamente.</span><span class="sxs-lookup"><span data-stu-id="ceddb-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
