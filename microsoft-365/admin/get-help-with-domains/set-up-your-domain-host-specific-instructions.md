---
title: Configurar su dominio (instrucciones específicas del host)
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
- Adm_TOC
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Obtenga información sobre cómo administrar sus propios registros DNS o dejar que Office 365 administre los registros DNS por usted.
ms.custom: okr_smb
ms.openlocfilehash: 2313aa6c629c76a852e38b4da9093576a3b75d6e
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255081"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="5eb16-103">Configurar su dominio (instrucciones específicas del host)</span><span class="sxs-lookup"><span data-stu-id="5eb16-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="5eb16-104">Para empezar a usar un dominio personalizado (contoso.com) con Office 365, debe comprobar el dominio y configurar los registros DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="5eb16-104">To start using a custom domain (contoso.com) with Office 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="5eb16-105">Puede Agregar y administrar registros DNS con las herramientas administrativas en su host de dominio o dar control de Office 365 a sus registros de dominio y los configuraremos para usted.</span><span class="sxs-lookup"><span data-stu-id="5eb16-105">You can add and manage DNS records using the administrative tools at your domain host, or give Office 365 control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="5eb16-106">Seleccione su host de dominio a continuación para conocer los pasos exactos.</span><span class="sxs-lookup"><span data-stu-id="5eb16-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="5eb16-107">Si no está seguro de quién es su host, consulte [Buscar el registrador de dominios](find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="5eb16-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-office-365-manage-your-dns-records"></a><span data-ttu-id="5eb16-108">Permitir que Office 365 administre los registros DNS</span><span class="sxs-lookup"><span data-stu-id="5eb16-108">Let Office 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="5eb16-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="5eb16-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="5eb16-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="5eb16-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="5eb16-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="5eb16-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="5eb16-112">Dominios de Google</span><span class="sxs-lookup"><span data-stu-id="5eb16-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="5eb16-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="5eb16-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="5eb16-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="5eb16-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="5eb16-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="5eb16-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="5eb16-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="5eb16-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="5eb16-117">O bien, obtenga información sobre cómo [cambiar los servidores de nombres para configurar Office 365 con cualquier registrador de dominios](change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="5eb16-117">Or, learn how to [change nameservers to set up Office 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="5eb16-118">Administrar sus propios registros DNS</span><span class="sxs-lookup"><span data-stu-id="5eb16-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="5eb16-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="5eb16-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="5eb16-120">Coloque</span><span class="sxs-lookup"><span data-stu-id="5eb16-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="5eb16-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="5eb16-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="5eb16-122">Administrado por Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="5eb16-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="5eb16-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="5eb16-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="5eb16-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="5eb16-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="5eb16-125">Zonas DNS de Azure</span><span class="sxs-lookup"><span data-stu-id="5eb16-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="5eb16-126">name.com</span><span class="sxs-lookup"><span data-stu-id="5eb16-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="5eb16-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="5eb16-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="5eb16-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="5eb16-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="5eb16-129">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="5eb16-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="5eb16-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="5eb16-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="5eb16-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="5eb16-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="5eb16-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="5eb16-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="5eb16-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="5eb16-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="5eb16-134">Soluciones de red</span><span class="sxs-lookup"><span data-stu-id="5eb16-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="5eb16-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="5eb16-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="5eb16-136">OVH</span><span class="sxs-lookup"><span data-stu-id="5eb16-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="5eb16-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="5eb16-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="5eb16-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="5eb16-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="5eb16-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="5eb16-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="5eb16-140">Register365 para Office 365</span><span class="sxs-lookup"><span data-stu-id="5eb16-140">Register365 for Office 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="5eb16-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="5eb16-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="5eb16-142">web.com</span><span class="sxs-lookup"><span data-stu-id="5eb16-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="5eb16-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="5eb16-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="5eb16-144">DNS basado en Windows</span><span class="sxs-lookup"><span data-stu-id="5eb16-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="5eb16-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="5eb16-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="5eb16-146">Wix</span><span class="sxs-lookup"><span data-stu-id="5eb16-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="5eb16-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="5eb16-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="5eb16-148">Yahoo!   Pequeña empresa</span><span class="sxs-lookup"><span data-stu-id="5eb16-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="5eb16-149">Necesito instrucciones generales porque mi host de dominio no está en esta lista.</span><span class="sxs-lookup"><span data-stu-id="5eb16-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   