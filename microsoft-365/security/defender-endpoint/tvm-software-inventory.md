---
title: Inventario de software en la administración de amenazas y vulnerabilidades
description: La página de inventario de software para la administración de amenazas y vulnerabilidades de ATP de Microsoft Defender muestra cuántas debilidades y vulnerabilidades se han detectado en el software.
keywords: administración de amenazas y vulnerabilidades, atp de microsoft defender, inventario de software atp de microsoft defender, mdatp threat & vulnerability management, mdatp threat & vulnerability management software inventory, mdatp tvm software inventory, tvm software inventory
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
ms.openlocfilehash: a161cfcad301c6e5cac2c7398b5c13559b27698d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074008"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a><span data-ttu-id="67965-104">Inventario de software: administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="67965-104">Software inventory - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="67965-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="67965-105">**Applies to:**</span></span>
- [<span data-ttu-id="67965-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="67965-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="67965-107">Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="67965-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="67965-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67965-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="67965-109">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="67965-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="67965-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="67965-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="67965-111">El inventario de software en la administración de amenazas y vulnerabilidades es una lista de software conocido en su organización con enumeraciones de plataforma [común (CPE) oficiales.](https://nvd.nist.gov/products/cpe)</span><span class="sxs-lookup"><span data-stu-id="67965-111">The software inventory in threat and vulnerability management is a list of known software in your organization with official [Common Platform Enumerations (CPE)](https://nvd.nist.gov/products/cpe).</span></span> <span data-ttu-id="67965-112">Los productos de software sin un CPE oficial no tienen vulnerabilidades publicadas.</span><span class="sxs-lookup"><span data-stu-id="67965-112">Software products without an official CPE don’t have vulnerabilities published.</span></span> <span data-ttu-id="67965-113">También incluye detalles como el nombre del proveedor, el número de debilidades, las amenazas y el número de dispositivos expuestos.</span><span class="sxs-lookup"><span data-stu-id="67965-113">It also includes details such as the name of the vendor, number of weaknesses, threats, and number of exposed devices.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="67965-114">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="67965-114">How it works</span></span>

<span data-ttu-id="67965-115">En el campo de la detección, estamos aprovechando el mismo conjunto de señales responsables de la detección y evaluación de vulnerabilidades en Microsoft Defender para la detección de puntos de conexión y las capacidades [de respuesta.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="67965-115">In the field of discovery, we're leveraging the same set of signals that is responsible for detection and vulnerability assessment in [Microsoft Defender for Endpoint detection and response capabilities](overview-endpoint-detection-response.md).</span></span>

<span data-ttu-id="67965-116">Dado que es en tiempo real, en cuestión de minutos, verá información de vulnerabilidad a medida que se descubran.</span><span class="sxs-lookup"><span data-stu-id="67965-116">Since it's real time, in a matter of minutes, you'll see vulnerability information as they get discovered.</span></span> <span data-ttu-id="67965-117">El motor captura automáticamente información de varias fuentes de seguridad.</span><span class="sxs-lookup"><span data-stu-id="67965-117">The engine automatically grabs information from multiple security feeds.</span></span> <span data-ttu-id="67965-118">De hecho, verás si un software determinado está conectado a una campaña de amenazas en directo.</span><span class="sxs-lookup"><span data-stu-id="67965-118">In fact, you'll see if a particular software is connected to a live threat campaign.</span></span> <span data-ttu-id="67965-119">También proporciona un vínculo a un informe de Análisis de amenazas tan pronto como esté disponible.</span><span class="sxs-lookup"><span data-stu-id="67965-119">It also provides a link to a Threat Analytics report soon as it's available.</span></span>

## <a name="navigate-to-the-software-inventory-page"></a><span data-ttu-id="67965-120">Vaya a la página Inventario de software</span><span class="sxs-lookup"><span data-stu-id="67965-120">Navigate to the Software inventory page</span></span>

<span data-ttu-id="67965-121">Para obtener acceso a la página Inventario de software, seleccione **Inventario** de software en el menú de navegación de administración de amenazas y vulnerabilidades en el Centro de seguridad [de Microsoft Defender](portal-overview.md).</span><span class="sxs-lookup"><span data-stu-id="67965-121">Access the Software inventory page by selecting **Software inventory** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md).</span></span>

<span data-ttu-id="67965-122">Ver software en dispositivos específicos en las páginas de dispositivos individuales de la [lista de dispositivos](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="67965-122">View software on specific devices in the individual devices pages from the [devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="67965-123">Si busca software con la búsqueda global de Microsoft Defender para endpoint, asegúrese de colocar un carácter de subrayado en lugar de un espacio.</span><span class="sxs-lookup"><span data-stu-id="67965-123">If you search for software using the Microsoft Defender for Endpoint global search, make sure to put an underscore instead of a space.</span></span> <span data-ttu-id="67965-124">Por ejemplo, para obtener los mejores resultados de búsqueda, escribirías "windows_10" en lugar de "Windows 10".</span><span class="sxs-lookup"><span data-stu-id="67965-124">For example, for the best search results you'd write "windows_10" instead of "Windows 10".</span></span>

## <a name="software-inventory-overview"></a><span data-ttu-id="67965-125">Introducción al inventario de software</span><span class="sxs-lookup"><span data-stu-id="67965-125">Software inventory overview</span></span>

<span data-ttu-id="67965-126">La **página** Inventario de software se abre con una lista de software instalado en la red, incluido el nombre del proveedor, las debilidades encontradas, las amenazas asociadas a ellos, los dispositivos expuestos, el impacto en la puntuación de exposición y las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="67965-126">The **Software inventory** page opens with a list of software installed in your network, including the vendor name, weaknesses found, threats associated with them, exposed devices, impact to exposure score, and tags.</span></span>

<span data-ttu-id="67965-127">Puede filtrar la vista de lista en función de las debilidades encontradas en el software, las amenazas asociadas con ellos y las etiquetas como si el software ha llegado al final de la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="67965-127">You can filter the list view based on weaknesses found in the software, threats associated with them, and tags like whether the software has reached end-of-support.</span></span>

![Ejemplo de la página de aterrizaje para el inventario de software.](images/tvm-software-inventory.png)

<span data-ttu-id="67965-129">Seleccione el software que desea investigar.</span><span class="sxs-lookup"><span data-stu-id="67965-129">Select the software that you want to investigate.</span></span> <span data-ttu-id="67965-130">Se abrirá un panel desplegable con una vista más compacta de la información de la página.</span><span class="sxs-lookup"><span data-stu-id="67965-130">A flyout panel will open with a more compact view of the information on the page.</span></span> <span data-ttu-id="67965-131">Puede profundizar en la investigación y seleccionar Abrir **página de software,** o marcar cualquier incoherencia técnica seleccionando **Imprecisión de informe.**</span><span class="sxs-lookup"><span data-stu-id="67965-131">You can either dive deeper into the investigation and select **Open software page**, or flag any technical inconsistencies by selecting **Report inaccuracy**.</span></span>

### <a name="software-that-isnt-supported"></a><span data-ttu-id="67965-132">Software que no es compatible</span><span class="sxs-lookup"><span data-stu-id="67965-132">Software that isn't supported</span></span>

<span data-ttu-id="67965-133">El software que actualmente no es compatible con las amenazas & la administración de vulnerabilidades puede estar presente en la página Inventario de software.</span><span class="sxs-lookup"><span data-stu-id="67965-133">Software that isn't currently supported by threat & vulnerability management may be present in the Software inventory page.</span></span> <span data-ttu-id="67965-134">Como no se admite, solo estarán disponibles datos limitados.</span><span class="sxs-lookup"><span data-stu-id="67965-134">Because it is not supported, only limited data will be available.</span></span> <span data-ttu-id="67965-135">Filtra por software no compatible con la opción "No disponible" en la sección "Debilidad".</span><span class="sxs-lookup"><span data-stu-id="67965-135">Filter by unsupported software with the "Not available" option in the "Weakness" section.</span></span>

![Filtro de software no compatible.](images/tvm-unsupported-software-filter.png)

<span data-ttu-id="67965-137">Lo siguiente indica que no se admite un software:</span><span class="sxs-lookup"><span data-stu-id="67965-137">The following indicates that a software is not supported:</span></span>

- <span data-ttu-id="67965-138">El campo Debilidades muestra "No disponible"</span><span class="sxs-lookup"><span data-stu-id="67965-138">Weaknesses field shows "Not available"</span></span>
- <span data-ttu-id="67965-139">El campo Dispositivos expuestos muestra un guión</span><span class="sxs-lookup"><span data-stu-id="67965-139">Exposed devices field shows a dash</span></span>
- <span data-ttu-id="67965-140">Texto informativo agregado en el panel lateral y en la página de software</span><span class="sxs-lookup"><span data-stu-id="67965-140">Informational text added in side panel and in software page</span></span>
- <span data-ttu-id="67965-141">La página de software no tendrá las recomendaciones de seguridad, vulnerabilidades detectadas ni secciones de escala de tiempo de eventos</span><span class="sxs-lookup"><span data-stu-id="67965-141">The software page won't have the security recommendations, discovered vulnerabilities, or event timeline sections</span></span>

<span data-ttu-id="67965-142">Actualmente, los productos sin CPE no se muestran en la página de inventario de software, solo en el inventario de software de nivel de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67965-142">Currently, products without a CPE are not shown in the software inventory page, only in the device level software inventory.</span></span>

## <a name="software-inventory-on-devices"></a><span data-ttu-id="67965-143">Inventario de software en dispositivos</span><span class="sxs-lookup"><span data-stu-id="67965-143">Software inventory on devices</span></span>

<span data-ttu-id="67965-144">En el panel de navegación del Centro de seguridad de Microsoft Defender, vaya a la **[lista Dispositivos](machines-view-overview.md)**.</span><span class="sxs-lookup"><span data-stu-id="67965-144">From the Microsoft Defender Security Center navigation panel, go to the **[Devices list](machines-view-overview.md)**.</span></span> <span data-ttu-id="67965-145">Selecciona el nombre de un dispositivo para abrir la página  del dispositivo (como Computer1) y luego selecciona la pestaña Inventario de software para ver una lista de todo el software conocido presente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67965-145">Select the name of a device to open the device page (like Computer1), then select the **Software inventory** tab to see a list of all the known software present on the device.</span></span> <span data-ttu-id="67965-146">Seleccione una entrada de software específica para abrir el menú desplegable con más información.</span><span class="sxs-lookup"><span data-stu-id="67965-146">Select a specific software entry to open the flyout with more information.</span></span>

<span data-ttu-id="67965-147">El software puede estar visible en el nivel del dispositivo incluso si actualmente no es compatible con la administración de amenazas y vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="67965-147">Software may be visible at the device level even if it is currently not supported by threat and vulnerability management.</span></span> <span data-ttu-id="67965-148">Sin embargo, solo estarán disponibles datos limitados.</span><span class="sxs-lookup"><span data-stu-id="67965-148">However, only limited data will be available.</span></span> <span data-ttu-id="67965-149">Sabrás si el software no es compatible porque dirá "No disponible" en la columna "Debilidad".</span><span class="sxs-lookup"><span data-stu-id="67965-149">You'll know if software is unsupported because it will say "Not available" in the "Weakness" column.</span></span>

<span data-ttu-id="67965-150">El software sin CPE también puede aparecer en este inventario de software específico del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67965-150">Software with no CPE can also show up under this device specific software inventory.</span></span>

### <a name="software-evidence"></a><span data-ttu-id="67965-151">Pruebas de software</span><span class="sxs-lookup"><span data-stu-id="67965-151">Software evidence</span></span>

<span data-ttu-id="67965-152">Consulta la evidencia de dónde hemos detectado un software específico en un dispositivo desde el registro, el disco o ambos. Puedes encontrarlo en cualquier dispositivo en el inventario de software del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67965-152">See evidence of where we detected a specific software on a device from the registry, disk, or both.You can find it on any device in the device software inventory.</span></span>

<span data-ttu-id="67965-153">Seleccione un nombre de software para abrir el menú desplegable y busque la sección denominada "Evidencia de software".</span><span class="sxs-lookup"><span data-stu-id="67965-153">Select a software name to open the flyout, and look for the section called "Software Evidence."</span></span>

![Ejemplo de prueba de software de Windows 10 de la lista de dispositivos, que muestra la ruta del Registro de pruebas de software.](images/tvm-software-evidence.png)

## <a name="software-pages"></a><span data-ttu-id="67965-155">Páginas de software</span><span class="sxs-lookup"><span data-stu-id="67965-155">Software pages</span></span>

<span data-ttu-id="67965-156">Puede ver las páginas de software de varias maneras diferentes:</span><span class="sxs-lookup"><span data-stu-id="67965-156">You can view software pages a few different ways:</span></span>

- <span data-ttu-id="67965-157">Página de inventario de > Seleccione un nombre de software > Página Seleccionar **software abierto** en el control desplegable</span><span class="sxs-lookup"><span data-stu-id="67965-157">Software inventory page > Select a software name > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="67965-158">[Página recomendaciones de](tvm-security-recommendation.md) seguridad > Seleccionar una recomendación > Página Seleccionar **software abierto** en el control desplegable</span><span class="sxs-lookup"><span data-stu-id="67965-158">[Security recommendations page](tvm-security-recommendation.md) > Select a recommendation > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="67965-159">[Página](threat-and-vuln-mgt-event-timeline.md) escala de tiempo de eventos > Seleccione un evento > Seleccione el nombre del software con hipervínculo (como Visual Studio 2017) en la sección denominada "Componente relacionado" en el control desplegable</span><span class="sxs-lookup"><span data-stu-id="67965-159">[Event timeline page](threat-and-vuln-mgt-event-timeline.md) > Select an event > Select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout</span></span>

 <span data-ttu-id="67965-160">Aparecerá una página completa con todos los detalles de un software específico y la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="67965-160">A full page will appear with all the details of a specific software and the following information:</span></span>

- <span data-ttu-id="67965-161">Panel lateral con información del proveedor, prevalencia del software en la organización (incluido el número de dispositivos en los que está instalado y dispositivos expuestos que no están parcheados), si está disponible y la vulnerabilidad de vulnerabilidad y el impacto en la puntuación de exposición.</span><span class="sxs-lookup"><span data-stu-id="67965-161">Side panel with vendor information, prevalence of the software in the organization (including number of devices it's installed on, and exposed devices that aren't patched), whether and exploit is available, and impact to your exposure score.</span></span>
- <span data-ttu-id="67965-162">Visualizaciones de datos que muestran el número y la gravedad de vulnerabilidades y configuraciones erróneas.</span><span class="sxs-lookup"><span data-stu-id="67965-162">Data visualizations showing the number of, and severity of, vulnerabilities and misconfigurations.</span></span> <span data-ttu-id="67965-163">Además, gráficos con el número de dispositivos expuestos.</span><span class="sxs-lookup"><span data-stu-id="67965-163">Also, graphs with the number of exposed devices.</span></span>
- <span data-ttu-id="67965-164">Pestañas que muestran información como:</span><span class="sxs-lookup"><span data-stu-id="67965-164">Tabs showing information such as:</span></span>
    - <span data-ttu-id="67965-165">Recomendaciones de seguridad correspondientes para las debilidades y vulnerabilidades identificadas.</span><span class="sxs-lookup"><span data-stu-id="67965-165">Corresponding security recommendations for the weaknesses and vulnerabilities identified.</span></span>
    - <span data-ttu-id="67965-166">CVEs con nombre de vulnerabilidades detectadas.</span><span class="sxs-lookup"><span data-stu-id="67965-166">Named CVEs of discovered vulnerabilities.</span></span>
    - <span data-ttu-id="67965-167">Dispositivos que tienen instalado el software (junto con el nombre del dispositivo, el dominio, el sistema operativo y mucho más).</span><span class="sxs-lookup"><span data-stu-id="67965-167">Devices that have the software installed (along with device name, domain, OS, and more).</span></span>
    - <span data-ttu-id="67965-168">Lista de versiones de software (incluido el número de dispositivos en los que está instalada la versión, el número de vulnerabilidades detectadas y los nombres de los dispositivos instalados).</span><span class="sxs-lookup"><span data-stu-id="67965-168">Software version list (including number of devices the version is installed on, the number of discovered vulnerabilities, and the names of the installed devices).</span></span>

    ![Página de ejemplo de software Visual Studio 2017 con los detalles del software, las debilidades, los dispositivos expuestos y mucho más.](images/tvm-software-page-example.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="67965-170">Imprecisión de informe</span><span class="sxs-lookup"><span data-stu-id="67965-170">Report inaccuracy</span></span>

<span data-ttu-id="67965-171">Informe de un falso positivo cuando vea información imprecisa, inexacta o incompleta.</span><span class="sxs-lookup"><span data-stu-id="67965-171">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="67965-172">También puede informar sobre las recomendaciones de seguridad que ya se han corregido.</span><span class="sxs-lookup"><span data-stu-id="67965-172">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="67965-173">Abra el control desplegable de software en la página Inventario de software.</span><span class="sxs-lookup"><span data-stu-id="67965-173">Open the software flyout on the Software inventory page.</span></span>
2. <span data-ttu-id="67965-174">Seleccione **Error de informe**.</span><span class="sxs-lookup"><span data-stu-id="67965-174">Select **Report inaccuracy**.</span></span>
3. <span data-ttu-id="67965-175">En el panel desplegable, seleccione la categoría de imprecisión en el menú desplegable, rellene la dirección de correo electrónico y los detalles sobre la imprecisión.</span><span class="sxs-lookup"><span data-stu-id="67965-175">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details about the inaccuracy.</span></span>
4. <span data-ttu-id="67965-176">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="67965-176">Select **Submit**.</span></span> <span data-ttu-id="67965-177">Sus comentarios se envían inmediatamente a los expertos en administración de amenazas y vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="67965-177">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="67965-178">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="67965-178">Related articles</span></span>

- [<span data-ttu-id="67965-179">Introducción a la administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="67965-179">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="67965-180">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="67965-180">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="67965-181">Escala de tiempo del evento</span><span class="sxs-lookup"><span data-stu-id="67965-181">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
- [<span data-ttu-id="67965-182">Ver y organizar la lista de Microsoft Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="67965-182">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
