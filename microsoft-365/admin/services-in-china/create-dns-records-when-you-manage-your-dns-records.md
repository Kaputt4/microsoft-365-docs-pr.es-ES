---
title: Crear registros DNS para Office 365 al administrar los registros DNS
f1.keywords:
- CSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Aprenda a crear registros DNS para Office 365 operado por 21Vianet cuando administre sus registros DNS. '
monikerRange: o365-21vianet
ms.openlocfilehash: c05dc1c84465ea06572021610744f0cbe5aa9fea
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779910"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="48859-103">Crear registros DNS para Office 365 al administrar los registros DNS</span><span class="sxs-lookup"><span data-stu-id="48859-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="48859-104">Para obtener instrucciones detalladas acerca de cómo crear registros DNS para Office 365 operado por 21Vianet, incluido el registro MX necesario para el enrutamiento de correo, vea [crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="48859-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="48859-105">Más opciones y algunas cosas que debe tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="48859-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="48859-106">Si no conoce el proveedor de host DNS o el registrador de dominios de su dominio, vea [Encuentre su registrador de dominios o proveedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="48859-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="48859-107">Para obtener una descripción de lo que hacen los registros DNS, consulte [conceptos básicos de DNS](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="48859-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="48859-108">Algunos proveedores de hospedaje DNS no permiten crear todos los tipos de registro necesarios, lo que provoca [limitaciones de servicio cuando el proveedor de hospedaje no admite SRV, CNAME, txt o redirección](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="48859-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="48859-109">Si su proveedor no admite los registros SRV, TXT o CNAME, le recomendamos que [transfiera su dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) a un [proveedor que admita todos los tipos de registros necesarios](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="48859-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="48859-110">Para ver qué registros DNS son necesarios y buscar los valores que se van a usar para cada registro, incluido el registro MX para el correo electrónico, vea [recopilar la información necesaria para crear los registros DNS de Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span><span class="sxs-lookup"><span data-stu-id="48859-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span> <span data-ttu-id="48859-111">Para obtener una descripción de lo que hacen los registros DNS, consulte [conceptos básicos de DNS](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="48859-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

