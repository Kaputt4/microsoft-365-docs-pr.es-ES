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
ms.openlocfilehash: def9fbe201e158f1e071a67caeaf29ed26732f97
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256848"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="a666e-103">Recopilar la información que necesita para crear registros DNS</span><span class="sxs-lookup"><span data-stu-id="a666e-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="a666e-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="a666e-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="a666e-105">Paso 1: Buscar el valor del registro TXT y comprobar</span><span class="sxs-lookup"><span data-stu-id="a666e-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a666e-106">En el Centro de administración de Microsoft 365, vaya a la **página Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios.</a></span><span class="sxs-lookup"><span data-stu-id="a666e-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a666e-107">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="a666e-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a666e-108">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="a666e-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="a666e-109">En la **página Dominios,** seleccione el dominio y, a continuación, **seleccione Iniciar instalación.**</span><span class="sxs-lookup"><span data-stu-id="a666e-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="a666e-110">Volverá al asistente de configuración de dominios para ver el valor específico que debe agregar.</span><span class="sxs-lookup"><span data-stu-id="a666e-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="a666e-111">En la **página Comprobación de dominio,** seleccione Agregar un registro **TXT a los** registros DNS del dominio y, a continuación, **seleccione Continuar**.</span><span class="sxs-lookup"><span data-stu-id="a666e-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="a666e-112">Copie el **valor TXT que se** muestra.</span><span class="sxs-lookup"><span data-stu-id="a666e-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="a666e-113">Tiene el siguiente aspecto: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="a666e-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="a666e-114">Vaya a [Agregar registros DNS para conectar el dominio](create-dns-records-at-any-dns-hosting-provider.md)y siga los pasos para agregar registros en el sitio web del host DNS.</span><span class="sxs-lookup"><span data-stu-id="a666e-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="a666e-115">Siga los pasos para crear el registro TXT (o registro MX) en el host DNS y, a continuación, compruebe el dominio de nuevo en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a666e-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="a666e-116">Quite el registro TXT (o registro MX) del host DNS una vez comprobado el dominio en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a666e-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="a666e-117">Paso 2: Buscar el valor del registro MX para el correo electrónico y mucho más</span><span class="sxs-lookup"><span data-stu-id="a666e-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a666e-118">En el Centro de administración de Microsoft 365, vaya a la **página Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios.</a></span><span class="sxs-lookup"><span data-stu-id="a666e-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="a666e-119">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="a666e-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a666e-120">En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="a666e-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="a666e-121">En la página **Dominios**, seleccione su dominio.</span><span class="sxs-lookup"><span data-stu-id="a666e-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="a666e-122">Elija **Administrar DNS,** **seleccione Más opciones Agregar** su propio DNS y seleccione Continuar para ver los registros DNS que se  >   agregarán. </span><span class="sxs-lookup"><span data-stu-id="a666e-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="a666e-123">Querrá mantener esta información disponible mientras realiza cambios en su host DNS, para poder copiar y pegar los valores.</span><span class="sxs-lookup"><span data-stu-id="a666e-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="a666e-124">Los grupos de registros DNS que aparecen en esta página varían en función de las opciones que se seleccionan en **Finalidad del dominio**.</span><span class="sxs-lookup"><span data-stu-id="a666e-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="a666e-125">Vaya a [Agregar registros DNS para conectar el dominio](create-dns-records-at-any-dns-hosting-provider.md)y siga los pasos para agregar registros en el sitio web del host DNS.</span><span class="sxs-lookup"><span data-stu-id="a666e-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="a666e-126">Si el host DNS no tiene un vínculo en la página, puede seguir las instrucciones generales.</span><span class="sxs-lookup"><span data-stu-id="a666e-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="a666e-127">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="a666e-127">Related content</span></span>

<span data-ttu-id="a666e-128">[Preguntas más frecuentes sobre dominios](../setup/domains-faq.yml) (artículo)</span><span class="sxs-lookup"><span data-stu-id="a666e-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="a666e-129">[Buscar y corregir problemas después de agregar el dominio o los registros DNS](find-and-fix-issues.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="a666e-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="a666e-130">[Administrar dominios](index.yml) (página de vínculo)</span><span class="sxs-lookup"><span data-stu-id="a666e-130">[Manage domains](index.yml) (link page)</span></span>