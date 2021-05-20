---
title: Recopilar la información que necesita para crear registros DNS
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Recopila los valores/información que necesita para crear registros DNS para conectar su dominio a su Microsoft 365 suscripción.
ms.openlocfilehash: c8ff30c27e67c8a29b7122ea80a6a33f0594b1b9
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582961"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="5e1ac-103">Recopilar la información que necesita para crear registros DNS</span><span class="sxs-lookup"><span data-stu-id="5e1ac-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="5e1ac-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="5e1ac-105">Paso 1: Buscar el valor del registro TXT y comprobar</span><span class="sxs-lookup"><span data-stu-id="5e1ac-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5e1ac-106">En el centro Microsoft 365 administración, vaya a la página **Dominios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">de instalación.</a></span><span class="sxs-lookup"><span data-stu-id="5e1ac-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5e1ac-107">En el Centro de administración, vaya a la página **Dominios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">de</a> instalación.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5e1ac-108">En el Centro de administración, vaya a la página **Dominios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">de</a> instalación.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="5e1ac-109">En la **página Dominios,** seleccione el dominio y, a continuación, **seleccione Iniciar instalación.**</span><span class="sxs-lookup"><span data-stu-id="5e1ac-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="5e1ac-110">Volverá al asistente de configuración de dominios para ver el valor específico que debe agregar.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="5e1ac-111">En la **página Comprobar dominio,** seleccione **Agregar un registro TXT** en su lugar y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="5e1ac-112">Copie el **valor TXT que se** muestra.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="5e1ac-113">Tiene el siguiente aspecto: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="5e1ac-114">Vaya a [Crear registros DNS en cualquier proveedor](create-dns-records-at-any-dns-hosting-provider.md)de hospedaje DNS y seleccione el host DNS de la lista de registradores para ver las instrucciones paso a paso.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="5e1ac-115">Siga los pasos para crear el registro TXT (o registro MX) en el host DNS y, a continuación, compruebe el dominio de nuevo en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="5e1ac-116">Quite el registro TXT (o registro MX) del host DNS una vez comprobado el dominio en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="5e1ac-117">Paso 2: Buscar el valor del registro MX para el correo electrónico y mucho más</span><span class="sxs-lookup"><span data-stu-id="5e1ac-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5e1ac-118">En el centro Microsoft 365 administración, vaya a la página **Dominios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">de instalación.</a></span><span class="sxs-lookup"><span data-stu-id="5e1ac-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="5e1ac-119">En el Centro de administración, vaya a la página **Dominios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">de</a> instalación.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5e1ac-120">En el Centro de administración, vaya a la página **Dominios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">de</a> instalación.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="5e1ac-121">En la página **Dominios**, seleccione su dominio.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="5e1ac-122">En **Configuración DNS requerida**, verá los registros DNS para agregar.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="5e1ac-123">Querrá mantener esta información disponible mientras realiza cambios en su host DNS, para poder copiar y pegar los valores.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="5e1ac-124">Los grupos de registros DNS que aparecen en esta página varían en función de las opciones que se seleccionan en **Finalidad del dominio**.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="5e1ac-125">Vaya a Crear registros DNS en cualquier proveedor de hospedaje [DNS](create-dns-records-at-any-dns-hosting-provider.md)y, a continuación, seleccione el host DNS de la lista de registradores para ver instrucciones paso a paso para agregar registros en el sitio web del host DNS.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="5e1ac-126">Si el host DNS no tiene un vínculo en la página, puede seguir las instrucciones generales.</span><span class="sxs-lookup"><span data-stu-id="5e1ac-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="5e1ac-127">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="5e1ac-127">Related content</span></span>

<span data-ttu-id="5e1ac-128">[Preguntas más frecuentes sobre](../setup/domains-faq.yml) dominios (artículo)</span><span class="sxs-lookup"><span data-stu-id="5e1ac-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

<span data-ttu-id="5e1ac-129">[Buscar y corregir problemas después de agregar el dominio o los registros DNS](find-and-fix-issues.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="5e1ac-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>

<span data-ttu-id="5e1ac-130">[Administrar dominios](index.yml) (página de vínculo)</span><span class="sxs-lookup"><span data-stu-id="5e1ac-130">[Manage domains](index.yml) (link page)</span></span>