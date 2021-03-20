---
title: Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Obtenga información sobre cómo enrutar el tráfico a un sitio web público existente hospedado fuera de Microsoft, si ha establecido Microsoft para administrar registros DNS para su dominio personalizado.
ms.openlocfilehash: ceef82345e562e2aa4c291f416c454fb831ee45b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915979"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="25123-103">Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual</span><span class="sxs-lookup"><span data-stu-id="25123-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="25123-104">**Si administra los registros de Microsoft** de su dominio en su proveedor de hospedaje DNS, no tiene que preocuparse por los pasos descritos en este tema.</span><span class="sxs-lookup"><span data-stu-id="25123-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="25123-105">El sitio web permanece en su ubicación y los usuarios pueden obtener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="25123-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="25123-106">**Si Microsoft administra los** registros DNS , para enrutar el tráfico a un sitio web público existente hospedado fuera de Microsoft, después de agregar el dominio a Microsoft, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25123-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="25123-107">Actualizar registros DNS en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="25123-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="25123-108">En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.</span><span class="sxs-lookup"><span data-stu-id="25123-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="25123-109">En la **página Dominios,** seleccione el dominio y, a continuación, elija **Registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="25123-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="25123-110">En **Configuración dns,** seleccione **Registros personalizados**.</span><span class="sxs-lookup"><span data-stu-id="25123-110">Under **DNS settings**, select **Custom Records**.</span></span>

4. <span data-ttu-id="25123-111">Seleccione **Nuevo registro personalizado** y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25123-111">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="25123-112">Como **Tipo DNS**, escriba " **D (Dirección)** ".</span><span class="sxs-lookup"><span data-stu-id="25123-112">For **DNS type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="25123-113">Como **Nombre de host o alias**, escriba " **@** ".</span><span class="sxs-lookup"><span data-stu-id="25123-113">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="25123-114">Como **Dirección IP**, escriba la dirección IP estática en la que se hospeda actualmente su sitio web (por ejemplo: 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="25123-114">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="25123-p102">Esta dirección IP debe ser  *estática*  , no puede ser  *dinámica*  . Consulte al proveedor donde se hospeda el sitio web para asegurarse de que puede obtener una dirección IP estática para su sitio web público.</span><span class="sxs-lookup"><span data-stu-id="25123-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
5. <span data-ttu-id="25123-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="25123-117">Select **Save**.</span></span> 
    
<span data-ttu-id="25123-118">Además, puede crear un registro CNAME para ayudar a los clientes a encontrar su sitio web.</span><span class="sxs-lookup"><span data-stu-id="25123-118">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="25123-119">Seleccione **Nuevo registro personalizado** y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25123-119">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="25123-120">Como **Tipo DNS**, escriba " **CNAME (Alias)** ".</span><span class="sxs-lookup"><span data-stu-id="25123-120">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="25123-121">Como **Nombre de host o alias**, escriba " **www** ".</span><span class="sxs-lookup"><span data-stu-id="25123-121">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="25123-122">Como **Dirección de destino**, escriba el FQDN (nombre de dominio completo) de su sitio web (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="25123-122">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="25123-123">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="25123-123">Select **Save**.</span></span> 
    
<span data-ttu-id="25123-124">Por último, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25123-124">Finally, do the following:</span></span>
  
<span data-ttu-id="25123-125">[Actualice los registros NS de su dominio](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para que apunten a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25123-125">[Update your domain's NS records](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to point to Microsoft.</span></span> 
  
<span data-ttu-id="25123-126">Cuando los registros NS se hayan actualizado para que apunten a Microsoft, el dominio está configurado.</span><span class="sxs-lookup"><span data-stu-id="25123-126">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="25123-127">El correo electrónico se enruta a Microsoft y el tráfico a la dirección de su sitio web continuará en el host del sitio web actual.</span><span class="sxs-lookup"><span data-stu-id="25123-127">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
