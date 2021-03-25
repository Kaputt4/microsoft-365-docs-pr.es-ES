---
title: 'Vulnerabilidades en mi organización: administración de amenazas y vulnerabilidades'
description: Enumera el identificador de vulnerabilidades y exposiciones (CVE) común de las debilidades encontradas en el software que se ejecuta en la organización. Detectada por la funcionalidad de administración de vulnerabilidades y amenazas de ATP de Microsoft Defender.
keywords: mdatp threat & vulnerability management, threat and vulnerability management, mdatp tvm weaknesses page, finding weaknesses through tvm, tvm vulnerability list, vulnerability details in tvm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b42e25c409ba19639e77e95fafc3d939514511ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076483"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="29220-105">Vulnerabilidades en mi organización: administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="29220-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="29220-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="29220-106">**Applies to:**</span></span>
- [<span data-ttu-id="29220-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="29220-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="29220-108">Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="29220-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="29220-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29220-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="29220-110">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="29220-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="29220-111">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="29220-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="29220-112">La administración de amenazas y vulnerabilidades usa las mismas señales en Defender para la protección de puntos de conexión de Endpoint para examinar y detectar vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="29220-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="29220-113">En la página Puntos débiles se enumeran las vulnerabilidades de software a las que se exponen los dispositivos al enumerar el identificador vulnerabilidades y **exposiciones** comunes (CVE).</span><span class="sxs-lookup"><span data-stu-id="29220-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="29220-114">También puede ver la gravedad, la clasificación del Sistema de puntuación de vulnerabilidad común (CVSS), la prevalencia en su organización, la vulneración correspondiente, las perspectivas de amenazas y mucho más.</span><span class="sxs-lookup"><span data-stu-id="29220-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="29220-115">Si no hay ningún identificador CVE oficial asignado a una vulnerabilidad, el nombre de vulnerabilidad se asigna mediante la administración de amenazas y vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="29220-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="29220-116">Para obtener correos electrónicos sobre nuevos eventos de vulnerabilidad, consulte [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="29220-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="29220-117">Vaya a la página Puntos débiles</span><span class="sxs-lookup"><span data-stu-id="29220-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="29220-118">Acceder a la página Puntos débiles de varias maneras diferentes:</span><span class="sxs-lookup"><span data-stu-id="29220-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="29220-119">Selección de **puntos débiles** en el menú de navegación de administración de amenazas y vulnerabilidades en el Centro de [seguridad de Microsoft Defender](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="29220-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="29220-120">Búsqueda global</span><span class="sxs-lookup"><span data-stu-id="29220-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="29220-121">Menú navegación</span><span class="sxs-lookup"><span data-stu-id="29220-121">Navigation menu</span></span>

<span data-ttu-id="29220-122">Ve al menú de navegación de administración de amenazas y vulnerabilidades y selecciona **Puntos débiles** para abrir la lista de CVEs.</span><span class="sxs-lookup"><span data-stu-id="29220-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="29220-123">Vulnerabilidades en la búsqueda global</span><span class="sxs-lookup"><span data-stu-id="29220-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="29220-124">Vaya al menú desplegable búsqueda global.</span><span class="sxs-lookup"><span data-stu-id="29220-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="29220-125">Seleccione **Vulnerabilidad y** clave en el identificador de vulnerabilidades y exposiciones comunes (CVE) que está buscando y, a continuación, seleccione el icono de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="29220-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="29220-126">La **página Puntos débiles** se abre con la información CVE que está buscando.</span><span class="sxs-lookup"><span data-stu-id="29220-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="29220-127">![Cuadro de búsqueda global con la opción desplegable "vulnerabilidad" seleccionada y un cve de ejemplo.](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="29220-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="29220-128">Selecciona CVE para abrir un panel desplegable con más información, incluida la descripción de vulnerabilidad, los detalles, las perspectivas de amenazas y los dispositivos expuestos.</span><span class="sxs-lookup"><span data-stu-id="29220-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="29220-129">Para ver el resto de las vulnerabilidades en la página Puntos **débiles,** escriba CVE y, a continuación, seleccione buscar.</span><span class="sxs-lookup"><span data-stu-id="29220-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="29220-130">Información general sobre debilidades</span><span class="sxs-lookup"><span data-stu-id="29220-130">Weaknesses overview</span></span>

<span data-ttu-id="29220-131">Corrija las vulnerabilidades de los dispositivos expuestos para reducir el riesgo para los activos y la organización.</span><span class="sxs-lookup"><span data-stu-id="29220-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="29220-132">Si la **columna Dispositivos expuestos** muestra 0, significa que no estás en riesgo.</span><span class="sxs-lookup"><span data-stu-id="29220-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![Página de aterrizaje Debilidades.](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="29220-134">Información sobre infracciones y amenazas</span><span class="sxs-lookup"><span data-stu-id="29220-134">Breach and threat insights</span></span>

<span data-ttu-id="29220-135">Vea cualquier información relacionada sobre infracciones y amenazas en la columna **Amenaza** cuando los iconos estén de color rojo.</span><span class="sxs-lookup"><span data-stu-id="29220-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="29220-136">Priorice siempre las recomendaciones asociadas con amenazas continuas.</span><span class="sxs-lookup"><span data-stu-id="29220-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="29220-137">Estas recomendaciones se marcan con el icono de información de amenazas ![ Dibujo simple de un error rojo.](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="29220-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="29220-138">e icono de información de vulneración ![ Dibujo simple de una flecha que alcanza un destino. ](images/tvm_alert_icon.png) .</span><span class="sxs-lookup"><span data-stu-id="29220-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="29220-139">El icono de información de infracciones se resalta si hay una vulnerabilidad encontrada en su organización.</span><span class="sxs-lookup"><span data-stu-id="29220-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="29220-140">![Ejemplo de un texto de información de infracciones que podría aparecer al pasar el mouse sobre el icono.</span><span class="sxs-lookup"><span data-stu-id="29220-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="29220-141">Este dice que "la posible alerta activa está asociada con esta recomendación.](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="29220-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="29220-142">El icono de información sobre amenazas se resalta si hay vulnerabilidades asociadas en la vulnerabilidad encontrada en la organización.</span><span class="sxs-lookup"><span data-stu-id="29220-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="29220-143">Si se mantiene el mouse sobre el icono, se muestra si la amenaza forma parte de un kit de vulnerabilidades o está conectada a grupos de actividades o campañas persistentes avanzadas específicos.</span><span class="sxs-lookup"><span data-stu-id="29220-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="29220-144">Cuando está disponible, hay un vínculo a un informe de Análisis de amenazas con noticias de explotación de día cero, divulgaciones o avisos de seguridad relacionados.</span><span class="sxs-lookup"><span data-stu-id="29220-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![Threat insights text that could show up when hovering over icon.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="29220-147">Obtener información sobre vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="29220-147">Gain vulnerability insights</span></span>

<span data-ttu-id="29220-148">Si seleccionas una CVE, se abrirá un panel desplegable con más información, como la descripción de vulnerabilidad, los detalles, las perspectivas de amenazas y los dispositivos expuestos.</span><span class="sxs-lookup"><span data-stu-id="29220-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="29220-149">La categoría "Característica del sistema operativo" se muestra en escenarios relevantes</span><span class="sxs-lookup"><span data-stu-id="29220-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="29220-150">Puedes ir a la recomendación de seguridad relacionada para cada CVE con dispositivo expuesto</span><span class="sxs-lookup"><span data-stu-id="29220-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![Ejemplo de flyout de debilidad.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="29220-152">Software que no es compatible</span><span class="sxs-lookup"><span data-stu-id="29220-152">Software that isn't supported</span></span>

<span data-ttu-id="29220-153">Las CVE para software que actualmente no son compatibles con amenazas & la administración de vulnerabilidades aún está presente en la página Debilidades.</span><span class="sxs-lookup"><span data-stu-id="29220-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="29220-154">Dado que el software no es compatible, solo estarán disponibles datos limitados.</span><span class="sxs-lookup"><span data-stu-id="29220-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="29220-155">La información de dispositivo expuesta no estará disponible para las CVE con software no compatible.</span><span class="sxs-lookup"><span data-stu-id="29220-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="29220-156">Filtre por software no compatible seleccionando la opción "No disponible" en la sección "Dispositivos expuestos".</span><span class="sxs-lookup"><span data-stu-id="29220-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![Filtro de dispositivos expuestos.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="29220-158">Ver entradas de vulnerabilidades y exposiciones comunes (CVE) en otros lugares</span><span class="sxs-lookup"><span data-stu-id="29220-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="29220-159">Software vulnerable superior en el panel</span><span class="sxs-lookup"><span data-stu-id="29220-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="29220-160">Ve al panel de administración de amenazas y [vulnerabilidades](tvm-dashboard-insights.md) y desplázate hacia abajo hasta el **widget de software vulnerable** superior.</span><span class="sxs-lookup"><span data-stu-id="29220-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="29220-161">Verás el número de vulnerabilidades encontradas en cada software, junto con la información sobre amenazas y una vista de alto nivel de la exposición del dispositivo con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="29220-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![Tarjeta de software vulnerable superior con cuatro columnas: software, debilidades, amenazas, dispositivos expuestos.](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="29220-163">Seleccione el software que desea investigar para ir a una página de investigación.</span><span class="sxs-lookup"><span data-stu-id="29220-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="29220-164">Seleccione la **pestaña Vulnerabilidades detectadas.**</span><span class="sxs-lookup"><span data-stu-id="29220-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="29220-165">Seleccione la vulnerabilidad que desea investigar para obtener más información sobre los detalles de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="29220-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Información general sobre Windows Server 2019.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="29220-167">Detectar vulnerabilidades en la página del dispositivo</span><span class="sxs-lookup"><span data-stu-id="29220-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="29220-168">Ver información de puntos débiles relacionados en la página del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29220-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="29220-169">Ve a la barra de menús de navegación del Centro de seguridad de Microsoft Defender y selecciona el icono del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29220-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="29220-170">Se **abre la página de lista** Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="29220-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="29220-171">En la **página de lista** Dispositivos, selecciona el nombre del dispositivo que quieras investigar.</span><span class="sxs-lookup"><span data-stu-id="29220-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![Lista de dispositivos con el dispositivo seleccionado para investigar.](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="29220-173">La página del dispositivo se abrirá con detalles y opciones de respuesta para el dispositivo que quieras investigar.</span><span class="sxs-lookup"><span data-stu-id="29220-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="29220-174">Seleccione **Vulnerabilidades detectadas**.</span><span class="sxs-lookup"><span data-stu-id="29220-174">Select **Discovered vulnerabilities**.</span></span>

    ![Página del dispositivo con detalles y opciones de respuesta.](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="29220-176">Seleccione la vulnerabilidad que desea investigar para abrir un panel desplegable con los detalles de CVE, como: descripción de vulnerabilidad, información sobre amenazas y lógica de detección.</span><span class="sxs-lookup"><span data-stu-id="29220-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="29220-177">Lógica de detección CVE</span><span class="sxs-lookup"><span data-stu-id="29220-177">CVE Detection logic</span></span>

<span data-ttu-id="29220-178">De forma similar a la evidencia de software, ahora mostramos la lógica de detección que aplicamos en un dispositivo para decir que es vulnerable.</span><span class="sxs-lookup"><span data-stu-id="29220-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="29220-179">La nueva sección se denomina "Lógica de detección" (en cualquier vulnerabilidad detectada en la página del dispositivo) y muestra la lógica y el origen de detección.</span><span class="sxs-lookup"><span data-stu-id="29220-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="29220-180">La categoría "Característica del sistema operativo" también se muestra en escenarios relevantes.</span><span class="sxs-lookup"><span data-stu-id="29220-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="29220-181">Una CVE afectaría a los dispositivos que ejecutan un sistema operativo vulnerable solo si se habilita un componente del sistema operativo específico.</span><span class="sxs-lookup"><span data-stu-id="29220-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="29220-182">Supongamos que Windows Server 2019 tiene vulnerabilidad en su componente DNS.</span><span class="sxs-lookup"><span data-stu-id="29220-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="29220-183">Con esta nueva funcionalidad, solo adjuntaremos esta CVE a los dispositivos Windows Server 2019 con la funcionalidad DNS habilitada en su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="29220-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![Ejemplo de lógica de detección que enumera el software detectado en el dispositivo y los KB.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="29220-185">Imprecisión de informe</span><span class="sxs-lookup"><span data-stu-id="29220-185">Report inaccuracy</span></span>

<span data-ttu-id="29220-186">Informe de un falso positivo cuando vea información imprecisa, inexacta o incompleta.</span><span class="sxs-lookup"><span data-stu-id="29220-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="29220-187">También puede informar sobre las recomendaciones de seguridad que ya se han corregido.</span><span class="sxs-lookup"><span data-stu-id="29220-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="29220-188">Abra CVE en la página Puntos débiles.</span><span class="sxs-lookup"><span data-stu-id="29220-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="29220-189">Seleccione **Informar de imprecisión y** se abrirá un panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="29220-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="29220-190">Seleccione la categoría de imprecisión en el menú desplegable y rellene la dirección de correo electrónico y los detalles de imprecisión.</span><span class="sxs-lookup"><span data-stu-id="29220-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="29220-191">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="29220-191">Select **Submit**.</span></span> <span data-ttu-id="29220-192">Sus comentarios se envían inmediatamente a los expertos en administración de amenazas y vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="29220-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="29220-193">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="29220-193">Related articles</span></span>

- [<span data-ttu-id="29220-194">Introducción a la administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="29220-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="29220-195">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="29220-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="29220-196">Inventario de software</span><span class="sxs-lookup"><span data-stu-id="29220-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="29220-197">Información del panel</span><span class="sxs-lookup"><span data-stu-id="29220-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="29220-198">Ver y organizar la lista de Microsoft Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="29220-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
