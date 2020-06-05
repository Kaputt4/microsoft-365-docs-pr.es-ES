---
title: Usar la búsqueda de contenido para buscar datos importados de terceros
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Use la herramienta de búsqueda de contenido eDiscovery para buscar elementos importados a los buzones en Microsoft 365 desde un origen de datos de terceros. Puede crear una consulta para buscar todos los elementos importados o crear una consulta para buscar determinados tipos de datos de terceros. En este artículo se enumeran los valores que se pueden usar en una consulta de palabras clave para buscar en los tipos de datos de terceros que se pueden importar a Microsoft 365.
ms.openlocfilehash: ab693ff8e2283e201b9d573e68f4bdfb9f859749
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564973"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="be548-105">Usar la búsqueda de contenido para buscar datos de terceros importados por un conector de asociado personalizado</span><span class="sxs-lookup"><span data-stu-id="be548-105">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="be548-106">Puede usar la [herramienta de búsqueda de contenido eDiscovery](content-search.md) en el centro de seguridad & cumplimiento para buscar elementos importados a los buzones en Microsoft 365 desde un origen de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="be548-106">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="be548-107">Puede crear una consulta para buscar en todos los elementos de datos de terceros importados o puede crear una consulta para buscar elementos de datos de terceros específicos.</span><span class="sxs-lookup"><span data-stu-id="be548-107">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="be548-108">Además, también puede crear una directiva de retención basada en consultas o una retención de exhibición de documentos electrónicos basada en consultas para conservar los datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="be548-108">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="be548-109">Para obtener más información sobre cómo trabajar con un partner para importar datos de terceros y una lista de los tipos de datos de terceros que puede importar a Microsoft 365, vea [trabajar con un partner para archivar datos de terceros en Office 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="be548-109">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be548-110">Las instrucciones de este artículo solo se aplican a los datos de terceros importados por un conector de socio personalizado.</span><span class="sxs-lookup"><span data-stu-id="be548-110">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="be548-111">Este artículo no se aplica a los datos de terceros que se importan mediante [conectores de datos de terceros](archiving-third-party-data.md#third-party-data-connectors) en el centro de cumplimiento de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="be548-111">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="be548-112">Crear una consulta para buscar en todos los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="be548-112">Creating a query to search all third-party data</span></span>

<span data-ttu-id="be548-113">Para buscar (o poner en espera) cualquier tipo de datos de terceros que haya importado a Office 365, puede usar el `kind:externaldata` par propiedad-valor del mensaje en el cuadro palabra clave para una búsqueda de contenido o al crear una suspensión basada en consulta.</span><span class="sxs-lookup"><span data-stu-id="be548-113">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="be548-114">Por ejemplo, para buscar elementos importados de cualquier origen de datos de terceros y que contengan la palabra "Contoso" en la propiedad Subject del elemento importado, debe utilizar la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="be548-114">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="be548-115">En el ejemplo anterior de consulta de palabra clave se incluye la propiedad Subject.</span><span class="sxs-lookup"><span data-stu-id="be548-115">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="be548-116">Para obtener una lista de otras propiedades de elementos de datos de terceros que pueden incluirse en una consulta de palabras clave, vea la sección "más información" en [trabajar con un partner para archivar datos de terceros en Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span><span class="sxs-lookup"><span data-stu-id="be548-116">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="be548-117">Al crear consultas para buscar y conservar datos de terceros, también puede usar las condiciones para restringir los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="be548-117">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="be548-118">Para obtener más información acerca de la creación de consultas de búsqueda de contenido, vea [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="be548-118">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="be548-119">Crear una consulta para buscar tipos específicos de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="be548-119">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="be548-120">En lugar de buscar en todos los tipos de datos de terceros, puede crear consultas que solo busquen un tipo especificado de datos de terceros mediante el siguiente mensaje de propiedad de mensaje *: valor* en el cuadro de palabras clave para una búsqueda de contenido:</span><span class="sxs-lookup"><span data-stu-id="be548-120">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property:value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="be548-121">Por ejemplo, para buscar datos de Facebook que contengan la palabra "Contoso" en la propiedad Subject, debe usar la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="be548-121">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="be548-122">En la siguiente tabla se enumeran los tipos de datos de terceros que se pueden buscar y el valor que se debe usar para la `itemclass:` propiedad Message para buscar específicamente ese tipo de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="be548-122">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="be548-123">La sintaxis de consulta no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="be548-123">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="be548-124">**Tipo de datos de terceros**</span><span class="sxs-lookup"><span data-stu-id="be548-124">**Third-party data type**</span></span>|<span data-ttu-id="be548-125">**Valor de la `itemclass:` propiedad**</span><span class="sxs-lookup"><span data-stu-id="be548-125">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be548-126">APUNTA</span><span class="sxs-lookup"><span data-stu-id="be548-126">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="be548-127">American Idol</span><span class="sxs-lookup"><span data-stu-id="be548-127">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="be548-128">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="be548-128">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="be548-129">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="be548-129">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="be548-130">Áreas</span><span class="sxs-lookup"><span data-stu-id="be548-130">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="be548-131">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="be548-131">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="be548-132">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="be548-132">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="be548-133">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="be548-133">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="be548-134">Marcador de posición de AXS</span><span class="sxs-lookup"><span data-stu-id="be548-134">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="be548-135">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="be548-135">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="be548-136">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="be548-136">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="be548-137">Bearshare</span><span class="sxs-lookup"><span data-stu-id="be548-137">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="be548-138">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="be548-138">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="be548-139">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="be548-139">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="be548-140">Registros de llamadas de BlackBerry</span><span class="sxs-lookup"><span data-stu-id="be548-140">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="be548-141">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="be548-141">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="be548-142">PIN BlackBerry</span><span class="sxs-lookup"><span data-stu-id="be548-142">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="be548-143">SMS de BlackBerry</span><span class="sxs-lookup"><span data-stu-id="be548-143">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="be548-144">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="be548-144">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="be548-145">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="be548-145">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="be548-146">Bloomberg Messaging</span><span class="sxs-lookup"><span data-stu-id="be548-146">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="be548-147">Cuadro</span><span class="sxs-lookup"><span data-stu-id="be548-147">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="be548-148">Servidor de presencia de mensajería instantánea de Cisco &amp;</span><span class="sxs-lookup"><span data-stu-id="be548-148">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="be548-149">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="be548-149">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="be548-150">CipherCloud para Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="be548-150">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="be548-151">Conexión directa</span><span class="sxs-lookup"><span data-stu-id="be548-151">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="be548-152">Facebook</span><span class="sxs-lookup"><span data-stu-id="be548-152">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="be548-153">FastTrack</span><span class="sxs-lookup"><span data-stu-id="be548-153">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="be548-154">FXConnect</span><span class="sxs-lookup"><span data-stu-id="be548-154">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="be548-155">Flickr</span><span class="sxs-lookup"><span data-stu-id="be548-155">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="be548-156">Gnutella</span><span class="sxs-lookup"><span data-stu-id="be548-156">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="be548-157">Google +</span><span class="sxs-lookup"><span data-stu-id="be548-157">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="be548-158">Google Talk</span><span class="sxs-lookup"><span data-stu-id="be548-158">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="be548-159">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="be548-159">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="be548-160">HipChat</span><span class="sxs-lookup"><span data-stu-id="be548-160">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="be548-161">Hopster</span><span class="sxs-lookup"><span data-stu-id="be548-161">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="be548-162">HubConnex</span><span class="sxs-lookup"><span data-stu-id="be548-162">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="be548-163">Conexiones IBM</span><span class="sxs-lookup"><span data-stu-id="be548-163">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="be548-164">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="be548-164">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="be548-165">Chat de ICE</span><span class="sxs-lookup"><span data-stu-id="be548-165">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="be548-166">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="be548-166">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="be548-167">Instagram</span><span class="sxs-lookup"><span data-stu-id="be548-167">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="be548-168">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="be548-168">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="be548-169">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="be548-169">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="be548-170">IRC</span><span class="sxs-lookup"><span data-stu-id="be548-170">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="be548-171">Jive</span><span class="sxs-lookup"><span data-stu-id="be548-171">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="be548-172">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="be548-172">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="be548-173">JXTA</span><span class="sxs-lookup"><span data-stu-id="be548-173">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="be548-174">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="be548-174">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="be548-175">MFTP</span><span class="sxs-lookup"><span data-stu-id="be548-175">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="be548-176">Comunicaciones unificadas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="be548-176">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="be548-177">Idea</span><span class="sxs-lookup"><span data-stu-id="be548-177">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="be548-178">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="be548-178">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="be548-179">Fotos</span><span class="sxs-lookup"><span data-stu-id="be548-179">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="be548-180">MySpace</span><span class="sxs-lookup"><span data-stu-id="be548-180">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="be548-181">Subred</span><span class="sxs-lookup"><span data-stu-id="be548-181">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="be548-182">OpenNap</span><span class="sxs-lookup"><span data-stu-id="be548-182">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="be548-183">Pinterest</span><span class="sxs-lookup"><span data-stu-id="be548-183">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="be548-184">Pivot</span><span class="sxs-lookup"><span data-stu-id="be548-184">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="be548-185">QQ</span><span class="sxs-lookup"><span data-stu-id="be548-185">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="be548-186">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="be548-186">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="be548-187">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="be548-187">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="be548-188">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="be548-188">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="be548-189">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="be548-189">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="be548-190">SoftEther</span><span class="sxs-lookup"><span data-stu-id="be548-190">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="be548-191">Squawker</span><span class="sxs-lookup"><span data-stu-id="be548-191">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="be548-192">Symphony</span><span class="sxs-lookup"><span data-stu-id="be548-192">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="be548-193">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="be548-193">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="be548-194">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="be548-194">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="be548-195">Términos</span><span class="sxs-lookup"><span data-stu-id="be548-195">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="be548-196">TTT</span><span class="sxs-lookup"><span data-stu-id="be548-196">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="be548-197">Twitter</span><span class="sxs-lookup"><span data-stu-id="be548-197">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="be548-198">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="be548-198">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="be548-199">Vimeo</span><span class="sxs-lookup"><span data-stu-id="be548-199">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="be548-200">WinMX</span><span class="sxs-lookup"><span data-stu-id="be548-200">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="be548-201">Winny</span><span class="sxs-lookup"><span data-stu-id="be548-201">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="be548-202">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="be548-202">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="be548-203">Yammer</span><span class="sxs-lookup"><span data-stu-id="be548-203">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="be548-204">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="be548-204">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="be548-205">YouTube</span><span class="sxs-lookup"><span data-stu-id="be548-205">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
