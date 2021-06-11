---
title: Vistas en el Explorador de amenazas y detecciones en tiempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre cómo usar el Explorador de amenazas y el informe de detecciones en tiempo real para investigar y responder a las amenazas en el Centro de seguridad & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78c03b45063f4bc34b47ab003bcf00d2befab886
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207331"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="bdaa2-103">Vistas en el Explorador de amenazas y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="bdaa2-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bdaa2-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="bdaa2-104">**Applies to**</span></span>
- [<span data-ttu-id="bdaa2-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="bdaa2-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bdaa2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdaa2-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


![Explorador de amenazas](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="bdaa2-108">[El Explorador de](threat-explorer.md) amenazas (y el informe de detecciones en tiempo real) es una herramienta eficaz y casi en tiempo real que ayuda a los equipos de operaciones de seguridad a investigar y responder a las amenazas en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="bdaa2-109">El Explorador (y el informe de detecciones en tiempo real) muestra información sobre el malware sospechoso y la suplantación de identidad (phish) en el correo electrónico y los archivos de Office 365, así como otras amenazas y riesgos de seguridad para su organización.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="bdaa2-110">Si tienes [Microsoft Defender para Office 365](defender-for-office-365.md) plan 2, tienes Explorer.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-110">If you have [Microsoft Defender for Office 365](defender-for-office-365.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="bdaa2-111">Si tienes Microsoft Defender para Office 365 plan 1, tienes detecciones en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="bdaa2-112">Al abrir por primera vez el Explorador (o el informe de detecciones en tiempo real), la vista predeterminada muestra las detecciones de malware de correo electrónico de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="bdaa2-113">Este informe también puede mostrar Microsoft Defender para detecciones Office 365, como direcciones URL malintencionadas detectadas por [Caja fuerte Links](safe-links.md)y archivos malintencionados detectados por [Caja fuerte Attachments](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="bdaa2-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](safe-links.md), and malicious files detected by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="bdaa2-114">Este informe se puede modificar para mostrar datos de los últimos 30 días (con una suscripción de pago de Microsoft Defender Office 365 P2).</span><span class="sxs-lookup"><span data-stu-id="bdaa2-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="bdaa2-115">Las suscripciones de prueba solo incluirán datos de los últimos siete días.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="bdaa2-116">Suscripción</span><span class="sxs-lookup"><span data-stu-id="bdaa2-116">Subscription</span></span>|<span data-ttu-id="bdaa2-117">Utilidad</span><span class="sxs-lookup"><span data-stu-id="bdaa2-117">Utility</span></span>|<span data-ttu-id="bdaa2-118">Días de datos</span><span class="sxs-lookup"><span data-stu-id="bdaa2-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="bdaa2-119">Prueba de Microsoft Defender Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="bdaa2-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="bdaa2-120">Detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="bdaa2-120">Real-time detections</span></span>|<span data-ttu-id="bdaa2-121">7 </span><span class="sxs-lookup"><span data-stu-id="bdaa2-121">7</span></span>|
|<span data-ttu-id="bdaa2-122">Microsoft Defender para Office 365 P1 pagado</span><span class="sxs-lookup"><span data-stu-id="bdaa2-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="bdaa2-123">Detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="bdaa2-123">Real-time detections</span></span>|<span data-ttu-id="bdaa2-124">30</span><span class="sxs-lookup"><span data-stu-id="bdaa2-124">30</span></span>|
|<span data-ttu-id="bdaa2-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span><span class="sxs-lookup"><span data-stu-id="bdaa2-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="bdaa2-126">Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="bdaa2-126">Threat Explorer</span></span>|<span data-ttu-id="bdaa2-127">7 </span><span class="sxs-lookup"><span data-stu-id="bdaa2-127">7</span></span>|
|<span data-ttu-id="bdaa2-128">Prueba de Microsoft Defender Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="bdaa2-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="bdaa2-129">Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="bdaa2-129">Threat Explorer</span></span>|<span data-ttu-id="bdaa2-130">7 </span><span class="sxs-lookup"><span data-stu-id="bdaa2-130">7</span></span>|
|<span data-ttu-id="bdaa2-131">Microsoft Defender para Office 365 P2 pagado</span><span class="sxs-lookup"><span data-stu-id="bdaa2-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="bdaa2-132">Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="bdaa2-132">Threat Explorer</span></span>|<span data-ttu-id="bdaa2-133">30</span><span class="sxs-lookup"><span data-stu-id="bdaa2-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="bdaa2-134">Pronto ampliaremos el límite de búsqueda y retención de datos del Explorador (y detecciones en tiempo real) para los inquilinos de prueba de 7 a 30 días.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="bdaa2-135">Este cambio se realiza como parte del elemento de la hoja de ruta n. 70544 y actualmente se encuentra en una fase de implementación.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="bdaa2-136">Use el **menú** Ver para cambiar la información que se muestra.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="bdaa2-137">Las herramientas le ayudan a determinar qué vista usar.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-137">Tooltips help you determine which view to use.</span></span>

![Menú Vista del Explorador de amenazas](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="bdaa2-139">Una vez que haya seleccionado una vista, puede aplicar filtros y configurar consultas para realizar análisis adicionales.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="bdaa2-140">Las secciones siguientes proporcionan una breve introducción a las distintas vistas disponibles en el Explorador (o detecciones en tiempo real).</span><span class="sxs-lookup"><span data-stu-id="bdaa2-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="bdaa2-141">Malware > correo electrónico</span><span class="sxs-lookup"><span data-stu-id="bdaa2-141">Email > Malware</span></span>

<span data-ttu-id="bdaa2-142">Para ver este informe, en el Explorador (o detecciones en tiempo real), elija **Ver** malware \>  \> **de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="bdaa2-143">Esta vista muestra información sobre los mensajes de correo electrónico que se identificaron como que contienen malware.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-143">This view shows information about email messages that were identified as containing malware.</span></span>

![Ver datos sobre el correo electrónico identificado como malware](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="bdaa2-145">Haga **clic en** Remitente para abrir la lista de opciones de visualización.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="bdaa2-146">Use esta lista para ver datos por remitente, destinatarios, dominio del remitente, asunto, tecnología de detección, estado de protección y mucho más.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="bdaa2-147">Por ejemplo, para ver qué acciones se realizaron en los mensajes de correo electrónico detectados, elija **Estado de protección en** la lista.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="bdaa2-148">Seleccione una opción y, a continuación, haga clic en el botón Actualizar para aplicar ese filtro al informe.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Opciones de estado de protección contra amenazas para el Explorador de amenazas](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="bdaa2-150">Debajo del gráfico, vea más detalles sobre mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="bdaa2-151">Al seleccionar un elemento de la lista, se abre un panel desplegable, donde puede obtener más información sobre el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Explorador de amenazas con el menú desplegable abierto](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="bdaa2-153">Correo electrónico > phish</span><span class="sxs-lookup"><span data-stu-id="bdaa2-153">Email > Phish</span></span>

<span data-ttu-id="bdaa2-154">Para ver este informe, en el Explorador (o detecciones en tiempo real), elija **Ver** \> **suplantación de** identidad \> **de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="bdaa2-155">En esta vista se muestran los mensajes de correo electrónico identificados como intentos de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-155">This view shows email messages identified as phishing attempts.</span></span>

![Ver datos sobre el correo electrónico identificado como intentos de suplantación de identidad](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="bdaa2-157">Haga **clic en** Remitente para abrir la lista de opciones de visualización.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="bdaa2-158">Use esta lista para ver los datos por remitente, destinatarios, dominio del remitente, IP del remitente, dominio url, veredicto de clic y mucho más.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="bdaa2-159">Por ejemplo, para ver qué acciones se realizaron cuando las personas hicieron clic en direcciones URL que se identificaron como intentos de suplantación de identidad, elija Hacer clic en veredicto en la lista, seleccione una o más opciones y, a continuación, haga clic en el botón Actualizar. </span><span class="sxs-lookup"><span data-stu-id="bdaa2-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Haga clic en opciones de veredicto para el informe de suplantación de identidad](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="bdaa2-161">Debajo del gráfico, vea más detalles sobre mensajes específicos, clics de dirección URL, direcciones URL y origen de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![Direcciones URL detectadas como suplantación de identidad en mensajes de correo electrónico](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="bdaa2-163">Al seleccionar un elemento de la lista, como una dirección URL que se detectó, se abrirá un panel desplegable, donde podrá obtener más información sobre el elemento que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Detalles sobre una dirección URL detectada](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="bdaa2-165">Envíos > correo electrónico</span><span class="sxs-lookup"><span data-stu-id="bdaa2-165">Email > Submissions</span></span>

<span data-ttu-id="bdaa2-166">Para ver este informe, en el Explorador (o detecciones en tiempo real), elija **Ver** \>  \> **envíos de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="bdaa2-167">Esta vista muestra el correo electrónico que los usuarios han notificado como correo no deseado, no como correo no deseado o correo electrónico de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![Mensajes de correo electrónico notificados por los usuarios](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="bdaa2-169">Haga **clic en** Remitente para abrir la lista de opciones de visualización.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="bdaa2-170">Use esta lista para ver información por remitente, destinatarios, tipo de informe (la determinación del usuario de que el correo electrónico era correo no deseado, no correo no deseado o suplantación de identidad) y mucho más.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="bdaa2-171">Por ejemplo, para ver información sobre los mensajes de  correo electrónico que se notificaron como intentos de suplantación de identidad, haga clic en Tipo de informe del remitente, seleccione Suplantación de identidad y, a continuación, haga clic en \> el botón Actualizar. </span><span class="sxs-lookup"><span data-stu-id="bdaa2-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish seleccionado para el filtro tipo de informe](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="bdaa2-173">Debajo del gráfico, vea más detalles sobre mensajes de correo electrónico específicos, como la línea de asunto, la dirección IP del remitente, el usuario que informó del mensaje como correo no deseado, no correo no deseado o suplantación de identidad, etc.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Mensajes que se han notificado como intentos de suplantación de identidad](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="bdaa2-175">Seleccione un elemento de la lista para ver detalles adicionales.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="bdaa2-176">Correo > todo el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="bdaa2-176">Email > All email</span></span>

<span data-ttu-id="bdaa2-177">Para ver este informe, en el Explorador, elija **Ver** \> **correo electrónico** todo el \> **correo**.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="bdaa2-178">Esta vista muestra una vista general de la actividad del correo electrónico, incluido el correo electrónico identificado como malintencionado debido a la suplantación de identidad o malware, así como todo el correo no malintencionado (correo electrónico normal, correo no deseado y correo masivo).</span><span class="sxs-lookup"><span data-stu-id="bdaa2-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="bdaa2-179">Si recibe un error que lee **demasiados** datos para mostrar, agregue un filtro y, si es necesario, limite el intervalo de fechas que está viendo.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="bdaa2-180">Para aplicar un filtro, elija **Remitente**, seleccione un elemento de la lista y, a continuación, haga clic en el botón Actualizar.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="bdaa2-181">En nuestro ejemplo, utilizamos la **tecnología de detección** como filtro (hay varias opciones disponibles).</span><span class="sxs-lookup"><span data-stu-id="bdaa2-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="bdaa2-182">Ver información por remitente, dominio del remitente, destinatarios, asunto, nombre de archivo de datos adjuntos, familia de malware, estado de protección (acciones realizadas por las características y directivas de protección contra amenazas en Office 365), tecnología de detección (cómo se detectó el malware) y mucho más.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Ver datos sobre el correo electrónico detectado mediante tecnología de detección](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="bdaa2-184">Debajo del gráfico, vea más detalles sobre mensajes de correo electrónico específicos, como la línea de asunto, el destinatario, el remitente, el estado, etc.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="bdaa2-185">Malware > contenido</span><span class="sxs-lookup"><span data-stu-id="bdaa2-185">Content > Malware</span></span>

<span data-ttu-id="bdaa2-186">Para ver este informe, en el Explorador (o detecciones en tiempo real), elija **Ver** \> **malware de** \> **contenido**.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="bdaa2-187">Esta vista muestra los archivos identificados como malintencionados por Microsoft Defender para Office 365 en [SharePoint Online, OneDrive para la Empresa y Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bdaa2-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="bdaa2-188">Ver información por familia de malware, tecnología de detección (cómo se detectó el malware) y carga de trabajo (OneDrive, SharePoint o Teams).</span><span class="sxs-lookup"><span data-stu-id="bdaa2-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Ver datos sobre malware detectado](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="bdaa2-190">Debajo del gráfico, vea más detalles sobre archivos específicos, como el nombre de archivo de datos adjuntos, la carga de trabajo, el tamaño del archivo, quién modificó por última vez el archivo y mucho más.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="bdaa2-191">Capacidades de hacer clic y filtrar</span><span class="sxs-lookup"><span data-stu-id="bdaa2-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="bdaa2-192">Con el Explorador (y las detecciones en tiempo real), puede aplicar un filtro en un clic.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="bdaa2-193">Haga clic en un elemento de la leyenda y ese elemento se convierte en un filtro para el informe.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="bdaa2-194">Por ejemplo, supongamos que estamos viendo la vista Malware en el Explorador:</span><span class="sxs-lookup"><span data-stu-id="bdaa2-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Ir al Explorador de administración de \> amenazas](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="bdaa2-196">Al **hacer clic en Detonación de ATP** en este gráfico, se muestra una vista como esta:</span><span class="sxs-lookup"><span data-stu-id="bdaa2-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Explorador filtrado para mostrar solo Defender para obtener Office 365 detonación](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="bdaa2-198">En esta vista, ahora estamos buscando datos para los archivos que fueron detonados [por Caja fuerte datos adjuntos](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="bdaa2-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="bdaa2-199">Debajo del gráfico, podemos ver detalles sobre mensajes de correo electrónico específicos que tenían datos adjuntos detectados por Caja fuerte datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Detalles específicos sobre los mensajes de correo electrónico con datos adjuntos detectados](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="bdaa2-201">Al seleccionar uno o varios elementos, se activa el menú **Acciones,** que ofrece varias opciones entre las que elegir para los elementos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Al seleccionar un elemento se activa el menú Acciones](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="bdaa2-203">La capacidad de filtrar en un clic y navegar a detalles específicos puede ahorrarle mucho tiempo en investigar amenazas.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="bdaa2-204">Consultas y filtros</span><span class="sxs-lookup"><span data-stu-id="bdaa2-204">Queries and filters</span></span>

<span data-ttu-id="bdaa2-205">El Explorador (así como el informe de detecciones en tiempo real) tiene varios filtros eficaces y capacidades de consulta que le permiten profundizar en detalles, como los principales usuarios dirigidos, las principales familias de malware, la tecnología de detección y mucho más.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="bdaa2-206">Cada tipo de informe ofrece una variedad de formas de ver y explorar datos.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdaa2-207">No use caracteres comodín, como un asterisco o un signo de interrogación, en la barra de consultas del Explorador (o detecciones en tiempo real).</span><span class="sxs-lookup"><span data-stu-id="bdaa2-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="bdaa2-208">Al buscar mensajes de correo electrónico en el campo **Asunto,** el Explorador (o detecciones en tiempo real) realizará coincidencias parciales y dará resultados similares a una búsqueda de caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="bdaa2-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
