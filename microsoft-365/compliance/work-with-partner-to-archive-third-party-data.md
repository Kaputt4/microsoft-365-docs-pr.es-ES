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
ms.openlocfilehash: f76ceda12bf48d26454a47e4b0b5d6ad42fbe55d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817045"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="24737-103">Trabajar con un socio para archivar datos de terceros</span><span class="sxs-lookup"><span data-stu-id="24737-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="24737-104">Puede trabajar con un socio de Microsoft para importar y archivar datos desde un origen de datos de terceros a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24737-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="24737-105">Un asociado puede proporcionarle un conector personalizado que está configurado para extraer elementos del origen de datos de terceros (de forma periódica) y, a continuación, importar dichos elementos.</span><span class="sxs-lookup"><span data-stu-id="24737-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="24737-106">El conector de asociados convierte el contenido de un elemento del origen de datos en un formato de mensaje de correo electrónico y, a continuación, almacena los elementos en los buzones.</span><span class="sxs-lookup"><span data-stu-id="24737-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="24737-107">Una vez importados los datos de terceros, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la búsqueda de contenido, el archivado local, la auditoría y las directivas de retención de Microsoft 365 a estos datos.</span><span class="sxs-lookup"><span data-stu-id="24737-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>
  
<span data-ttu-id="24737-108">A continuación, se presenta una introducción al proceso y los pasos necesarios para trabajar con un socio de Microsoft para importar datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="24737-108">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="24737-109">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="24737-109">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="24737-110">Paso 2: crear y configurar un buzón de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="24737-110">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="24737-111">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="24737-111">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="24737-112">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="24737-112">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="24737-113">Paso 5: registrar el conector de datos de terceros en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="24737-113">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="24737-114">Cómo funciona el proceso de importación de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="24737-114">How the third-party data import process works</span></span>

<span data-ttu-id="24737-115">En la siguiente ilustración y descripción se explica cómo funciona el proceso de importación de datos de terceros al trabajar con un partner.</span><span class="sxs-lookup"><span data-stu-id="24737-115">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![Cómo funciona el proceso de importación de datos de terceros](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="24737-117">El cliente trabaja con su partner de elección para configurar un conector que extraerá elementos del origen de datos de terceros y, a continuación, importará dichos elementos a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24737-117">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="24737-118">El conector del asociado se conecta a orígenes de datos de terceros a través de una API de terceros (en una base programada o configurada) y extrae elementos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="24737-118">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="24737-119">El conector asociado convierte el contenido de un elemento en un formato de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="24737-119">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="24737-120">Consulte la sección [More Information](#more-information) para obtener una descripción del esquema de formato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="24737-120">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="24737-121">El conector del asociado se conecta al servicio de Azure en Microsoft 365 mediante el servicio Web Exchange (EWS) a través de un punto final conocido.</span><span class="sxs-lookup"><span data-stu-id="24737-121">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="24737-122">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox.</span><span class="sxs-lookup"><span data-stu-id="24737-122">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox.</span></span> <span data-ttu-id="24737-123">Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span><span class="sxs-lookup"><span data-stu-id="24737-123">Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="24737-124">**Elementos que tienen un identificador de usuario que corresponde a una cuenta de usuario:** Si el conector del asociado puede asignar el identificador de usuario del elemento del origen de datos de terceros a un identificador de usuario específico en Office 365, el elemento se copia en la carpeta **depuraciones** de la carpeta elementos recuperables del usuario.</span><span class="sxs-lookup"><span data-stu-id="24737-124">**Items that have a user ID that corresponds to an user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="24737-125">Los usuarios no pueden acceder a los elementos de esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="24737-125">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="24737-126">Sin embargo, puede usar las herramientas de eDiscovery para buscar elementos en la carpeta depuraciones.</span><span class="sxs-lookup"><span data-stu-id="24737-126">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="24737-127">**Elementos que no tienen un identificador de usuario correspondiente a una cuenta de usuario:** Si el conector del asociado no puede asignar el identificador de usuario de un elemento a un identificador de usuario específico, el elemento se copia en la carpeta **bandeja de entrada** del buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="24737-127">**Items that don't have a user ID that corresponds to an user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="24737-128">La importación de elementos a la Bandeja de entrada permite que usted u otra persona de la organización inicie sesión en el buzón de correo de terceros para ver y administrar estos elementos, y ver si es necesario realizar ajustes en la configuración del conector asociado.</span><span class="sxs-lookup"><span data-stu-id="24737-128">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="24737-129">Paso 1: Buscar un asociado de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="24737-129">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="24737-130">Un componente clave para archivar datos de terceros en Microsoft 365 es encontrar y trabajar con un socio de Microsoft que se especializa en capturar datos de un origen de datos de terceros e importarlos a Office 365.</span><span class="sxs-lookup"><span data-stu-id="24737-130">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="24737-131">Una vez importados los datos, se pueden archivar y conservar junto con los otros datos de Microsoft de la organización, como el correo electrónico de Exchange y los documentos de SharePoint y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="24737-131">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="24737-132">Un asociado crea un conector que extrae datos de los orígenes de datos de terceros de la organización (como BlackBerry, Facebook, Google +, Thomson Reuters, Twitter y YouTube) y pasa esos datos a una API 365 de Office que importa elementos a buzones de Exchange como mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="24737-132">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="24737-133">En las secciones siguientes se enumeran los socios de Microsoft (y los orígenes de datos de terceros que admiten) que participan en el programa para archivar datos de terceros en Office 365.</span><span class="sxs-lookup"><span data-stu-id="24737-133">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="24737-134">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="24737-134">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="24737-135">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="24737-135">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="24737-136">Globanet</span><span class="sxs-lookup"><span data-stu-id="24737-136">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="24737-137">OpenText</span><span class="sxs-lookup"><span data-stu-id="24737-137">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="24737-138">Smarsh</span><span class="sxs-lookup"><span data-stu-id="24737-138">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="24737-139">Verboa</span><span class="sxs-lookup"><span data-stu-id="24737-139">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="24737-140">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="24737-140">17a-4 LLC</span></span>

<span data-ttu-id="24737-141">[17a-4 LLC](https://www.17a-4.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="24737-141">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="24737-142">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="24737-142">BlackBerry</span></span>
    
- <span data-ttu-id="24737-143">Secuencias de datos de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="24737-143">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="24737-144">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="24737-144">Cisco Jabber</span></span>
    
- <span data-ttu-id="24737-145">FactSet</span><span class="sxs-lookup"><span data-stu-id="24737-145">FactSet</span></span>
    
- <span data-ttu-id="24737-146">HipChat</span><span class="sxs-lookup"><span data-stu-id="24737-146">HipChat</span></span>
    
- <span data-ttu-id="24737-147">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="24737-147">InvestEdge</span></span>
    
- <span data-ttu-id="24737-148">LivePerson</span><span class="sxs-lookup"><span data-stu-id="24737-148">LivePerson</span></span>
    
- <span data-ttu-id="24737-149">Secuencias de datos de MessageLabs</span><span class="sxs-lookup"><span data-stu-id="24737-149">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="24737-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="24737-150">OpenText</span></span>
    
- <span data-ttu-id="24737-151">Ayuda de Hacer clic para llamar de Oracle/ATG Live</span><span class="sxs-lookup"><span data-stu-id="24737-151">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="24737-152">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="24737-152">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="24737-153">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="24737-153">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="24737-154">MindAlign</span><span class="sxs-lookup"><span data-stu-id="24737-154">MindAlign</span></span>
    
- <span data-ttu-id="24737-155">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="24737-155">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="24737-156">Skype Empresarial (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="24737-156">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="24737-157">Skype Empresarial Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="24737-157">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="24737-158">Bases de datos SQL</span><span class="sxs-lookup"><span data-stu-id="24737-158">SQL Databases</span></span>
    
- <span data-ttu-id="24737-159">Squawker</span><span class="sxs-lookup"><span data-stu-id="24737-159">Squawker</span></span>
    
- <span data-ttu-id="24737-160">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="24737-160">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="24737-161">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="24737-161">ArchiveSocial</span></span>

<span data-ttu-id="24737-162">[ArchiveSocial](https://www.archivesocial.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="24737-162">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="24737-163">Facebook</span><span class="sxs-lookup"><span data-stu-id="24737-163">Facebook</span></span>
    
- <span data-ttu-id="24737-164">Flickr</span><span class="sxs-lookup"><span data-stu-id="24737-164">Flickr</span></span>
    
- <span data-ttu-id="24737-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="24737-165">Instagram</span></span>
    
- <span data-ttu-id="24737-166">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="24737-166">LinkedIn</span></span>
    
- <span data-ttu-id="24737-167">Pinterest</span><span class="sxs-lookup"><span data-stu-id="24737-167">Pinterest</span></span>
    
- <span data-ttu-id="24737-168">Twitter</span><span class="sxs-lookup"><span data-stu-id="24737-168">Twitter</span></span>
    
- <span data-ttu-id="24737-169">YouTube</span><span class="sxs-lookup"><span data-stu-id="24737-169">YouTube</span></span>
    
- <span data-ttu-id="24737-170">Vimeo</span><span class="sxs-lookup"><span data-stu-id="24737-170">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="24737-171">Globanet</span><span class="sxs-lookup"><span data-stu-id="24737-171">Globanet</span></span>

<span data-ttu-id="24737-172">[Globanet](https://www.globanet.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="24737-172">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="24737-173">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="24737-173">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="24737-174">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="24737-174">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="24737-175">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="24737-175">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="24737-176">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="24737-176">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="24737-177">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="24737-177">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="24737-178">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="24737-178">Bloomberg Chat</span></span>
    
- <span data-ttu-id="24737-179">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="24737-179">Bloomberg Mail</span></span>
    
- <span data-ttu-id="24737-180">Cuadro</span><span class="sxs-lookup"><span data-stu-id="24737-180">Box</span></span>
    
- <span data-ttu-id="24737-181">CipherCloud para Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="24737-181">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="24737-182">Servidor de presencia de mensajería instantánea de Cisco &amp; (V10, v 10.5.1 SU1, v 11.0, v 11,5 SU2)</span><span class="sxs-lookup"><span data-stu-id="24737-182">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="24737-183">Equipos Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="24737-183">Cisco Webex Teams</span></span>

- <span data-ttu-id="24737-184">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="24737-184">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="24737-185">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="24737-185">CrowdCompass</span></span>

- <span data-ttu-id="24737-186">Archivos de texto delimitados personalizados</span><span class="sxs-lookup"><span data-stu-id="24737-186">Custom-delimited text files</span></span>
    
- <span data-ttu-id="24737-187">Archivos XML personalizados</span><span class="sxs-lookup"><span data-stu-id="24737-187">Custom XML files</span></span>
    
- <span data-ttu-id="24737-188">Facebook (páginas)</span><span class="sxs-lookup"><span data-stu-id="24737-188">Facebook (Pages)</span></span>
    
- <span data-ttu-id="24737-189">Factset</span><span class="sxs-lookup"><span data-stu-id="24737-189">Factset</span></span>
    
- <span data-ttu-id="24737-190">FXConnect</span><span class="sxs-lookup"><span data-stu-id="24737-190">FXConnect</span></span>
    
- <span data-ttu-id="24737-191">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="24737-191">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="24737-192">Jive</span><span class="sxs-lookup"><span data-stu-id="24737-192">Jive</span></span>
    
- <span data-ttu-id="24737-193">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="24737-193">Macgregor XIP</span></span>

- <span data-ttu-id="24737-194">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="24737-194">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="24737-195">Microsoft OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="24737-195">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="24737-196">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24737-196">Microsoft Teams</span></span>
       
- <span data-ttu-id="24737-197">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="24737-197">Microsoft Yammer</span></span>
    
- <span data-ttu-id="24737-198">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="24737-198">Mobile Guard</span></span>
    
- <span data-ttu-id="24737-199">Pivot</span><span class="sxs-lookup"><span data-stu-id="24737-199">Pivot</span></span>
    
- <span data-ttu-id="24737-200">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="24737-200">Salesforce Chatter</span></span>

- <span data-ttu-id="24737-201">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="24737-201">Skype for Business Online</span></span>
    
- <span data-ttu-id="24737-202">Skype Empresarial, versiones 2007 R2 - 2016 (local)</span><span class="sxs-lookup"><span data-stu-id="24737-202">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="24737-203">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="24737-203">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="24737-204">Symphony</span><span class="sxs-lookup"><span data-stu-id="24737-204">Symphony</span></span>
    
- <span data-ttu-id="24737-205">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="24737-205">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="24737-206">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="24737-206">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="24737-207">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="24737-207">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="24737-208">Twitter</span><span class="sxs-lookup"><span data-stu-id="24737-208">Twitter</span></span>
    
- <span data-ttu-id="24737-209">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="24737-209">UBS Chat</span></span>
    
- <span data-ttu-id="24737-210">YouTube</span><span class="sxs-lookup"><span data-stu-id="24737-210">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="24737-211">OpenText</span><span class="sxs-lookup"><span data-stu-id="24737-211">OpenText</span></span>

<span data-ttu-id="24737-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="24737-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="24737-213">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="24737-213">Axs Encrypted</span></span>
    
- <span data-ttu-id="24737-214">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="24737-214">Axs Exchange</span></span>
    
- <span data-ttu-id="24737-215">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="24737-215">Axs Local Archive</span></span>
    
- <span data-ttu-id="24737-216">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="24737-216">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="24737-217">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="24737-217">Axs Signed</span></span>
    
- <span data-ttu-id="24737-218">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="24737-218">Bloomberg</span></span>
    
- <span data-ttu-id="24737-219">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="24737-219">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="24737-220">Smarsh</span><span class="sxs-lookup"><span data-stu-id="24737-220">Smarsh</span></span>

<span data-ttu-id="24737-221">[Smarsh](https://www.smarsh.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="24737-221">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="24737-222">APUNTA</span><span class="sxs-lookup"><span data-stu-id="24737-222">AIM</span></span>
    
- <span data-ttu-id="24737-223">American Idol</span><span class="sxs-lookup"><span data-stu-id="24737-223">American Idol</span></span>
    
- <span data-ttu-id="24737-224">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="24737-224">Apple Juice</span></span>
    
- <span data-ttu-id="24737-225">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="24737-225">AOL with Pivot client</span></span>
    
- <span data-ttu-id="24737-226">Áreas</span><span class="sxs-lookup"><span data-stu-id="24737-226">Ares</span></span>
    
- <span data-ttu-id="24737-227">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="24737-227">Bazaar Voice</span></span>
    
- <span data-ttu-id="24737-228">Bear Share</span><span class="sxs-lookup"><span data-stu-id="24737-228">Bear Share</span></span>
    
- <span data-ttu-id="24737-229">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="24737-229">Bit Torrent</span></span>
    
- <span data-ttu-id="24737-230">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="24737-230">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="24737-231">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="24737-231">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="24737-232">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="24737-232">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="24737-233">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="24737-233">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="24737-234">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="24737-234">Bloomberg Mail</span></span>
    
- <span data-ttu-id="24737-235">CellTrust</span><span class="sxs-lookup"><span data-stu-id="24737-235">CellTrust</span></span>
    
- <span data-ttu-id="24737-236">Importación de chat</span><span class="sxs-lookup"><span data-stu-id="24737-236">Chat Import</span></span>
    
- <span data-ttu-id="24737-237">Directiva y registro en tiempo real de chat</span><span class="sxs-lookup"><span data-stu-id="24737-237">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="24737-238">Flanco</span><span class="sxs-lookup"><span data-stu-id="24737-238">Chatter</span></span>
    
- <span data-ttu-id="24737-239">Servidor de presencia de mensajería instantánea de Cisco &amp; (v 9.0.1, v 9.1, v 9.1.1 SU1, V10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="24737-239">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="24737-240">Servidor de presencia unificada de Cisco (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="24737-240">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="24737-241">Importación de colaboración</span><span class="sxs-lookup"><span data-stu-id="24737-241">Collaboration Import</span></span>
    
- <span data-ttu-id="24737-242">Registro de colaboración en tiempo real</span><span class="sxs-lookup"><span data-stu-id="24737-242">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="24737-243">Conexión directa</span><span class="sxs-lookup"><span data-stu-id="24737-243">Direct Connect</span></span>
    
- <span data-ttu-id="24737-244">Facebook</span><span class="sxs-lookup"><span data-stu-id="24737-244">Facebook</span></span>
    
- <span data-ttu-id="24737-245">FactSet</span><span class="sxs-lookup"><span data-stu-id="24737-245">FactSet</span></span>
    
- <span data-ttu-id="24737-246">FastTrack</span><span class="sxs-lookup"><span data-stu-id="24737-246">FastTrack</span></span>
    
- <span data-ttu-id="24737-247">Gnutella</span><span class="sxs-lookup"><span data-stu-id="24737-247">Gnutella</span></span>
    
- <span data-ttu-id="24737-248">Google +</span><span class="sxs-lookup"><span data-stu-id="24737-248">Google+</span></span>
    
- <span data-ttu-id="24737-249">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="24737-249">GoToMyPC</span></span>
    
- <span data-ttu-id="24737-250">Hopster</span><span class="sxs-lookup"><span data-stu-id="24737-250">Hopster</span></span>
    
- <span data-ttu-id="24737-251">HubConnex</span><span class="sxs-lookup"><span data-stu-id="24737-251">HubConnex</span></span>
    
- <span data-ttu-id="24737-252">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="24737-252">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="24737-253">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="24737-253">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="24737-254">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="24737-254">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="24737-255">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="24737-255">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="24737-256">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="24737-256">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="24737-257">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="24737-257">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="24737-258">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="24737-258">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="24737-259">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="24737-259">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="24737-260">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="24737-260">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="24737-261">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="24737-261">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="24737-262">Importación de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="24737-262">IM Import</span></span>
    
- <span data-ttu-id="24737-263">Directiva y registro de mensajería instantánea en tiempo real</span><span class="sxs-lookup"><span data-stu-id="24737-263">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="24737-264">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="24737-264">Indii Messenger</span></span>
    
- <span data-ttu-id="24737-265">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="24737-265">Instant Bloomberg</span></span>
    
- <span data-ttu-id="24737-266">IRC</span><span class="sxs-lookup"><span data-stu-id="24737-266">IRC</span></span>
    
- <span data-ttu-id="24737-267">Jive</span><span class="sxs-lookup"><span data-stu-id="24737-267">Jive</span></span>
    
- <span data-ttu-id="24737-268">Jive 6 Real Time Logging (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="24737-268">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="24737-269">Jive Import</span><span class="sxs-lookup"><span data-stu-id="24737-269">Jive Import</span></span>
    
- <span data-ttu-id="24737-270">JXTA</span><span class="sxs-lookup"><span data-stu-id="24737-270">JXTA</span></span>
    
- <span data-ttu-id="24737-271">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="24737-271">LinkedIn</span></span>
    
- <span data-ttu-id="24737-272">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="24737-272">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="24737-273">MFTP</span><span class="sxs-lookup"><span data-stu-id="24737-273">MFTP</span></span>
    
- <span data-ttu-id="24737-274">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="24737-274">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="24737-275">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="24737-275">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="24737-276">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="24737-276">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="24737-277">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="24737-277">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="24737-278">MindAlign</span><span class="sxs-lookup"><span data-stu-id="24737-278">MindAlign</span></span>
    
- <span data-ttu-id="24737-279">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="24737-279">Mobile Guard</span></span>
    
- <span data-ttu-id="24737-280">Fotos</span><span class="sxs-lookup"><span data-stu-id="24737-280">MSN</span></span>
    
- <span data-ttu-id="24737-281">My Space</span><span class="sxs-lookup"><span data-stu-id="24737-281">My Space</span></span>
    
- <span data-ttu-id="24737-282">Subred</span><span class="sxs-lookup"><span data-stu-id="24737-282">NEONetwork</span></span>
    
- <span data-ttu-id="24737-283">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="24737-283">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="24737-284">Mensajería instantánea compartida de Office 365</span><span class="sxs-lookup"><span data-stu-id="24737-284">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="24737-285">Pinterest</span><span class="sxs-lookup"><span data-stu-id="24737-285">Pinterest</span></span>
    
- <span data-ttu-id="24737-286">Pivot</span><span class="sxs-lookup"><span data-stu-id="24737-286">Pivot</span></span>
    
- <span data-ttu-id="24737-287">QQ</span><span class="sxs-lookup"><span data-stu-id="24737-287">QQ</span></span>
    
- <span data-ttu-id="24737-288">Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="24737-288">Skype for Business 2015</span></span>
    
- <span data-ttu-id="24737-289">SoftEther</span><span class="sxs-lookup"><span data-stu-id="24737-289">SoftEther</span></span>
    
- <span data-ttu-id="24737-290">Symphony</span><span class="sxs-lookup"><span data-stu-id="24737-290">Symphony</span></span>
    
- <span data-ttu-id="24737-291">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="24737-291">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="24737-292">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="24737-292">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="24737-293">Términos</span><span class="sxs-lookup"><span data-stu-id="24737-293">Tor</span></span>
    
- <span data-ttu-id="24737-294">TTT</span><span class="sxs-lookup"><span data-stu-id="24737-294">TTT</span></span>
    
- <span data-ttu-id="24737-295">Twitter</span><span class="sxs-lookup"><span data-stu-id="24737-295">Twitter</span></span>
    
- <span data-ttu-id="24737-296">WinMX</span><span class="sxs-lookup"><span data-stu-id="24737-296">WinMX</span></span>
    
- <span data-ttu-id="24737-297">Winny</span><span class="sxs-lookup"><span data-stu-id="24737-297">Winny</span></span>
    
- <span data-ttu-id="24737-298">Toolbar</span><span class="sxs-lookup"><span data-stu-id="24737-298">Yahoo</span></span>
    
- <span data-ttu-id="24737-299">Yammer</span><span class="sxs-lookup"><span data-stu-id="24737-299">Yammer</span></span>
    
- <span data-ttu-id="24737-300">YouTube</span><span class="sxs-lookup"><span data-stu-id="24737-300">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="24737-301">Verboa</span><span class="sxs-lookup"><span data-stu-id="24737-301">Verba</span></span>

<span data-ttu-id="24737-302">[Verboa](https://www.verba.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="24737-302">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="24737-303">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="24737-303">Avaya Aura Video</span></span>
    
- <span data-ttu-id="24737-304">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="24737-304">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="24737-305">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="24737-305">Avtec Radio</span></span>
    
- <span data-ttu-id="24737-306">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="24737-306">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="24737-307">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="24737-307">BroadSoft Video</span></span>
    
- <span data-ttu-id="24737-308">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="24737-308">BroadSoft Voice</span></span>
    
- <span data-ttu-id="24737-309">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="24737-309">Centile Voice</span></span>
    
- <span data-ttu-id="24737-310">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="24737-310">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="24737-311">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="24737-311">Cisco UC Video</span></span>
    
- <span data-ttu-id="24737-312">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="24737-312">Cisco UC Voice</span></span>
    
- <span data-ttu-id="24737-313">Vídeo de Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="24737-313">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="24737-314">Cisco UCCX/UCCE de voz</span><span class="sxs-lookup"><span data-stu-id="24737-314">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="24737-315">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="24737-315">ESChat Radio</span></span>
    
- <span data-ttu-id="24737-316">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="24737-316">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="24737-317">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="24737-317">IP Trade Voice</span></span>
    
- <span data-ttu-id="24737-318">Centro de contacto de Luware LUCS</span><span class="sxs-lookup"><span data-stu-id="24737-318">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="24737-319">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="24737-319">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="24737-320">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="24737-320">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="24737-321">Vídeo de controlador de borde de sesión de paquete Oracle/Acme</span><span class="sxs-lookup"><span data-stu-id="24737-321">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="24737-322">Voz de controlador de borde de sesión de paquete Oracle/Acme</span><span class="sxs-lookup"><span data-stu-id="24737-322">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="24737-323">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="24737-323">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="24737-324">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="24737-324">SIPREC Video</span></span>
    
-  <span data-ttu-id="24737-325">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="24737-325">SIPREC Voice</span></span> 
    
- <span data-ttu-id="24737-326">Skype Empresarial/MI de Lync</span><span class="sxs-lookup"><span data-stu-id="24737-326">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="24737-327">Skype Empresarial/Vídeo de Lync</span><span class="sxs-lookup"><span data-stu-id="24737-327">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="24737-328">Skype Empresarial/Voz de Lync</span><span class="sxs-lookup"><span data-stu-id="24737-328">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="24737-329">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="24737-329">Speakerbus Voice</span></span>
    
- <span data-ttu-id="24737-330">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="24737-330">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="24737-331">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="24737-331">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="24737-332">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="24737-332">Truphone Voice</span></span>
    
- <span data-ttu-id="24737-333">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="24737-333">TwistedPair Radio</span></span>
    
- <span data-ttu-id="24737-334">Pantalla de equipo de escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="24737-334">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="24737-335">Paso 2: Crear y configurar un buzón de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="24737-335">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="24737-336">Estos son los pasos para crear y configurar un buzón de datos de terceros para importar datos a Office 365.</span><span class="sxs-lookup"><span data-stu-id="24737-336">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="24737-337">Como se ha explicado anteriormente, los elementos se importan a este buzón si el conector del asociado no puede asignar el identificador de usuario del elemento a una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="24737-337">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an user account.</span></span>
  
 <span data-ttu-id="24737-338">**Complete estas tareas en el centro de administración de 365 de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="24737-338">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="24737-339">Cree una cuenta de usuario y asígnela una licencia de Exchange Online plan 2; vea [Agregar usuarios a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="24737-339">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="24737-340">Se necesita una licencia de plan 2 para poner el buzón en retención por juicio o habilitar un buzón de archivo que tenga una cuota de almacenamiento ilimitada.</span><span class="sxs-lookup"><span data-stu-id="24737-340">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="24737-341">Agregue la cuenta de usuario para el buzón de datos de terceros a la función de administrador de **Administrador de Exchange** en Office 365; consulte [asignar roles de administrador en Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="24737-341">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="24737-342">Escriba las credenciales para esta cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="24737-342">Write down the credentials for this user account.</span></span> <span data-ttu-id="24737-343">Necesitará proporcionárselas a su socio, tal como se describe en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="24737-343">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="24737-344">**Completar estas tareas en el centro de administración de Exchange**</span><span class="sxs-lookup"><span data-stu-id="24737-344">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="24737-345">Ocultar el buzón de datos de terceros de la libreta de direcciones y de otras listas de direcciones de la organización; consulte [Manage User mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="24737-345">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="24737-346">Como alternativa, puede ejecutar el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="24737-346">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="24737-347">Asignar el permiso **FullAccess** al buzón de datos de terceros para que los administradores o responsables de cumplimiento puedan abrir el buzón de datos de terceros en el cliente de escritorio de Outlook; consulte [administrar permisos para los destinatarios](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="24737-347">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="24737-348">Habilite las siguientes características relacionadas con el cumplimiento para el buzón de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="24737-348">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="24737-349">Habilitar el buzón de archivo; Consulte habilitar el archivado de [buzones de archivo](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="24737-349">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="24737-350">Esto le permite liberar espacio de almacenamiento en el buzón de correo principal mediante la configuración de una directiva de archivo que mueva los elementos de datos de terceros al buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="24737-350">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="24737-351">Esto proporciona un almacenamiento ilimitado para los datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="24737-351">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="24737-352">Coloque el buzón de datos de la tercera persona en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="24737-352">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="24737-353">También puede aplicar una directiva de retención de Microsoft 365 en el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="24737-353">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="24737-354">Colocar este buzón de correo en retención retiene los elementos de datos de terceros (indefinidamente o durante un tiempo especificado) y evita que se purguen del buzón.</span><span class="sxs-lookup"><span data-stu-id="24737-354">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="24737-355">Consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="24737-355">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="24737-356">Poner un buzón en retención por juicio</span><span class="sxs-lookup"><span data-stu-id="24737-356">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="24737-357">Información general sobre las directivas de retención</span><span class="sxs-lookup"><span data-stu-id="24737-357">Overview of retention policies</span></span>](retention-policies.md)
    
    - <span data-ttu-id="24737-358">Habilitar el registro de auditoría de buzones de correo para el propietario, el delegado y el acceso de administrador al buzón de datos de terceros; consulte [Habilitar la auditoría de buzones de correo](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="24737-358">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="24737-359">Esto le permite auditar todas las actividades realizadas por cualquier usuario que tenga acceso al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="24737-359">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="24737-360">Paso 3: Configurar los buzones de usuario para los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="24737-360">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="24737-361">El paso siguiente es configurar los buzones de usuario para que admitan los datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="24737-361">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="24737-362">Complete estas tareas con el centro de administración de Exchange o con los cmdlets de Windows PowerShell correspondientes.</span><span class="sxs-lookup"><span data-stu-id="24737-362">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="24737-363">Habilitar el buzón de archivo para cada usuario; Consulte habilitar el archivado de [buzones de archivo](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="24737-363">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="24737-364">Coloque los buzones de usuario en retención por juicio o aplique una directiva de retención de Microsoft 365; Consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="24737-364">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="24737-365">Poner un buzón en retención por juicio</span><span class="sxs-lookup"><span data-stu-id="24737-365">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="24737-366">Información general sobre las directivas de retención</span><span class="sxs-lookup"><span data-stu-id="24737-366">Overview of retention policies</span></span>](retention-policies.md)
    
    <span data-ttu-id="24737-367">Como ya se ha indicado, al poner los buzones en retención, puede determinar durante cuánto tiempo deben retenerse los elementos del origen de datos de terceros o puede optar por retener los elementos indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="24737-367">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="24737-368">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="24737-368">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="24737-369">El último paso es proporcionar a su compañero la siguiente información para que pueda configurar el conector para que se conecte a su organización para importar datos a los buzones de usuario y al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="24737-369">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="24737-370">El extremo que se usa para conectarse al servicio de Azure en Office 365:</span><span class="sxs-lookup"><span data-stu-id="24737-370">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="24737-371">Las credenciales de inicio de sesión (identificador de usuario y contraseña de Microsoft 365) del buzón de datos de terceros que ha creado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="24737-371">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="24737-372">Estas credenciales son necesarias para que el conector asociado pueda tener acceso e importar elementos a los buzones de usuario y al buzón de datos de un tercero.</span><span class="sxs-lookup"><span data-stu-id="24737-372">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="24737-373">Paso 5: registrar el conector de datos de terceros en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="24737-373">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="24737-374">A partir del 30 de septiembre de 2018, el servicio de Azure en Office 365 empezará a usar la autenticación moderna en Exchange Online para autenticar conectores de datos de terceros que intenten conectarse a su organización para importar datos.</span><span class="sxs-lookup"><span data-stu-id="24737-374">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="24737-375">El motivo de este cambio es que la autenticación moderna proporciona más seguridad que el método actual, que se basaba en una lista de permitidos para conectores de terceros que usan el punto de conexión descrito anteriormente para conectarse al servicio de Azure.</span><span class="sxs-lookup"><span data-stu-id="24737-375">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="24737-376">Para permitir que un conector de datos de terceros se conecte a Office 365 mediante el nuevo método de autenticación moderna, un administrador de la organización debe dar su consentimiento para registrar el conector como una aplicación de servicio de confianza en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24737-376">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="24737-377">Esto se realiza al aceptar una solicitud de permiso para permitir que el conector tenga acceso a los datos de la organización en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24737-377">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="24737-378">Después de aceptar esta solicitud, el conector de datos de terceros se agrega como una aplicación de empresa a Azure Active Directory y se representa como una entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="24737-378">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="24737-379">Para obtener más información sobre el proceso de consentimiento, consulte [consentimiento de administrador de inquilinos](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="24737-379">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="24737-380">Estos son los pasos para acceder y aceptar la solicitud para registrar el conector:</span><span class="sxs-lookup"><span data-stu-id="24737-380">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="24737-381">Vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e inicie sesión con las credenciales de un administrador global.</span><span class="sxs-lookup"><span data-stu-id="24737-381">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="24737-382">Se muestra el siguiente cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="24737-382">The following dialog box is displayed.</span></span> <span data-ttu-id="24737-383">Puede expandir los Cares para revisar los permisos que se asignarán al conector.</span><span class="sxs-lookup"><span data-stu-id="24737-383">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Se muestra el cuadro de diálogo de solicitud de permisos](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="24737-385">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="24737-385">Click **Accept**.</span></span>

<span data-ttu-id="24737-386">Después de aceptar la solicitud, se muestra el [portal de Azure](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="24737-386">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="24737-387">Para ver la lista de aplicaciones de su organización, haga clic en aplicaciones empresariales de **Azure Active Directory**  >  **Enterprise applications**.</span><span class="sxs-lookup"><span data-stu-id="24737-387">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="24737-388">El conector de datos de terceros de Office 365 aparece en la hoja **aplicaciones empresariales** .</span><span class="sxs-lookup"><span data-stu-id="24737-388">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24737-389">Después del 30 de septiembre de 2018, los datos de terceros ya no se importarán en los buzones de la organización si no registra un conector de datos de terceros en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24737-389">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="24737-390">Nota los conectores de datos de terceros existentes (los creados antes del 30 de septiembre de 2018) también deben registrarse en Azure Active Directory siguiendo el procedimiento que se indica en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="24737-390">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="24737-391">Revocar el consentimiento de un conector de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="24737-391">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="24737-392">Una vez que la organización ha Condado permiso a la solicitud de permisos para registrar un conector de datos de terceros en Azure Active Directory, su organización puede revocar ese consentimiento en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="24737-392">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="24737-393">Sin embargo, la revocación del consentimiento de un conector significa que los datos del origen de datos de terceros ya no se importarán en Office 365.</span><span class="sxs-lookup"><span data-stu-id="24737-393">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="24737-394">Para revocar el consentimiento de un conector de datos de terceros, puede eliminar la aplicación (eliminando la entidad de servicio correspondiente) de Azure Active Directory mediante la hoja **aplicaciones empresariales** de Azure portal, o bien con [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) en Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24737-394">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="24737-395">También puede usar el cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) en PowerShell de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24737-395">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="24737-396">Más información</span><span class="sxs-lookup"><span data-stu-id="24737-396">More information</span></span>

- <span data-ttu-id="24737-397">Tal como se ha explicado, los elementos de orígenes de datos de terceros se importan a los buzones de Exchange como mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="24737-397">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="24737-398">El conector del asociado importa el elemento mediante un esquema requerido por la API 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="24737-398">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="24737-399">En la tabla siguiente se describen las propiedades del mensaje de un elemento de un origen de datos de terceros después de que este se importe a un buzón de Exchange como un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="24737-399">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="24737-400">La tabla también indica si la propiedad del mensaje es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="24737-400">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="24737-401">Las propiedades obligatorias deben rellenarse.</span><span class="sxs-lookup"><span data-stu-id="24737-401">Mandatory properties must be populated.</span></span> <span data-ttu-id="24737-402">Si a un elemento le falta una propiedad obligatoria, no se importará a Office 365.</span><span class="sxs-lookup"><span data-stu-id="24737-402">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="24737-403">El proceso de importación devuelve un mensaje de error que explica por qué no se ha importado un elemento y qué propiedad falta.</span><span class="sxs-lookup"><span data-stu-id="24737-403">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="24737-404">**Propiedad del mensaje**</span><span class="sxs-lookup"><span data-stu-id="24737-404">**Message property**</span></span>|<span data-ttu-id="24737-405">**¿Es obligatoria?**</span><span class="sxs-lookup"><span data-stu-id="24737-405">**Mandatory?**</span></span>|<span data-ttu-id="24737-406">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="24737-406">**Description**</span></span>|<span data-ttu-id="24737-407">**Valor de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="24737-407">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="24737-408">**FROM**</span><span class="sxs-lookup"><span data-stu-id="24737-408">**FROM**</span></span> <br/> |<span data-ttu-id="24737-409">Sí</span><span class="sxs-lookup"><span data-stu-id="24737-409">Yes</span></span>  <br/> |<span data-ttu-id="24737-410">El usuario que originalmente ha creado o enviado el elemento en el origen de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="24737-410">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="24737-411">El conector del asociado intenta asignar el identificador de usuario desde el elemento de origen (por ejemplo, un controlador de Twitter) a una cuenta de usuario para todos los participantes (usuarios de los campos de y a).</span><span class="sxs-lookup"><span data-stu-id="24737-411">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="24737-412">Una copia del mensaje se importará al buzón de cada participante.</span><span class="sxs-lookup"><span data-stu-id="24737-412">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="24737-413">Si ninguno de los participantes del elemento se puede asignar a una cuenta de usuario, el elemento se importará al buzón de archivado de terceros en Office 365.</span><span class="sxs-lookup"><span data-stu-id="24737-413">If none of the participants from the item can be mapped to an user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="24737-414">El participante que se identifica como remitente del elemento debe tener un buzón activo en la organización a la que se va a importar el elemento.</span><span class="sxs-lookup"><span data-stu-id="24737-414">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="24737-415">Si el remitente no tiene un buzón activo, se devolverá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="24737-415">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="24737-416">**TO**</span><span class="sxs-lookup"><span data-stu-id="24737-416">**TO**</span></span> <br/> |<span data-ttu-id="24737-417">Sí</span><span class="sxs-lookup"><span data-stu-id="24737-417">Yes</span></span>  <br/> |<span data-ttu-id="24737-418">El usuario que ha recibido un elemento, si es aplicable a un elemento del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="24737-418">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="24737-419">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="24737-419">**SUBJECT**</span></span> <br/> |<span data-ttu-id="24737-420">No</span><span class="sxs-lookup"><span data-stu-id="24737-420">No</span></span>  <br/> |<span data-ttu-id="24737-421">El asunto del elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="24737-421">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="24737-422">**OBSOLET**</span><span class="sxs-lookup"><span data-stu-id="24737-422">**DATE**</span></span> <br/> |<span data-ttu-id="24737-423">Sí</span><span class="sxs-lookup"><span data-stu-id="24737-423">Yes</span></span>  <br/> |<span data-ttu-id="24737-424">La fecha en que el elemento se creó o publicó originalmente en el origen de datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="24737-424">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="24737-425">Por ejemplo, la fecha en la que se ha enviado un mensaje a Twitter.</span><span class="sxs-lookup"><span data-stu-id="24737-425">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="24737-426">**CUERPO**</span><span class="sxs-lookup"><span data-stu-id="24737-426">**BODY**</span></span> <br/> |<span data-ttu-id="24737-427">No</span><span class="sxs-lookup"><span data-stu-id="24737-427">No</span></span>  <br/> |<span data-ttu-id="24737-428">El contenido del mensaje o la publicación.</span><span class="sxs-lookup"><span data-stu-id="24737-428">The contents of the message or post.</span></span> <span data-ttu-id="24737-429">En el caso de algunos orígenes de datos, el contenido de esta propiedad podría ser el mismo que el contenido de la propiedad **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="24737-429">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="24737-430">Durante el proceso de importación, el conector del asociado intenta mantener la fidelidad total del origen de contenido como sea posible.</span><span class="sxs-lookup"><span data-stu-id="24737-430">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="24737-431">Si es posible, los archivos, los gráficos u otro contenido del cuerpo del elemento de origen se incluyen en esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="24737-431">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="24737-432">Si no es así, el contenido del elemento de origen se incluye en la propiedad **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="24737-432">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="24737-433">El contenido de esta propiedad depende del conector del asociado y de la capacidad de la plataforma de origen.</span><span class="sxs-lookup"><span data-stu-id="24737-433">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="24737-434">**DATOS adjuntos**</span><span class="sxs-lookup"><span data-stu-id="24737-434">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="24737-435">No</span><span class="sxs-lookup"><span data-stu-id="24737-435">No</span></span>  <br/> |<span data-ttu-id="24737-436">Si un elemento del origen de datos (como un Tweet en Twitter o una conversación de mensajería instantánea) tiene un archivo adjunto o incluye imágenes, la conexión del asociado intentará primero incluir datos adjuntos en la propiedad **Body** .</span><span class="sxs-lookup"><span data-stu-id="24737-436">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="24737-437">Si esto no es posible, se agrega a la propiedad \* \* ATTACHMENT \* \*.</span><span class="sxs-lookup"><span data-stu-id="24737-437">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="24737-438">Otros ejemplos de datos adjuntos son los "Me gusta" de Facebook, los metadatos del origen del contenido y las respuestas a un mensaje o una publicación.</span><span class="sxs-lookup"><span data-stu-id="24737-438">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="24737-439">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="24737-439">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="24737-440">Sí</span><span class="sxs-lookup"><span data-stu-id="24737-440">Yes</span></span>  <br/> | <span data-ttu-id="24737-441">Se trata de una propiedad de varios valores, que se crea y rellena con el conector de asociado.</span><span class="sxs-lookup"><span data-stu-id="24737-441">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="24737-442">El formato de esta propiedad es `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="24737-442">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="24737-443">(Esta propiedad debe comenzar con `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="24737-443">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="24737-444">Este formato es similar al de la clase de `IPM.NOTE.X` mensaje. Esta propiedad incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="24737-444">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="24737-445">`Source`: Indica el origen de datos de terceros; por ejemplo, Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="24737-445">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="24737-446">`Event`: Indica el tipo de actividad que se realizó en el origen de datos de terceros que generó los elementos; por ejemplo, un Tweet en Twitter o un post en Facebook.</span><span class="sxs-lookup"><span data-stu-id="24737-446">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="24737-447">Los eventos son específicos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="24737-447">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="24737-448">Un objetivo de esta propiedad es filtrar elementos específicos en función del origen de datos en el que un elemento se originó o basó, o bien en función del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="24737-448">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="24737-449">Por ejemplo, en una búsqueda de exhibición de documentos electrónicos podría crear una consulta de búsqueda para encontrar todos los tweets publicados por un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="24737-449">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="24737-450">Cuando los elementos se importan correctamente a los buzones de Office 365, un identificador único se devuelve al autor de la llamada como parte de la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="24737-450">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="24737-451">Este identificador, llamado `x-IngestionCorrelationID` , se puede usar para solucionar problemas posteriores de los asociados para el seguimiento de elementos de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="24737-451">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="24737-452">Se recomienda que los asociados capturen esta información y la registren según corresponda en su extremo.</span><span class="sxs-lookup"><span data-stu-id="24737-452">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="24737-453">A continuación se incluye un ejemplo de una respuesta HTTP que muestra este identificador:</span><span class="sxs-lookup"><span data-stu-id="24737-453">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="24737-454">Puede usar la herramienta de búsqueda de contenido en el centro de seguridad y cumplimiento para buscar los elementos que se importaron a los buzones de un origen de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="24737-454">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="24737-455">Para buscar específicamente estos elementos importados, puede usar los siguientes pares de valores y propiedades de mensaje en el cuadro palabra clave para una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="24737-455">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="24737-456">**`kind:externaldata`**: Use este par Property-Value para buscar todos los tipos de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="24737-456">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="24737-457">Por ejemplo, para buscar elementos que se importaron de un origen de datos de terceros y contenían la palabra "Contoso" en la propiedad Subject del elemento importado, usaría la palabra clave Query `kind:externaldata AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="24737-457">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="24737-458">**`itemclass:ipm.externaldata.<third-party data type>`**: Use este par Property-Value solo para buscar un tipo de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="24737-458">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="24737-459">Por ejemplo, para buscar únicamente datos de Facebook que contengan la palabra "Contoso" en la propiedad Subject, usaría la consulta de palabra clave `itemclass:ipm.externaldata.Facebook* AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="24737-459">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="24737-460">Para obtener una lista completa de los valores que se van a usar para los tipos de datos de terceros para la `itemclass` propiedad, consulte [use Content Search to Search a data de terceros importado a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span><span class="sxs-lookup"><span data-stu-id="24737-460">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="24737-461">Para obtener más información sobre cómo usar la búsqueda de contenido y crear consultas de búsqueda de palabras clave, vea:</span><span class="sxs-lookup"><span data-stu-id="24737-461">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="24737-462">Búsqueda de contenido de Office 365</span><span class="sxs-lookup"><span data-stu-id="24737-462">Content Search in Office 365</span></span>](content-search.md)
    
  - <span data-ttu-id="24737-463">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="24737-463">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
 
