---
title: Vistas de campaña en Office 365 plan ATP
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
ms.openlocfilehash: df3b3c7a0e8d8f614e5f743b445af07916f1dfd5
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326596"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="737f9-103">Vistas de la campaña en ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="737f9-103">Campaign Views in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="737f9-104">Las vistas de campañas son una característica del plan 2 de la protección contra amenazas avanzada (ATP) (por ejemplo, Microsoft 365 E5 u organizaciones con un complemento ATP plan 2).</span><span class="sxs-lookup"><span data-stu-id="737f9-104">Campaign Views is a feature in Advanced Threat Protection (ATP) Plan 2 (for example Microsoft 365 E5 or organizations with an ATP Plan 2 add-on).</span></span> <span data-ttu-id="737f9-105">Vistas de campañas en el centro de seguridad & cumplimiento identifica y categoriza los ataques de suplantación de identidad (phishing) en el servicio.</span><span class="sxs-lookup"><span data-stu-id="737f9-105">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="737f9-106">Vistas de la campaña puede ayudarle a:</span><span class="sxs-lookup"><span data-stu-id="737f9-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="737f9-107">Investigar y responder eficazmente a los ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="737f9-107">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="737f9-108">Entender mejor el alcance del ataque.</span><span class="sxs-lookup"><span data-stu-id="737f9-108">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="737f9-109">Proporcionar información a los responsables de la toma de decisiones.</span><span class="sxs-lookup"><span data-stu-id="737f9-109">Show value to decision makers.</span></span>

<span data-ttu-id="737f9-110">La característica Vistas de la campaña le permite obtener una perspectiva general del ataque más completa y más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="737f9-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="737f9-111">¿Qué es una campaña?</span><span class="sxs-lookup"><span data-stu-id="737f9-111">What is a campaign?</span></span>

<span data-ttu-id="737f9-112">Una campaña es un ataque de correo electrónico coordinado contra una o varias organizaciones.</span><span class="sxs-lookup"><span data-stu-id="737f9-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="737f9-113">Los ataques de correo electrónico que roban credenciales y datos de la empresa son un sector importante y lucrativo.</span><span class="sxs-lookup"><span data-stu-id="737f9-113">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="737f9-114">A medida que las tecnologías aumentan en un esfuerzo por detener los ataques, los atacantes modifican sus métodos en un esfuerzo para garantizar un éxito continuo.</span><span class="sxs-lookup"><span data-stu-id="737f9-114">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="737f9-115">Microsoft aprovecha la gran cantidad de datos contra phishing, contra correo electrónico no deseado y antimalware en todo el servicio para ayudarle a identificar las campañas.</span><span class="sxs-lookup"><span data-stu-id="737f9-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="737f9-116">Analizamos y clasificamos la información de ataques de acuerdo con varios factores.</span><span class="sxs-lookup"><span data-stu-id="737f9-116">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="737f9-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="737f9-117">For example:</span></span>

- <span data-ttu-id="737f9-118">**Origen del ataque**: las direcciones IP de origen y los dominios de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="737f9-118">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="737f9-119">**Propiedades del mensaje**: el contenido, el estilo y el tono de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="737f9-119">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="737f9-120">**Destinatarios del mensaje**: cómo se relacionan los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="737f9-120">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="737f9-121">Por ejemplo, dominios de destinatarios, funciones de trabajo de destinatarios (administradores, ejecutivos, etc.), tipos de empresas (grandes, pequeñas, públicas, privadas, etc.) y sectores.</span><span class="sxs-lookup"><span data-stu-id="737f9-121">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="737f9-122">**Carga de ataques**: vínculos malintencionados, datos adjuntos u otras cargas en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="737f9-122">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="737f9-123">Una campaña puede ser de corta duración o puede abarcar varios días, semanas o meses con períodos activos e inactivos.</span><span class="sxs-lookup"><span data-stu-id="737f9-123">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="737f9-124">Es posible que se inicie una campaña en su organización específica o que la organización forme parte de una campaña más grande en varias compañías.</span><span class="sxs-lookup"><span data-stu-id="737f9-124">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="737f9-125">Vistas de campaña en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="737f9-125">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="737f9-126">Las vistas de campaña están disponibles en el [centro de seguridad & cumplimiento](https://protection.office.com) en las campañas de **Administración de amenazas** \> **Campaigns**, o directamente en <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="737f9-126">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Información general de las campañas en el Centro de seguridad y cumplimiento](../../media/campaigns-overview.png)

<span data-ttu-id="737f9-128">También puede obtener acceso a las vistas de campañas desde:</span><span class="sxs-lookup"><span data-stu-id="737f9-128">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="737f9-129">**Administración** \> de amenazas **Explorador** \> **Ver** \> **Campañas**</span><span class="sxs-lookup"><span data-stu-id="737f9-129">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="737f9-130">**Administración** \> de amenazas **Explorador** \> **Ver** \> **Todo el correo electrónico** \> Ficha **campaña**</span><span class="sxs-lookup"><span data-stu-id="737f9-130">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="737f9-131">**Administración** \> de amenazas **Explorador** \> **Ver** \> **Phish** \> Ficha **campaña**</span><span class="sxs-lookup"><span data-stu-id="737f9-131">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="737f9-132">**Administración** \> de amenazas **Explorador** \> **Ver** \> **Malware** \> Ficha **campaña**</span><span class="sxs-lookup"><span data-stu-id="737f9-132">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="737f9-133">Para tener acceso a las vistas de campaña, debe ser miembro de los grupos de roles administración de la **organización**, **Administrador de seguridad**o **lector** de seguridad en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="737f9-133">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="737f9-134">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="737f9-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="737f9-135">Información general sobre campañas</span><span class="sxs-lookup"><span data-stu-id="737f9-135">Campaigns overview</span></span>

<span data-ttu-id="737f9-136">La página información general muestra información sobre todas las campañas.</span><span class="sxs-lookup"><span data-stu-id="737f9-136">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="737f9-137">En la ficha **campaña** predeterminada, el área **tipo de campaña** muestra un gráfico de barras que muestra el número de destinatarios por día.</span><span class="sxs-lookup"><span data-stu-id="737f9-137">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="737f9-138">De forma predeterminada, el gráfico muestra los datos de **phish** y **malware** .</span><span class="sxs-lookup"><span data-stu-id="737f9-138">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="737f9-139">Si no ve ningún dato de la campaña, pruebe a cambiar el intervalo de fechas o los [filtros](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="737f9-139">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="737f9-140">El resto de la página de información general muestra la siguiente información en la pestaña **campaña** :</span><span class="sxs-lookup"><span data-stu-id="737f9-140">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="737f9-141">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="737f9-141">**Name**</span></span>

- <span data-ttu-id="737f9-142">**Asunto de ejemplo**: línea de asunto de uno de los mensajes de la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-142">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="737f9-143">Tenga en cuenta que todos los mensajes de la campaña no tendrán necesariamente el mismo asunto.</span><span class="sxs-lookup"><span data-stu-id="737f9-143">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="737f9-144">**Destino**: porcentaje calculado por: (el número de destinatarios de la campaña de la organización)/(el número total de destinatarios en la campaña en todas las organizaciones del servicio).</span><span class="sxs-lookup"><span data-stu-id="737f9-144">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="737f9-145">Este valor indica el grado al que se dirige la campaña sólo a la organización (un valor superior) en comparación con otras organizaciones del servicio (un valor inferior).</span><span class="sxs-lookup"><span data-stu-id="737f9-145">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="737f9-146">**Tipo**: este valor puede ser **phish** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="737f9-146">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="737f9-147">**Subtipo**: este valor contiene más información sobre la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-147">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="737f9-148">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="737f9-148">For example:</span></span>

  - <span data-ttu-id="737f9-149">**Phish**: donde esté disponible, la marca que se está suplantando en esta campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-149">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="737f9-150">Por ejemplo,,,, `Microsoft` `365` `Unknown` `Outlook` o `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="737f9-150">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="737f9-151">**Malware**: por ejemplo, `HTML/PHISH` o `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="737f9-151">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="737f9-152">Donde esté disponible, la marca que está en phish a la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-152">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="737f9-153">Cuando la tecnología ATP controla la detección, el prefijo **ATP-** se agrega al valor SubType.</span><span class="sxs-lookup"><span data-stu-id="737f9-153">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="737f9-154">**Destinatarios**: el número de usuarios a los que se ha dirigido esta campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-154">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="737f9-155">**Bandeja de entrada**: el número de usuarios que recibieron mensajes de esta campaña en su bandeja de entrada (no se entregaron a la carpeta de correo electrónico no deseado).</span><span class="sxs-lookup"><span data-stu-id="737f9-155">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="737f9-156">**Haga clic en**: el número de usuarios que hizo clic en la dirección URL o abrieron los datos adjuntos en el mensaje de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="737f9-156">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="737f9-157">**Tasa de clic**: porcentaje calculado con "se ha**pulsado en**la  /  **bandeja de entrada**".</span><span class="sxs-lookup"><span data-stu-id="737f9-157">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="737f9-158">Este valor es un indicador de la efectividad de la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-158">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="737f9-159">Es decir, si los destinatarios pudieron identificar el mensaje como suplantación de identidad (phishing) y no han hecho clic en la dirección URL de carga.</span><span class="sxs-lookup"><span data-stu-id="737f9-159">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="737f9-160">Tenga en cuenta que la **tasa de clics** no se usa en las campañas de malware.</span><span class="sxs-lookup"><span data-stu-id="737f9-160">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="737f9-161">**Visitado**: el número de usuarios que se han realizado realmente a través del sitio web de carga.</span><span class="sxs-lookup"><span data-stu-id="737f9-161">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="737f9-162">Si hay valores en los que se ha **pulsado** , pero los vínculos seguros han bloqueado el acceso al sitio web, este valor será cero.</span><span class="sxs-lookup"><span data-stu-id="737f9-162">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="737f9-163">La pestaña origen de la **campaña** muestra los orígenes del mensaje en un mapa del mundo.</span><span class="sxs-lookup"><span data-stu-id="737f9-163">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="737f9-164">Filtros y configuración</span><span class="sxs-lookup"><span data-stu-id="737f9-164">Filters and settings</span></span>

<span data-ttu-id="737f9-165">En la parte superior de la página vistas de campañas, hay varios filtros y configuraciones de consulta para ayudarle a encontrar y aislar campañas específicas.</span><span class="sxs-lookup"><span data-stu-id="737f9-165">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Filtros de campaña](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="737f9-167">El filtrado más básico que puede hacer es la fecha y hora de inicio y la fecha y hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="737f9-167">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="737f9-168">Para filtrar más la vista, puede hacer una sola propiedad con varios valores al filtrar haciendo clic en el botón **tipo de campaña** , haciendo su selección y, a continuación, haciendo clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="737f9-168">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="737f9-169">Las propiedades de la campaña disponibles se describen en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="737f9-169">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="737f9-170">Basic</span><span class="sxs-lookup"><span data-stu-id="737f9-170">Basic</span></span>

  - <span data-ttu-id="737f9-171">**Tipo de campaña**: seleccione **malware** o **phish**.</span><span class="sxs-lookup"><span data-stu-id="737f9-171">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="737f9-172">Si se quitan las selecciones, se obtiene el mismo resultado que al seleccionar ambas.</span><span class="sxs-lookup"><span data-stu-id="737f9-172">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="737f9-173">**Nombre de la campaña**</span><span class="sxs-lookup"><span data-stu-id="737f9-173">**Campaign name**</span></span>
  - <span data-ttu-id="737f9-174">**Subtipo de campaña**</span><span class="sxs-lookup"><span data-stu-id="737f9-174">**Campaign subtype**</span></span>
  - <span data-ttu-id="737f9-175">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="737f9-175">**Sender**</span></span>
  - <span data-ttu-id="737f9-176">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="737f9-176">**Recipients**</span></span>
  - <span data-ttu-id="737f9-177">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="737f9-177">**Sender domain**</span></span>
  - <span data-ttu-id="737f9-178">**Subject**</span><span class="sxs-lookup"><span data-stu-id="737f9-178">**Subject**</span></span>
  - <span data-ttu-id="737f9-179">**Nombres de archivos adjuntos**</span><span class="sxs-lookup"><span data-stu-id="737f9-179">**Attachment filename**</span></span>
  - <span data-ttu-id="737f9-180">**Familia de malware**</span><span class="sxs-lookup"><span data-stu-id="737f9-180">**Malware family**</span></span>
  - <span data-ttu-id="737f9-181">**Acción de entrega**</span><span class="sxs-lookup"><span data-stu-id="737f9-181">**Delivery action**</span></span>
  - <span data-ttu-id="737f9-182">**Tecnología de detección**</span><span class="sxs-lookup"><span data-stu-id="737f9-182">**Detection technology**</span></span>
  - <span data-ttu-id="737f9-183">**Tags**</span><span class="sxs-lookup"><span data-stu-id="737f9-183">**Tags**</span></span>
  - <span data-ttu-id="737f9-184">**Invalidaciones del sistema**</span><span class="sxs-lookup"><span data-stu-id="737f9-184">**System overrides**</span></span>

- <span data-ttu-id="737f9-185">Advanced</span><span class="sxs-lookup"><span data-stu-id="737f9-185">Advanced</span></span>

  - <span data-ttu-id="737f9-186">**Identificador del mensaje de Internet**: disponible en el campo de encabezado del **identificador del mensaje** en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="737f9-186">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="737f9-187">Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observe los corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="737f9-187">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="737f9-188">**Identificador de mensaje de red**: un valor GUID que está disponible en el campo de encabezado **X-MS-Exchange-Organization-Network-Message-ID** en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="737f9-188">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="737f9-189">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="737f9-189">**Sender IP**</span></span>
  
  - <span data-ttu-id="737f9-190">**Datos adjuntos SHA256**: para buscar el valor de hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="737f9-190">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="737f9-191">**IDENTIFICADOR de clúster**</span><span class="sxs-lookup"><span data-stu-id="737f9-191">**Cluster ID**</span></span>
  
  - <span data-ttu-id="737f9-192">**IDENTIFICADOR de la Directiva de alertas**</span><span class="sxs-lookup"><span data-stu-id="737f9-192">**Alert Policy ID**</span></span>

- <span data-ttu-id="737f9-193">Direcciones URL</span><span class="sxs-lookup"><span data-stu-id="737f9-193">URLs</span></span>

  - <span data-ttu-id="737f9-194">**Dominio de dirección URL**</span><span class="sxs-lookup"><span data-stu-id="737f9-194">**URL domain**</span></span>
  - <span data-ttu-id="737f9-195">**Dominio y ruta de acceso de dirección URL**</span><span class="sxs-lookup"><span data-stu-id="737f9-195">**URL domain and path**</span></span>
  - <span data-ttu-id="737f9-196">**URL**</span><span class="sxs-lookup"><span data-stu-id="737f9-196">**URL**</span></span>
  - <span data-ttu-id="737f9-197">**Ruta de dirección URL**</span><span class="sxs-lookup"><span data-stu-id="737f9-197">**URL path**</span></span>
  - <span data-ttu-id="737f9-198">**Haga clic en veredicto**</span><span class="sxs-lookup"><span data-stu-id="737f9-198">**Click verdict**</span></span>

<span data-ttu-id="737f9-199">Para un filtrado más avanzado, incluido el filtrado por varias propiedades, puede hacer clic en el botón **filtro avanzado** para crear una consulta.</span><span class="sxs-lookup"><span data-stu-id="737f9-199">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="737f9-200">Están disponibles las mismas propiedades de la campaña, pero con las siguientes mejoras:</span><span class="sxs-lookup"><span data-stu-id="737f9-200">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="737f9-201">Puede hacer clic en **Agregar condición** para seleccionar varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="737f9-201">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="737f9-202">Puede elegir el operador **y** u **o** entre las condiciones.</span><span class="sxs-lookup"><span data-stu-id="737f9-202">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="737f9-203">Puede seleccionar el elemento de **grupo de condición** en la parte inferior de la lista de condiciones para crear condiciones compuestas complejas.</span><span class="sxs-lookup"><span data-stu-id="737f9-203">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="737f9-204">Cuando haya terminado, haga clic en el botón **consulta** .</span><span class="sxs-lookup"><span data-stu-id="737f9-204">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="737f9-205">Después de crear un filtro básico o avanzado, puede guardarlo con **Guardar consulta** o **Guardar consulta como**.</span><span class="sxs-lookup"><span data-stu-id="737f9-205">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="737f9-206">Más adelante, cuando vuelva a las vistas de campañas, puede cargar un filtro guardado haciendo clic en **configuración de consulta guardada**.</span><span class="sxs-lookup"><span data-stu-id="737f9-206">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="737f9-207">Para exportar el gráfico o la lista de campañas, haga clic en **exportar** y seleccione **exportar datos de gráfico** o **Exportar lista de campañas**.</span><span class="sxs-lookup"><span data-stu-id="737f9-207">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="737f9-208">Si tiene una suscripción ATP de Microsoft defender, puede hacer clic en **WDATP** para conectar o desconectar la información sobre campañas con ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="737f9-208">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="737f9-209">Para obtener más información, consulte [integrar Office 365 ATP con Microsoft defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="737f9-209">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="737f9-210">Detalles de la campaña</span><span class="sxs-lookup"><span data-stu-id="737f9-210">Campaign details</span></span>

<span data-ttu-id="737f9-211">Al hacer clic en el nombre de una campaña, los detalles de la campaña aparecen en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="737f9-211">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="737f9-212">Información de la campaña</span><span class="sxs-lookup"><span data-stu-id="737f9-212">Campaign information</span></span>

<span data-ttu-id="737f9-213">En la parte superior de la vista detalles de la campaña, está disponible la siguiente información de la campaña:</span><span class="sxs-lookup"><span data-stu-id="737f9-213">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="737f9-214">**ID**: el identificador único de la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-214">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="737f9-215">**Iniciado** y **finalizado**: fecha de inicio y fecha de finalización de la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-215">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="737f9-216">Tenga en cuenta que estas fechas pueden extenderse más allá de las fechas de filtro que ha seleccionado en la página información general.</span><span class="sxs-lookup"><span data-stu-id="737f9-216">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="737f9-217">**Impacto**: esta sección contiene los datos siguientes para el filtro de intervalo de fechas que haya seleccionado (o que seleccione en la escala de tiempo):</span><span class="sxs-lookup"><span data-stu-id="737f9-217">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="737f9-218">Número total de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="737f9-218">The total number of recipients.</span></span>
  - <span data-ttu-id="737f9-219">El número de mensajes que se han "bandeja de entrada" (es decir, que se entregan a la bandeja de entrada y no a la carpeta de correo electrónico no deseado).</span><span class="sxs-lookup"><span data-stu-id="737f9-219">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="737f9-220">El número de usuarios que hizo clic en la carga de la URL en el mensaje de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="737f9-220">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="737f9-221">Howe muchos usuarios visitaron la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="737f9-221">Howe many users visited the URL.</span></span>

- <span data-ttu-id="737f9-222">**Destino**: porcentaje calculado por: (el número de destinatarios de la campaña de la organización)/(el número total de destinatarios en la campaña en todas las organizaciones del servicio).</span><span class="sxs-lookup"><span data-stu-id="737f9-222">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="737f9-223">Tenga en cuenta que este valor se calcula en toda la duración de la campaña y no cambia en función de los filtros de fecha.</span><span class="sxs-lookup"><span data-stu-id="737f9-223">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="737f9-224">Escala de tiempo interactiva de la actividad de la campaña: la escala de tiempo muestra la actividad durante toda la duración de la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-224">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="737f9-225">De forma predeterminada, el área sombreada incluye el filtro de intervalo de fechas que ha seleccionado en la información general.</span><span class="sxs-lookup"><span data-stu-id="737f9-225">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="737f9-226">Puede hacer clic y arrastrar para seleccionar un punto inicial y un punto final específicos, <u>que cambiarán los datos que se muestran en el área de **impacto** y el resto de la página, tal y como se describe en las siguientes secciones</u>.</span><span class="sxs-lookup"><span data-stu-id="737f9-226">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="737f9-227">En la barra de título, puede hacer clic en el icono de descarga de la campaña de descarga del botón de instalación de la **campaña** ![ para descargar ](../../media/download-campaign-write-up-button.png) los detalles de la campaña en un documento de Word (de forma predeterminada, con el nombre CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="737f9-227">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="737f9-228">Tenga en cuenta que la descarga contiene detalles sobre toda la duración de la campaña (no solo las fechas de filtro seleccionadas).</span><span class="sxs-lookup"><span data-stu-id="737f9-228">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Información de la campaña](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="737f9-230">Flujo de la campaña</span><span class="sxs-lookup"><span data-stu-id="737f9-230">Campaign flow</span></span>

<span data-ttu-id="737f9-231">En la parte central de la vista detalles de la campaña, los detalles importantes sobre la campaña se presentan en la sección **flujo** en un diagrama de flujo horizontal (conocido como diagrama _Sankey_ ).</span><span class="sxs-lookup"><span data-stu-id="737f9-231">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="737f9-232">Estos detalles pueden ayudarle a comprender los elementos de la campaña y su posible impacto en la organización.</span><span class="sxs-lookup"><span data-stu-id="737f9-232">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="737f9-233">La información que se muestra en el diagrama de **flujo** está controlada por el intervalo de fechas sombreado de la escala de tiempo tal como se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="737f9-233">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Detalles de la campaña que no contienen clics del usuario en la URL.](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="737f9-235">Si coloca el puntero del mouse sobre una de las bandas horizontales del diagrama, verá el número de mensajes relacionados (por ejemplo, mensajes de una IP de origen en particular, mensajes de la dirección IP de origen con el dominio de remitente especificado, etc.).</span><span class="sxs-lookup"><span data-stu-id="737f9-235">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="737f9-236">El diagrama contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="737f9-236">The diagram contains the following information:</span></span>

- <span data-ttu-id="737f9-237">**IP de remitentes**</span><span class="sxs-lookup"><span data-stu-id="737f9-237">**Sender IPs**</span></span>

- <span data-ttu-id="737f9-238">**Dominios de remitente**</span><span class="sxs-lookup"><span data-stu-id="737f9-238">**Sender domains**</span></span>

- <span data-ttu-id="737f9-239">**Filtrar veredictos**: los valores de veredicto están relacionados con los veredictos de filtrado de suplantación de identidad y correo no deseado disponibles, como se describe en [encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="737f9-239">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="737f9-240">En la tabla siguiente se describen los valores disponibles:</span><span class="sxs-lookup"><span data-stu-id="737f9-240">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="737f9-241">Valor</span><span class="sxs-lookup"><span data-stu-id="737f9-241">Value</span></span>|<span data-ttu-id="737f9-242">Veredicto de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="737f9-242">Spam filter verdict</span></span>|<span data-ttu-id="737f9-243">Description</span><span class="sxs-lookup"><span data-stu-id="737f9-243">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="737f9-244">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="737f9-244">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="737f9-245">El mensaje se marcó como no es correo no deseado o omitido antes de ser evaluado por el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="737f9-245">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="737f9-246">Por ejemplo, un mensaje se marcó como no correo no deseado mediante una regla de flujo de correo (también denominada regla de transporte).</span><span class="sxs-lookup"><span data-stu-id="737f9-246">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span><br/><br/><span data-ttu-id="737f9-247">El mensaje omitió el filtrado de correo no deseado por otros motivos.</span><span class="sxs-lookup"><span data-stu-id="737f9-247">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="737f9-248">Por ejemplo, el remitente y el destinatario parecen estar en la misma organización.</span><span class="sxs-lookup"><span data-stu-id="737f9-248">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="737f9-249">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="737f9-249">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="737f9-250">El mensaje se marcó como correo no deseado antes de ser evaluado por el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="737f9-250">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="737f9-251">Por ejemplo, por una regla de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="737f9-251">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="737f9-252">**Detectados**</span><span class="sxs-lookup"><span data-stu-id="737f9-252">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="737f9-253">El mensaje se marcó como correo no deseado por el filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="737f9-253">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="737f9-254">**No detectado**</span><span class="sxs-lookup"><span data-stu-id="737f9-254">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="737f9-255">El mensaje se marcó como no correo no deseado por el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="737f9-255">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="737f9-256">**Exento**</span><span class="sxs-lookup"><span data-stu-id="737f9-256">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="737f9-257">El mensaje omitió el filtrado de correo no deseado porque se liberó de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="737f9-257">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="737f9-258">**Permitir inquilino**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="737f9-258">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="737f9-259">El mensaje omitió el filtrado de correo no deseado debido a la configuración de una directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="737f9-259">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="737f9-260">Por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="737f9-260">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="737f9-261">**Bloque tenant**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="737f9-261">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="737f9-262">El mensaje fue bloqueado por el filtrado de correo no deseado debido a la configuración de una directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="737f9-262">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="737f9-263">Por ejemplo, el remitente estaba en la lista de remitentes permitidos o en la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="737f9-263">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="737f9-264">**Permitir al usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="737f9-264">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="737f9-265">El mensaje omitió el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes seguros del usuario.</span><span class="sxs-lookup"><span data-stu-id="737f9-265">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="737f9-266">**Bloque de usuario**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="737f9-266">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="737f9-267">El mensaje fue bloqueado por el filtrado de correo no deseado porque el remitente estaba en la lista de remitentes bloqueados del usuario.</span><span class="sxs-lookup"><span data-stu-id="737f9-267">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="737f9-268">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="737f9-268">**ZAP**</span></span>|<span data-ttu-id="737f9-269">No aplicable</span><span class="sxs-lookup"><span data-stu-id="737f9-269">n/a</span></span>|<span data-ttu-id="737f9-270">La [depuración automática de cero horas (ZAP)](zero-hour-auto-purge.md) movió el mensaje entregado a la carpeta de correo electrónico no deseado o a la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="737f9-270">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="737f9-271">La acción se configura en la Directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="737f9-271">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="737f9-272"><sup>\*</sup> Revise las directivas contra correo no deseado, ya que es probable que el servicio haya bloqueado el mensaje permitido.</span><span class="sxs-lookup"><span data-stu-id="737f9-272"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="737f9-273"><sup>\*\*</sup> Revise las directivas contra correo no deseado, ya que estos mensajes deben estar en cuarentena, no entregados.</span><span class="sxs-lookup"><span data-stu-id="737f9-273"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="737f9-274">**Ubicaciones de entrega**: probablemente querrá investigar los mensajes que se entregaron a los destinatarios (ya sea a la bandeja de entrada o a la carpeta de correo electrónico no deseado), incluso si los usuarios no han hecho clic en la dirección URL de carga en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="737f9-274">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="737f9-275">También puede quitar los mensajes en cuarentena de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="737f9-275">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="737f9-276">Para obtener más información, vea [mensajes de correo electrónico en cuarentena en EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="737f9-276">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="737f9-277">**Carpeta eliminada**</span><span class="sxs-lookup"><span data-stu-id="737f9-277">**Deleted folder**</span></span>
  - <span data-ttu-id="737f9-278">**Sombra**</span><span class="sxs-lookup"><span data-stu-id="737f9-278">**Dropped**</span></span>
  - <span data-ttu-id="737f9-279">**Externos**: el destinatario se encuentra en su organización de correo electrónico local en entornos híbridos.</span><span class="sxs-lookup"><span data-stu-id="737f9-279">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="737f9-280">**Failed**</span><span class="sxs-lookup"><span data-stu-id="737f9-280">**Failed**</span></span>
  - <span data-ttu-id="737f9-281">**Reenviado**</span><span class="sxs-lookup"><span data-stu-id="737f9-281">**Forwarded**</span></span>
  - <span data-ttu-id="737f9-282">**Bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="737f9-282">**Inbox**</span></span>
  - <span data-ttu-id="737f9-283">**Carpeta de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="737f9-283">**Junk folder**</span></span>
  - <span data-ttu-id="737f9-284">**Cuarentena**</span><span class="sxs-lookup"><span data-stu-id="737f9-284">**Quarantine**</span></span>
  - <span data-ttu-id="737f9-285">**Desconocido**</span><span class="sxs-lookup"><span data-stu-id="737f9-285">**Unknown**</span></span>

- <span data-ttu-id="737f9-286">**Clics de dirección URL**: estos valores se describen en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="737f9-286">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="737f9-287">En todas las capas que contienen más de 10 elementos, se muestran los 10 elementos principales, mientras que el resto se agrupan en **otros**.</span><span class="sxs-lookup"><span data-stu-id="737f9-287">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="737f9-288">Clics de URL</span><span class="sxs-lookup"><span data-stu-id="737f9-288">URL clicks</span></span>

<span data-ttu-id="737f9-289">Cuando un mensaje de suplantación de identidad se entrega a la bandeja de entrada o a la carpeta de correo no deseado del destinatario, siempre existe la posibilidad de que el usuario haga clic en la dirección URL de la carga.</span><span class="sxs-lookup"><span data-stu-id="737f9-289">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="737f9-290">No hacer clic en la dirección URL es una pequeña medida del éxito, pero debe determinar por qué el mensaje de suplantación de identidad se entregó hasta el buzón.</span><span class="sxs-lookup"><span data-stu-id="737f9-290">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="737f9-291">Si un usuario hace clic en la dirección URL de carga en el mensaje de suplantación de identidad (phishing), las acciones se muestran en el área de **clics de la dirección URL** del diagrama en la vista detalles de la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-291">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="737f9-292">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="737f9-292">**Allowed**</span></span>

- <span data-ttu-id="737f9-293">**BlockPage**: el destinatario hizo clic en la dirección URL de carga, pero su acceso al sitio Web malintencionado fue bloqueado por una directiva de [vínculos seguros](atp-safe-links.md) en su organización.</span><span class="sxs-lookup"><span data-stu-id="737f9-293">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](atp-safe-links.md) policy in your organization.</span></span>

- <span data-ttu-id="737f9-294">**BlockPageOverride**: el destinatario hizo clic en la dirección URL de carga en el mensaje, los vínculos seguros intentaron detenerlos, pero podían invalidar el bloque.</span><span class="sxs-lookup"><span data-stu-id="737f9-294">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="737f9-295">Revise sus [directivas de vínculos seguros](set-up-atp-safe-links-policies.md) para ver por qué los usuarios pueden invalidar el veredicto de vínculos seguros y continuar con el sitio Web malintencionado.</span><span class="sxs-lookup"><span data-stu-id="737f9-295">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="737f9-296">**PendingDetonationPage**: datos adjuntos seguros en Office 365 ATP está en proceso de abrir y investigar la dirección URL de carga en un entorno de equipo virtual.</span><span class="sxs-lookup"><span data-stu-id="737f9-296">**PendingDetonationPage**: Safe Attachments in Office 365 ATP is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>

- <span data-ttu-id="737f9-297">**PendingDetonationPageOverride**: el destinatario tuvo permiso para invalidar el proceso de detonación de carga y abrir la dirección URL sin esperar los resultados.</span><span class="sxs-lookup"><span data-stu-id="737f9-297">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="737f9-298">Pestañas</span><span class="sxs-lookup"><span data-stu-id="737f9-298">Tabs</span></span>

<span data-ttu-id="737f9-299">Las pestañas de la vista detalles de la campaña le permiten investigar más detalladamente la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-299">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="737f9-300">La información que se muestra en las pestañas se controla mediante el intervalo de fechas sombreado en la escala de tiempo como se describe en la sección información de la [campaña](#campaign-information) .</span><span class="sxs-lookup"><span data-stu-id="737f9-300">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="737f9-301">**Clics en dirección URL**: si los usuarios no han hecho clic en la dirección URL de la carga en el mensaje, esta sección estará en blanco.</span><span class="sxs-lookup"><span data-stu-id="737f9-301">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="737f9-302">Si un usuario pudo hacer clic en la dirección URL, se rellenarán los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="737f9-302">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="737f9-303">**Usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="737f9-303">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="737f9-304">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="737f9-304">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="737f9-305">**Haga clic en hora**</span><span class="sxs-lookup"><span data-stu-id="737f9-305">**Click time**</span></span>
  - <span data-ttu-id="737f9-306">**Haga clic en veredicto**</span><span class="sxs-lookup"><span data-stu-id="737f9-306">**Click verdict**</span></span>

- <span data-ttu-id="737f9-307">**IP de remitentes**</span><span class="sxs-lookup"><span data-stu-id="737f9-307">**Sender IPs**</span></span>

  - <span data-ttu-id="737f9-308">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="737f9-308">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="737f9-309">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="737f9-309">**Total count**</span></span>
  - <span data-ttu-id="737f9-310">**En la bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="737f9-310">**Inboxed**</span></span>
  - <span data-ttu-id="737f9-311">**Sin bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="737f9-311">**Not Inboxed**</span></span>
  - <span data-ttu-id="737f9-312">**SPF superado**: el [marco de directivas de remitente (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)autenticó el remitente.</span><span class="sxs-lookup"><span data-stu-id="737f9-312">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="737f9-313">Un remitente que no pasa la validación SPF indica que un remitente no está autenticado o que el mensaje está suplantando a un remitente legítimo.</span><span class="sxs-lookup"><span data-stu-id="737f9-313">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="737f9-314">**Remitentes**</span><span class="sxs-lookup"><span data-stu-id="737f9-314">**Senders**</span></span>

  - <span data-ttu-id="737f9-315">**Sender**: esta es la dirección del remitente real en el comando SMTP mail from, que no tiene que ser necesariamente la dirección de correo electrónico que los usuarios ven en sus clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="737f9-315">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="737f9-316">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="737f9-316">**Total count**</span></span>
  - <span data-ttu-id="737f9-317">**En la bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="737f9-317">**Inboxed**</span></span>
  - <span data-ttu-id="737f9-318">**Sin bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="737f9-318">**Not Inboxed**</span></span>
  - <span data-ttu-id="737f9-319">**DKIM pasado**: el remitente ha sido autenticado por el [correo identificado por claves de dominio (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="737f9-319">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="737f9-320">Un remitente que no pasa la validación de DKIM indica un remitente no autenticado o el mensaje está suplantando a un remitente legítimo.</span><span class="sxs-lookup"><span data-stu-id="737f9-320">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="737f9-321">**DMARC pasada**: el remitente ha sido autenticado por la [autenticación de mensajes basada en dominio, la creación de informes y la conformidad (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="737f9-321">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="737f9-322">Un remitente que no pasa la validación de DMARC indica un remitente no autenticado o el mensaje está suplantando a un remitente legítimo.</span><span class="sxs-lookup"><span data-stu-id="737f9-322">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="737f9-323">**Datos adjuntos**</span><span class="sxs-lookup"><span data-stu-id="737f9-323">**Attachments**</span></span>

  - <span data-ttu-id="737f9-324">**Filename**</span><span class="sxs-lookup"><span data-stu-id="737f9-324">**Filename**</span></span>
  - <span data-ttu-id="737f9-325">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="737f9-325">**SHA256**</span></span>
  - <span data-ttu-id="737f9-326">**Familia de malware**</span><span class="sxs-lookup"><span data-stu-id="737f9-326">**Malware family**</span></span>
  - <span data-ttu-id="737f9-327">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="737f9-327">**Total count**</span></span>

- <span data-ttu-id="737f9-328">**URL**</span><span class="sxs-lookup"><span data-stu-id="737f9-328">**URL**</span></span>

  - <span data-ttu-id="737f9-329">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="737f9-329">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="737f9-330">**Recuento total**</span><span class="sxs-lookup"><span data-stu-id="737f9-330">**Total Count**</span></span>

<span data-ttu-id="737f9-331"><sup>\*</sup> Al hacer clic en este valor, se abre un nuevo control flotante que contiene más detalles sobre el elemento especificado (usuario, URL, etc.) en la parte superior de la vista de detalles de la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-331"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="737f9-332">Para volver a la vista de detalles de la campaña, haga clic en **Hecho** en el nuevo control flotante.</span><span class="sxs-lookup"><span data-stu-id="737f9-332">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="737f9-333">Botones</span><span class="sxs-lookup"><span data-stu-id="737f9-333">Buttons</span></span>

<span data-ttu-id="737f9-334">Los botones de la vista de detalles de la campaña le permiten usar todo el potencial del Explorador de amenazas para investigar más a fondo la campaña.</span><span class="sxs-lookup"><span data-stu-id="737f9-334">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="737f9-335">**Explorar campaña**: abre una nueva pestaña de búsqueda del Explorador de amenazas con el valor **Id. de campaña** como filtro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="737f9-335">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="737f9-336">**Explorar mensajes**de la bandeja de entrada: abre una nueva ficha de búsqueda del explorador de amenazas usando el identificador de la **campaña** y la **Ubicación de entrega: bandeja de entrada** como filtro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="737f9-336">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
