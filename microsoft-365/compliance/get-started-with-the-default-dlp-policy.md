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
description: Obtenga información sobre cómo usar el informe para refinar la directiva predeterminada de prevención de pérdida de datos (DLP) de su organización.
ms.openlocfilehash: 4530e570f0ce593a7d2cb62acc28dfa4e1658df0
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114088"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="4138a-103">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="4138a-103">Get started with the default DLP policy</span></span>

<span data-ttu-id="4138a-104">Antes incluso de crear la primera directiva de prevención de pérdida de datos (DLP), DLP ayuda a proteger la información confidencial con una directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4138a-104">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="4138a-105">Esta directiva predeterminada y su recomendación (que se muestra a continuación) ayudan a proteger el contenido confidencial al notificarle cuándo el correo electrónico o los documentos que contienen un número de tarjeta de crédito se han compartido con alguien de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="4138a-105">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="4138a-106">Verá esta recomendación en la página **principal** del Centro de &amp; seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4138a-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4138a-107">Puede usar este widget para ver rápidamente cuándo y cuánta información confidencial se ha compartido y, a continuación, refinar la directiva DLP predeterminada en uno o dos clics.</span><span class="sxs-lookup"><span data-stu-id="4138a-107">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="4138a-108">También puede editar la directiva DLP predeterminada en cualquier momento porque es totalmente personalizable.</span><span class="sxs-lookup"><span data-stu-id="4138a-108">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="4138a-109">Tenga en cuenta que si no ve la recomendación al principio, intente hacer clic en **+Más** en la parte inferior de la sección Recomendado **para usted.**</span><span class="sxs-lookup"><span data-stu-id="4138a-109">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget denominado Proteger aún más el contenido compartido](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="4138a-111">Ver el informe y refinar la directiva DLP predeterminada</span><span class="sxs-lookup"><span data-stu-id="4138a-111">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="4138a-112">Cuando el widget le muestre que los usuarios han compartido información confidencial con personas ajenas a su organización, elija **Refinar** directiva DLP en la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="4138a-112">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="4138a-113">El informe detallado muestra cuándo y cuánto contenido que contiene números de tarjeta de crédito se compartió en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="4138a-113">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="4138a-114">Ten en cuenta que las coincidencias de reglas pueden tardar hasta 48 horas en aparecer en el widget.</span><span class="sxs-lookup"><span data-stu-id="4138a-114">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="4138a-115">Para ayudar a proteger la información confidencial, la directiva DLP predeterminada:</span><span class="sxs-lookup"><span data-stu-id="4138a-115">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="4138a-116">Detecta cuándo el contenido de Exchange, SharePoint y OneDrive que contiene al menos un número de tarjeta de crédito se comparte con personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="4138a-116">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="4138a-117">Muestra una sugerencia de directiva y envía una notificación por correo electrónico a los usuarios cuando intentan compartir esta información confidencial con personas ajenas a su organización.</span><span class="sxs-lookup"><span data-stu-id="4138a-117">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="4138a-118">Para obtener más información sobre estas opciones, vea Enviar notificaciones [por correo electrónico y mostrar sugerencias de directivas para directivas DLP](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="4138a-118">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="4138a-119">Genera informes de actividad detallados para que pueda realizar un seguimiento de cosas como quién compartió el contenido con personas ajenas a su organización y cuándo lo hizo.</span><span class="sxs-lookup"><span data-stu-id="4138a-119">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="4138a-120">Puede usar los informes [DLP](view-the-dlp-reports.md) y los datos de [registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (donde **DLP** de  =  **actividad)** para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="4138a-120">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="4138a-121">Para refinar rápidamente la directiva DLP predeterminada, puede elegir tenerla:</span><span class="sxs-lookup"><span data-stu-id="4138a-121">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="4138a-122">Envíe un correo electrónico de informe de incidentes cuando los usuarios compartan esta información confidencial con personas ajenas a su organización.</span><span class="sxs-lookup"><span data-stu-id="4138a-122">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="4138a-123">Agregue otros usuarios al informe de incidentes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4138a-123">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="4138a-124">Bloquear el acceso al contenido que contiene la información confidencial, pero permitir que el usuario invalide y comparta o envíe si es necesario.</span><span class="sxs-lookup"><span data-stu-id="4138a-124">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="4138a-125">Para obtener más información sobre los informes de incidentes o restringir el acceso, vea [Referencia de prevención de pérdida de datos](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4138a-125">For more information on incident reports or restricting access, see [Data loss prevention reference](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="4138a-126">Si quieres cambiar estas opciones más adelante, puedes editar la directiva DLP predeterminada en cualquier momento: consulta la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="4138a-126">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Configuración para el widget denominado Proteger aún más el contenido compartido](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="4138a-128">Editar la directiva DLP predeterminada</span><span class="sxs-lookup"><span data-stu-id="4138a-128">Edit the default DLP policy</span></span>

<span data-ttu-id="4138a-129">Esta directiva se denomina **Directiva DLP predeterminada** y aparece en **Prevención de pérdida de** datos en la página **Directiva** del Centro de cumplimiento &amp; de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4138a-129">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4138a-130">Esta directiva es totalmente personalizable, igual que cualquier directiva DLP que cree usted mismo desde cero.</span><span class="sxs-lookup"><span data-stu-id="4138a-130">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="4138a-131">También puede desactivar o eliminar la directiva para que los usuarios ya no reciban sugerencias de directiva ni notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4138a-131">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Directiva DLP denominada Directiva DLP predeterminada](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="4138a-133">Cuando el widget lo hace y no aparece</span><span class="sxs-lookup"><span data-stu-id="4138a-133">When the widget does and does not appear</span></span>

<span data-ttu-id="4138a-134">El widget denominado Proteger aún  más el contenido **compartido** aparece en la sección Recomendado para usted de la página **principal** del Centro de seguridad y &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4138a-134">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4138a-135">Este widget solo aparece cuando:</span><span class="sxs-lookup"><span data-stu-id="4138a-135">This widget appears only when:</span></span>
  
- <span data-ttu-id="4138a-136">No hay directivas de prevención de pérdida de datos en el Centro de &amp; seguridad y cumplimiento Exchange centro de administración.</span><span class="sxs-lookup"><span data-stu-id="4138a-136">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="4138a-137">Este widget está pensado para ayudarle a empezar con DLP, por lo que no aparece si ya tiene directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="4138a-137">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="4138a-138">El contenido que contiene al menos una tarjeta de crédito se ha compartido con alguien de fuera de la organización en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="4138a-138">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="4138a-139">Tenga en cuenta que las coincidencias de reglas pueden tardar hasta 48 horas en estar disponibles para el widget, por lo que después de detectar información confidencial compartida externamente, la recomendación puede tardar hasta dos días.</span><span class="sxs-lookup"><span data-stu-id="4138a-139">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="4138a-140">Por último, después de usar el widget para refinar la directiva DLP predeterminada, el widget desaparece de la **página principal.**</span><span class="sxs-lookup"><span data-stu-id="4138a-140">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

