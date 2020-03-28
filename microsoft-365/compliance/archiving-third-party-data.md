---
title: Archivar datos de terceros
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Los administradores pueden importar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a los buzones de la organización de Microsoft 365. Esto le permite archivar datos de Facebook, Twitter y otros orígenes de datos de terceros en Microsoft 365. A continuación, puede usar y aplicar las características de cumplimiento de Microsoft 365 (como la retención legal, la exhibición de documentos electrónicos, el archivado local y las directivas de retención) para los datos de terceros.
ms.openlocfilehash: 72afb48f74a30bac2904e857a33487a83eba48cd
ms.sourcegitcommit: f9b5eca20e025acc36635cbd1786ff3407295857
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "43027660"
---
# <a name="archive-third-party-data"></a><span data-ttu-id="98861-105">Archivar datos de terceros</span><span class="sxs-lookup"><span data-stu-id="98861-105">Archive third-party data</span></span>

<span data-ttu-id="98861-106">Microsoft 365 permite a los administradores importar y archivar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a los buzones de la organización 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98861-106">Microsoft 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="98861-107">Algunos ejemplos de orígenes de datos de terceros que puede importar a Microsoft 365 incluyen los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="98861-107">Examples of third-party data sources that you can import to Microsoft 365 include the following services:</span></span> 
  
- <span data-ttu-id="98861-108">**Social:** Facebook, LinkedIn, Twitter y Yammer</span><span class="sxs-lookup"><span data-stu-id="98861-108">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span>

- <span data-ttu-id="98861-109">**Mensajería instantánea:** Yahoo Messenger y GoogleTalk</span><span class="sxs-lookup"><span data-stu-id="98861-109">**Instant messaging:** Yahoo Messenger and GoogleTalk</span></span>

- <span data-ttu-id="98861-110">**Colaboración en documentos:** Box y DropBox</span><span class="sxs-lookup"><span data-stu-id="98861-110">**Document collaboration:** Box and DropBox</span></span>

- <span data-ttu-id="98861-111">**Sectores verticales:** Administración de relaciones con el cliente (como Salesforce chatter) y servicios financieros (como Bloomberg y Thomson Reuters)</span><span class="sxs-lookup"><span data-stu-id="98861-111">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span>

- <span data-ttu-id="98861-112">**SMS/mensajería de texto:** BlackBerry</span><span class="sxs-lookup"><span data-stu-id="98861-112">**SMS/text messaging:** BlackBerry</span></span>

<span data-ttu-id="98861-113">Una vez importados los datos de terceros, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la exhibición de documentos electrónicos, el archivado local, la auditoría, el cumplimiento de comunicaciones y las directivas de retención a estos datos.</span><span class="sxs-lookup"><span data-stu-id="98861-113">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and retention policies to this data.</span></span> <span data-ttu-id="98861-114">Por ejemplo, cuando un buzón de correo se coloca en retención por juicio, se conservan los datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="98861-114">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="98861-115">Puede buscar datos de terceros mediante las herramientas de exhibición de documentos electrónicos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98861-115">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="98861-116">O bien, puede aplicar directivas de archivado y retención a datos de terceros, como lo haría con los datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98861-116">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="98861-117">En Resumen, el archivado de datos de terceros en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.</span><span class="sxs-lookup"><span data-stu-id="98861-117">In short, archiving third-party data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="98861-118">Hay dos formas de importar y archivar datos de terceros en Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="98861-118">There are two ways to import and archive third-party data in Microsoft 365:</span></span>

- <span data-ttu-id="98861-119">**Use un conector de datos de terceros en el centro de seguridad & cumplimiento:** Usar un conector de datos personalizado que está disponible en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98861-119">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="98861-120">Una vez que haya configurado y configurado el conector, se conecta al origen de datos de terceros, convierte el contenido de un elemento a un formato de mensaje de correo electrónico y, a continuación, importa el elemento a un buzón en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98861-120">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="98861-121">Actualmente, puede implementar conectores para importar y archivar datos de páginas empresariales de Facebook, cuentas corporativas de Twitter, LinkedIn, Bloomberg y los datos de recursos humanos (HR) de la organización.</span><span class="sxs-lookup"><span data-stu-id="98861-121">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, LinkedIn, Instant Bloomberg, and your organization's human resources (HR) data.</span></span> <span data-ttu-id="98861-122">Para obtener instrucciones paso a paso para configurar uno de estos conectores, consulte:</span><span class="sxs-lookup"><span data-stu-id="98861-122">For the step-by-step instructions to set up one of these connectors, see:</span></span>

   - <span data-ttu-id="98861-123">**Facebook:** [usar un conector para archivar datos de Facebook](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="98861-123">**Facebook:** [Use a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="98861-124">**Twitter:** [usar un conector para archivar datos de Twitter](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="98861-124">**Twitter:** [Use a connector to archive Twitter data](archive-twitter-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="98861-125">**LinkedIn:** [configurar un conector para archivar datos de LinkedIn](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="98861-125">**LinkedIn:** [Set up a connector to archive LinkedIn data](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="98861-126">**Bloomberg instantáneo:** [configurar un conector para archivar datos Instant Bloomberg](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="98861-126">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data](archive-instant-bloomberg-data.md)</span></span>

   - <span data-ttu-id="98861-127">**Datos de recursos humanos:** [configurar un conector para importar datos de recursos humanos](import-hr-data.md)</span><span class="sxs-lookup"><span data-stu-id="98861-127">**HR data:** [Set up a connector to import HR data](import-hr-data.md)</span></span>

- <span data-ttu-id="98861-128">**Trabajar con un socio de Microsoft:** Su organización trabaja con un socio de Microsoft que proporcionará un conector personalizado que se configurará para extraer elementos del origen de datos de terceros de forma periódica y, a continuación, conectarse a la nube de Microsoft mediante una API de terceros e importar dichos elementos a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98861-128">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Microsoft 365.</span></span> <span data-ttu-id="98861-129">El conector de asociados también convierte el contenido de un elemento del origen de datos de terceros en un mensaje de correo electrónico y, a continuación, lo importa a un buzón en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98861-129">The partner connector also converts the content of an item from the third-party data source to an email message and then imports it to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="98861-130">Para obtener una lista de los socios con los que puede trabajar y el proceso paso a paso para este método, vea [trabajar con un partner para archivar datos de terceros en Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="98861-130">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span></span>
