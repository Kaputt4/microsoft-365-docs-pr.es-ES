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
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="9d4eb-103">Registros DNS para Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="9d4eb-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="9d4eb-104">*Este artículo se aplica a Office 365 DoD y Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="9d4eb-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="9d4eb-105">Como parte de la incorporación a Office 365 DoD, deberá agregar los dominios SMTP y SIP al inquilino de Servicios en línea.</span><span class="sxs-lookup"><span data-stu-id="9d4eb-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="9d4eb-106">Para ello, use el cmdlet New-MsolDomain en PowerShell de Azure AD o use [Azure Government Portal](https://portal.azure.us) para iniciar el proceso de agregar el dominio y probar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9d4eb-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="9d4eb-107">Una vez que haya agregado los dominios al inquilino y validado, use las siguientes instrucciones para agregar los registros DNS adecuados para los servicios siguientes.</span><span class="sxs-lookup"><span data-stu-id="9d4eb-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="9d4eb-108">Es posible que deba modificar la tabla siguiente para que se ajuste a las necesidades de su organización con respecto a los registros MX entrantes y los registros de detección automática de Exchange existentes que tenga en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9d4eb-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="9d4eb-109">Recomendamos encarecidamente coordinar estos registros DNS con el equipo de mensajería para evitar interrupciones o entregas erróneas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9d4eb-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="9d4eb-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9d4eb-110">Exchange Online</span></span>

| <span data-ttu-id="9d4eb-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="9d4eb-111">Type</span></span> | <span data-ttu-id="9d4eb-112">Prioridad</span><span class="sxs-lookup"><span data-stu-id="9d4eb-112">Priority</span></span> | <span data-ttu-id="9d4eb-113">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="9d4eb-113">Host name</span></span> | <span data-ttu-id="9d4eb-114">Apuntar a dirección o valor</span><span class="sxs-lookup"><span data-stu-id="9d4eb-114">Points to address or value</span></span> | <span data-ttu-id="9d4eb-115">TTL</span><span class="sxs-lookup"><span data-stu-id="9d4eb-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="9d4eb-116">MX</span><span class="sxs-lookup"><span data-stu-id="9d4eb-116">MX</span></span> | <span data-ttu-id="9d4eb-117">0</span><span class="sxs-lookup"><span data-stu-id="9d4eb-117">0</span></span> | @ | <span data-ttu-id="9d4eb-118">*tenant*.mail.protection.office365.us (vea más adelante para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="9d4eb-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="9d4eb-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9d4eb-119">1 Hour</span></span> |
| <span data-ttu-id="9d4eb-120">TXT</span><span class="sxs-lookup"><span data-stu-id="9d4eb-120">TXT</span></span> | - | @ | <span data-ttu-id="9d4eb-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="9d4eb-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="9d4eb-122">1 hora</span><span class="sxs-lookup"><span data-stu-id="9d4eb-122">1 Hour</span></span> |
| <span data-ttu-id="9d4eb-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="9d4eb-123">CNAME</span></span> | - | <span data-ttu-id="9d4eb-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9d4eb-124">autodiscover</span></span> | <span data-ttu-id="9d4eb-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="9d4eb-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="9d4eb-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9d4eb-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="9d4eb-127">Exchange Registro de detección automática</span><span class="sxs-lookup"><span data-stu-id="9d4eb-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="9d4eb-128">Si ha Exchange Server local, se recomienda dejar el registro existente en su lugar mientras migra a Exchange Online y actualizar ese registro una vez que haya completado la migración.</span><span class="sxs-lookup"><span data-stu-id="9d4eb-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="9d4eb-129">Exchange Online Registro MX</span><span class="sxs-lookup"><span data-stu-id="9d4eb-129">Exchange Online MX Record</span></span>

<span data-ttu-id="9d4eb-130">El valor de registro MX para los dominios aceptados sigue un formato estándar  como se mencionó anteriormente: *inquilino*.mail.protection.office365.us, reemplazando el espacio empresarial por la primera parte del nombre de inquilino predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9d4eb-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="9d4eb-131">Por ejemplo, si el nombre del espacio empresarial contoso.onmicrosoft.us, usaría contoso.mail.protection.office365.us **como** valor para el registro MX.</span><span class="sxs-lookup"><span data-stu-id="9d4eb-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="9d4eb-132">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="9d4eb-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="9d4eb-133">Registros CNAME</span><span class="sxs-lookup"><span data-stu-id="9d4eb-133">CNAME records</span></span>

| <span data-ttu-id="9d4eb-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="9d4eb-134">Type</span></span> | <span data-ttu-id="9d4eb-135">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="9d4eb-135">Host name</span></span> | <span data-ttu-id="9d4eb-136">Apuntar a dirección o valor</span><span class="sxs-lookup"><span data-stu-id="9d4eb-136">Points to address or value</span></span> | <span data-ttu-id="9d4eb-137">TTL</span><span class="sxs-lookup"><span data-stu-id="9d4eb-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="9d4eb-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="9d4eb-138">CNAME</span></span> | <span data-ttu-id="9d4eb-139">sip</span><span class="sxs-lookup"><span data-stu-id="9d4eb-139">sip</span></span> | <span data-ttu-id="9d4eb-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="9d4eb-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="9d4eb-141">1 hora</span><span class="sxs-lookup"><span data-stu-id="9d4eb-141">1 Hour</span></span> |
| <span data-ttu-id="9d4eb-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="9d4eb-142">CNAME</span></span> | <span data-ttu-id="9d4eb-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9d4eb-143">lyncdiscover</span></span> | <span data-ttu-id="9d4eb-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="9d4eb-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="9d4eb-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9d4eb-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="9d4eb-146">Registros SRV</span><span class="sxs-lookup"><span data-stu-id="9d4eb-146">SRV records</span></span>

| <span data-ttu-id="9d4eb-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="9d4eb-147">Type</span></span> | <span data-ttu-id="9d4eb-148">Servicio</span><span class="sxs-lookup"><span data-stu-id="9d4eb-148">Service</span></span> | <span data-ttu-id="9d4eb-149">Protocolo</span><span class="sxs-lookup"><span data-stu-id="9d4eb-149">Protocol</span></span> | <span data-ttu-id="9d4eb-150">Puerto</span><span class="sxs-lookup"><span data-stu-id="9d4eb-150">Port</span></span> | <span data-ttu-id="9d4eb-151">Peso</span><span class="sxs-lookup"><span data-stu-id="9d4eb-151">Weight</span></span> | <span data-ttu-id="9d4eb-152">Prioridad</span><span class="sxs-lookup"><span data-stu-id="9d4eb-152">Priority</span></span> | <span data-ttu-id="9d4eb-153">Nombre</span><span class="sxs-lookup"><span data-stu-id="9d4eb-153">Name</span></span> | <span data-ttu-id="9d4eb-154">Target</span><span class="sxs-lookup"><span data-stu-id="9d4eb-154">Target</span></span> | <span data-ttu-id="9d4eb-155">TTL</span><span class="sxs-lookup"><span data-stu-id="9d4eb-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="9d4eb-156">SRV</span><span class="sxs-lookup"><span data-stu-id="9d4eb-156">SRV</span></span> | <span data-ttu-id="9d4eb-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="9d4eb-157">\_sip</span></span> | <span data-ttu-id="9d4eb-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="9d4eb-158">\_tls</span></span> | <span data-ttu-id="9d4eb-159">443</span><span class="sxs-lookup"><span data-stu-id="9d4eb-159">443</span></span> | <span data-ttu-id="9d4eb-160">1</span><span class="sxs-lookup"><span data-stu-id="9d4eb-160">1</span></span> | <span data-ttu-id="9d4eb-161">100</span><span class="sxs-lookup"><span data-stu-id="9d4eb-161">100</span></span> | @ | <span data-ttu-id="9d4eb-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="9d4eb-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="9d4eb-163">1 hora</span><span class="sxs-lookup"><span data-stu-id="9d4eb-163">1 Hour</span></span> |
| <span data-ttu-id="9d4eb-164">SRV</span><span class="sxs-lookup"><span data-stu-id="9d4eb-164">SRV</span></span> | <span data-ttu-id="9d4eb-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9d4eb-165">\_sipfederationtls</span></span> | <span data-ttu-id="9d4eb-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="9d4eb-166">\_tcp</span></span> | <span data-ttu-id="9d4eb-167">5061</span><span class="sxs-lookup"><span data-stu-id="9d4eb-167">5061</span></span> | <span data-ttu-id="9d4eb-168">1</span><span class="sxs-lookup"><span data-stu-id="9d4eb-168">1</span></span> | <span data-ttu-id="9d4eb-169">100</span><span class="sxs-lookup"><span data-stu-id="9d4eb-169">100</span></span> | @ | <span data-ttu-id="9d4eb-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="9d4eb-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="9d4eb-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9d4eb-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="9d4eb-172">Registros DNS adicionales</span><span class="sxs-lookup"><span data-stu-id="9d4eb-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d4eb-173">Si tiene un registro *CNAME msoid* existente en la zona DNS, debe quitar **el** registro de DNS en este momento.</span><span class="sxs-lookup"><span data-stu-id="9d4eb-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="9d4eb-174">El registro msoid es incompatible con Microsoft 365 Enterprise Apps *(anteriormente Office 365 ProPlus)* y evitará que la activación se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="9d4eb-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
