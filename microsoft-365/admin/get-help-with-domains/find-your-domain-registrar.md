---
title: Buscar el registrador de dominios para Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Aprenda a encontrar su registrador de dominios y su proveedor de host DNS utilizando la búsqueda InterNIC.
ms.openlocfilehash: 71af74a0f94f2cdc251dab78fd59e9bdd90da5ce
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210397"
---
# <a name="find-your-domain-registrar-for-office-365"></a><span data-ttu-id="6c5e6-103">Buscar el registrador de dominios para Office 365</span><span class="sxs-lookup"><span data-stu-id="6c5e6-103">Find your domain registrar for Office 365</span></span>

 <span data-ttu-id="6c5e6-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="6c5e6-105">Registrador de dominios</span><span class="sxs-lookup"><span data-stu-id="6c5e6-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="6c5e6-106">Buscar el registrador de nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="6c5e6-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="6c5e6-107">Solo los dominios que terminen en *.COM*, *.NET* y *.EDU* funcionarán con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="6c5e6-108">En la página [búsqueda de InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), en el cuadro **Búsqueda de Whois**, escriba el nombre de su dominio.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="6c5e6-109">Por ejemplo, *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="6c5e6-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="6c5e6-110">Seleccione la opción **Dominio** y, a continuación, seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="6c5e6-111">En la página **Whois Search Results** (Resultados de la búsqueda de Whois), busque la entrada **Registrar** (Registrador).</span><span class="sxs-lookup"><span data-stu-id="6c5e6-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="6c5e6-112">En esta entrada se indica la organización que proporciona el servicio de registrador para su dominio.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="6c5e6-113">Proveedor de host DNS</span><span class="sxs-lookup"><span data-stu-id="6c5e6-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="6c5e6-114">Buscar su proveedor de host DNS</span><span class="sxs-lookup"><span data-stu-id="6c5e6-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="6c5e6-115">Solo los dominios que terminen en *.COM*, *.NET* y *.EDU* funcionarán con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="6c5e6-116">En la página [búsqueda de InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), en el cuadro **Búsqueda de Whois**, escriba el nombre de su dominio.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="6c5e6-117">Por ejemplo, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="6c5e6-118">Seleccione la opción **Dominio** y, a continuación, seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="6c5e6-119">En la página **Whois Search Results** (Resultados de la búsqueda de Whois), busque la primera entrada de **Name Server** (Servidor DNS).</span><span class="sxs-lookup"><span data-stu-id="6c5e6-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="6c5e6-120">Copie la información del servidor DNS que aparece después de los dos puntos (:) y, después, péguela en el cuadro de **búsqueda** que hay en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="6c5e6-121">Seleccione **Nameserver** y, a continuación, seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="6c5e6-p105">En la página **Resultados de la búsqueda de Whois**, busque la entrada **Registrador**, en la que se indica su proveedor de hospedaje de DNS, que es propietario del servidor DNS para su dominio.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

