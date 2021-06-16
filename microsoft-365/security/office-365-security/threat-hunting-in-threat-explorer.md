---
title: Búsqueda de amenazas en el Explorador de amenazas para Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Use el Explorador de amenazas o las detecciones en tiempo real en el portal de Microsoft 365 Defender para investigar y responder a las amenazas de forma eficaz.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71052cc5a3874da250772bfa628417824ba51c63
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930138"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="842c4-103">Búsqueda de amenazas en el Explorador de amenazas para Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="842c4-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="842c4-104">En este artículo:</span><span class="sxs-lookup"><span data-stu-id="842c4-104">In this article:</span></span>

- [<span data-ttu-id="842c4-105">Paso a paso del Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="842c4-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="842c4-106">Investigación de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="842c4-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="842c4-107">Corrección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="842c4-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="842c4-108">Mejoras en la experiencia de búsqueda de amenazas</span><span class="sxs-lookup"><span data-stu-id="842c4-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="842c4-109">Esto forma parte de una serie de **3** artículos sobre explorador de amenazas **(Explorer),** seguridad de correo electrónico y **conceptos** básicos de detecciones de Explorador y tiempo real (como diferencias entre las herramientas y los permisos necesarios para operarlas).</span><span class="sxs-lookup"><span data-stu-id="842c4-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="842c4-110">Los otros dos artículos de esta serie son Seguridad de correo [electrónico con](email-security-in-microsoft-defender.md) el Explorador de amenazas y el Explorador de amenazas y [conceptos](real-time-detections.md)básicos de detecciones en tiempo real .</span><span class="sxs-lookup"><span data-stu-id="842c4-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="842c4-111">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="842c4-111">**Applies to**</span></span>
- [<span data-ttu-id="842c4-112">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="842c4-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="842c4-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="842c4-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="842c4-114">Si su organización tiene [Microsoft Defender](defender-for-office-365.md)para Office 365 y tiene los [permisos,](#required-licenses-and-permissions)puede usar detecciones en tiempo **real** o **explorador** para detectar y corregir amenazas.</span><span class="sxs-lookup"><span data-stu-id="842c4-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span> 

<span data-ttu-id="842c4-115">En el **portal Microsoft 365 Defender,** vaya **a Correo electrónico & colaboración** y, a continuación, **elija Explorador**.</span><span class="sxs-lookup"><span data-stu-id="842c4-115">In the **Microsoft 365 Defender portal**, go to **Email & collaboration**, and then choose **Explorer**.</span></span>

<br>

****

|<span data-ttu-id="842c4-116">Con Microsoft Defender para Office 365 plan 2, verá:</span><span class="sxs-lookup"><span data-stu-id="842c4-116">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="842c4-117">Con Microsoft Defender para Office 365 plan 1, verá:</span><span class="sxs-lookup"><span data-stu-id="842c4-117">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Explorador de amenazas](../../media/path-to-explorer.png)|![Detecciones en tiempo real](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="842c4-120">Con estas herramientas, puede:</span><span class="sxs-lookup"><span data-stu-id="842c4-120">With these tools, you can:</span></span>

- <span data-ttu-id="842c4-121">Ver malware detectado por Microsoft 365 de seguridad</span><span class="sxs-lookup"><span data-stu-id="842c4-121">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="842c4-122">Ver la dirección URL de suplantación de identidad (phishing) y hacer clic en datos de veredicto</span><span class="sxs-lookup"><span data-stu-id="842c4-122">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="842c4-123">Iniciar un proceso automatizado de investigación y respuesta desde una vista en el Explorador</span><span class="sxs-lookup"><span data-stu-id="842c4-123">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="842c4-124">Investigar correo electrónico malintencionado y mucho más</span><span class="sxs-lookup"><span data-stu-id="842c4-124">Investigate malicious email, and more</span></span>

<span data-ttu-id="842c4-125">Para obtener más información, vea [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span><span class="sxs-lookup"><span data-stu-id="842c4-125">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span> 

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="842c4-126">Paso a paso del Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="842c4-126">Threat Explorer walk-through</span></span>

<span data-ttu-id="842c4-127">En Microsoft Defender para Office 365, hay dos planes de suscripción: plan 1 y plan 2.</span><span class="sxs-lookup"><span data-stu-id="842c4-127">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="842c4-128">Las herramientas de búsqueda de amenazas operadas manualmente existen en ambos planes, con nombres diferentes y con capacidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="842c4-128">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="842c4-129">Defender for Office 365 Plan 1 usa detecciones en tiempo *real,* que es un subconjunto de la herramienta de búsqueda Explorador de amenazas *(también* denominada *Explorador)* del Plan 2.</span><span class="sxs-lookup"><span data-stu-id="842c4-129">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="842c4-130">En esta serie de artículos, la mayoría de los ejemplos se crearon con el Explorador de amenazas completo.</span><span class="sxs-lookup"><span data-stu-id="842c4-130">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="842c4-131">Los administradores deben probar los pasos de las detecciones en tiempo real para ver dónde se aplican.</span><span class="sxs-lookup"><span data-stu-id="842c4-131">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="842c4-132">Para abrir la herramienta Explorador, vaya **a Microsoft 365 Portal de Defender** Correo electrónico & explorador de  >    >  **colaboración.**</span><span class="sxs-lookup"><span data-stu-id="842c4-132">To open the Explorer tool, go to **Microsoft 365 Defender portal** > **Email & collaboration** > **Explorer**.</span></span> <span data-ttu-id="842c4-133">De forma predeterminada, llegarás a la página  **Malware,** pero usa la lista desplegable Ver para familiarizarte con tus opciones.</span><span class="sxs-lookup"><span data-stu-id="842c4-133">By default, you’ll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="842c4-134">Si estás buscando phishing o buscando en una campaña de amenazas, elige esas vistas.</span><span class="sxs-lookup"><span data-stu-id="842c4-134">If you’re hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-135">![Vista desplegable en el Explorador de amenazas](../../media/view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-135">![View drop down in Threat Explorer](../../media/view-drop-down.png)</span></span>

<span data-ttu-id="842c4-136">Una vez que una persona de operaciones de seguridad (Operaciones de sec) selecciona los datos que desea ver, si el  ámbito es una vista estrecha como **envíos** de usuario o una vista más amplia, como Todo el correo **electrónico,** puede usar el botón Remitente para filtrar aún más.</span><span class="sxs-lookup"><span data-stu-id="842c4-136">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="842c4-137">Recuerde seleccionar Actualizar para completar las acciones de filtrado.</span><span class="sxs-lookup"><span data-stu-id="842c4-137">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-138">![Botón Remitente en el Explorador de amenazas](../../media/sender-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-138">![Sender button in Threat Explorer](../../media/sender-drop-down.png)</span></span>

<span data-ttu-id="842c4-139">El enfoque de refinamiento en el Explorador o la detección en tiempo real se puede pensar en capas.</span><span class="sxs-lookup"><span data-stu-id="842c4-139">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="842c4-140">El primero es **View**.</span><span class="sxs-lookup"><span data-stu-id="842c4-140">The first is **View**.</span></span> <span data-ttu-id="842c4-141">El segundo se puede pensar como un *foco filtrado.*</span><span class="sxs-lookup"><span data-stu-id="842c4-141">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="842c4-142">Por ejemplo, puede volver a seguir los pasos que realizó para encontrar una amenaza registrando sus decisiones como esta: Para encontrar el problema en el Explorador, elegí la vista malware con un foco de filtro **de destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="842c4-142">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="842c4-143">Esto facilita el retraso de los pasos.</span><span class="sxs-lookup"><span data-stu-id="842c4-143">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="842c4-144">Si Sec Ops usa **etiquetas** para marcar cuentas que consideren destinos de alto valor, pueden realizar selecciones como La vista de suplantación de identidad con un foco de filtro *etiquetas (incluir* un intervalo de fechas si se usa).</span><span class="sxs-lookup"><span data-stu-id="842c4-144">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="842c4-145">Esto les mostrará los intentos de suplantación de identidad dirigidos a sus objetivos de usuario de alto valor durante un intervalo de tiempo (como las fechas en las que ciertos ataques de suplantación de identidad están sucediendo mucho para su sector).</span><span class="sxs-lookup"><span data-stu-id="842c4-145">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span> 

<span data-ttu-id="842c4-146">Los refinamientos se pueden realizar en intervalos de fechas mediante los controles de intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="842c4-146">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="842c4-147">Aquí puede ver explorador en la vista **Malware,** con un foco de filtro **de tecnología** de detección.</span><span class="sxs-lookup"><span data-stu-id="842c4-147">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="842c4-148">Pero es el botón **Filtro** avanzado el que permite a los equipos de Sec Ops profundizar.</span><span class="sxs-lookup"><span data-stu-id="842c4-148">But it’s the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-149">![Filtro avanzado en el Explorador de amenazas](../../media/advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-149">![Advanced filter in Threat Explorer](../../media/advanced-filter.png)</span></span>

<span data-ttu-id="842c4-150">Al hacer **clic en** el filtro Avanzado, aparece un panel que permitirá a los cazacarros de Sec Ops crear consultas por sí mismos, lo que les permite incluir o excluir la información que necesitan ver.</span><span class="sxs-lookup"><span data-stu-id="842c4-150">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="842c4-151">Tanto el gráfico como la tabla de la página Explorador reflejarán sus resultados.</span><span class="sxs-lookup"><span data-stu-id="842c4-151">Both the chart and table on the Explorer page will reflect their results.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-152">![Resultados de una consulta](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-152">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="842c4-153">Use el **botón Opciones de** columna para obtener el tipo de información de la tabla que sería más útil:</span><span class="sxs-lookup"><span data-stu-id="842c4-153">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-154">![Botón De opciones de columna resaltado](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-154">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-155">![Opciones disponibles en columnas](../../media/column-options.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-155">![Available options in Columns](../../media/column-options.png)</span></span>

<span data-ttu-id="842c4-156">En el mismo mien, asegúrate de probar las opciones de visualización.</span><span class="sxs-lookup"><span data-stu-id="842c4-156">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="842c4-157">Diferentes audiencias reaccionarán bien a diferentes presentaciones de los mismos datos.</span><span class="sxs-lookup"><span data-stu-id="842c4-157">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="842c4-158">Para algunos visores, el mapa **Orígenes** de correo electrónico puede mostrar que una amenaza es generalizada o discreta más rápidamente que la opción Mostrar **campaña** justo al lado.</span><span class="sxs-lookup"><span data-stu-id="842c4-158">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="842c4-159">Sec Ops puede hacer uso de estas pantallas para hacer puntos que subrayan la necesidad de seguridad y protección, o para la comparación posterior, para demostrar la eficacia de sus acciones.</span><span class="sxs-lookup"><span data-stu-id="842c4-159">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-160">![Mapa orígenes de correo electrónico](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-160">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-161">![Opciones de presentación de campaña](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-161">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="842c4-162">Investigación de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="842c4-162">Email investigation</span></span>

<span data-ttu-id="842c4-163">Cuando vea un correo electrónico sospechoso, haga clic en el nombre para expandir el menú desplegable a la derecha.</span><span class="sxs-lookup"><span data-stu-id="842c4-163">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="842c4-164">Aquí, está disponible el banner que permite a las Operaciones de Sec ver la página [de entidad de correo](mdo-email-entity-page.md) electrónico.</span><span class="sxs-lookup"><span data-stu-id="842c4-164">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="842c4-165">La página de entidad de correo electrónico reúne contenidos que se pueden encontrar en **Detalles**, **Datos adjuntos** **,** Dispositivos, pero incluye datos más organizados.</span><span class="sxs-lookup"><span data-stu-id="842c4-165">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="842c4-166">Esto incluye aspectos como los resultados de DMARC, la presentación de texto sin formato del encabezado de correo electrónico con una opción de copia, la información de veredicto sobre los datos adjuntos que se detonaron de forma segura y los archivos que se eliminaron (pueden incluir direcciones IP que se han contactado y capturas de pantalla de páginas o archivos).</span><span class="sxs-lookup"><span data-stu-id="842c4-166">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="842c4-167">Las direcciones URL y sus veredictos también se enumeran con detalles similares notificados.</span><span class="sxs-lookup"><span data-stu-id="842c4-167">URLs and their verdicts are also listed with similar details reported.</span></span> 

<span data-ttu-id="842c4-168">Cuando llegue a esta fase, la página de entidad de correo electrónico será fundamental para el paso final:*corrección*.</span><span class="sxs-lookup"><span data-stu-id="842c4-168">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-169">![La página de entidad de correo electrónico](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-169">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="842c4-170">Para obtener más información sobre la página  de entidad de correo electrónico enriquecido (que se ve a continuación en la pestaña Análisis), incluidos los resultados de los datos adjuntos detonados, los resultados de las direcciones URL incluidas y la vista previa de correo electrónico seguro, haga clic [aquí](mdo-email-entity-page.md).</span><span class="sxs-lookup"><span data-stu-id="842c4-170">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-171">![Ficha Análisis de la página de entidad de correo electrónico](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-171">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="842c4-172">Corrección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="842c4-172">Email remediation</span></span>

<span data-ttu-id="842c4-173">Una vez que una persona de Operaciones de Sec determina que un correo electrónico es una amenaza, el siguiente paso de detección en tiempo real o explorador se ocupa de la amenaza y la corrige.</span><span class="sxs-lookup"><span data-stu-id="842c4-173">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="842c4-174">Esto se puede hacer volviendo al Explorador de amenazas, seleccionando la casilla del correo electrónico del problema y usando el **botón** Acciones.</span><span class="sxs-lookup"><span data-stu-id="842c4-174">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-175">![Botón Acciones en el Explorador de amenazas](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-175">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="842c4-176">Aquí, el analista puede realizar acciones como notificar el correo como correo no deseado, suplantación de identidad o malware, ponerse en contacto con destinatarios o realizar investigaciones adicionales que pueden incluir activar libros de juegos de investigación y respuesta automatizadas (o AIR) (si tienes plan 2).</span><span class="sxs-lookup"><span data-stu-id="842c4-176">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="842c4-177">O bien, el correo también puede ser notificado como limpio.</span><span class="sxs-lookup"><span data-stu-id="842c4-177">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-178">![La lista desplegable Acciones](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-178">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="842c4-179">Mejoras en la experiencia de búsqueda de amenazas</span><span class="sxs-lookup"><span data-stu-id="842c4-179">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="842c4-180">Id. de alerta</span><span class="sxs-lookup"><span data-stu-id="842c4-180">Alert ID</span></span>

<span data-ttu-id="842c4-181">Al navegar desde una alerta al Explorador de amenazas, **la vista** se filtrará mediante el identificador **de alerta**.</span><span class="sxs-lookup"><span data-stu-id="842c4-181">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="842c4-182">Esto también se aplica en la detección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="842c4-182">This also applies in Real-time detection.</span></span> <span data-ttu-id="842c4-183">Se muestran los mensajes relevantes para la alerta específica y un total de correo electrónico (un recuento).</span><span class="sxs-lookup"><span data-stu-id="842c4-183">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="842c4-184">Podrás ver si un mensaje formaba parte de una alerta, así como navegar de ese mensaje a la alerta relacionada.</span><span class="sxs-lookup"><span data-stu-id="842c4-184">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="842c4-185">Por último, el identificador de alerta se incluye en la dirección URL, por ejemplo: `https://https://security.microsoft.com/viewalerts`</span><span class="sxs-lookup"><span data-stu-id="842c4-185">Finally, alert ID is included in the URL, for example: `https://https://security.microsoft.com/viewalerts`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-186">![Filtrado del identificador de alerta](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-186">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-187">![Identificador de alerta en el menú desplegable de detalles](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="842c4-188">Ampliar el límite de búsqueda y retención de datos del Explorador (y detecciones en tiempo real) para inquilinos de prueba</span><span class="sxs-lookup"><span data-stu-id="842c4-188">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span> 

<span data-ttu-id="842c4-189">Como parte de este cambio, los analistas podrán buscar y filtrar datos de correo electrónico durante 30 días (aumentado a partir de siete días) en el Explorador de amenazas y detecciones en tiempo real para los inquilinos de prueba de Defender para Office P1 y P2.</span><span class="sxs-lookup"><span data-stu-id="842c4-189">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="842c4-190">Esto no afecta a los inquilinos de producción para clientes de P1 y P2 E5, donde el valor predeterminado de retención ya es de 30 días.</span><span class="sxs-lookup"><span data-stu-id="842c4-190">This doesn’t impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="842c4-191">Límite de exportación actualizado</span><span class="sxs-lookup"><span data-stu-id="842c4-191">Updated Export limit</span></span> 

<span data-ttu-id="842c4-192">El número de registros de correos electrónicos que se pueden exportar desde el Explorador de amenazas es ahora de 200 000 (en lugar de 9990).</span><span class="sxs-lookup"><span data-stu-id="842c4-192">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="842c4-193">El conjunto de columnas que se pueden exportar no cambia.</span><span class="sxs-lookup"><span data-stu-id="842c4-193">The set of columns that can be exported is unchanged.</span></span> 

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="842c4-194">Etiquetas en el Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="842c4-194">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="842c4-195">La característica de etiquetas de usuario está en Versión preliminar y puede que no esté disponible para todos.</span><span class="sxs-lookup"><span data-stu-id="842c4-195">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="842c4-196">Además, las vistas previas están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="842c4-196">Also, Previews are subject to change.</span></span> <span data-ttu-id="842c4-197">Para obtener información acerca de la programación de lanzamiento, consulte el mapa de ruta Microsoft 365 versión.</span><span class="sxs-lookup"><span data-stu-id="842c4-197">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="842c4-198">Las etiquetas de usuario identifican grupos específicos de usuarios en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="842c4-198">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="842c4-199">Para obtener más información acerca de las etiquetas, incluidas las licencias y la configuración, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="842c4-199">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="842c4-200">En el Explorador de amenazas, puede ver información sobre las etiquetas de usuario en las siguientes experiencias.</span><span class="sxs-lookup"><span data-stu-id="842c4-200">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="842c4-201">Vista cuadrícula de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="842c4-201">Email grid view</span></span>

<span data-ttu-id="842c4-202">Cuando los analistas miran la columna **Etiquetas** de la cuadrícula de correo electrónico, están viendo todas las etiquetas que se han aplicado a buzones de remitente o destinatario.</span><span class="sxs-lookup"><span data-stu-id="842c4-202">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="842c4-203">De forma predeterminada, las etiquetas del sistema como *las cuentas* de prioridad se muestran primero.</span><span class="sxs-lookup"><span data-stu-id="842c4-203">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-204">![Filtrar etiquetas en la vista cuadrícula de correo electrónico](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-204">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="842c4-205">Filtrado</span><span class="sxs-lookup"><span data-stu-id="842c4-205">Filtering</span></span>

<span data-ttu-id="842c4-206">Las etiquetas se pueden usar como filtros.</span><span class="sxs-lookup"><span data-stu-id="842c4-206">Tags can be used as filters.</span></span> <span data-ttu-id="842c4-207">Buscar solo entre cuentas de prioridad o usar escenarios de etiquetas de usuario específicos de esta manera.</span><span class="sxs-lookup"><span data-stu-id="842c4-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="842c4-208">También puede excluir los resultados que tienen determinadas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="842c4-208">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="842c4-209">Combine etiquetas con otros filtros y intervalos de fechas para restringir el ámbito de investigación.</span><span class="sxs-lookup"><span data-stu-id="842c4-209">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span> 

<span data-ttu-id="842c4-210">[![Etiquetas de filtro](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="842c4-210">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-211">![Etiquetas sin filtro](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-211">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="842c4-212">Flyout de detalles de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="842c4-212">Email detail flyout</span></span>

<span data-ttu-id="842c4-213">Para ver las etiquetas individuales del remitente y el destinatario, seleccione un correo electrónico para abrir el control desplegable de detalles del mensaje.</span><span class="sxs-lookup"><span data-stu-id="842c4-213">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="842c4-214">En la **pestaña Resumen,** las etiquetas de remitente y destinatario se muestran por separado.</span><span class="sxs-lookup"><span data-stu-id="842c4-214">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="842c4-215">La información sobre las etiquetas individuales del remitente y el destinatario se puede exportar como datos CSV.</span><span class="sxs-lookup"><span data-stu-id="842c4-215">The information about individual tags for sender and recipient can be exported as CSV data.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-216">![Etiquetas de detalles de correo electrónico](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-216">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="842c4-217">La información de etiquetas también se muestra en el control desplegable de clics de dirección URL.</span><span class="sxs-lookup"><span data-stu-id="842c4-217">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="842c4-218">Para verlo, vaya a la vista Phish o All Email > **url url** **clicks** tab. Seleccione un control desplegable de dirección URL individual para ver detalles adicionales acerca de los clics de esa dirección URL, incluidas las etiquetas asociadas con ese clic.</span><span class="sxs-lookup"><span data-stu-id="842c4-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="842c4-219">Vista de escala de tiempo actualizada</span><span class="sxs-lookup"><span data-stu-id="842c4-219">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-220">![Etiquetas URL](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-220">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="842c4-221">Obtenga más información con [este vídeo](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span><span class="sxs-lookup"><span data-stu-id="842c4-221">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="842c4-222">Funcionalidades extendidas</span><span class="sxs-lookup"><span data-stu-id="842c4-222">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="842c4-223">Principales usuarios dirigidos</span><span class="sxs-lookup"><span data-stu-id="842c4-223">Top targeted users</span></span>

<span data-ttu-id="842c4-224">Las principales familias de malware muestran los principales usuarios **dirigidos** en la sección Malware.</span><span class="sxs-lookup"><span data-stu-id="842c4-224">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="842c4-225">Los principales usuarios dirigidos también se extenderán a través de las vistas Phish y All Email.</span><span class="sxs-lookup"><span data-stu-id="842c4-225">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="842c4-226">Los analistas podrán ver los cinco primeros usuarios dirigidos, junto con el número de intentos de cada usuario en cada vista.</span><span class="sxs-lookup"><span data-stu-id="842c4-226">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span> 

<span data-ttu-id="842c4-227">Las personas de operaciones de seguridad pueden exportar la lista de usuarios dirigidos, hasta un límite de 3.000, junto con el número de intentos realizados, para el análisis sin conexión para cada vista de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="842c4-227">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="842c4-228">Además, al seleccionar el número de intentos (por ejemplo, 13 intentos en la imagen siguiente) se abrirá una vista filtrada en el Explorador de amenazas, para que pueda ver más detalles entre correos electrónicos y amenazas para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="842c4-228">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-229">![Principales usuarios dirigidos](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-229">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="842c4-230">Exchange de transporte</span><span class="sxs-lookup"><span data-stu-id="842c4-230">Exchange transport rules</span></span>

<span data-ttu-id="842c4-231">El equipo de operaciones de seguridad podrá ver todas las reglas de transporte Exchange (o reglas de flujo de correo) aplicadas a un mensaje, en la vista Cuadrícula de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="842c4-231">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="842c4-232">Seleccione **Opciones de columna** en la cuadrícula **y, a continuación, Exchange regla de transporte en** las opciones de columna.</span><span class="sxs-lookup"><span data-stu-id="842c4-232">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="842c4-233">La Exchange reglas de transporte también está visible en el **menú** desplegable Detalles del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="842c4-233">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span> 

<span data-ttu-id="842c4-234">Aparecen nombres y GUID de las reglas de transporte aplicadas al mensaje.</span><span class="sxs-lookup"><span data-stu-id="842c4-234">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="842c4-235">Los analistas podrán buscar mensajes mediante el nombre de la regla de transporte.</span><span class="sxs-lookup"><span data-stu-id="842c4-235">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="842c4-236">Se trata de una búsqueda CONTAINS, lo que significa que también puede realizar búsquedas parciales.</span><span class="sxs-lookup"><span data-stu-id="842c4-236">This is a CONTAINS search, which means you can do partial searches as well.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="842c4-237">Exchange búsqueda de reglas de transporte y disponibilidad de nombres dependen del rol específico que se le asigne.</span><span class="sxs-lookup"><span data-stu-id="842c4-237">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="842c4-238">Debe tener uno de los siguientes roles o permisos para ver los nombres de regla de transporte y la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="842c4-238">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="842c4-239">Sin embargo, incluso sin los roles o permisos siguientes, un analista puede ver la etiqueta de regla de transporte y la información GUID en los detalles del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="842c4-239">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="842c4-240">No se ven afectadas otras experiencias de visualización de registros en cuadrículas de correo electrónico, control de envío de correo electrónico, filtros y exportación.</span><span class="sxs-lookup"><span data-stu-id="842c4-240">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="842c4-241">Exchange Online Solo - Prevención de pérdida de datos: Todo</span><span class="sxs-lookup"><span data-stu-id="842c4-241">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="842c4-242">Exchange Online Only - O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="842c4-242">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="842c4-243">Microsoft Azure Active Directory o Exchange Online: Administrador de seguridad: Todo</span><span class="sxs-lookup"><span data-stu-id="842c4-243">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="842c4-244">Azure Active Directory o Exchange Online: Lector de seguridad: Todos</span><span class="sxs-lookup"><span data-stu-id="842c4-244">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="842c4-245">Exchange Online Solo- Reglas de transporte: Todas</span><span class="sxs-lookup"><span data-stu-id="842c4-245">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="842c4-246">Exchange Online Solo - configuración View-Only: todo</span><span class="sxs-lookup"><span data-stu-id="842c4-246">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="842c4-247">Dentro de la cuadrícula de correo electrónico, el control desplegable Detalles y csv exportado, los ETR se presentan con un Nombre/GUID como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="842c4-247">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="842c4-248">![Exchange Reglas de transporte](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-248">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="842c4-249">Conectores de entrada</span><span class="sxs-lookup"><span data-stu-id="842c4-249">Inbound connectors</span></span>

<span data-ttu-id="842c4-250">Los conectores son una colección de instrucciones que personalizan cómo fluye el correo electrónico hacia y desde Microsoft 365 o Office 365 organización.</span><span class="sxs-lookup"><span data-stu-id="842c4-250">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="842c4-251">Permiten aplicar cualquier restricción o control de seguridad.</span><span class="sxs-lookup"><span data-stu-id="842c4-251">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="842c4-252">En el Explorador de amenazas, puede ver los conectores relacionados con un correo electrónico y buscar correos electrónicos con nombres de conector.</span><span class="sxs-lookup"><span data-stu-id="842c4-252">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span> 

<span data-ttu-id="842c4-253">La búsqueda de conectores es una consulta CONTAINS, lo que significa que las búsquedas de palabras clave parciales pueden funcionar:</span><span class="sxs-lookup"><span data-stu-id="842c4-253">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="842c4-254">![Detalles del conector](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="842c4-254">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="842c4-255">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="842c4-255">Required licenses and permissions</span></span>

<span data-ttu-id="842c4-256">Debe tener [Microsoft Defender para Office 365](defender-for-office-365.md) usar detecciones en tiempo real o explorador.</span><span class="sxs-lookup"><span data-stu-id="842c4-256">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="842c4-257">El Explorador se incluye en Defender for Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="842c4-257">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="842c4-258">El informe de detecciones en tiempo real se incluye en Defender for Office 365 Plan 1.</span><span class="sxs-lookup"><span data-stu-id="842c4-258">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="842c4-259">Planee asignar licencias para todos los usuarios que deberán estar protegidos por Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="842c4-259">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="842c4-260">Las detecciones de explorador y en tiempo real muestran datos de detección para usuarios con licencia.</span><span class="sxs-lookup"><span data-stu-id="842c4-260">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="842c4-261">Para ver y usar detecciones en tiempo real o explorador, debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="842c4-261">To view and use Explorer or Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="842c4-262">Para el portal Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="842c4-262">For the Microsoft 365 Defender portal:</span></span>

  - <span data-ttu-id="842c4-263">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="842c4-263">Organization Management</span></span>
  - <span data-ttu-id="842c4-264">Administrador de seguridad (se puede asignar en el centro Azure Active Directory de administración ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="842c4-264">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="842c4-265">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="842c4-265">Security Reader</span></span>

- <span data-ttu-id="842c4-266">Para Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="842c4-266">For Exchange Online:</span></span>

  - <span data-ttu-id="842c4-267">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="842c4-267">Organization Management</span></span>
  - <span data-ttu-id="842c4-268">Administración de la organización de solo visualización</span><span class="sxs-lookup"><span data-stu-id="842c4-268">View-Only Organization Management</span></span>
  - <span data-ttu-id="842c4-269">Destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="842c4-269">View-Only Recipients</span></span>
  - <span data-ttu-id="842c4-270">Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="842c4-270">Compliance Management</span></span>

<span data-ttu-id="842c4-271">Para obtener más información sobre roles y permisos, consulte los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="842c4-271">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="842c4-272">Permisos en el portal de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="842c4-272">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="842c4-273">Permisos de características de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="842c4-273">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="842c4-274">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="842c4-274">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="842c4-275">Más información</span><span class="sxs-lookup"><span data-stu-id="842c4-275">More information</span></span>

- [<span data-ttu-id="842c4-276">Buscar e investigar el correo electrónico malintencionado que se ha entregado</span><span class="sxs-lookup"><span data-stu-id="842c4-276">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md) 
- [<span data-ttu-id="842c4-277">Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="842c4-277">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md) 
- [<span data-ttu-id="842c4-278">Obtener información general sobre las vistas en el Explorador de amenazas (y detecciones en tiempo real)</span><span class="sxs-lookup"><span data-stu-id="842c4-278">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md) 
- [<span data-ttu-id="842c4-279">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="842c4-279">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report) 
- [<span data-ttu-id="842c4-280">Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="842c4-280">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md) 
- [<span data-ttu-id="842c4-281">Investigar correos electrónicos con la página Entidad de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="842c4-281">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)