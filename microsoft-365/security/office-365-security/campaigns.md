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
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre las Vistas de la campaña en la Protección contra amenazas avanzada de Office 365.
ms.openlocfilehash: f0f5d2305b4f17c7018d32eebd155b4ad2d459e7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825802"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="5d0d3-103">Vistas de campañas en ATP</span><span class="sxs-lookup"><span data-stu-id="5d0d3-103">Campaign Views in ATP</span></span>

<span data-ttu-id="5d0d3-104">Las vistas de campañas son una característica de la protección contra amenazas avanzada (ATP) en el centro de seguridad & cumplimiento que identifica y categoriza los ataques de suplantación de identidad (phishing) en el servicio.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="5d0d3-105">Vistas de la campaña puede ayudarle a:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="5d0d3-106">Investigar y responder eficazmente a los ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="5d0d3-107">Entender mejor el alcance del ataque.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="5d0d3-108">Proporcionar información a los responsables de la toma de decisiones.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-108">Show value to decision makers.</span></span>

<span data-ttu-id="5d0d3-109">La característica Vistas de la campaña le permite obtener una perspectiva general del ataque más completa y más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="5d0d3-110">¿Qué es una campaña?</span><span class="sxs-lookup"><span data-stu-id="5d0d3-110">What is a campaign?</span></span>

<span data-ttu-id="5d0d3-111">Una campaña es un ataque de correo electrónico coordinado contra una o varias organizaciones.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="5d0d3-112">Los ataques de correo electrónico que roban credenciales y datos de la empresa son un sector importante y lucrativo.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="5d0d3-113">A medida que las tecnologías aumentan en un esfuerzo por detener los ataques, los atacantes modifican sus métodos en un esfuerzo para garantizar un éxito continuo.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="5d0d3-114">Microsoft aprovecha la gran cantidad de datos contra phishing, contra correo electrónico no deseado y antimalware en todo el servicio para ayudarle a identificar las campañas.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="5d0d3-115">Analizamos y clasificamos la información de ataques de acuerdo con varios factores.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="5d0d3-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-116">For example:</span></span>

- <span data-ttu-id="5d0d3-117">**Origen del ataque**: las direcciones IP de origen y los dominios de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="5d0d3-118">**Propiedades**de los mensajes de ataque: el contenido, el estilo y el tono de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="5d0d3-119">**Los destinatarios del ataque**: dominios de destinatarios, funciones de trabajo de los destinatarios (administradores, ejecutivos, etc.), tipos de empresa (grandes, pequeñas, públicas, privadas, etc.) y sectores.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="5d0d3-120">**Carga de ataques**: vínculos malintencionados, datos adjuntos u otras cargas en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="5d0d3-121">Una campaña puede ser de corta duración o puede abarcar varios días, semanas o meses con períodos activos e inactivos.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="5d0d3-122">Es posible que se inicie una campaña en su organización específica o que la organización forme parte de una campaña más grande en varias compañías.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="5d0d3-123">Vistas de campaña el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="5d0d3-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="5d0d3-124">Las vistas de campaña están disponibles en el [centro de seguridad & cumplimiento](https://protection.office.com) en las campañas de **Administración de amenazas** \> **Campaigns**, o directamente en <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="5d0d3-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Información general de las campañas en el Centro de seguridad y cumplimiento](../../media/campaigns-overview.png)

<span data-ttu-id="5d0d3-126">También puede obtener acceso a las vistas de campañas desde:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="5d0d3-127">**Administración** \> de amenazas **Explorador** \> **Ver** \> **Campañas**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="5d0d3-128">**Administración** \> de amenazas **Explorador** \> **Ver** \> **Todo el correo electrónico** \> Ficha **campaña**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="5d0d3-129">**Administración** \> de amenazas **Explorador** \> **Ver** \> **Phish** \> Ficha **campaña**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="5d0d3-130">**Administración** \> de amenazas **Explorador** \> **Ver** \> **Malware** \> Ficha **campaña**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="5d0d3-131">Para tener acceso a las vistas de campaña, debe ser miembro de los grupos de roles administración de la **organización**, **Administrador de seguridad**o **lector** de seguridad en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="5d0d3-132">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="5d0d3-133">Información general sobre campañas</span><span class="sxs-lookup"><span data-stu-id="5d0d3-133">Campaigns overview</span></span>

<span data-ttu-id="5d0d3-134">La página información general muestra información sobre todas las campañas.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="5d0d3-135">En la ficha **campaña** predeterminada, el área **tipo de campaña** muestra un gráfico de barras que muestra el número de destinatarios por día.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="5d0d3-136">De forma predeterminada, el gráfico muestra los datos de **phish** y **malware** .</span><span class="sxs-lookup"><span data-stu-id="5d0d3-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="5d0d3-137">Si no ve ningún dato de la campaña, pruebe a cambiar el intervalo de fechas o los [filtros](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="5d0d3-138">El resto de la página de información general muestra la siguiente información en la pestaña **campaña** :</span><span class="sxs-lookup"><span data-stu-id="5d0d3-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="5d0d3-139">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-139">**Name**</span></span>

- <span data-ttu-id="5d0d3-140">**Asunto de ejemplo**: línea de asunto de uno de los mensajes de la campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="5d0d3-141">Tenga en cuenta que todos los mensajes de la campaña no tendrán necesariamente el mismo asunto.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="5d0d3-142">**Destino**: porcentaje calculado por: (el número de destinatarios de la campaña de la organización)/(el número total de destinatarios en la campaña en todas las organizaciones del servicio).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="5d0d3-143">Este valor indica el grado al que la campaña está dirigida específicamente a su organización (un valor superior) frente a la dirigida a otras organizaciones del servicio (un valor inferior).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="5d0d3-144">**Tipo**: este valor puede ser **phish** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="5d0d3-145">**Subtipo**: este valor contiene más información sobre la campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="5d0d3-146">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-146">For example:</span></span>

  - <span data-ttu-id="5d0d3-147">**Phish**: donde esté disponible, la marca que se está suplantando en esta campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="5d0d3-148">Por ejemplo,,,, `Microsoft` `365` `Unknown` `Outlook` o `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="5d0d3-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="5d0d3-149">**Malware**: por ejemplo, `HTML/PHISH` o `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="5d0d3-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="5d0d3-150">Donde esté disponible, la marca que está en phish a la campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="5d0d3-151">Cuando la tecnología ATP controla la detección, el prefijo **ATP-** se agrega al valor SubType.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="5d0d3-152">**Destinatarios**: el número de usuarios a los que se ha dirigido esta campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="5d0d3-153">**Bandeja de entrada**: el número de usuarios que recibieron mensajes de esta campaña en su bandeja de entrada (no se entregaron a la carpeta de correo electrónico no deseado).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="5d0d3-154">**Haga clic en**: el número de usuarios que hizo clic en la dirección URL o abrieron los datos adjuntos en el mensaje de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="5d0d3-155">**Tasa de clic**: porcentaje calculado con "se ha**pulsado en**la  /  **bandeja de entrada**".</span><span class="sxs-lookup"><span data-stu-id="5d0d3-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="5d0d3-156">Este valor es un indicador de la efectividad de la campaña y de si los destinatarios pudieron identificar el mensaje como suplantación de identidad (phishing) y evitar hacer clic en la dirección URL de carga.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="5d0d3-157">Tenga en cuenta que este valor no se usa en las campañas de malware.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="5d0d3-158">**Visitado**: el número de usuarios que se han realizado realmente a través del sitio web de carga.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="5d0d3-159">Si hay valores en los que se ha **pulsado** , pero los vínculos seguros han bloqueado el acceso al sitio web, este valor será cero.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="5d0d3-160">La pestaña origen de la **campaña** muestra los orígenes del mensaje en un mapa del mundo.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="5d0d3-161">Filtros y configuración</span><span class="sxs-lookup"><span data-stu-id="5d0d3-161">Filters and settings</span></span>

<span data-ttu-id="5d0d3-162">En la parte superior de la página vistas de campañas, hay varios filtros y configuraciones de consulta para ayudarle a encontrar y aislar campañas específicas.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Filtros de campaña](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="5d0d3-164">El filtrado más básico que puede hacer es la fecha y hora de inicio y la fecha y hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="5d0d3-165">Para filtrar más la vista, puede hacer una sola propiedad con varios valores al filtrar haciendo clic en el botón **tipo de campaña** , haciendo su selección y, a continuación, haciendo clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="5d0d3-166">Las propiedades de la campaña disponibles se describen en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="5d0d3-167">Básica</span><span class="sxs-lookup"><span data-stu-id="5d0d3-167">Basic</span></span>

  - <span data-ttu-id="5d0d3-168">**Tipo de campaña**: seleccione **malware** o **phish**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="5d0d3-169">Si se quitan las selecciones, se obtiene el mismo resultado que al seleccionar ambas.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="5d0d3-170">**Nombre de la campaña**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-170">**Campaign name**</span></span>
  - <span data-ttu-id="5d0d3-171">**Subtipo de campaña**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="5d0d3-172">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-172">**Sender**</span></span>
  - <span data-ttu-id="5d0d3-173">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-173">**Recipients**</span></span>
  - <span data-ttu-id="5d0d3-174">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-174">**Sender domain**</span></span>
  - <span data-ttu-id="5d0d3-175">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-175">**Subject**</span></span>
  - <span data-ttu-id="5d0d3-176">**Nombres de archivos adjuntos**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-176">**Attachment filename**</span></span>
  - <span data-ttu-id="5d0d3-177">**Familia de malware**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-177">**Malware family**</span></span>
  - <span data-ttu-id="5d0d3-178">**Acción de entrega**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-178">**Delivery action**</span></span>
  - <span data-ttu-id="5d0d3-179">**Tecnología de detección**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-179">**Detection technology**</span></span>
  - <span data-ttu-id="5d0d3-180">**Tags**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-180">**Tags**</span></span>
  - <span data-ttu-id="5d0d3-181">**Invalidaciones del sistema**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-181">**System overrides**</span></span>

- <span data-ttu-id="5d0d3-182">Opciones avanzadas</span><span class="sxs-lookup"><span data-stu-id="5d0d3-182">Advanced</span></span>

  - <span data-ttu-id="5d0d3-183">**Identificador del mensaje de Internet**: disponible en el campo de encabezado del **identificador del mensaje** en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="5d0d3-184">Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observe los corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="5d0d3-185">**Identificador de mensaje de red**: un valor GUID que está disponible en el campo de encabezado **X-MS-Exchange-Organization-Network-Message-ID** en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="5d0d3-186">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="5d0d3-187">**Datos adjuntos SHA256**: para buscar el valor de hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="5d0d3-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="5d0d3-188">**IDENTIFICADOR de clúster**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="5d0d3-189">**IDENTIFICADOR de la Directiva de alertas**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="5d0d3-190">Direcciones URL</span><span class="sxs-lookup"><span data-stu-id="5d0d3-190">URLs</span></span>

  - <span data-ttu-id="5d0d3-191">**Dominio de dirección URL**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-191">**URL domain**</span></span>
  - <span data-ttu-id="5d0d3-192">**Dominio y ruta de acceso de dirección URL**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-192">**URL domain and path**</span></span>
  - <span data-ttu-id="5d0d3-193">**URL**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-193">**URL**</span></span>
  - <span data-ttu-id="5d0d3-194">**Ruta de dirección URL**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-194">**URL path**</span></span>
  - <span data-ttu-id="5d0d3-195">**Haga clic en veredicto**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-195">**Click verdict**</span></span>

<span data-ttu-id="5d0d3-196">Para un filtrado más avanzado, incluido el filtrado por varias propiedades, puede hacer clic en el botón **filtro avanzado** para crear una consulta.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="5d0d3-197">Están disponibles las mismas propiedades de la campaña, pero con las siguientes mejoras:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="5d0d3-198">Puede hacer clic en **Agregar condición** para seleccionar varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="5d0d3-199">Puede elegir el operador **y** u **o** entre las condiciones.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="5d0d3-200">Puede seleccionar el elemento de **grupo de condición** en la parte inferior de la lista de condiciones para crear condiciones compuestas complejas.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="5d0d3-201">Cuando haya terminado, haga clic en el botón **consulta** .</span><span class="sxs-lookup"><span data-stu-id="5d0d3-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="5d0d3-202">Después de crear un filtro básico o avanzado, puede guardarlo con **Guardar consulta** o **Guardar consulta como**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="5d0d3-203">Más adelante, cuando vuelva a las vistas de campañas, puede cargar un filtro guardado haciendo clic en **configuración de consulta guardada**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="5d0d3-204">Para exportar el gráfico o la lista de campañas, haga clic en **exportar** y seleccione **exportar datos de gráfico** o **Exportar lista de campañas**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="5d0d3-205">Si tiene una suscripción ATP de Microsoft defender, puede hacer clic en **WDATP** para conectar o desconectar la información sobre campañas con ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="5d0d3-206">Para obtener más información, consulte [integrar Office 365 ATP con Microsoft defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="5d0d3-207">Detalles de la campaña</span><span class="sxs-lookup"><span data-stu-id="5d0d3-207">Campaign details</span></span>

<span data-ttu-id="5d0d3-208">Al hacer clic en el nombre de una campaña, los detalles de la campaña aparecen en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="5d0d3-209">Información de la campaña</span><span class="sxs-lookup"><span data-stu-id="5d0d3-209">Campaign information</span></span>

<span data-ttu-id="5d0d3-210">En la parte superior de la vista detalles de la campaña, está disponible la siguiente información de la campaña:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="5d0d3-211">**ID**: el identificador único de la campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="5d0d3-212">**Iniciado** y **finalizado**: fecha de inicio y fecha de finalización de la campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="5d0d3-213">Tenga en cuenta que estas fechas pueden extenderse más allá de las fechas de filtro que ha seleccionado en la página información general.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="5d0d3-214">**Impacto**: esta sección contiene los datos siguientes para el filtro de intervalo de fechas que haya seleccionado (o que seleccione en la escala de tiempo):</span><span class="sxs-lookup"><span data-stu-id="5d0d3-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="5d0d3-215">Número total de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-215">The total number of recipients.</span></span>
  - <span data-ttu-id="5d0d3-216">El número de mensajes que se han "bandeja de entrada" (es decir, que se entregan a la bandeja de entrada y no a la carpeta de correo electrónico no deseado).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="5d0d3-217">El número de usuarios que hizo clic en la carga de la URL en el mensaje de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="5d0d3-218">Howe muchos usuarios visitaron la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="5d0d3-219">**Destino**: porcentaje calculado por: (el número de destinatarios de la campaña de la organización)/(el número total de destinatarios en la campaña en todas las organizaciones del servicio).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="5d0d3-220">Tenga en cuenta que este valor se calcula en toda la duración de la campaña y no cambia las fechas de filtro.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="5d0d3-221">Escala de tiempo interactiva de la actividad de la campaña: la escala de tiempo muestra la actividad durante toda la duración de la campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="5d0d3-222">De forma predeterminada, el área sombreada incluye el filtro de intervalo de fechas que ha seleccionado en la información general.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="5d0d3-223">Puede hacer clic y arrastrar para seleccionar un punto inicial y un punto final específicos, <u>que cambiarán los datos que se muestran en el área de **impacto** y el resto de la página, tal y como se describe en las siguientes secciones</u>.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="5d0d3-224">En la barra de título, puede hacer clic en el icono de descarga de la campaña de descarga del botón de instalación de la **campaña** ![ para descargar ](../../media/download-campaign-write-up-button.png) los detalles de la campaña en un documento de Word (de forma predeterminada, con el nombre CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="5d0d3-225">Tenga en cuenta que este documento contiene detalles sobre toda la duración de la campaña (no solo las fechas de filtro seleccionadas).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Información de la campaña](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="5d0d3-227">Flujo de la campaña</span><span class="sxs-lookup"><span data-stu-id="5d0d3-227">Campaign flow</span></span>

<span data-ttu-id="5d0d3-228">En la parte central de la vista detalles de la campaña, los detalles importantes sobre la campaña se presentan en la sección **flujo** en un diagrama de flujo horizontal (conocido como diagrama _Sankey_ ).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="5d0d3-229">Estos detalles pueden ayudarle a comprender los elementos de la campaña y su posible impacto en la organización.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="5d0d3-230">La información que se muestra en el diagrama de **flujo** está controlada por el intervalo de fechas sombreado de la escala de tiempo tal como se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Detalles de la campaña que no contienen clics del usuario en la URL.](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="5d0d3-232">Si coloca el puntero del mouse sobre una de las bandas horizontales del diagrama, verá el número de mensajes relacionados (por ejemplo, mensajes de una IP de origen en particular, mensajes de la dirección IP de origen con el dominio de remitente especificado, etc.).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="5d0d3-233">El diagrama contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="5d0d3-234">**IP de remitentes**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-234">**Sender IPs**</span></span>

- <span data-ttu-id="5d0d3-235">**Dominios de remitente**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-235">**Sender domains**</span></span>

- <span data-ttu-id="5d0d3-236">**Filtrar veredictos**: estos valores están relacionados con los veredictos de filtrado de suplantación de identidad (phishing) y correo no deseado disponibles, tal como se describe en [anti-spam Message headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="5d0d3-237">En la tabla siguiente se describen los valores disponibles:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-237">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="5d0d3-238">Valor</span><span class="sxs-lookup"><span data-stu-id="5d0d3-238">Value</span></span>|<span data-ttu-id="5d0d3-239">Veredicto de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="5d0d3-239">Spam filter verdict</span></span>|<span data-ttu-id="5d0d3-240">Description</span><span class="sxs-lookup"><span data-stu-id="5d0d3-240">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="5d0d3-241">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="5d0d3-242">El mensaje se marcó como no es correo no deseado o omitido antes de ser evaluado por el filtrado de correo no deseado (por ejemplo, mediante una regla de flujo de correo, también denominada regla de transporte).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="5d0d3-243">El mensaje omitió el filtrado de correo no deseado por otros motivos (por ejemplo, el remitente y el destinatario parecen estar en la misma organización).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="5d0d3-244">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="5d0d3-245">El mensaje se marcó como correo no deseado antes de ser evaluado por el filtrado de correo no deseado (por ejemplo, mediante una regla de flujo de correo).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="5d0d3-246">**Detectados**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="5d0d3-247">El mensaje se marcó como correo no deseado por el filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="5d0d3-248">**No detectado**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="5d0d3-249">El mensaje se marcó como no correo no deseado por el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="5d0d3-250">**Exento**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="5d0d3-251">El mensaje omitió el filtrado de correo no deseado porque se liberó de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="5d0d3-252">**Permitir inquilino**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5d0d3-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="5d0d3-253">El mensaje omitió el filtrado de correo no deseado debido a la configuración de la Directiva contra correo no deseado (por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="5d0d3-254">**Bloque tenant**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="5d0d3-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="5d0d3-255">El mensaje fue bloqueado por el filtrado de correo no deseado debido a la configuración de la Directiva contra correo no deseado (por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="5d0d3-256">**Permitir al usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5d0d3-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="5d0d3-257">El mensaje omitió el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes seguros de un usuario en Outlook.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="5d0d3-258">**Bloque de usuario**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="5d0d3-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="5d0d3-259">El mensaje fue bloqueado por el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes bloqueados de un usuario en Outlook.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="5d0d3-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-260">**ZAP**</span></span>|<span data-ttu-id="5d0d3-261">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5d0d3-261">n/a</span></span>|<span data-ttu-id="5d0d3-262">La [depuración automática de cero horas (ZAP)](zero-hour-auto-purge.md) llevó a cabo una acción en el mensaje entregado de acuerdo con la configuración de la Directiva contra correo no deseado (se movió a la carpeta de correo no deseado o en cuarentena).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="5d0d3-263"><sup>\*</sup> Revise las directivas contra correo no deseado, ya que es probable que el servicio haya bloqueado el mensaje permitido.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="5d0d3-264"><sup>\*\*</sup> Revise las directivas contra correo no deseado, ya que estos mensajes deben estar en cuarentena, no entregados.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="5d0d3-265">**Ubicaciones de entrega**: probablemente querrá investigar los mensajes que se entregaron a los destinatarios (ya sea en la bandeja de entrada o en la carpeta de correo no deseado), incluso aunque los usuarios no hayan hecho clic en la URL de carga del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="5d0d3-266">También puede quitar los mensajes en cuarentena de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="5d0d3-267">Para obtener más información, vea [mensajes de correo electrónico en cuarentena en EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="5d0d3-268">**Carpeta eliminada**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-268">**Deleted folder**</span></span>
  - <span data-ttu-id="5d0d3-269">**Sombra**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-269">**Dropped**</span></span>
  - <span data-ttu-id="5d0d3-270">**Externos**: el destinatario se encuentra en su organización de correo electrónico local en entornos híbridos.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="5d0d3-271">**Failed**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-271">**Failed**</span></span>
  - <span data-ttu-id="5d0d3-272">**Reenviado**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-272">**Forwarded**</span></span>
  - <span data-ttu-id="5d0d3-273">**Bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-273">**Inbox**</span></span>
  - <span data-ttu-id="5d0d3-274">**Carpeta de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-274">**Junk folder**</span></span>
  - <span data-ttu-id="5d0d3-275">**Cuarentena**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-275">**Quarantine**</span></span>
  - <span data-ttu-id="5d0d3-276">**Desconocido**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-276">**Unknown**</span></span>

- <span data-ttu-id="5d0d3-277">**Clics en dirección URL**: se describen en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="5d0d3-278">En todas las capas que contienen más de 10 elementos, se muestran los 10 elementos principales, mientras que el resto se agrupan en **otros**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="5d0d3-279">Clics de URL</span><span class="sxs-lookup"><span data-stu-id="5d0d3-279">URL clicks</span></span>

<span data-ttu-id="5d0d3-280">Cuando se entrega un mensaje de suplantación de identidad a un destinatario (en la bandeja de entrada o en la carpeta de correo electrónico no deseado), siempre hay una posibilidad de que el usuario haga clic en la dirección URL de la carga.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="5d0d3-281">No hacer clic en la dirección URL de un mensaje entregado es una pequeña medida de éxito, pero debe determinar por qué el mensaje de suplantación de identidad (phishing) se entregó a su buzón en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="5d0d3-282">Si un usuario hace clic en la dirección URL de carga en el mensaje de suplantación de identidad (phishing), las acciones se muestran en el área de **clics de la dirección URL** del diagrama en la vista detalles de la campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="5d0d3-283">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-283">**Allowed**</span></span>

- <span data-ttu-id="5d0d3-284">**BlockPage**: el destinatario hizo clic en la dirección URL de carga, pero el acceso al sitio Web malintencionado fue bloqueado por las directivas de [vínculos seguros de ATP](atp-safe-links.md) en su organización.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="5d0d3-285">**BlockPageOverride**: el destinatario hizo clic en la dirección URL de carga en el mensaje, los vínculos seguros de ATP intentaron detenerlos, pero se permitió invalidar el bloque.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="5d0d3-286">Debe investigar sus directivas de [vínculos seguros](set-up-atp-safe-links-policies.md) para ver por qué los usuarios pueden invalidar el veredicto de vínculos seguros y continuar con el sitio Web malintencionado.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="5d0d3-287">**PendingDetonationPage**: los datos adjuntos seguros de ATP están en proceso de abrir la URL de carga en un entorno de equipo virtual y ver qué sucede.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="5d0d3-288">**PendingDetonationPageOverride**: el destinatario tuvo permiso para invalidar el proceso de detonación de carga y abrir la dirección URL sin esperar los resultados.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="5d0d3-289">Pestañas</span><span class="sxs-lookup"><span data-stu-id="5d0d3-289">Tabs</span></span>

<span data-ttu-id="5d0d3-290">Las pestañas de la vista detalles de la campaña le permiten investigar más detalladamente la campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="5d0d3-291">La información que se muestra en las pestañas se controla mediante el intervalo de fechas sombreado en la escala de tiempo como se describe en la sección información de la [campaña](#campaign-information) .</span><span class="sxs-lookup"><span data-stu-id="5d0d3-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="5d0d3-292">**Clics en dirección URL**: si los usuarios no han hecho clic en la dirección URL de carga en el mensaje de suplantación de identidad, esta sección estará en blanco.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="5d0d3-293">Si un usuario pudo hacer clic en la dirección URL, se rellenarán los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="5d0d3-294">**Usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5d0d3-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="5d0d3-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5d0d3-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="5d0d3-296">**Haga clic en hora**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-296">**Click time**</span></span>
  - <span data-ttu-id="5d0d3-297">**Haga clic en veredicto**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-297">**Click verdict**</span></span>

- <span data-ttu-id="5d0d3-298">**IP de remitentes**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-298">**Sender IPs**</span></span>

  - <span data-ttu-id="5d0d3-299">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5d0d3-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="5d0d3-300">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-300">**Total count**</span></span>
  - <span data-ttu-id="5d0d3-301">**En la bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-301">**Inboxed**</span></span>
  - <span data-ttu-id="5d0d3-302">**Sin bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="5d0d3-303">**SPF superado**: el [marco de directivas de remitente (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)autenticó el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="5d0d3-304">Un remitente que no pasa la validación SPF indica que el remitente no está autenticado o que está suplantando a un remitente legítimo.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="5d0d3-305">**Remitentes**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-305">**Senders**</span></span>

  - <span data-ttu-id="5d0d3-306">**Sender**: esta es la dirección del remitente real en el comando SMTP mail from, que no tiene que ser necesariamente la dirección de correo electrónico que los usuarios ven en sus clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="5d0d3-307">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-307">**Total count**</span></span>
  - <span data-ttu-id="5d0d3-308">**En la bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-308">**Inboxed**</span></span>
  - <span data-ttu-id="5d0d3-309">**Sin bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="5d0d3-310">**DKIM pasado**: el remitente ha sido autenticado por el [correo identificado por claves de dominio (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="5d0d3-311">Un remitente que no pasa la validación de DKIM indica que el remitente no está autenticado o que el mensaje está suplantando a un remitente legítimo.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="5d0d3-312">**DMARC pasada**: el remitente ha sido autenticado por la [autenticación de mensajes basada en dominio, la creación de informes y la conformidad (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="5d0d3-313">Un remitente que no pasa la validación de DMARC indica que el remitente no está autenticado o que el mensaje está suplantando a un remitente legítimo.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="5d0d3-314">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-314">**Attachments**</span></span>

  - <span data-ttu-id="5d0d3-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-315">**Filename**</span></span>
  - <span data-ttu-id="5d0d3-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-316">**SHA256**</span></span>
  - <span data-ttu-id="5d0d3-317">**Familia de malware**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-317">**Malware family**</span></span>
  - <span data-ttu-id="5d0d3-318">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-318">**Total count**</span></span>

- <span data-ttu-id="5d0d3-319">**URL**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-319">**URL**</span></span>

  - <span data-ttu-id="5d0d3-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5d0d3-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="5d0d3-321">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="5d0d3-321">**Total Count**</span></span>

<span data-ttu-id="5d0d3-322"><sup>\*</sup> Al hacer clic en este valor, se abre un nuevo control flotante que contiene más detalles sobre el elemento especificado (usuario, URL, etc.) en la parte superior de la vista de detalles de la campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="5d0d3-323">Para volver a la vista de detalles de la campaña, haga clic en **Hecho** en el nuevo control flotante.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="5d0d3-324">Botones</span><span class="sxs-lookup"><span data-stu-id="5d0d3-324">Buttons</span></span>

<span data-ttu-id="5d0d3-325">Los botones de la vista de detalles de la campaña le permiten usar todo el potencial del Explorador de amenazas para investigar más a fondo la campaña.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="5d0d3-326">**Explorar campaña**: abre una nueva pestaña de búsqueda del Explorador de amenazas con el valor **Id. de campaña** como filtro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="5d0d3-327">**Explorar mensajes**de la bandeja de entrada: abre una nueva ficha de búsqueda del explorador de amenazas usando el identificador de la **campaña** y la **Ubicación de entrega: bandeja de entrada** como filtro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
