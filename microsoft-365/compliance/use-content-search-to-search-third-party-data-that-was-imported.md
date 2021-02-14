---
title: Usar la búsqueda de contenido para buscar datos importados de terceros
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Use la herramienta de exhibición de documentos electrónicos de búsqueda de contenido para buscar elementos importados a buzones en Microsoft 365 desde un origen de datos de terceros mediante la creación de consultas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324576"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="9be60-103">Usar la búsqueda de contenido para buscar datos de terceros importados por un conector de asociado personalizado</span><span class="sxs-lookup"><span data-stu-id="9be60-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="9be60-104">Puede usar la herramienta de [exhibición](content-search.md) de documentos electrónicos de búsqueda de contenido en el Centro de seguridad y cumplimiento de & para buscar elementos importados a buzones en Microsoft 365 desde un origen de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="9be60-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="9be60-105">Puede crear una consulta para buscar en todos los elementos de datos de terceros importados o puede crear una consulta para buscar elementos de datos de terceros específicos.</span><span class="sxs-lookup"><span data-stu-id="9be60-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="9be60-106">Además, también puede crear una directiva de retención basada en consultas o una suspensión de exhibición de documentos electrónicos basada en consultas para conservar datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="9be60-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="9be60-107">Para obtener más información sobre cómo trabajar con un asociado para importar datos de terceros y una lista de los tipos de datos de terceros que puede importar a Microsoft 365, vea Trabajar con un asociado para archivar datos de terceros en [Office 365.](work-with-partner-to-archive-third-party-data.md)</span><span class="sxs-lookup"><span data-stu-id="9be60-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9be60-108">Las instrucciones de este artículo solo se aplican a los datos de terceros importados por un conector de asociado personalizado.</span><span class="sxs-lookup"><span data-stu-id="9be60-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="9be60-109">Este artículo no se aplica a los datos de terceros que se importan mediante conectores de datos de terceros [en](archiving-third-party-data.md#third-party-data-connectors) el Centro de cumplimiento de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9be60-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="9be60-110">Creación de una consulta para buscar en todos los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="9be60-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="9be60-111">Para buscar (o poner en espera) cualquier tipo de datos de terceros que haya importado a Office 365, puede usar el par propiedad-valor del mensaje en el cuadro de palabras clave para una búsqueda de contenido o al crear una retención basada en  `kind:externaldata` consultas.</span><span class="sxs-lookup"><span data-stu-id="9be60-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="9be60-112">Por ejemplo, para buscar elementos importados desde cualquier origen de datos de terceros y contener la palabra "contoso" en la propiedad Subject del elemento importado, debe usar la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="9be60-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="9be60-113">El ejemplo de consulta de palabra clave anterior incluye la propiedad subject.</span><span class="sxs-lookup"><span data-stu-id="9be60-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="9be60-114">Para obtener una lista de otras propiedades para los elementos de datos de terceros que pueden incluirse en una consulta de palabras clave, vea la sección "Más información" en Trabajar con un asociado para archivar datos de terceros en [Office 365.](work-with-partner-to-archive-third-party-data.md#more-information)</span><span class="sxs-lookup"><span data-stu-id="9be60-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="9be60-115">Al crear consultas para buscar y retener datos de terceros, también puede usar condiciones para restringir los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9be60-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="9be60-116">Para obtener más información acerca de la creación de consultas de búsqueda de contenido, vea Consultas de palabras clave y [condiciones de búsqueda para búsqueda de contenido.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="9be60-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="9be60-117">Creación de una consulta para buscar tipos específicos de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="9be60-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="9be60-118">En lugar de buscar en todos los tipos de datos de terceros, puede crear consultas que solo busquen un tipo específico de datos de terceros mediante la siguiente propiedad de *mensaje:* par de valores en el cuadro de palabras clave de una búsqueda de contenido:</span><span class="sxs-lookup"><span data-stu-id="9be60-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property: value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="9be60-119">Por ejemplo, para buscar datos de Facebook que contengan la palabra "contoso" en la propiedad Subject, use la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="9be60-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="9be60-120">En la tabla siguiente se enumeran los tipos de datos de terceros que puede buscar y el valor que se debe usar para la propiedad de mensaje para buscar específicamente ese tipo de datos  `itemclass:` de terceros.</span><span class="sxs-lookup"><span data-stu-id="9be60-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="9be60-121">La sintaxis de consulta no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9be60-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="9be60-122">**Tipo de datos de terceros**</span><span class="sxs-lookup"><span data-stu-id="9be60-122">**Third-party data type**</span></span>|<span data-ttu-id="9be60-123">**Valor de la  `itemclass:` propiedad**</span><span class="sxs-lookup"><span data-stu-id="9be60-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9be60-124">AIM</span><span class="sxs-lookup"><span data-stu-id="9be60-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="9be60-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="9be60-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="9be60-126">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="9be60-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="9be60-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="9be60-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="9be60-128">Ares</span><span class="sxs-lookup"><span data-stu-id="9be60-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="9be60-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="9be60-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="9be60-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="9be60-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="9be60-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="9be60-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="9be60-132">Marcador de posición de ejes</span><span class="sxs-lookup"><span data-stu-id="9be60-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="9be60-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="9be60-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="9be60-134">Voice desaprobado</span><span class="sxs-lookup"><span data-stu-id="9be60-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="9be60-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="9be60-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="9be60-136">Bit Magnet</span><span class="sxs-lookup"><span data-stu-id="9be60-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="9be60-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="9be60-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="9be60-138">Registros de llamadas de BlackBerry</span><span class="sxs-lookup"><span data-stu-id="9be60-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="9be60-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="9be60-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="9be60-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="9be60-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="9be60-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="9be60-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="9be60-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="9be60-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="9be60-143">Mensaje de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="9be60-143">Bloomberg Message</span></span>  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|<span data-ttu-id="9be60-144">Mensajes de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="9be60-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="9be60-145">Box</span><span class="sxs-lookup"><span data-stu-id="9be60-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="9be60-146">Servidor de presencia de mensajería instantánea de Cisco &amp;</span><span class="sxs-lookup"><span data-stu-id="9be60-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="9be60-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="9be60-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="9be60-148">CipherCloud para Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="9be60-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="9be60-149">Conexión directa</span><span class="sxs-lookup"><span data-stu-id="9be60-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="9be60-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="9be60-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="9be60-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="9be60-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="9be60-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="9be60-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="9be60-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="9be60-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="9be60-154">Dialecto</span><span class="sxs-lookup"><span data-stu-id="9be60-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="9be60-155">Google+</span><span class="sxs-lookup"><span data-stu-id="9be60-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="9be60-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="9be60-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="9be60-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="9be60-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="9be60-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="9be60-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="9be60-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="9be60-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="9be60-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="9be60-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="9be60-161">IBM Connections</span><span class="sxs-lookup"><span data-stu-id="9be60-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="9be60-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="9be60-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="9be60-163">Chat ICE</span><span class="sxs-lookup"><span data-stu-id="9be60-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|<span data-ttu-id="9be60-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="9be60-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="9be60-165">Twitter</span><span class="sxs-lookup"><span data-stu-id="9be60-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="9be60-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="9be60-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="9be60-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="9be60-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="9be60-168">IRC</span><span class="sxs-lookup"><span data-stu-id="9be60-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="9be60-169">Jive</span><span class="sxs-lookup"><span data-stu-id="9be60-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="9be60-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="9be60-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="9be60-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="9be60-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="9be60-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="9be60-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="9be60-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="9be60-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="9be60-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="9be60-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="9be60-175">Alineación de mente</span><span class="sxs-lookup"><span data-stu-id="9be60-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="9be60-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="9be60-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="9be60-177">MSN</span><span class="sxs-lookup"><span data-stu-id="9be60-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="9be60-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="9be60-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="9be60-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="9be60-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="9be60-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="9be60-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="9be60-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="9be60-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="9be60-182">Documento principal</span><span class="sxs-lookup"><span data-stu-id="9be60-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="9be60-183">QQ</span><span class="sxs-lookup"><span data-stu-id="9be60-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="9be60-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="9be60-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="9be60-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="9be60-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="9be60-186">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="9be60-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="9be60-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="9be60-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="9be60-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="9be60-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="9be60-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="9be60-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="9be60-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="9be60-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="9be60-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="9be60-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="9be60-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="9be60-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="9be60-193">Tor</span><span class="sxs-lookup"><span data-stu-id="9be60-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="9be60-194">TTT</span><span class="sxs-lookup"><span data-stu-id="9be60-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="9be60-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="9be60-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="9be60-196">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="9be60-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="9be60-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="9be60-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="9be60-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="9be60-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="9be60-199">Winny</span><span class="sxs-lookup"><span data-stu-id="9be60-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="9be60-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9be60-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="9be60-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="9be60-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="9be60-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="9be60-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="9be60-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="9be60-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
