---
title: Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Obtenga información sobre cómo enrutar el tráfico a un sitio web público existente hospedado fuera de Office 365, si ha configurado Office 365 para que administre los registros DNS para su dominio personalizado.
ms.openlocfilehash: de95818eea729cb11972faf986c9be40bb6e76da
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255353"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="a88c6-103">Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual</span><span class="sxs-lookup"><span data-stu-id="a88c6-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="a88c6-p101">**Si administra sus registros de Office 365 en su proveedor de host DNS**, no tiene que preocuparse de los pasos de este tema. El sitio web permanece en su ubicación y los usuarios pueden obtener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="a88c6-p101">**If you manage your domain's Office 365 records at your DNS hosting provider**, you don't have to worry about the steps in this topic. Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="a88c6-106">**Si Office 365 administra sus registros DNS**, para redirigir el tráfico a un sitio web público existente hospedado fuera de Office 365, haga lo siguiente después de agregar el dominio a Office 365:</span><span class="sxs-lookup"><span data-stu-id="a88c6-106">**If Office 365 manages your DNS records**, to route traffic to an existing public website hosted outside of Office 365, after you add your domain to Office 365, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a88c6-107">Actualizar registros DNS en el centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a88c6-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="a88c6-108">En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .</span><span class="sxs-lookup"><span data-stu-id="a88c6-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="a88c6-109">En la página **Dominios**, en la lista de dominios, seleccione el que use para su sitio web y, después, **Configuración de DNS** en el panel de administración.</span><span class="sxs-lookup"><span data-stu-id="a88c6-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="a88c6-110">Seleccione **Nuevo registro personalizado** y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a88c6-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="a88c6-111">Como **Tipo DNS**, escriba " **D (Dirección)** ".</span><span class="sxs-lookup"><span data-stu-id="a88c6-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="a88c6-112">Como **Nombre de host o alias**, escriba " **@** ".</span><span class="sxs-lookup"><span data-stu-id="a88c6-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="a88c6-113">Como **Dirección IP**, escriba la dirección IP estática en la que se hospeda actualmente su sitio web (por ejemplo: 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="a88c6-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="a88c6-p102">Esta dirección IP debe ser  *estática*  , no puede ser  *dinámica*  . Consulte al proveedor donde se hospeda el sitio web para asegurarse de que puede obtener una dirección IP estática para su sitio web público.</span><span class="sxs-lookup"><span data-stu-id="a88c6-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="a88c6-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a88c6-116">Select **Save**.</span></span> 
    
<span data-ttu-id="a88c6-117">Además, puede crear un registro CNAME para ayudar a los clientes a encontrar su sitio web.</span><span class="sxs-lookup"><span data-stu-id="a88c6-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="a88c6-118">Seleccione **Nuevo registro personalizado** y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a88c6-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="a88c6-119">Como **Tipo DNS**, escriba " **CNAME (Alias)** ".</span><span class="sxs-lookup"><span data-stu-id="a88c6-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="a88c6-120">Como **Nombre de host o alias**, escriba " **www** ".</span><span class="sxs-lookup"><span data-stu-id="a88c6-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="a88c6-121">Como **Dirección de destino**, escriba el FQDN (nombre de dominio completo) de su sitio web (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a88c6-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="a88c6-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a88c6-122">Select **Save**.</span></span> 
    
<span data-ttu-id="a88c6-123">Por último, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a88c6-123">Finally, do the following:</span></span>
  
<span data-ttu-id="a88c6-124">[Actualice sus registros NS de dominio](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) para que señalen a Office 365.</span><span class="sxs-lookup"><span data-stu-id="a88c6-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Office 365.</span></span> 
  
<span data-ttu-id="a88c6-p103">Cuando los registros NS se hayan actualizado para señalar a Office 365, su dominio estará listo: el correo electrónico se enrutará a Office 365 y el tráfico dirigido a su sitio web seguirá yendo a su proveedor de hospedaje actual.</span><span class="sxs-lookup"><span data-stu-id="a88c6-p103">When the NS records have been updated to point to Office 365, your domain is all set up. Email will be routed to Office 365, and traffic to your website address will continue to go to your current website host.</span></span>
 