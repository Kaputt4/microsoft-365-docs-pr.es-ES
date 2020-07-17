---
title: Introducción a la directiva predeterminada de DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar el informe para refinar la directiva predeterminada de prevención de pérdida de datos (DLP) de la organización.
ms.openlocfilehash: 7c8f0460f9cd02ee3d26197965f5ea74737ac833
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817619"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="a7c94-103">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="a7c94-103">Get started with the default DLP policy</span></span>

<span data-ttu-id="a7c94-104">Antes de crear la primera Directiva de prevención de pérdida de datos (DLP), DLP ayuda a proteger la información confidencial con una directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a7c94-104">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="a7c94-105">Esta directiva predeterminada y su recomendación (que se muestra a continuación) ayudan a mantener seguro el contenido confidencial mediante una notificación cuando el correo electrónico o los documentos que contienen un número de tarjeta de crédito se han compartido con alguien ajeno a la organización.</span><span class="sxs-lookup"><span data-stu-id="a7c94-105">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="a7c94-106">Verá esta recomendación en la página **principal** del centro de seguridad y &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a7c94-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="a7c94-107">Puede usar este widget para ver rápidamente cuándo y cuánto se ha compartido la información confidencial y, a continuación, refinar la Directiva de DLP predeterminada en solo un clic o dos.</span><span class="sxs-lookup"><span data-stu-id="a7c94-107">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="a7c94-108">También puede editar la Directiva DLP predeterminada en cualquier momento, ya que es totalmente personalizable.</span><span class="sxs-lookup"><span data-stu-id="a7c94-108">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="a7c94-109">Tenga en cuenta que si no ve la recomendación en primer lugar, intente hacer clic en **+ más** en la parte inferior de la sección **recomendada para usted** .</span><span class="sxs-lookup"><span data-stu-id="a7c94-109">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget denominado protección de contenido compartido adicional](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="a7c94-111">Ver el informe y refinar la Directiva de DLP predeterminada</span><span class="sxs-lookup"><span data-stu-id="a7c94-111">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="a7c94-112">Cuando el widget muestre que los usuarios comparten información confidencial con personas de fuera de la organización, elija **refinar la Directiva DLP** en la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="a7c94-112">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="a7c94-113">El informe detallado muestra Cuándo y cuánto contenido que contiene los números de las tarjetas de crédito se ha compartido en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="a7c94-113">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="a7c94-114">Tenga en cuenta que las coincidencias de regla pueden tardar hasta 48 horas en mostrarse en el widget.</span><span class="sxs-lookup"><span data-stu-id="a7c94-114">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="a7c94-115">Para ayudar a proteger la información confidencial, la Directiva de DLP predeterminada:</span><span class="sxs-lookup"><span data-stu-id="a7c94-115">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="a7c94-116">Detecta si el contenido de Exchange, SharePoint y OneDrive que contiene al menos un número de tarjeta de crédito se comparte con personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="a7c94-116">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="a7c94-117">Muestra una sugerencia de directiva y envía una notificación por correo electrónico a los usuarios cuando intentan compartir esta información confidencial con personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="a7c94-117">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="a7c94-118">Para obtener más información sobre estas opciones, vea [enviar notificaciones de correo electrónico y Mostrar sugerencias de directiva para directivas de DLP](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="a7c94-118">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="a7c94-119">Genera informes de actividad detallados para que pueda realizar un seguimiento de cosas como quién ha compartido el contenido con personas de fuera de la organización y cuándo lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="a7c94-119">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="a7c94-120">Puede usar los [informes de DLP](view-the-dlp-reports.md) y los datos del [registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (donde **Activity**  =  **DLP**de actividad) para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="a7c94-120">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="a7c94-121">Para refinar rápidamente la Directiva DLP predeterminada, puede elegir que:</span><span class="sxs-lookup"><span data-stu-id="a7c94-121">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="a7c94-122">Envíe un informe de correo electrónico de incidentes cuando los usuarios compartan esta información confidencial con personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="a7c94-122">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="a7c94-123">Agregar otros usuarios al informe de incidentes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a7c94-123">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="a7c94-124">Bloquee el acceso al contenido que contiene la información confidencial, pero permita al usuario reemplazar y compartir o enviar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a7c94-124">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="a7c94-125">Para obtener más información sobre los informes de incidentes o restringir el acceso, consulte [información general sobre las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a7c94-125">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="a7c94-126">Si desea cambiar estas opciones más adelante, puede editar la Directiva DLP predeterminada en cualquier momento (consulte la sección siguiente).</span><span class="sxs-lookup"><span data-stu-id="a7c94-126">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Configuración del widget con el nombre protección de contenido compartido adicional](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="a7c94-128">Edición de la Directiva de DLP predeterminada</span><span class="sxs-lookup"><span data-stu-id="a7c94-128">Edit the default DLP policy</span></span>

<span data-ttu-id="a7c94-129">Esta Directiva se denomina **Directiva DLP predeterminada** y aparece en **prevención de pérdida de datos** en la página de la **Directiva** del centro de seguridad y &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a7c94-129">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="a7c94-130">Esta directiva es totalmente personalizable, igual que cualquier directiva DLP que se cree a partir de cero.</span><span class="sxs-lookup"><span data-stu-id="a7c94-130">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="a7c94-131">También puede desactivar o eliminar la Directiva para que los usuarios dejen de recibir sugerencias de directiva o notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a7c94-131">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Directiva DLP llamada Directiva DLP predeterminada](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="a7c94-133">Cuando el widget no aparece</span><span class="sxs-lookup"><span data-stu-id="a7c94-133">When the widget does and does not appear</span></span>

<span data-ttu-id="a7c94-134">El widget denominado **protección de contenido compartido adicional** aparece en la sección **recomendada para usted** de la página **principal** del centro de seguridad y &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a7c94-134">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="a7c94-135">Este widget solo aparece cuando:</span><span class="sxs-lookup"><span data-stu-id="a7c94-135">This widget appears only when:</span></span>
  
- <span data-ttu-id="a7c94-136">No hay directivas de prevención de pérdida de datos en el centro de seguridad &amp; y cumplimiento o en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="a7c94-136">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="a7c94-137">Este widget está pensado para ayudarle a empezar a usar DLP, por lo que no aparece si ya tiene directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="a7c94-137">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="a7c94-138">En los últimos 30 días se ha compartido el contenido que contiene menos una tarjeta de crédito con alguien ajeno a su organización.</span><span class="sxs-lookup"><span data-stu-id="a7c94-138">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="a7c94-139">Tenga en cuenta que las coincidencias de regla pueden tardar hasta 48 horas en estar disponibles para el widget, por lo que, una vez detectada la información confidencial compartida de forma externa, puede tardar hasta dos días en aparecer la recomendación.</span><span class="sxs-lookup"><span data-stu-id="a7c94-139">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="a7c94-140">Por último, después de usar el widget para refinar la Directiva de DLP predeterminada, el widget desaparecerá de la página **principal** .</span><span class="sxs-lookup"><span data-stu-id="a7c94-140">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

