---
title: Cómo funciona DLP con el Centro de & seguridad y cumplimiento & Exchange centro de administración
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Obtenga información sobre cómo DLP en el Centro de seguridad & cumplimiento funciona con dlp y reglas de flujo de correo (reglas de transporte) en el centro Exchange administración.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34ddee1c1f0997852b6e59295ab9b630acc3ba3c
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177182"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="2bbaa-103">Cómo funciona DLP entre el Centro de Microsoft 365 cumplimiento y Exchange de administración</span><span class="sxs-lookup"><span data-stu-id="2bbaa-103">How DLP works between the Microsoft 365 Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="2bbaa-104">En Microsoft 365, puede crear una directiva de prevención de pérdida de datos (DLP) en dos centros de administración diferentes:</span><span class="sxs-lookup"><span data-stu-id="2bbaa-104">In Microsoft 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="2bbaa-105">En el Centro de cumplimiento de **Microsoft 365,** puede crear una única directiva DLP para ayudar a proteger el contenido de SharePoint, OneDrive, Exchange, Teams y ahora Dispositivos de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-105">In the **Microsoft 365 Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, Teams, and now Endpoint Devices.</span></span> <span data-ttu-id="2bbaa-106">Se recomienda crear una directiva DLP aquí.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-106">We recommend that you create a DLP policy here.</span></span> <span data-ttu-id="2bbaa-107">Para obtener más información, vea [Data Loss Prevention reference](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2bbaa-107">For more information, see [Data Loss Prevention reference](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="2bbaa-108">En el **Centro Exchange administración,** puede crear una directiva DLP para ayudar a proteger el contenido solo en Exchange.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="2bbaa-109">Esta directiva puede usar Exchange de flujo de correo electrónico (también conocidas como reglas de transporte), por lo que tiene más opciones específicas para controlar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="2bbaa-110">Para obtener más información, vea [DLP en el centro Exchange administración.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="2bbaa-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="2bbaa-111">Las directivas DLP creadas en estos centros de administración funcionan en paralelo: en este tema se explica cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Páginas DLP en el Centro de seguridad y cumplimiento y Exchange centro de administración](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="2bbaa-113">Cómo funciona DLP en el Centro de & seguridad con DLP y reglas de flujo de correo en el Centro de administración de Exchange administración</span><span class="sxs-lookup"><span data-stu-id="2bbaa-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="2bbaa-114">Después de crear una directiva DLP en el Centro de seguridad & cumplimiento, la directiva se implementa en todas las ubicaciones incluidas en la directiva.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="2bbaa-115">Si la directiva incluye Exchange Online, la directiva se sincroniza allí y se aplica exactamente de la misma manera que una directiva DLP creada en el centro de administración Exchange administración.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="2bbaa-116">Si ha creado directivas DLP en el Centro de administración de Exchange, estas directivas seguirán funcionando en paralelo con las directivas de correo electrónico que cree en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="2bbaa-117">Pero tenga en cuenta que las reglas creadas en Exchange centro de administración tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="2bbaa-118">Todas Exchange flujo de correo se procesan primero y, a continuación, se procesan las reglas DLP del Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="2bbaa-119">Esto significa que:</span><span class="sxs-lookup"><span data-stu-id="2bbaa-119">This means that:</span></span>
  
- <span data-ttu-id="2bbaa-120">Los mensajes bloqueados por Exchange flujo de correo no se examinarán mediante las reglas DLP creadas en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>

- <span data-ttu-id="2bbaa-121">DLP no examinará los mensajes que Exchange reglas de flujo de correo o cualquier otro filtro que se ejecute antes de DLP</span><span class="sxs-lookup"><span data-stu-id="2bbaa-121">Messages that are quarantined by Exchange mail flow rules or any other filters run before DLP will not be scanned by DLP</span></span>
    
- <span data-ttu-id="2bbaa-122">Si una regla de flujo de correo de Exchange modifica un mensaje de una manera que hace que coincida con una directiva DLP en el Centro de cumplimiento de & de seguridad , como agregar usuarios externos, las reglas DLP lo detectarán y aplicarán la directiva según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-122">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="2bbaa-123">Tenga en cuenta también que Exchange reglas de flujo de correo que usan la acción "detener el procesamiento" no afectan al procesamiento de las reglas DLP en el Centro de seguridad y cumplimiento de &: aún se procesarán.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-123">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="2bbaa-124">Sugerencias de directiva en el Centro de & seguridad frente al Centro de Exchange administración</span><span class="sxs-lookup"><span data-stu-id="2bbaa-124">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="2bbaa-125">Las sugerencias de directivas pueden funcionar con directivas DLP y reglas de flujo de correo creadas en el Centro de administración de Exchange o con directivas DLP creadas en el Centro de seguridad & cumplimiento, pero no ambas.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-125">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="2bbaa-126">Esto se debe a que estas directivas se almacenan en distintas ubicaciones, pero las sugerencias de directivas solo pueden dibujarse desde una sola ubicación.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-126">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="2bbaa-127">Si ha configurado las sugerencias de directiva en el Centro de administración de Exchange, las sugerencias de directiva que configure en el Centro de seguridad y cumplimiento de & no aparecerán para los usuarios de Outlook en la Web y Outlook 2013 y posteriores hasta que desactive las sugerencias en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-127">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="2bbaa-128">Esto garantiza que las reglas Exchange flujo de correo actuales seguirán funcionando hasta que elija cambiar al Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-128">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="2bbaa-129">Tenga en cuenta que, aunque las sugerencias de directiva solo pueden dibujarse desde una única ubicación, las notificaciones de correo electrónico siempre se envían, incluso si usa directivas DLP en el Centro de seguridad y cumplimiento de & y en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2bbaa-129">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
