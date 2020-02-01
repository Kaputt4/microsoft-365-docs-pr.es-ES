---
title: Vistas de las campañas en ATP de Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre las Vistas de la campaña en la Protección contra amenazas avanzada de Office 365.
ms.openlocfilehash: 65ae346fc4ffdcc502c7f479d7d92753cdb5b5bc
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599767"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="13df7-103">Vistas de la campaña en ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="13df7-103">Campaign Views in Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="13df7-104">Las características descritas en este tema se encuentran actualmente en fase preliminar y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="13df7-104">The features described in this topic are currently in preview, and are subject to change.</span></span>

<span data-ttu-id="13df7-105">Vistas de la campaña es una característica de la Protección contra amenazas avanzada (ATP) del Centro de seguridad y cumplimiento de Office 365 que identifica y categoriza los ataques de suplantación de identidad en el servicio.</span><span class="sxs-lookup"><span data-stu-id="13df7-105">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="13df7-106">Vistas de la campaña puede ayudarle a:</span><span class="sxs-lookup"><span data-stu-id="13df7-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="13df7-107">Investigar y responder eficazmente a los ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="13df7-107">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="13df7-108">Entender mejor el alcance del ataque.</span><span class="sxs-lookup"><span data-stu-id="13df7-108">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="13df7-109">Proporcionar información a los responsables de la toma de decisiones.</span><span class="sxs-lookup"><span data-stu-id="13df7-109">Show value to decision makers.</span></span>

<span data-ttu-id="13df7-110">La característica Vistas de la campaña le permite obtener una perspectiva general del ataque más completa y más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="13df7-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="13df7-111">¿Qué es una campaña?</span><span class="sxs-lookup"><span data-stu-id="13df7-111">What is a campaign?</span></span>

<span data-ttu-id="13df7-112">Una campaña es un ataque de correo electrónico coordinado contra una o varias organizaciones.</span><span class="sxs-lookup"><span data-stu-id="13df7-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="13df7-113">Hoy en día, los ataques de correo electrónico de robo de credenciales y datos empresariales son un negocio lucrativo y extendido.</span><span class="sxs-lookup"><span data-stu-id="13df7-113">Today, email attacks that steal credentials and company data are a big and lucrative business.</span></span> <span data-ttu-id="13df7-114">A pesar de los esfuerzos por aumentar las tecnologías para detener los ataques, los atacantes son lo suficientemente sofisticados como para modificar sus métodos y garantizar que sigan siendo eficaces.</span><span class="sxs-lookup"><span data-stu-id="13df7-114">As technologies increase in an effort to stop attacks, attackers are sophisticated enough to modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="13df7-115">Para identificar las campañas, Microsoft aprovecha la experiencia y la gran cantidad de datos de protección contra suplantación de identidades, correo electrónico no deseado y malware que ha adquirido con el servicio de Office 365 en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="13df7-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data and experience across the entire Office 365 service world-wide to identify campaigns.</span></span> <span data-ttu-id="13df7-116">La información del ataque se analiza y clasifica en función de varios factores.</span><span class="sxs-lookup"><span data-stu-id="13df7-116">The attack information is analyzed and classified according to several factors.</span></span> <span data-ttu-id="13df7-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="13df7-117">For example:</span></span>

- <span data-ttu-id="13df7-118">**Origen del ataque**: direcciones IP de origen y dominios de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="13df7-118">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="13df7-119">**Propiedades del mensaje del ataque**: contenido, estilo y tono de los mensajes del ataque.</span><span class="sxs-lookup"><span data-stu-id="13df7-119">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="13df7-120">**Los destinatarios del ataque**: dominios de destinatarios, funciones de trabajo de los destinatarios (administradores, ejecutivos, etc.), tipos de empresa (grandes, pequeñas, públicas, privadas, etc.) y sectores.</span><span class="sxs-lookup"><span data-stu-id="13df7-120">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="13df7-121">**Carga del ataque**: vínculos o datos adjuntos malintencionados u otras cargas.</span><span class="sxs-lookup"><span data-stu-id="13df7-121">**Attack payload**: Malicious links, attachments, or other payloads.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="13df7-122">Vistas de la campaña en el Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="13df7-122">Campaign Views the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="13df7-123">Vistas de la campaña está disponible en el [Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="13df7-123">Campaign Views is available in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) at the following locations:</span></span>

- <span data-ttu-id="13df7-124">**Administración de amenazas** \> **Explorador** \> **Ver** \> **Suplantación de identidad** \> **Campaña principal (versión preliminar)**</span><span class="sxs-lookup"><span data-stu-id="13df7-124">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Top campaign (Preview)**</span></span>

- <span data-ttu-id="13df7-125">**Administración de amenazas** \> **Explorador** \> **Ver** \> **Todo el correo electrónico** \> **Campaña principal (versión preliminar)**</span><span class="sxs-lookup"><span data-stu-id="13df7-125">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Top campaign (Preview)**</span></span>

![Información general de las campañas en el Centro de seguridad y cumplimiento](../media/campaigns-overview.png)

> [!TIP]
> <span data-ttu-id="13df7-127">Actualmente, el único filtro que está disponible es el de intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="13df7-127">Currently, the only filtering that's available is the date range.</span></span> <span data-ttu-id="13df7-128">Si no ve ningún dato de la campaña, pruebe a cambiar el intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="13df7-128">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="13df7-129">La página de información general muestra la siguiente información sobre la campaña:</span><span class="sxs-lookup"><span data-stu-id="13df7-129">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="13df7-130">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="13df7-130">**Name**</span></span>

- <span data-ttu-id="13df7-131">**Asunto de ejemplo**: línea de asunto de uno de los mensajes de la campaña.</span><span class="sxs-lookup"><span data-stu-id="13df7-131">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="13df7-132">Tenga en cuenta que no _todos_ los mensajes de la campaña tienen necesariamente esta línea de asunto.</span><span class="sxs-lookup"><span data-stu-id="13df7-132">Note that _all_ the messages in the campaign will not necessarily have this same subject line.</span></span>

- <span data-ttu-id="13df7-133">**Tipo**: actualmente, este valor será siempre **Suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="13df7-133">**Type**: Currently, this value will always be **Phish**.</span></span>

- <span data-ttu-id="13df7-134">**Subtipo**: si está disponible, la marca a la que la campaña está dirigiendo los ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="13df7-134">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="13df7-135">Cuando la detección se lleva a cabo por medio de la tecnología de ATP, se agrega el prefijo **ATP-** al valor del subtipo.</span><span class="sxs-lookup"><span data-stu-id="13df7-135">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="13df7-136">**Destinatarios**: el número de usuarios a los que se ha dirigido esta campaña.</span><span class="sxs-lookup"><span data-stu-id="13df7-136">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="13df7-137">**Entregados**: el número de usuarios que han recibido mensajes de esta campaña en sus buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="13df7-137">**Delivered**: The number of users that received messages from this campaign into their Inbox.</span></span>

- <span data-ttu-id="13df7-138">**Id.**: el identificador único de la campaña.</span><span class="sxs-lookup"><span data-stu-id="13df7-138">**ID**: A unique identifier for the campaign.</span></span>

<span data-ttu-id="13df7-139">Al hacer clic en el nombre de una campaña, se muestran los detalles de la campaña en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="13df7-139">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="13df7-140">Detalles de la campaña</span><span class="sxs-lookup"><span data-stu-id="13df7-140">Campaign details</span></span>

<span data-ttu-id="13df7-141">En la vista de detalles de la campaña se muestra una gran cantidad de información sobre la campaña:</span><span class="sxs-lookup"><span data-stu-id="13df7-141">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="13df7-142">Información de la campaña:</span><span class="sxs-lookup"><span data-stu-id="13df7-142">Campaign information:</span></span>

  - <span data-ttu-id="13df7-143">**Id.**: el mismo identificador único de la campaña de la pantalla de información general.</span><span class="sxs-lookup"><span data-stu-id="13df7-143">**ID**: The same unique identifier of the campaign from the overview screen.</span></span>

  - <span data-ttu-id="13df7-144">**Iniciada** y **Finalizada**: el filtro del intervalo de fechas que se ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="13df7-144">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="13df7-145">**Impacto**: el número de mensajes enviados en el intervalo de fechas que se ha seleccionado, cuántos se han entregado en la bandeja de entrada y cuántos usuarios han hecho clic en la URL de carga del mensaje de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="13df7-145">**Impact**: the number of messages sent in the date range you selected, how many were "inboxed" (that is, delivered to the Inbox), and how many users clicked on the URL payload in the phishing message.</span></span>

  - <span data-ttu-id="13df7-146">Una escala de tiempo de la actividad de la campaña: cuándo comenzó y finalizó la campaña y el volumen de mensajes a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="13df7-146">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="13df7-147">Flujo de la campaña</span><span class="sxs-lookup"><span data-stu-id="13df7-147">Campaign flow</span></span>

<span data-ttu-id="13df7-148">Los detalles importantes sobre la campaña se presentan en un diagrama de flujo horizontal (conocido como diagrama de _Sankey_) en la sección **Flujo**.</span><span class="sxs-lookup"><span data-stu-id="13df7-148">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="13df7-149">Estos detalles pueden ayudarle a comprender los elementos de la campaña y su posible impacto en la organización.</span><span class="sxs-lookup"><span data-stu-id="13df7-149">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Detalles de la campaña que no contienen clics del usuario en la URL.](../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="13df7-151">Si coloca el puntero del mouse sobre una de las bandas horizontales del diagrama, verá el número de mensajes relacionados (por ejemplo, mensajes de una IP de origen en particular, mensajes de la dirección IP de origen con el dominio de remitente especificado, etc.).</span><span class="sxs-lookup"><span data-stu-id="13df7-151">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="13df7-152">El diagrama contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="13df7-152">The diagram contains the following information:</span></span>

- <span data-ttu-id="13df7-153">**IP de remitentes**</span><span class="sxs-lookup"><span data-stu-id="13df7-153">**Sender IPs**</span></span>

- <span data-ttu-id="13df7-154">**Dominios de remitente**</span><span class="sxs-lookup"><span data-stu-id="13df7-154">**Sender domains**</span></span>

- <span data-ttu-id="13df7-155">**Veredictos de filtro**: los valores que se muestran aquí están relacionados con los datos de protección contra suplantación de identidad y correo no deseado disponibles, tal y como se describe en [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="13df7-155">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="13df7-156">Aquí son de especial interés los valores **Permitidos por el inquilino**, que significa que determinada configuración de la organización permitió que pasara un mensaje de que de otra forma habría sido bloqueado por el servicio (por ejemplo, un dominio de la lista de remitentes permitidos).</span><span class="sxs-lookup"><span data-stu-id="13df7-156">Of great interest here are the values **Tenant Allow**, which means a configured setting in the organization allowed a message through that would have been otherwise blocked by the service (for example, a domain in the Allowed Senders list).</span></span>

  - <span data-ttu-id="13df7-157">**Bloqueados por el inquilino**: este valor indica que determinada configuración de la organización (por ejemplo, una entrada de dominio de la [lista de remitentes bloqueados](create-block-sender-lists-in-office-365.md)) detectó el mensaje y determinó su ubicación de entrega.</span><span class="sxs-lookup"><span data-stu-id="13df7-157">**Tenant Block**: This value indicates that a setting in your organization (for example, a domain entry in the [Blocked Senders list](create-block-sender-lists-in-office-365.md)) both detected the message and determined where it was delivered.</span></span> <span data-ttu-id="13df7-158">En el caso de los mensajes que no se hayan puesto en cuarentena, revise la configuración de remitentes bloqueados para determinar por qué se entregó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="13df7-158">For messages that weren't quarantined, review your blocked senders settings to determine why the message was delivered.</span></span>

  - <span data-ttu-id="13df7-159">**Detectados**</span><span class="sxs-lookup"><span data-stu-id="13df7-159">**Detected**</span></span>

  - <span data-ttu-id="13df7-160">**Permitidos por el inquilino**</span><span class="sxs-lookup"><span data-stu-id="13df7-160">**Tenant Allow**</span></span>

- <span data-ttu-id="13df7-161">**Ubicaciones de entrega**: probablemente querrá investigar los mensajes que se entregaron a los destinatarios (ya sea en la bandeja de entrada o en la carpeta de correo no deseado), incluso aunque los usuarios no hayan hecho clic en la URL de carga del mensaje.</span><span class="sxs-lookup"><span data-stu-id="13df7-161">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="13df7-162">También puede eliminar los mensajes en cuarentena de la [Cuarentena de mensajes de correo electrónico en Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="13df7-162">You can also remove the quarantined messages from [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="13df7-163">**Carpeta de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="13df7-163">**Junk folder**</span></span>

  - <span data-ttu-id="13df7-164">**Cuarentena**</span><span class="sxs-lookup"><span data-stu-id="13df7-164">**Quarantine**</span></span>

  - <span data-ttu-id="13df7-165">**Bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="13df7-165">**Inbox**</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="13df7-166">Clics de URL</span><span class="sxs-lookup"><span data-stu-id="13df7-166">URL clicks</span></span>

<span data-ttu-id="13df7-167">Siempre existe la posibilidad de que los destinatarios interactúen con los mensajes entregados en su bandeja de entrada o en su carpeta de correo electrónico no deseado (es decir, que hagan clic en la URL malintencionada del mensaje).</span><span class="sxs-lookup"><span data-stu-id="13df7-167">There's always the chance that messages delivered to the recipient's Inbox or Junk Email folder can be acted upon by the user (that is, user will click on the malicious URL in the message).</span></span> <span data-ttu-id="13df7-168">Si no lo han hecho, es un pequeño éxito, aunque tendrá que determinar por qué se entregó en sus buzones el mensaje perjudicial en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="13df7-168">If they haven't, that's a small measure of success, although you certainly need to determine why the harmful message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="13df7-169">Si un usuario hace clic en la URL malintencionada, las acciones se muestran en el área de **Clics de URL** del diagrama.</span><span class="sxs-lookup"><span data-stu-id="13df7-169">If a user has clicked on the malicious URL, the actions are displayed in the **URL clicks** area of the diagram.</span></span>

![Detalles de la campaña que contienen clics del usuario en la URL.](../media/campaign-details-with-recipient-actions.png)

- <span data-ttu-id="13df7-171">**Bloqueo de Vínculos seguros**: este valor indica que el destinatario hizo clic en la URL de carga del mensaje, pero las directivas de [Vínculos seguros de ATP](atp-safe-links.md) de la organización la bloquearon.</span><span class="sxs-lookup"><span data-stu-id="13df7-171">**Safe Links Block**: This value indicates the recipient clicked on the payload URL in the message, but it was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="13df7-172">**Anulación de bloqueo de Vínculos seguros**: este valor también indica que el destinatario hizo clic en la URL de carga del mensaje y las directivas de Vínculos seguros de ATP intentaron detenerla, pero se permitió la invalidación del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="13df7-172">**Safe Links Block Override**: This value also indicates the recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="13df7-173">Debe investigar las [directivas de Vínculos seguros](set-up-atp-safe-links-policies.md) de la organización para ver por qué los usuarios pueden invalidar el veredicto de Vínculos seguros y hacer clic en direcciones URL malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="13df7-173">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and click on malicious URLs.</span></span>

### <a name="tabs"></a><span data-ttu-id="13df7-174">Pestañas</span><span class="sxs-lookup"><span data-stu-id="13df7-174">Tabs</span></span>

<span data-ttu-id="13df7-175">En la vista de detalles de la campaña hay varias pestañas que permiten investigar más a fondo la campaña.</span><span class="sxs-lookup"><span data-stu-id="13df7-175">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="13df7-176">**Clics de URL**: si no se hizo clic en la URL de carga del mensaje de suplantación de identidad, esta sección estará en blanco.</span><span class="sxs-lookup"><span data-stu-id="13df7-176">**URL Clicks**: If the payload URL in the phishing message wasn't clicked, this section will be blank.</span></span> <span data-ttu-id="13df7-177">Si un usuario pudo hacer clic en la URL,</span><span class="sxs-lookup"><span data-stu-id="13df7-177">If a user was able to click on the URL, you</span></span>

  - <span data-ttu-id="13df7-178">**Usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="13df7-178">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="13df7-179">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="13df7-179">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="13df7-180">**Hora del clic**</span><span class="sxs-lookup"><span data-stu-id="13df7-180">**Click Time**</span></span>

  - <span data-ttu-id="13df7-181">**Acción del clic**</span><span class="sxs-lookup"><span data-stu-id="13df7-181">**Click Action**</span></span>

- <span data-ttu-id="13df7-182">**IP de remitentes**</span><span class="sxs-lookup"><span data-stu-id="13df7-182">**Sender IPs**</span></span>

  - <span data-ttu-id="13df7-183">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="13df7-183">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="13df7-184">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="13df7-184">**Total Count**</span></span>

  - <span data-ttu-id="13df7-185">**Recuento de entregados en bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="13df7-185">**Inboxed Count**</span></span>

  - <span data-ttu-id="13df7-186">**Recuento de bloqueados**</span><span class="sxs-lookup"><span data-stu-id="13df7-186">**Blocked Count**</span></span>

  - <span data-ttu-id="13df7-187">**Aprobados por SPF**</span><span class="sxs-lookup"><span data-stu-id="13df7-187">**SPF Passed**</span></span>

- <span data-ttu-id="13df7-188">**Remitentes**</span><span class="sxs-lookup"><span data-stu-id="13df7-188">**Senders**</span></span>

  - <span data-ttu-id="13df7-189">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="13df7-189">**Sender**</span></span>

  - <span data-ttu-id="13df7-190">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="13df7-190">**Total Count**</span></span>

  - <span data-ttu-id="13df7-191">**Recuento de entregados en bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="13df7-191">**Inboxed Count**</span></span>

  - <span data-ttu-id="13df7-192">**Recuento de bloqueados**</span><span class="sxs-lookup"><span data-stu-id="13df7-192">**Blocked Count**</span></span>

  - <span data-ttu-id="13df7-193">**Aprobados por DKIM**</span><span class="sxs-lookup"><span data-stu-id="13df7-193">**DKIM Passed**</span></span>

  - <span data-ttu-id="13df7-194">**Aprobados por DMARC**</span><span class="sxs-lookup"><span data-stu-id="13df7-194">**DMARC Passed**</span></span>

- <span data-ttu-id="13df7-195">**Cargas**</span><span class="sxs-lookup"><span data-stu-id="13df7-195">**Payloads**</span></span>

  - <span data-ttu-id="13df7-196">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="13df7-196">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="13df7-197">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="13df7-197">**Total Count**</span></span>

<span data-ttu-id="13df7-198"><sup>\*</sup> Al hacer clic en este valor, se abre un nuevo control flotante que contiene más detalles sobre el elemento especificado (usuario, URL, etc.) en la parte superior de la vista de detalles de la campaña.</span><span class="sxs-lookup"><span data-stu-id="13df7-198"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="13df7-199">Para volver a la vista de detalles de la campaña, haga clic en **Hecho** en el nuevo control flotante.</span><span class="sxs-lookup"><span data-stu-id="13df7-199">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="13df7-200">Botones</span><span class="sxs-lookup"><span data-stu-id="13df7-200">Buttons</span></span>

<span data-ttu-id="13df7-201">Los botones de la vista de detalles de la campaña le permiten usar todo el potencial del Explorador de amenazas para investigar más a fondo la campaña.</span><span class="sxs-lookup"><span data-stu-id="13df7-201">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="13df7-202">**Explorar campaña**: abre una nueva pestaña de búsqueda del Explorador de amenazas con el valor **Id. de campaña** como filtro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="13df7-202">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="13df7-203">**Explorar mensajes de la bandeja de entrada**: abre una nueva pestaña de búsqueda del Explorador de amenazas con **Id. de campaña** y **Ubicación de entrega: Bandeja de entrada** como filtro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="13df7-203">**Explore Inbox messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
