---
title: Buscar su registrador de dominios
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Aprenda a encontrar su registrador de dominios y su proveedor de host DNS con la búsqueda InterNIC.
ms.openlocfilehash: af883f53c8c45aee2594b0f5b8b9da57e5717f9e
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706399"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="23841-103">Buscar su registrador de dominios</span><span class="sxs-lookup"><span data-stu-id="23841-103">Find your domain registrar</span></span>

 <span data-ttu-id="23841-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="23841-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="23841-105">Registrador de dominios</span><span class="sxs-lookup"><span data-stu-id="23841-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="23841-106">Buscar el registrador de nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="23841-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="23841-107">Solo los dominios que terminen en *.COM*, *.NET* y *.EDU* funcionarán con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="23841-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="23841-p101">En la [página de búsqueda de InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), en el cuadro **Búsqueda de Whois**, escriba el nombre de dominio, por ejemplo,  *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="23841-p101">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="23841-110">Seleccione la opción **Dominio** y, a continuación, seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="23841-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="23841-p102">En la página **Resultados de la búsqueda de Whois**, busque la entrada **Registrador**. En esta entrada se indica la organización que proporciona el servicio de registrador para su dominio.</span><span class="sxs-lookup"><span data-stu-id="23841-p102">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="23841-113">Proveedor de host DNS</span><span class="sxs-lookup"><span data-stu-id="23841-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="23841-114">Buscar su proveedor de host DNS</span><span class="sxs-lookup"><span data-stu-id="23841-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="23841-115">Solo los dominios que terminen en *.COM*, *.NET* y *.EDU* funcionarán con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="23841-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="23841-p103">En la [página de búsqueda de InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), en el cuadro **Búsqueda de Whois**, escriba el nombre de dominio, por ejemplo, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="23841-p103">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="23841-118">Seleccione la opción **Dominio** y, a continuación, seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="23841-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="23841-119">En la página **Whois Search Results** (Resultados de la búsqueda de Whois), busque la primera entrada de **Name Server** (Servidor DNS).</span><span class="sxs-lookup"><span data-stu-id="23841-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="23841-p104">Copie la información de nombre del servidor (NS) que aparece después de los dos puntos (:) y, después, péguela en el cuadro **Buscar** que hay en la parte superior de la página. Seleccione **Servidor de nombre** y, después, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="23841-p104">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="23841-p105">En la página **Resultados de la búsqueda de Whois**, busque la entrada **Registrador**, en la que se indica su proveedor de hospedaje de DNS, que es propietario del servidor DNS para su dominio.</span><span class="sxs-lookup"><span data-stu-id="23841-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

