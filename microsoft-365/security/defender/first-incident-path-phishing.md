---
title: Ejemplo de un ataque de correo electrónico de suplantación de identidad
description: Paso a paso por un análisis de ejemplo de un ataque de suplantación de identidad.
keywords: incidentes, alertas, investigar, correlación, ataque, equipos, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fb3656a9d3f67d979c012d9cc316a10e65a72042
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114786"
---
# <a name="example-of-a-phishing-email-attack"></a><span data-ttu-id="779f4-104">Ejemplo de un ataque de correo electrónico de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="779f4-104">Example of a phishing email attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="779f4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="779f4-105">**Applies to:**</span></span>
- <span data-ttu-id="779f4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="779f4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="779f4-107">Microsoft 365 Defender puede ayudar a detectar datos adjuntos malintencionados entregados por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="779f4-107">Microsoft 365 Defender can help detect malicious attachments delivered via email.</span></span> <span data-ttu-id="779f4-108">Dado que [el Centro](https://protection.office.com/) de seguridad y cumplimiento de Office 365 se integra con Microsoft 365 Defender, los analistas de seguridad pueden tener visibilidad de las amenazas procedentes de Office 365, como los datos adjuntos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="779f4-108">Since the [Office 365 Security and Compliance Center](https://protection.office.com/) integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Office 365, such as through email attachments.</span></span>

<span data-ttu-id="779f4-109">Por ejemplo, a un analista se le asignó un incidente de varias fases.</span><span class="sxs-lookup"><span data-stu-id="779f4-109">For example, an analyst was assigned a multi-stage incident.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Ejemplo de un incidente de varias fases"::: 

<span data-ttu-id="779f4-111">En la **pestaña** Alertas del incidente, se muestran las alertas de Defender Office 365 y Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="779f4-111">In the **Alerts** tab of the incident, alerts from Defender for Office 365 and Microsoft Cloud App Security are displayed.</span></span> <span data-ttu-id="779f4-112">El analista puede profundizar en defender para obtener Office 365 mediante la selección de las alertas de mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="779f4-112">The analyst can drill down into the Defender for Office 365 alerts by selecting the email messages alerts.</span></span> <span data-ttu-id="779f4-113">Los detalles de la alerta se muestran en el panel lateral.</span><span class="sxs-lookup"><span data-stu-id="779f4-113">The details of the alert are displayed on the side pane.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Ejemplo de una alerta de correo electrónico":::
 
<span data-ttu-id="779f4-115">Al desplazarse hacia abajo más adelante, se muestra más información, que muestra los archivos malintencionados y el usuario que se ha afectado.</span><span class="sxs-lookup"><span data-stu-id="779f4-115">By scrolling down further, more information is displayed, showing the malicious files and user that was impacted.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Ejemplo de impacto de usuario y archivo de una alerta de correo electrónico":::
  
<span data-ttu-id="779f4-117">Al seleccionar **Abrir página de alertas,** selecciona el vínculo para ver la alerta específica en la que se puede ver información diversa con mayor detalle.</span><span class="sxs-lookup"><span data-stu-id="779f4-117">Selecting **Open alert page** takes you to the specific alert where various information can be viewed in greater detail by selecting the link.</span></span> <span data-ttu-id="779f4-118">El mensaje de correo electrónico real se puede ver seleccionando Ver **mensajes en el Explorador** hacia la parte inferior del panel.</span><span class="sxs-lookup"><span data-stu-id="779f4-118">The actual email message can be viewed by selecting **View messages in Explorer** toward the bottom of the panel.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Ejemplo de los detalles de una alerta"::: 

<span data-ttu-id="779f4-120">Esto lleva al analista a la página Administración de amenazas donde se muestran el asunto de correo electrónico, el destinatario, el remitente y otra información.</span><span class="sxs-lookup"><span data-stu-id="779f4-120">This takes the analyst to the Threat Management page where the email Subject, Recipient, Sender, and other information are displayed.</span></span> <span data-ttu-id="779f4-121">**ZAP** en **Acciones especiales** indica al analista que se implementó la característica de purga automática de hora cero.</span><span class="sxs-lookup"><span data-stu-id="779f4-121">**ZAP** under **Special Actions** tells the analyst that the Zero-hour auto purge feature was implemented.</span></span> <span data-ttu-id="779f4-122">ZAP detecta y quita automáticamente mensajes malintencionados y de correo no deseado de los buzones de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="779f4-122">ZAP automatically detects and removes malicious and spam messages from mailboxes across the organization.</span></span> <span data-ttu-id="779f4-123">Para obtener más información, vea [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="779f4-123">For more information, see [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="779f4-124">Otras acciones se pueden realizar en mensajes específicos seleccionando **Acciones**.</span><span class="sxs-lookup"><span data-stu-id="779f4-124">Other actions can be taken on specific messages by selecting **Actions**.</span></span> 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Ejemplo de las otras acciones que se pueden realizar en los mensajes de correo electrónico"::: 

## <a name="next-step"></a><span data-ttu-id="779f4-126">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="779f4-126">Next step</span></span>

<span data-ttu-id="779f4-127">Consulta la [ruta de investigación de ataques basada](first-incident-path-identity.md) en identidades.</span><span class="sxs-lookup"><span data-stu-id="779f4-127">See the [identity-based attack](first-incident-path-identity.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="779f4-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="779f4-128">See also</span></span>

- [<span data-ttu-id="779f4-129">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="779f4-129">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="779f4-130">Analizar incidentes</span><span class="sxs-lookup"><span data-stu-id="779f4-130">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="779f4-131">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="779f4-131">Manage incidents</span></span>](manage-incidents.md)
