---
title: Vistas de campañas en ATP
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
ms.openlocfilehash: 69b11319ffb033b628e59abac931b6a3f30d082c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637823"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="0c7ac-103">Vistas de campañas en ATP</span><span class="sxs-lookup"><span data-stu-id="0c7ac-103">Campaign Views in ATP</span></span>

<span data-ttu-id="0c7ac-104">Las vistas de campañas son una característica de la protección contra amenazas avanzada (ATP) en el centro de seguridad & cumplimiento que identifica y categoriza los ataques de suplantación de identidad (phishing) en el servicio.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="0c7ac-105">Vistas de la campaña puede ayudarle a:</span><span class="sxs-lookup"><span data-stu-id="0c7ac-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="0c7ac-106">Investigar y responder eficazmente a los ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="0c7ac-107">Entender mejor el alcance del ataque.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="0c7ac-108">Proporcionar información a los responsables de la toma de decisiones.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-108">Show value to decision makers.</span></span>

<span data-ttu-id="0c7ac-109">La característica Vistas de la campaña le permite obtener una perspectiva general del ataque más completa y más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="0c7ac-110">¿Qué es una campaña?</span><span class="sxs-lookup"><span data-stu-id="0c7ac-110">What is a campaign?</span></span>

<span data-ttu-id="0c7ac-111">Una campaña es un ataque de correo electrónico coordinado contra una o varias organizaciones.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="0c7ac-112">Los ataques de correo electrónico que roban credenciales y datos de la empresa son un sector importante y lucrativo.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="0c7ac-113">A medida que las tecnologías aumentan en un esfuerzo por detener los ataques, los atacantes modifican sus métodos en un esfuerzo para garantizar un éxito continuo.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="0c7ac-114">Microsoft aprovecha la gran cantidad de datos contra phishing, contra correo electrónico no deseado y antimalware en todo el servicio para ayudarle a identificar las campañas.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="0c7ac-115">Analizamos y clasificamos la información de ataques de acuerdo con varios factores.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="0c7ac-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c7ac-116">For example:</span></span>

- <span data-ttu-id="0c7ac-117">**Origen del ataque**: direcciones IP de origen y dominios de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="0c7ac-118">**Propiedades del mensaje del ataque**: contenido, estilo y tono de los mensajes del ataque.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="0c7ac-119">**Los destinatarios del ataque**: dominios de destinatarios, funciones de trabajo de los destinatarios (administradores, ejecutivos, etc.), tipos de empresa (grandes, pequeñas, públicas, privadas, etc.) y sectores.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="0c7ac-120">**Carga de ataques**: vínculos malintencionados, datos adjuntos u otras cargas en los mensajes de ataque.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="0c7ac-121">Una campaña puede ser de corta duración o puede abarcar varios días, semanas o meses con períodos activos e inactivos.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="0c7ac-122">Es posible que se inicie una campaña en su organización específica o que la organización forme parte de una campaña más grande en varias compañías.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="0c7ac-123">Vistas de campaña el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="0c7ac-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="0c7ac-124">Las vistas de campaña están disponibles en el [centro de seguridad & cumplimiento](https://protection.office.com) en las **campañas**de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![Información general de las campañas en el Centro de seguridad y cumplimiento](../../media/campaigns-overview.png)

<span data-ttu-id="0c7ac-126">También puede obtener acceso a la vista campañas desde:</span><span class="sxs-lookup"><span data-stu-id="0c7ac-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="0c7ac-127">**Threat management** \> **Explorer** Explorador \> de administración de amenazas **Ver** \> **campañas**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="0c7ac-128">**Threat management** \> **Explorer** Explorador \> de administración de amenazas **Ver** \> **todas las** \> **campañas** de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="0c7ac-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="0c7ac-129">Si no ve ningún dato de la campaña, pruebe a cambiar el intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="0c7ac-130">La página de información general muestra la siguiente información sobre la campaña:</span><span class="sxs-lookup"><span data-stu-id="0c7ac-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="0c7ac-131">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-131">**Name**</span></span>

- <span data-ttu-id="0c7ac-132">**Asunto de ejemplo**: línea de asunto de uno de los mensajes de la campaña.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="0c7ac-133">Tenga en cuenta que todos los mensajes de la campaña no tendrán necesariamente el mismo asunto.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="0c7ac-134">**Tipo**: Actualmente, este valor es siempre **phish**.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="0c7ac-135">**Subtipo**: si está disponible, la marca a la que la campaña está dirigiendo los ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="0c7ac-136">Cuando la tecnología ATP controla la detección, el prefijo **ATP-** se agrega al valor SubType.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="0c7ac-137">**Destinatarios**: el número de usuarios a los que se ha dirigido esta campaña.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="0c7ac-138">**Bandeja de entrada**: el número de usuarios que recibieron mensajes de esta campaña en su bandeja de entrada (no se entregaron a correo no deseado).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="0c7ac-139">**Haga clic en**: el número de usuarios que hizo clic en la dirección URL en el mensaje de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="0c7ac-140">**Tasa de clic**: porcentaje calculado con "se ha**pulsado en** / la**bandeja de entrada**".</span><span class="sxs-lookup"><span data-stu-id="0c7ac-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="0c7ac-141">Este valor es un indicador de la efectividad de la campaña y de si los destinatarios pudieron identificar el mensaje como suplantación de identidad (phishing) y evitar hacer clic en la dirección URL de carga.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="0c7ac-142">**Visitado**: el número de usuarios que se han realizado realmente a través del sitio web de carga.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="0c7ac-143">Si hay valores en los que se ha **pulsado** , pero los vínculos seguros han bloqueado el acceso al sitio web, este valor será cero.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="0c7ac-144">Al hacer clic en el nombre de una campaña, se muestran los detalles de la campaña en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="0c7ac-145">Detalles de la campaña</span><span class="sxs-lookup"><span data-stu-id="0c7ac-145">Campaign details</span></span>

<span data-ttu-id="0c7ac-146">En la vista de detalles de la campaña se muestra una gran cantidad de información sobre la campaña:</span><span class="sxs-lookup"><span data-stu-id="0c7ac-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="0c7ac-147">Información de la campaña:</span><span class="sxs-lookup"><span data-stu-id="0c7ac-147">Campaign information:</span></span>

  - <span data-ttu-id="0c7ac-148">**ID**: el identificador único de la campaña.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="0c7ac-149">**Iniciada** y **Finalizada**: el filtro del intervalo de fechas que se ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="0c7ac-150">**Impacto**: los siguientes datos para el filtro de intervalo de fechas seleccionado:</span><span class="sxs-lookup"><span data-stu-id="0c7ac-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="0c7ac-151">Número total de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-151">The total number of recipients.</span></span>

    - <span data-ttu-id="0c7ac-152">El número de mensajes que se han "bandeja de entrada" (es decir, que se entregan a la bandeja de entrada, no de correo no deseado).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="0c7ac-153">El número de usuarios que hizo clic en la carga de la URL en el mensaje de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="0c7ac-154">Howe muchos usuarios visitaron la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="0c7ac-155">Una escala de tiempo de la actividad de la campaña: cuándo comenzó y finalizó la campaña y el volumen de mensajes a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="0c7ac-156">Flujo de la campaña</span><span class="sxs-lookup"><span data-stu-id="0c7ac-156">Campaign flow</span></span>

<span data-ttu-id="0c7ac-157">Los detalles importantes sobre la campaña se presentan en un diagrama de flujo horizontal (conocido como diagrama de _Sankey_) en la sección **Flujo**.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="0c7ac-158">Estos detalles pueden ayudarle a comprender los elementos de la campaña y su posible impacto en la organización.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Detalles de la campaña que no contienen clics del usuario en la URL.](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="0c7ac-160">Si coloca el puntero del mouse sobre una de las bandas horizontales del diagrama, verá el número de mensajes relacionados (por ejemplo, mensajes de una IP de origen en particular, mensajes de la dirección IP de origen con el dominio de remitente especificado, etc.).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="0c7ac-161">El diagrama contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c7ac-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="0c7ac-162">**IP de remitentes**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-162">**Sender IPs**</span></span>

- <span data-ttu-id="0c7ac-163">**Dominios de remitente**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-163">**Sender domains**</span></span>

- <span data-ttu-id="0c7ac-164">**Filtrar veredictos**: los valores aquí están relacionados con los veredictos de filtrado de suplantación de identidad (phishing) y correo no deseado disponibles como se describe en [encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-164">**Filter verdicts**: The values here are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="0c7ac-165">En la tabla siguiente se describen los valores disponibles:</span><span class="sxs-lookup"><span data-stu-id="0c7ac-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="0c7ac-166">Valor</span><span class="sxs-lookup"><span data-stu-id="0c7ac-166">Value</span></span>|<span data-ttu-id="0c7ac-167">Veredicto de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="0c7ac-167">Spam filter verdict</span></span>|<span data-ttu-id="0c7ac-168">Description</span><span class="sxs-lookup"><span data-stu-id="0c7ac-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="0c7ac-169">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="0c7ac-170">El mensaje se marcó como no es correo no deseado o omitido antes de ser evaluado por el filtrado de correo no deseado (por ejemplo, mediante una regla de flujo de correo, también denominada regla de transporte).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-170">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="0c7ac-171">El mensaje omitió el filtrado de correo no deseado por otros motivos (por ejemplo, el remitente y el destinatario parecen estar en la misma organización).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="0c7ac-172">**Blocked**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="0c7ac-173">El mensaje se marcó como correo no deseado antes de ser evaluado por el filtrado de correo no deseado (por ejemplo, mediante una regla de flujo de correo).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-173">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="0c7ac-174">**Detectados**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="0c7ac-175">El mensaje se marcó como correo no deseado por el filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-175">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="0c7ac-176">**No detectado**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="0c7ac-177">El mensaje se marcó como no correo no deseado por el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-177">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="0c7ac-178">**Exento**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="0c7ac-179">El mensaje omitió el filtrado de correo no deseado porque se liberó de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="0c7ac-180">**Permitir inquilino**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c7ac-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="0c7ac-181">El mensaje omitió el filtrado de correo no deseado debido a la configuración de la Directiva contra correo no deseado (por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-181">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="0c7ac-182">**Bloque tenant**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c7ac-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="0c7ac-183">El mensaje fue bloqueado por el filtrado de correo no deseado debido a la configuración de la Directiva contra correo no deseado (por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-183">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="0c7ac-184">**Permitir al usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c7ac-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="0c7ac-185">El mensaje omitió el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes seguros de un usuario en Outlook.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="0c7ac-186">**Bloque de usuario**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c7ac-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="0c7ac-187">El mensaje fue bloqueado por el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes bloqueados de un usuario en Outlook.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="0c7ac-188">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-188">**ZAP**</span></span>|<span data-ttu-id="0c7ac-189">N/D</span><span class="sxs-lookup"><span data-stu-id="0c7ac-189">n/a</span></span>|<span data-ttu-id="0c7ac-190">La [depuración automática de cero horas (ZAP)](zero-hour-auto-purge.md) llevó a cabo una acción en el mensaje entregado de acuerdo con la configuración de la Directiva contra correo no deseado (se movió a la carpeta de correo no deseado o en cuarentena).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="0c7ac-191"><sup>\*</sup>Revise las directivas contra correo no deseado, ya que es probable que el servicio haya bloqueado el mensaje permitido.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-191"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="0c7ac-192"><sup>\*\*</sup>Revise las directivas contra correo no deseado, ya que estos mensajes deben estar en cuarentena, no entregados.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-192"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="0c7ac-193">**Ubicaciones de entrega**: probablemente querrá investigar los mensajes que se entregaron a los destinatarios (ya sea en la bandeja de entrada o en la carpeta de correo no deseado), incluso aunque los usuarios no hayan hecho clic en la URL de carga del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="0c7ac-194">También puede quitar los mensajes en cuarentena de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="0c7ac-195">Para obtener más información, vea [cuarentena de mensajes de correo electrónico en Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-195">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="0c7ac-196">**Carpeta eliminada**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-196">**Deleted folder**</span></span>

  - <span data-ttu-id="0c7ac-197">**Sombra**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-197">**Dropped**</span></span>

  - <span data-ttu-id="0c7ac-198">**Externos**: el destinatario se encuentra en su organización de correo electrónico local.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="0c7ac-199">**Failed**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-199">**Failed**</span></span>

  - <span data-ttu-id="0c7ac-200">**Reenviado**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-200">**Forwarded**</span></span>

  - <span data-ttu-id="0c7ac-201">**Bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-201">**Inbox**</span></span>

  - <span data-ttu-id="0c7ac-202">**Carpeta de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-202">**Junk folder**</span></span>

  - <span data-ttu-id="0c7ac-203">**Cuarentena**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-203">**Quarantine**</span></span>

  - <span data-ttu-id="0c7ac-204">**Desconocido**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="0c7ac-205">En todas las capas que contienen más de 10 elementos, se muestran los 10 elementos principales, mientras que el resto se agrupan en **otros**.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="0c7ac-206">Clics de URL</span><span class="sxs-lookup"><span data-stu-id="0c7ac-206">URL clicks</span></span>

<span data-ttu-id="0c7ac-207">Cuando se entrega un mensaje de suplantación de identidad a un destinatario (en la bandeja de entrada o en la carpeta de correo electrónico no deseado), siempre hay una posibilidad de que el usuario haga clic en la dirección URL de la carga.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="0c7ac-208">No hacer clic en la dirección URL de un mensaje entregado es una pequeña medida de éxito, pero debe determinar por qué el mensaje de suplantación de identidad (phishing) se entregó a su buzón en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="0c7ac-209">Si un usuario hace clic en la dirección URL de carga en el mensaje de suplantación de identidad (phishing), las acciones se muestran en el área de **clics de la dirección URL** del diagrama en la vista detalles de la campaña.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="0c7ac-210">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-210">**Allowed**</span></span>

- <span data-ttu-id="0c7ac-211">**BlockPage**: el destinatario hizo clic en la dirección URL de carga, pero el acceso al sitio Web malintencionado fue bloqueado por las directivas de [vínculos seguros de ATP](atp-safe-links.md) en su organización.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="0c7ac-212">**BlockPageOverride**: el destinatario hizo clic en la dirección URL de carga en el mensaje, los vínculos seguros de ATP intentaron detenerlos, pero se permitió invalidar el bloque.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="0c7ac-213">Debe investigar sus directivas de [vínculos seguros](set-up-atp-safe-links-policies.md) para ver por qué los usuarios pueden invalidar el veredicto de vínculos seguros y continuar con el sitio Web malintencionado.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="0c7ac-214">**PendingDetonationPage**: los datos adjuntos seguros de ATP están en proceso de abrir la URL de carga en un entorno de equipo virtual y ver qué sucede.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="0c7ac-215">**PendingDetonationPageOverride**: el destinatario tuvo permiso para invalidar el proceso de detonación de carga y abrir la dirección URL sin esperar los resultados.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="0c7ac-216">Pestañas</span><span class="sxs-lookup"><span data-stu-id="0c7ac-216">Tabs</span></span>

<span data-ttu-id="0c7ac-217">En la vista de detalles de la campaña hay varias pestañas que permiten investigar más a fondo la campaña.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="0c7ac-218">**Clics en dirección URL**: si los usuarios no han hecho clic en la dirección URL de carga en el mensaje de suplantación de identidad, esta sección estará en blanco.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="0c7ac-219">Si un usuario pudo hacer clic en la dirección URL, se rellenarán los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0c7ac-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="0c7ac-220">**Usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c7ac-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="0c7ac-221">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c7ac-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="0c7ac-222">**Hora del clic**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-222">**Click Time**</span></span>

  - <span data-ttu-id="0c7ac-223">**Acción del clic**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-223">**Click Action**</span></span>

- <span data-ttu-id="0c7ac-224">**IP de remitentes**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-224">**Sender IPs**</span></span>

  - <span data-ttu-id="0c7ac-225">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c7ac-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="0c7ac-226">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-226">**Total Count**</span></span>

  - <span data-ttu-id="0c7ac-227">**Recuento de entregados en bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="0c7ac-228">**Recuento de bloqueados**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-228">**Blocked Count**</span></span>

  - <span data-ttu-id="0c7ac-229">**SPF superado**: el [marco de directivas de remitente (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)autenticó el remitente.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="0c7ac-230">Un remitente que no pasa la validación SPF indica que el remitente no está autenticado o que está suplantando a un remitente legítimo.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="0c7ac-231">**Remitentes**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-231">**Senders**</span></span>

  - <span data-ttu-id="0c7ac-232">**Sender**: esta es la dirección del remitente real en el comando SMTP mail from, que no tiene que ser necesariamente la dirección de correo electrónico que los usuarios ven en sus clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="0c7ac-233">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-233">**Total Count**</span></span>

  - <span data-ttu-id="0c7ac-234">**En la bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-234">**Inboxed**</span></span>

  - <span data-ttu-id="0c7ac-235">**Sin bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="0c7ac-236">**DKIM pasado**: el remitente ha sido autenticado por el [correo identificado por claves de dominio (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="0c7ac-237">Un remitente que no pasa la validación de DKIM indica que el remitente no está autenticado o que el mensaje está suplantando a un remitente legítimo.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="0c7ac-238">**DMARC pasada**: el remitente ha sido autenticado por la [autenticación de mensajes basada en dominio, la creación de informes y la conformidad (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="0c7ac-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="0c7ac-239">Un remitente que no pasa la validación de DMARC indica que el remitente no está autenticado o que el mensaje está suplantando a un remitente legítimo.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="0c7ac-240">**Cargas**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-240">**Payloads**</span></span>

  - <span data-ttu-id="0c7ac-241">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0c7ac-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="0c7ac-242">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="0c7ac-242">**Total Count**</span></span>

<span data-ttu-id="0c7ac-243"><sup>\*</sup> Al hacer clic en este valor, se abre un nuevo control flotante que contiene más detalles sobre el elemento especificado (usuario, URL, etc.) en la parte superior de la vista de detalles de la campaña.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="0c7ac-244">Para volver a la vista de detalles de la campaña, haga clic en **Hecho** en el nuevo control flotante.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="0c7ac-245">Botones</span><span class="sxs-lookup"><span data-stu-id="0c7ac-245">Buttons</span></span>

<span data-ttu-id="0c7ac-246">Los botones de la vista de detalles de la campaña le permiten usar todo el potencial del Explorador de amenazas para investigar más a fondo la campaña.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="0c7ac-247">**Explorar campaña**: abre una nueva pestaña de búsqueda del Explorador de amenazas con el valor **Id. de campaña** como filtro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="0c7ac-248">**Explorar mensajes**de la bandeja de entrada: abre una nueva ficha de búsqueda del explorador de amenazas usando el identificador de la **campaña** y la **Ubicación de entrega: bandeja de entrada** como filtro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0c7ac-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
