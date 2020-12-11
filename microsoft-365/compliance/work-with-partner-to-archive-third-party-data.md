---
title: Trabajar con un socio para archivar datos de terceros
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo configurar un conector personalizado para importar datos de terceros desde orígenes de datos como Salesforce chatter, Yahoo Messenger o Yammer.
ms.openlocfilehash: 64e903604ea56e5f53e3cc154bd54459a6d8d554
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620216"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="3d24b-103">Trabajar con un socio para archivar datos de terceros</span><span class="sxs-lookup"><span data-stu-id="3d24b-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="3d24b-104">Puede trabajar con un socio de Microsoft para importar y archivar datos desde un origen de datos de terceros a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d24b-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="3d24b-105">Un asociado puede proporcionarle un conector personalizado que está configurado para extraer elementos del origen de datos de terceros (de forma periódica) y, a continuación, importar dichos elementos.</span><span class="sxs-lookup"><span data-stu-id="3d24b-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="3d24b-106">El conector de asociados convierte el contenido de un elemento del origen de datos en un formato de mensaje de correo electrónico y, a continuación, almacena los elementos en los buzones.</span><span class="sxs-lookup"><span data-stu-id="3d24b-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="3d24b-107">Una vez importados los datos de terceros, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la exhibición de documentos electrónicos In-Place el archivado, la auditoría y las directivas de retención de Microsoft 365 a estos datos.</span><span class="sxs-lookup"><span data-stu-id="3d24b-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="3d24b-108">La solución de [cumplimiento de comunicaciones](communication-compliance.md) de Microsoft 365 no se puede aplicar a los datos de terceros importados por los conectores de asociados que se mencionan en este artículo.</span><span class="sxs-lookup"><span data-stu-id="3d24b-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span> 

<span data-ttu-id="3d24b-109">A continuación, se presenta una introducción al proceso y los pasos necesarios para trabajar con un socio de Microsoft para importar datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="3d24b-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="3d24b-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="3d24b-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="3d24b-111">Paso 2: crear y configurar un buzón de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="3d24b-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[<span data-ttu-id="3d24b-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="3d24b-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="3d24b-113">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="3d24b-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="3d24b-114">Paso 5: registrar el conector de datos de terceros en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3d24b-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="3d24b-115">Cómo funciona el proceso de importación de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="3d24b-115">How the third-party data import process works</span></span>

<span data-ttu-id="3d24b-116">En la siguiente ilustración y descripción se explica cómo funciona el proceso de importación de datos de terceros al trabajar con un partner.</span><span class="sxs-lookup"><span data-stu-id="3d24b-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![Cómo funciona el proceso de importación de datos de terceros](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="3d24b-118">El cliente trabaja con su partner de elección para configurar un conector que extraerá elementos del origen de datos de terceros y, a continuación, importará dichos elementos a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d24b-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="3d24b-119">El conector del asociado se conecta a orígenes de datos de terceros a través de una API de terceros (en una base programada o configurada) y extrae elementos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3d24b-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="3d24b-120">El conector asociado convierte el contenido de un elemento en un formato de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3d24b-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="3d24b-121">Consulte la sección [More Information](#more-information) para obtener una descripción del esquema de formato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3d24b-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="3d24b-122">El conector del asociado se conecta al servicio de Azure en Microsoft 365 mediante el servicio Web Exchange (EWS) a través de un punto final conocido.</span><span class="sxs-lookup"><span data-stu-id="3d24b-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="3d24b-p103">Los elementos se importan al buzón de un usuario específico o a un buzón global de datos de terceros. Que un elemento se importe al buzón de un usuario específico o al buzón de datos de terceros depende de los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d24b-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="3d24b-125">**Elementos que tienen un identificador de usuario que se corresponde con una cuenta de usuario:** Si el conector del asociado puede asignar el identificador de usuario del elemento del origen de datos de terceros a un identificador de usuario específico en Microsoft 365, el elemento se copia en la carpeta **purgas** de la carpeta elementos recuperables del usuario.</span><span class="sxs-lookup"><span data-stu-id="3d24b-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Microsoft 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="3d24b-126">Los usuarios no pueden acceder a los elementos de esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="3d24b-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="3d24b-127">Sin embargo, puede usar las herramientas de eDiscovery para buscar elementos en la carpeta depuraciones.</span><span class="sxs-lookup"><span data-stu-id="3d24b-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="3d24b-128">**Elementos que no tienen un identificador de usuario que se corresponde con una cuenta de usuario:** Si el conector del asociado no puede asignar el identificador de usuario de un elemento a un identificador de usuario específico, el elemento se copia en la carpeta **bandeja de entrada** del buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="3d24b-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="3d24b-129">La importación de elementos a la Bandeja de entrada permite que usted u otra persona de la organización inicie sesión en el buzón de correo de terceros para ver y administrar estos elementos, y ver si es necesario realizar ajustes en la configuración del conector asociado.</span><span class="sxs-lookup"><span data-stu-id="3d24b-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="3d24b-130">Paso 1: Buscar un asociado de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="3d24b-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="3d24b-131">Un componente clave para archivar datos de terceros en Microsoft 365 es encontrar y trabajar con un socio de Microsoft que se especializa en capturar datos de un origen de datos de terceros e importarlos a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d24b-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Microsoft 365.</span></span> <span data-ttu-id="3d24b-132">Una vez importados los datos, se pueden archivar y conservar junto con los otros datos de Microsoft de la organización, como el correo electrónico de Exchange y los documentos de SharePoint y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="3d24b-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="3d24b-133">Un asociado crea un conector que extrae datos de los orígenes de datos de terceros de la organización (como BlackBerry, Facebook, Google +, Thomson Reuters, Twitter y YouTube) y pasa esos datos a una API 365 de Microsoft que importa elementos a buzones de Exchange como mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3d24b-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to a Microsoft 365 API that imports items to Exchange mailboxes as email messages.</span></span>
  
<span data-ttu-id="3d24b-134">En las secciones siguientes se enumeran los socios de Microsoft (y los orígenes de datos de terceros que admiten) que participan en el programa para archivar datos de terceros en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d24b-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Microsoft 365.</span></span>

[<span data-ttu-id="3d24b-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="3d24b-135">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="3d24b-136">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="3d24b-136">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="3d24b-137">Globanet</span><span class="sxs-lookup"><span data-stu-id="3d24b-137">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="3d24b-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="3d24b-138">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="3d24b-139">Smarsh</span><span class="sxs-lookup"><span data-stu-id="3d24b-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="3d24b-140">Verboa</span><span class="sxs-lookup"><span data-stu-id="3d24b-140">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="3d24b-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="3d24b-141">17a-4 LLC</span></span>

<span data-ttu-id="3d24b-142">[17a-4 LLC](https://www.17a-4.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="3d24b-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="3d24b-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="3d24b-143">BlackBerry</span></span>
    
- <span data-ttu-id="3d24b-144">Secuencias de datos de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="3d24b-144">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="3d24b-145">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="3d24b-145">Cisco Jabber</span></span>
    
- <span data-ttu-id="3d24b-146">FactSet</span><span class="sxs-lookup"><span data-stu-id="3d24b-146">FactSet</span></span>
    
- <span data-ttu-id="3d24b-147">HipChat</span><span class="sxs-lookup"><span data-stu-id="3d24b-147">HipChat</span></span>
    
- <span data-ttu-id="3d24b-148">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="3d24b-148">InvestEdge</span></span>
    
- <span data-ttu-id="3d24b-149">LivePerson</span><span class="sxs-lookup"><span data-stu-id="3d24b-149">LivePerson</span></span>
    
- <span data-ttu-id="3d24b-150">Secuencias de datos de MessageLabs</span><span class="sxs-lookup"><span data-stu-id="3d24b-150">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="3d24b-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="3d24b-151">OpenText</span></span>
    
- <span data-ttu-id="3d24b-152">Ayuda de Hacer clic para llamar de Oracle/ATG Live</span><span class="sxs-lookup"><span data-stu-id="3d24b-152">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="3d24b-153">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="3d24b-153">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="3d24b-154">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="3d24b-154">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="3d24b-155">MindAlign</span><span class="sxs-lookup"><span data-stu-id="3d24b-155">MindAlign</span></span>
    
- <span data-ttu-id="3d24b-156">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="3d24b-156">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="3d24b-157">Skype Empresarial (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="3d24b-157">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="3d24b-158">Skype Empresarial Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="3d24b-158">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="3d24b-159">Bases de datos SQL</span><span class="sxs-lookup"><span data-stu-id="3d24b-159">SQL Databases</span></span>
    
- <span data-ttu-id="3d24b-160">Squawker</span><span class="sxs-lookup"><span data-stu-id="3d24b-160">Squawker</span></span>
    
- <span data-ttu-id="3d24b-161">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="3d24b-161">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="3d24b-162">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="3d24b-162">ArchiveSocial</span></span>

<span data-ttu-id="3d24b-163">[ArchiveSocial ](https://www.archivesocial.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="3d24b-163">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3d24b-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="3d24b-164">Facebook</span></span>
    
- <span data-ttu-id="3d24b-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="3d24b-165">Flickr</span></span>
    
- <span data-ttu-id="3d24b-166">Instagram</span><span class="sxs-lookup"><span data-stu-id="3d24b-166">Instagram</span></span>
    
- <span data-ttu-id="3d24b-167">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="3d24b-167">LinkedIn</span></span>
    
- <span data-ttu-id="3d24b-168">Pinterest</span><span class="sxs-lookup"><span data-stu-id="3d24b-168">Pinterest</span></span>
    
- <span data-ttu-id="3d24b-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="3d24b-169">Twitter</span></span>
    
- <span data-ttu-id="3d24b-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="3d24b-170">YouTube</span></span>
    
- <span data-ttu-id="3d24b-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="3d24b-171">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="3d24b-172">Globanet</span><span class="sxs-lookup"><span data-stu-id="3d24b-172">Globanet</span></span>

<span data-ttu-id="3d24b-173">[Globanet](https://www.globanet.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="3d24b-173">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3d24b-174">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="3d24b-174">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="3d24b-175">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="3d24b-175">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d24b-176">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="3d24b-176">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d24b-177">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="3d24b-177">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d24b-178">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="3d24b-178">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d24b-179">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="3d24b-179">Bloomberg Chat</span></span>
    
- <span data-ttu-id="3d24b-180">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="3d24b-180">Bloomberg Mail</span></span>
    
- <span data-ttu-id="3d24b-181">Box</span><span class="sxs-lookup"><span data-stu-id="3d24b-181">Box</span></span>
    
- <span data-ttu-id="3d24b-182">CipherCloud para Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="3d24b-182">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="3d24b-183">Servidor de presencia de mensajería instantánea de Cisco &amp; (V10, v 10.5.1 SU1, v 11.0, v 11,5 SU2)</span><span class="sxs-lookup"><span data-stu-id="3d24b-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="3d24b-184">Equipos Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="3d24b-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="3d24b-185">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="3d24b-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="3d24b-186">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="3d24b-186">CrowdCompass</span></span>

- <span data-ttu-id="3d24b-187">Archivos de texto delimitados personalizados</span><span class="sxs-lookup"><span data-stu-id="3d24b-187">Custom-delimited text files</span></span>
    
- <span data-ttu-id="3d24b-188">Archivos XML personalizados</span><span class="sxs-lookup"><span data-stu-id="3d24b-188">Custom XML files</span></span>
    
- <span data-ttu-id="3d24b-189">Facebook (páginas)</span><span class="sxs-lookup"><span data-stu-id="3d24b-189">Facebook (Pages)</span></span>
    
- <span data-ttu-id="3d24b-190">Factset</span><span class="sxs-lookup"><span data-stu-id="3d24b-190">Factset</span></span>
    
- <span data-ttu-id="3d24b-191">FXConnect</span><span class="sxs-lookup"><span data-stu-id="3d24b-191">FXConnect</span></span>
    
- <span data-ttu-id="3d24b-192">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="3d24b-192">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="3d24b-193">Jive</span><span class="sxs-lookup"><span data-stu-id="3d24b-193">Jive</span></span>
    
- <span data-ttu-id="3d24b-194">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="3d24b-194">Macgregor XIP</span></span>

- <span data-ttu-id="3d24b-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3d24b-195">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="3d24b-196">Microsoft OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="3d24b-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="3d24b-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d24b-197">Microsoft Teams</span></span>
       
- <span data-ttu-id="3d24b-198">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="3d24b-198">Microsoft Yammer</span></span>
    
- <span data-ttu-id="3d24b-199">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="3d24b-199">Mobile Guard</span></span>
    
- <span data-ttu-id="3d24b-200">Pivot</span><span class="sxs-lookup"><span data-stu-id="3d24b-200">Pivot</span></span>
    
- <span data-ttu-id="3d24b-201">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="3d24b-201">Salesforce Chatter</span></span>

- <span data-ttu-id="3d24b-202">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3d24b-202">Skype for Business Online</span></span>
    
- <span data-ttu-id="3d24b-203">Skype Empresarial, versiones 2007 R2 - 2016 (local)</span><span class="sxs-lookup"><span data-stu-id="3d24b-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="3d24b-204">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="3d24b-204">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="3d24b-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="3d24b-205">Symphony</span></span>
    
- <span data-ttu-id="3d24b-206">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="3d24b-206">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="3d24b-207">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="3d24b-207">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="3d24b-208">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="3d24b-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="3d24b-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="3d24b-209">Twitter</span></span>
    
- <span data-ttu-id="3d24b-210">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="3d24b-210">UBS Chat</span></span>
    
- <span data-ttu-id="3d24b-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="3d24b-211">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="3d24b-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="3d24b-212">OpenText</span></span>

<span data-ttu-id="3d24b-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="3d24b-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3d24b-214">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="3d24b-214">Axs Encrypted</span></span>
    
- <span data-ttu-id="3d24b-215">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="3d24b-215">Axs Exchange</span></span>
    
- <span data-ttu-id="3d24b-216">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="3d24b-216">Axs Local Archive</span></span>
    
- <span data-ttu-id="3d24b-217">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="3d24b-217">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="3d24b-218">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="3d24b-218">Axs Signed</span></span>
    
- <span data-ttu-id="3d24b-219">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="3d24b-219">Bloomberg</span></span>
    
- <span data-ttu-id="3d24b-220">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="3d24b-220">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="3d24b-221">Smarsh</span><span class="sxs-lookup"><span data-stu-id="3d24b-221">Smarsh</span></span>

<span data-ttu-id="3d24b-222">[Smarsh](https://www.smarsh.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="3d24b-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3d24b-223">APUNTA</span><span class="sxs-lookup"><span data-stu-id="3d24b-223">AIM</span></span>
    
- <span data-ttu-id="3d24b-224">American Idol</span><span class="sxs-lookup"><span data-stu-id="3d24b-224">American Idol</span></span>
    
- <span data-ttu-id="3d24b-225">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="3d24b-225">Apple Juice</span></span>
    
- <span data-ttu-id="3d24b-226">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="3d24b-226">AOL with Pivot client</span></span>
    
- <span data-ttu-id="3d24b-227">Áreas</span><span class="sxs-lookup"><span data-stu-id="3d24b-227">Ares</span></span>
    
- <span data-ttu-id="3d24b-228">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-228">Bazaar Voice</span></span>
    
- <span data-ttu-id="3d24b-229">Bear Share</span><span class="sxs-lookup"><span data-stu-id="3d24b-229">Bear Share</span></span>
    
- <span data-ttu-id="3d24b-230">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="3d24b-230">Bit Torrent</span></span>
    
- <span data-ttu-id="3d24b-231">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="3d24b-231">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d24b-232">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="3d24b-232">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d24b-233">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="3d24b-233">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d24b-234">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="3d24b-234">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d24b-235">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="3d24b-235">Bloomberg Mail</span></span>
    
- <span data-ttu-id="3d24b-236">CellTrust</span><span class="sxs-lookup"><span data-stu-id="3d24b-236">CellTrust</span></span>
    
- <span data-ttu-id="3d24b-237">Importación de chat</span><span class="sxs-lookup"><span data-stu-id="3d24b-237">Chat Import</span></span>
    
- <span data-ttu-id="3d24b-238">Directiva y registro en tiempo real de chat</span><span class="sxs-lookup"><span data-stu-id="3d24b-238">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="3d24b-239">Flanco</span><span class="sxs-lookup"><span data-stu-id="3d24b-239">Chatter</span></span>
    
- <span data-ttu-id="3d24b-240">Servidor de presencia de mensajería instantánea de Cisco &amp; (v 9.0.1, v 9.1, v 9.1.1 SU1, V10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="3d24b-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="3d24b-241">Servidor de presencia unificada de Cisco (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="3d24b-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="3d24b-242">Importación de colaboración</span><span class="sxs-lookup"><span data-stu-id="3d24b-242">Collaboration Import</span></span>
    
- <span data-ttu-id="3d24b-243">Registro de colaboración en tiempo real</span><span class="sxs-lookup"><span data-stu-id="3d24b-243">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="3d24b-244">Conexión directa</span><span class="sxs-lookup"><span data-stu-id="3d24b-244">Direct Connect</span></span>
    
- <span data-ttu-id="3d24b-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="3d24b-245">Facebook</span></span>
    
- <span data-ttu-id="3d24b-246">FactSet</span><span class="sxs-lookup"><span data-stu-id="3d24b-246">FactSet</span></span>
    
- <span data-ttu-id="3d24b-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="3d24b-247">FastTrack</span></span>
    
- <span data-ttu-id="3d24b-248">Gnutella</span><span class="sxs-lookup"><span data-stu-id="3d24b-248">Gnutella</span></span>
    
- <span data-ttu-id="3d24b-249">Google +</span><span class="sxs-lookup"><span data-stu-id="3d24b-249">Google+</span></span>
    
- <span data-ttu-id="3d24b-250">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="3d24b-250">GoToMyPC</span></span>
    
- <span data-ttu-id="3d24b-251">Hopster</span><span class="sxs-lookup"><span data-stu-id="3d24b-251">Hopster</span></span>
    
- <span data-ttu-id="3d24b-252">HubConnex</span><span class="sxs-lookup"><span data-stu-id="3d24b-252">HubConnex</span></span>
    
- <span data-ttu-id="3d24b-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="3d24b-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="3d24b-254">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="3d24b-254">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="3d24b-255">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="3d24b-255">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="3d24b-256">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="3d24b-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="3d24b-257">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="3d24b-257">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="3d24b-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="3d24b-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="3d24b-259">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="3d24b-259">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="3d24b-260">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="3d24b-260">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="3d24b-261">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="3d24b-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="3d24b-262">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="3d24b-262">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="3d24b-263">Importación de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="3d24b-263">IM Import</span></span>
    
- <span data-ttu-id="3d24b-264">Directiva y registro de mensajería instantánea en tiempo real</span><span class="sxs-lookup"><span data-stu-id="3d24b-264">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="3d24b-265">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="3d24b-265">Indii Messenger</span></span>
    
- <span data-ttu-id="3d24b-266">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="3d24b-266">Instant Bloomberg</span></span>
    
- <span data-ttu-id="3d24b-267">IRC</span><span class="sxs-lookup"><span data-stu-id="3d24b-267">IRC</span></span>
    
- <span data-ttu-id="3d24b-268">Jive</span><span class="sxs-lookup"><span data-stu-id="3d24b-268">Jive</span></span>
    
- <span data-ttu-id="3d24b-269">Jive 6 Real Time Logging (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="3d24b-269">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="3d24b-270">Jive Import</span><span class="sxs-lookup"><span data-stu-id="3d24b-270">Jive Import</span></span>
    
- <span data-ttu-id="3d24b-271">JXTA</span><span class="sxs-lookup"><span data-stu-id="3d24b-271">JXTA</span></span>
    
- <span data-ttu-id="3d24b-272">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="3d24b-272">LinkedIn</span></span>
    
- <span data-ttu-id="3d24b-273">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="3d24b-273">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="3d24b-274">MFTP</span><span class="sxs-lookup"><span data-stu-id="3d24b-274">MFTP</span></span>
    
- <span data-ttu-id="3d24b-275">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-275">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="3d24b-276">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="3d24b-276">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="3d24b-277">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3d24b-277">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="3d24b-278">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="3d24b-278">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="3d24b-279">MindAlign</span><span class="sxs-lookup"><span data-stu-id="3d24b-279">MindAlign</span></span>
    
- <span data-ttu-id="3d24b-280">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="3d24b-280">Mobile Guard</span></span>
    
- <span data-ttu-id="3d24b-281">Fotos</span><span class="sxs-lookup"><span data-stu-id="3d24b-281">MSN</span></span>
    
- <span data-ttu-id="3d24b-282">My Space</span><span class="sxs-lookup"><span data-stu-id="3d24b-282">My Space</span></span>
    
- <span data-ttu-id="3d24b-283">Subred</span><span class="sxs-lookup"><span data-stu-id="3d24b-283">NEONetwork</span></span>
    
- <span data-ttu-id="3d24b-284">Microsoft 365 Lync dedicado</span><span class="sxs-lookup"><span data-stu-id="3d24b-284">Microsoft 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="3d24b-285">Mensajería instantánea compartida 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d24b-285">Microsoft 365 Shared IM</span></span>
    
- <span data-ttu-id="3d24b-286">Pinterest</span><span class="sxs-lookup"><span data-stu-id="3d24b-286">Pinterest</span></span>
    
- <span data-ttu-id="3d24b-287">Pivot</span><span class="sxs-lookup"><span data-stu-id="3d24b-287">Pivot</span></span>
    
- <span data-ttu-id="3d24b-288">QQ</span><span class="sxs-lookup"><span data-stu-id="3d24b-288">QQ</span></span>
    
- <span data-ttu-id="3d24b-289">Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="3d24b-289">Skype for Business 2015</span></span>
    
- <span data-ttu-id="3d24b-290">SoftEther</span><span class="sxs-lookup"><span data-stu-id="3d24b-290">SoftEther</span></span>
    
- <span data-ttu-id="3d24b-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="3d24b-291">Symphony</span></span>
    
- <span data-ttu-id="3d24b-292">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="3d24b-292">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="3d24b-293">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="3d24b-293">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="3d24b-294">Términos</span><span class="sxs-lookup"><span data-stu-id="3d24b-294">Tor</span></span>
    
- <span data-ttu-id="3d24b-295">TTT</span><span class="sxs-lookup"><span data-stu-id="3d24b-295">TTT</span></span>
    
- <span data-ttu-id="3d24b-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="3d24b-296">Twitter</span></span>
    
- <span data-ttu-id="3d24b-297">WinMX</span><span class="sxs-lookup"><span data-stu-id="3d24b-297">WinMX</span></span>
    
- <span data-ttu-id="3d24b-298">Winny</span><span class="sxs-lookup"><span data-stu-id="3d24b-298">Winny</span></span>
    
- <span data-ttu-id="3d24b-299">Toolbar</span><span class="sxs-lookup"><span data-stu-id="3d24b-299">Yahoo</span></span>
    
- <span data-ttu-id="3d24b-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="3d24b-300">Yammer</span></span>
    
- <span data-ttu-id="3d24b-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="3d24b-301">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="3d24b-302">Verboa</span><span class="sxs-lookup"><span data-stu-id="3d24b-302">Verba</span></span>

<span data-ttu-id="3d24b-303">[Verboa](https://www.verba.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="3d24b-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3d24b-304">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="3d24b-304">Avaya Aura Video</span></span>
    
- <span data-ttu-id="3d24b-305">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-305">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="3d24b-306">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="3d24b-306">Avtec Radio</span></span>
    
- <span data-ttu-id="3d24b-307">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="3d24b-307">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="3d24b-308">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="3d24b-308">BroadSoft Video</span></span>
    
- <span data-ttu-id="3d24b-309">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-309">BroadSoft Voice</span></span>
    
- <span data-ttu-id="3d24b-310">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-310">Centile Voice</span></span>
    
- <span data-ttu-id="3d24b-311">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="3d24b-311">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="3d24b-312">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="3d24b-312">Cisco UC Video</span></span>
    
- <span data-ttu-id="3d24b-313">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-313">Cisco UC Voice</span></span>
    
- <span data-ttu-id="3d24b-314">Vídeo de Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="3d24b-314">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="3d24b-315">Cisco UCCX/UCCE de voz</span><span class="sxs-lookup"><span data-stu-id="3d24b-315">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="3d24b-316">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="3d24b-316">ESChat Radio</span></span>
    
- <span data-ttu-id="3d24b-317">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="3d24b-317">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="3d24b-318">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-318">IP Trade Voice</span></span>
    
- <span data-ttu-id="3d24b-319">Centro de contacto de Luware LUCS</span><span class="sxs-lookup"><span data-stu-id="3d24b-319">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="3d24b-320">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="3d24b-320">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="3d24b-321">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="3d24b-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="3d24b-322">Vídeo de controlador de borde de sesión de paquete Oracle/Acme</span><span class="sxs-lookup"><span data-stu-id="3d24b-322">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="3d24b-323">Voz de controlador de borde de sesión de paquete Oracle/Acme</span><span class="sxs-lookup"><span data-stu-id="3d24b-323">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="3d24b-324">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-324">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="3d24b-325">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="3d24b-325">SIPREC Video</span></span>
    
-  <span data-ttu-id="3d24b-326">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-326">SIPREC Voice</span></span> 
    
- <span data-ttu-id="3d24b-327">Skype Empresarial/MI de Lync</span><span class="sxs-lookup"><span data-stu-id="3d24b-327">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="3d24b-328">Skype Empresarial/Vídeo de Lync</span><span class="sxs-lookup"><span data-stu-id="3d24b-328">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="3d24b-329">Skype Empresarial/Voz de Lync</span><span class="sxs-lookup"><span data-stu-id="3d24b-329">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="3d24b-330">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-330">Speakerbus Voice</span></span>
    
- <span data-ttu-id="3d24b-331">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="3d24b-331">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="3d24b-332">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-332">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="3d24b-333">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="3d24b-333">Truphone Voice</span></span>
    
- <span data-ttu-id="3d24b-334">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="3d24b-334">TwistedPair Radio</span></span>
    
- <span data-ttu-id="3d24b-335">Pantalla de equipo de escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="3d24b-335">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a><span data-ttu-id="3d24b-336">Paso 2: crear y configurar un buzón de datos de terceros en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d24b-336">Step 2: Create and configure a third-party data mailbox in Microsoft 365</span></span>

<span data-ttu-id="3d24b-337">Estos son los pasos para crear y configurar un buzón de datos de terceros para importar datos a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d24b-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Microsoft 365.</span></span> <span data-ttu-id="3d24b-338">Como se ha explicado anteriormente, los elementos se importan a este buzón si el conector del asociado no puede asignar el identificador de usuario del elemento a una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="3d24b-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>
  
 <span data-ttu-id="3d24b-339">**Complete estas tareas en el centro de administración de 365 de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="3d24b-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="3d24b-340">Cree una cuenta de usuario y asígnela una licencia de Exchange Online plan 2; vea [Agregar usuarios a Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="3d24b-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="3d24b-341">Se necesita una licencia de plan 2 para poner el buzón en retención por juicio o habilitar un buzón de archivo que tenga una cuota de almacenamiento ilimitada.</span><span class="sxs-lookup"><span data-stu-id="3d24b-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="3d24b-342">Agregue la cuenta de usuario para el buzón de datos de terceros a la función de administrador de **Exchange Administrator** en Microsoft 365; consulte [asignar roles de administrador en Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="3d24b-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Microsoft 365; see [Assign admin roles in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3d24b-343">Escriba las credenciales para esta cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="3d24b-343">Write down the credentials for this user account.</span></span> <span data-ttu-id="3d24b-344">Necesitará proporcionárselas a su socio, tal como se describe en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="3d24b-344">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="3d24b-345">**Completar estas tareas en el centro de administración de Exchange**</span><span class="sxs-lookup"><span data-stu-id="3d24b-345">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="3d24b-346">Ocultar el buzón de datos de terceros de la libreta de direcciones y de otras listas de direcciones de la organización; consulte [Manage User mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="3d24b-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="3d24b-347">Como alternativa, puede ejecutar el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d24b-347">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="3d24b-348">Asignar el permiso **FullAccess** al buzón de datos de terceros para que los administradores o responsables de cumplimiento puedan abrir el buzón de datos de terceros en el cliente de escritorio de Outlook; consulte [administrar permisos para los destinatarios](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="3d24b-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="3d24b-349">Habilite las siguientes características relacionadas con el cumplimiento para el buzón de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="3d24b-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="3d24b-350">Habilitar el buzón de archivo; Consulte habilitar el archivado de [buzones de archivo](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="3d24b-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="3d24b-351">Esto le permite liberar espacio de almacenamiento en el buzón de correo principal mediante la configuración de una directiva de archivo que mueva los elementos de datos de terceros al buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="3d24b-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="3d24b-352">Esto proporciona un almacenamiento ilimitado para los datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="3d24b-352">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="3d24b-353">Coloque el buzón de datos de la tercera persona en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="3d24b-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="3d24b-354">También puede aplicar una directiva de retención de Microsoft 365 en el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="3d24b-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="3d24b-355">Colocar este buzón de correo en retención retiene los elementos de datos de terceros (indefinidamente o durante un tiempo especificado) y evita que se purguen del buzón.</span><span class="sxs-lookup"><span data-stu-id="3d24b-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="3d24b-356">Consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="3d24b-356">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="3d24b-357">Poner un buzón en retención por juicio</span><span class="sxs-lookup"><span data-stu-id="3d24b-357">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="3d24b-358">Más información sobre las directivas y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="3d24b-358">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="3d24b-359">Habilitar el registro de auditoría de buzones de correo para el propietario, el delegado y el acceso de administrador al buzón de datos de terceros; consulte [Habilitar la auditoría de buzones de correo](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="3d24b-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="3d24b-360">Esto le permite auditar todas las actividades realizadas por cualquier usuario que tenga acceso al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="3d24b-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="3d24b-361">Paso 3: Configurar los buzones de usuario para los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="3d24b-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="3d24b-362">El paso siguiente es configurar los buzones de usuario para que admitan los datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="3d24b-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="3d24b-363">Complete estas tareas con el centro de administración de Exchange o con los cmdlets de Windows PowerShell correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3d24b-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="3d24b-364">Habilitar el buzón de archivo para cada usuario; Consulte habilitar el archivado de [buzones de archivo](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="3d24b-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="3d24b-365">Coloque los buzones de usuario en retención por juicio o aplique una directiva de retención de Microsoft 365; Consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="3d24b-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="3d24b-366">Poner un buzón en retención por juicio</span><span class="sxs-lookup"><span data-stu-id="3d24b-366">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="3d24b-367">Más información sobre las directivas y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="3d24b-367">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="3d24b-368">Como ya se ha indicado, al poner los buzones en retención, puede determinar durante cuánto tiempo deben retenerse los elementos del origen de datos de terceros o puede optar por retener los elementos indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="3d24b-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="3d24b-369">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="3d24b-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="3d24b-370">El último paso es proporcionar a su compañero la siguiente información para que pueda configurar el conector para que se conecte a su organización para importar datos a los buzones de usuario y al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="3d24b-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="3d24b-371">El extremo que se usa para conectarse al servicio de Azure en Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="3d24b-371">The endpoint used to connect to the Azure service in Microsoft 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="3d24b-372">Las credenciales de inicio de sesión (identificador de usuario y contraseña de Microsoft 365) del buzón de datos de terceros que ha creado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="3d24b-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="3d24b-373">Estas credenciales son necesarias para que el conector asociado pueda tener acceso e importar elementos a los buzones de usuario y al buzón de datos de un tercero.</span><span class="sxs-lookup"><span data-stu-id="3d24b-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="3d24b-374">Paso 5: registrar el conector de datos de terceros en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3d24b-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="3d24b-375">A partir del 30 de septiembre de 2018, el servicio de Azure en Microsoft 365 empezará a usar la autenticación moderna en Exchange Online para autenticar conectores de datos de terceros que intenten conectarse a su organización para importar datos.</span><span class="sxs-lookup"><span data-stu-id="3d24b-375">Starting September 30, 2018, the Azure service in Microsoft 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="3d24b-376">El motivo de este cambio es que la autenticación moderna proporciona más seguridad que el método actual, que se basaba en una lista de permitidos para conectores de terceros que usan el punto de conexión descrito anteriormente para conectarse al servicio de Azure.</span><span class="sxs-lookup"><span data-stu-id="3d24b-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="3d24b-377">Para permitir que un conector de datos de terceros se conecte a Microsoft 365 mediante el nuevo método de autenticación moderna, un administrador de la organización debe dar su consentimiento para registrar el conector como una aplicación de servicio de confianza en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d24b-377">To enable a third-party data connector to connect to Microsoft 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="3d24b-378">Esto se realiza al aceptar una solicitud de permiso para permitir que el conector tenga acceso a los datos de la organización en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d24b-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="3d24b-379">Después de aceptar esta solicitud, el conector de datos de terceros se agrega como una aplicación de empresa a Azure Active Directory y se representa como una entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="3d24b-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="3d24b-380">Para obtener más información sobre el proceso de consentimiento, consulte  [consentimiento de administrador de inquilinos](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="3d24b-380">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="3d24b-381">Estos son los pasos para acceder y aceptar la solicitud para registrar el conector:</span><span class="sxs-lookup"><span data-stu-id="3d24b-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="3d24b-382">Vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e inicie sesión con las credenciales de un administrador global.</span><span class="sxs-lookup"><span data-stu-id="3d24b-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="3d24b-383">Se muestra el siguiente cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3d24b-383">The following dialog box is displayed.</span></span> <span data-ttu-id="3d24b-384">Puede expandir los Cares para revisar los permisos que se asignarán al conector.</span><span class="sxs-lookup"><span data-stu-id="3d24b-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Se muestra el cuadro de diálogo de solicitud de permisos](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="3d24b-386">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3d24b-386">Click **Accept**.</span></span>

<span data-ttu-id="3d24b-387">Después de aceptar la solicitud, se muestra el [portal de Azure](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="3d24b-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="3d24b-388">Para ver la lista de aplicaciones de su organización, haga clic en aplicaciones empresariales de **Azure Active Directory**  >  .</span><span class="sxs-lookup"><span data-stu-id="3d24b-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="3d24b-389">El conector de datos de terceros de Microsoft 365 aparece en la hoja **aplicaciones empresariales** .</span><span class="sxs-lookup"><span data-stu-id="3d24b-389">The Microsoft 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d24b-390">Después del 30 de septiembre de 2018, los datos de terceros ya no se importarán en los buzones de la organización si no registra un conector de datos de terceros en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d24b-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="3d24b-391">Nota los conectores de datos de terceros existentes (los creados antes del 30 de septiembre de 2018) también deben registrarse en Azure Active Directory siguiendo el procedimiento que se indica en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="3d24b-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="3d24b-392">Revocar el consentimiento de un conector de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="3d24b-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="3d24b-393">Una vez que la organización ha Condado permiso a la solicitud de permisos para registrar un conector de datos de terceros en Azure Active Directory, su organización puede revocar ese consentimiento en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="3d24b-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="3d24b-394">Sin embargo, revocar el consentimiento de un conector significa que los datos del origen de datos de terceros ya no se importarán en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d24b-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Microsoft 365.</span></span>

<span data-ttu-id="3d24b-395">Para revocar el consentimiento de un conector de datos de terceros, puede eliminar la aplicación (eliminando la entidad de servicio correspondiente) de Azure Active Directory mediante la hoja **aplicaciones empresariales** de Azure portal, o bien con [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) en Microsoft 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d24b-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell.</span></span> <span data-ttu-id="3d24b-396">También puede usar el cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) en PowerShell de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d24b-396">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="3d24b-397">Más información</span><span class="sxs-lookup"><span data-stu-id="3d24b-397">More information</span></span>

- <span data-ttu-id="3d24b-398">Tal como se ha explicado, los elementos de orígenes de datos de terceros se importan a los buzones de Exchange como mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3d24b-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="3d24b-399">El conector del asociado importa el elemento con un esquema que requiere la API 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d24b-399">The partner connector imports the item using a schema required by the Microsoft 365 API.</span></span> <span data-ttu-id="3d24b-400">En la tabla siguiente se describen las propiedades del mensaje de un elemento de un origen de datos de terceros después de que este se importe a un buzón de Exchange como un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3d24b-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="3d24b-401">La tabla también indica si la propiedad del mensaje es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="3d24b-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="3d24b-402">Las propiedades obligatorias deben rellenarse.</span><span class="sxs-lookup"><span data-stu-id="3d24b-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="3d24b-403">Si a un elemento le falta una propiedad obligatoria, no se importará a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d24b-403">If an item is missing a mandatory property, it won't be imported to Microsoft 365.</span></span> <span data-ttu-id="3d24b-404">El proceso de importación devuelve un mensaje de error que explica por qué no se ha importado un elemento y qué propiedad falta.</span><span class="sxs-lookup"><span data-stu-id="3d24b-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="3d24b-405">**Propiedad del mensaje**</span><span class="sxs-lookup"><span data-stu-id="3d24b-405">**Message property**</span></span>|<span data-ttu-id="3d24b-406">**¿Es obligatoria?**</span><span class="sxs-lookup"><span data-stu-id="3d24b-406">**Mandatory?**</span></span>|<span data-ttu-id="3d24b-407">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3d24b-407">**Description**</span></span>|<span data-ttu-id="3d24b-408">**Valor de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="3d24b-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d24b-409">**FROM**</span><span class="sxs-lookup"><span data-stu-id="3d24b-409">**FROM**</span></span> <br/> |<span data-ttu-id="3d24b-410">Sí</span><span class="sxs-lookup"><span data-stu-id="3d24b-410">Yes</span></span>  <br/> |<span data-ttu-id="3d24b-411">El usuario que originalmente ha creado o enviado el elemento en el origen de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="3d24b-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="3d24b-412">El conector del asociado intenta asignar el identificador de usuario desde el elemento de origen (por ejemplo, un controlador de Twitter) a una cuenta de usuario para todos los participantes (usuarios de los campos de y a).</span><span class="sxs-lookup"><span data-stu-id="3d24b-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="3d24b-413">Una copia del mensaje se importará al buzón de cada participante.</span><span class="sxs-lookup"><span data-stu-id="3d24b-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="3d24b-414">Si ninguno de los participantes del elemento se puede asignar a una cuenta de usuario, el elemento se importará al buzón de archivado de terceros en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d24b-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Microsoft 365.</span></span>  <br/> <br/> <span data-ttu-id="3d24b-415">El participante que se identifica como remitente del elemento debe tener un buzón activo en la organización a la que se va a importar el elemento.</span><span class="sxs-lookup"><span data-stu-id="3d24b-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="3d24b-416">Si el remitente no tiene un buzón activo, se devolverá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="3d24b-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="3d24b-417">**TO**</span><span class="sxs-lookup"><span data-stu-id="3d24b-417">**TO**</span></span> <br/> |<span data-ttu-id="3d24b-418">Sí</span><span class="sxs-lookup"><span data-stu-id="3d24b-418">Yes</span></span>  <br/> |<span data-ttu-id="3d24b-419">El usuario que ha recibido un elemento, si es aplicable a un elemento del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3d24b-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="3d24b-420">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="3d24b-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="3d24b-421">No</span><span class="sxs-lookup"><span data-stu-id="3d24b-421">No</span></span>  <br/> |<span data-ttu-id="3d24b-422">El asunto del elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="3d24b-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="3d24b-423">**OBSOLET**</span><span class="sxs-lookup"><span data-stu-id="3d24b-423">**DATE**</span></span> <br/> |<span data-ttu-id="3d24b-424">Sí</span><span class="sxs-lookup"><span data-stu-id="3d24b-424">Yes</span></span>  <br/> |<span data-ttu-id="3d24b-425">La fecha en que el elemento se creó o publicó originalmente en el origen de datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="3d24b-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="3d24b-426">Por ejemplo, la fecha en la que se ha enviado un mensaje a Twitter.</span><span class="sxs-lookup"><span data-stu-id="3d24b-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="3d24b-427">**CUERPO**</span><span class="sxs-lookup"><span data-stu-id="3d24b-427">**BODY**</span></span> <br/> |<span data-ttu-id="3d24b-428">No</span><span class="sxs-lookup"><span data-stu-id="3d24b-428">No</span></span>  <br/> |<span data-ttu-id="3d24b-429">El contenido del mensaje o la publicación.</span><span class="sxs-lookup"><span data-stu-id="3d24b-429">The contents of the message or post.</span></span> <span data-ttu-id="3d24b-430">En el caso de algunos orígenes de datos, el contenido de esta propiedad podría ser el mismo que el contenido de la propiedad **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="3d24b-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="3d24b-431">Durante el proceso de importación, el conector del asociado intenta mantener la fidelidad total del origen de contenido como sea posible.</span><span class="sxs-lookup"><span data-stu-id="3d24b-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="3d24b-432">Si es posible, los archivos, los gráficos u otro contenido del cuerpo del elemento de origen se incluyen en esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="3d24b-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="3d24b-433">Si no es así, el contenido del elemento de origen se incluye en la propiedad **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="3d24b-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="3d24b-434">El contenido de esta propiedad depende del conector del asociado y de la capacidad de la plataforma de origen.</span><span class="sxs-lookup"><span data-stu-id="3d24b-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="3d24b-435">**DATOS adjuntos**</span><span class="sxs-lookup"><span data-stu-id="3d24b-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="3d24b-436">No</span><span class="sxs-lookup"><span data-stu-id="3d24b-436">No</span></span>  <br/> |<span data-ttu-id="3d24b-437">Si un elemento del origen de datos (como un Tweet en Twitter o una conversación de mensajería instantánea) tiene un archivo adjunto o incluye imágenes, la conexión del asociado intentará primero incluir datos adjuntos en la propiedad **Body** .</span><span class="sxs-lookup"><span data-stu-id="3d24b-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="3d24b-438">Si esto no es posible, se agrega a la propiedad \* \* ATTACHMENT \* \*.</span><span class="sxs-lookup"><span data-stu-id="3d24b-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="3d24b-439">Otros ejemplos de datos adjuntos son los "Me gusta" de Facebook, los metadatos del origen del contenido y las respuestas a un mensaje o una publicación.</span><span class="sxs-lookup"><span data-stu-id="3d24b-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="3d24b-440">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="3d24b-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="3d24b-441">Sí</span><span class="sxs-lookup"><span data-stu-id="3d24b-441">Yes</span></span>  <br/> | <span data-ttu-id="3d24b-442">Se trata de una propiedad de varios valores, que se crea y rellena con el conector de asociado.</span><span class="sxs-lookup"><span data-stu-id="3d24b-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="3d24b-443">El formato de esta propiedad es  `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="3d24b-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="3d24b-444">(Esta propiedad debe comenzar con  `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="3d24b-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="3d24b-445">Este formato es similar al de la clase de  `IPM.NOTE.X` mensaje. Esta propiedad incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="3d24b-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="3d24b-446">`Source`: Indica el origen de datos de terceros; por ejemplo, Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="3d24b-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="3d24b-447">`Event`: Indica el tipo de actividad que se realizó en el origen de datos de terceros que generó los elementos; por ejemplo, un Tweet en Twitter o un post en Facebook.</span><span class="sxs-lookup"><span data-stu-id="3d24b-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="3d24b-448">Los eventos son específicos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3d24b-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="3d24b-449">Un objetivo de esta propiedad es filtrar elementos específicos en función del origen de datos en el que un elemento se originó o basó, o bien en función del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="3d24b-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="3d24b-450">Por ejemplo, en una búsqueda de exhibición de documentos electrónicos podría crear una consulta de búsqueda para encontrar todos los tweets publicados por un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="3d24b-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="3d24b-451">Cuando los elementos se importan correctamente a los buzones de correo de Microsoft 365, un identificador único se devuelve al autor de la llamada como parte de la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="3d24b-451">When items are successfully imported to mailboxes in Microsoft 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="3d24b-452">Este identificador, llamado  `x-IngestionCorrelationID` , se puede usar para solucionar problemas posteriores de los asociados para el seguimiento de elementos de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="3d24b-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="3d24b-453">Se recomienda que los asociados capturen esta información y la registren según corresponda en su extremo.</span><span class="sxs-lookup"><span data-stu-id="3d24b-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="3d24b-454">A continuación se incluye un ejemplo de una respuesta HTTP que muestra este identificador:</span><span class="sxs-lookup"><span data-stu-id="3d24b-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="3d24b-455">Puede usar la herramienta de búsqueda de contenido en el centro de seguridad y cumplimiento para buscar los elementos que se importaron a los buzones de un origen de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="3d24b-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="3d24b-456">Para buscar específicamente estos elementos importados, puede usar los siguientes pares de valores y propiedades de mensaje en el cuadro palabra clave para una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="3d24b-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="3d24b-457">**`kind:externaldata`**: Use este par Property-Value para buscar todos los tipos de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="3d24b-457">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="3d24b-458">Por ejemplo, para buscar elementos que se importaron de un origen de datos de terceros y contenían la palabra "Contoso" en la propiedad Subject del elemento importado, usaría la palabra clave Query  `kind:externaldata AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="3d24b-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="3d24b-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Use este par Property-Value solo para buscar un tipo de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="3d24b-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="3d24b-460">Por ejemplo, para buscar únicamente datos de Facebook que contengan la palabra "Contoso" en la propiedad Subject, usaría la consulta de palabra clave  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="3d24b-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="3d24b-461">Para obtener una lista completa de los valores que se van a usar para los tipos de datos de terceros para la  `itemclass` propiedad, consulte [use Content Search to Search a datos de terceros que se importaron a Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span><span class="sxs-lookup"><span data-stu-id="3d24b-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="3d24b-462">Para obtener más información sobre cómo usar la búsqueda de contenido y crear consultas de búsqueda de palabras clave, vea:</span><span class="sxs-lookup"><span data-stu-id="3d24b-462">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="3d24b-463">Búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="3d24b-463">Content Search</span></span>](content-search.md)
    
  - <span data-ttu-id="3d24b-464">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="3d24b-464">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
