---
title: Informar y solucionar problemas de Microsoft Defender para las reglas de ASR de punto de conexión
description: En este tema se describe cómo informar y solucionar problemas de Microsoft Defender para las reglas de ASR de punto de conexión
keywords: Reglas de reducción de superficie de ataque, asr, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 65e3e8d1baef7ca4440824c9a262f0b5f696b657
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194750"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="7fc97-104">Informar y solucionar problemas de Microsoft Defender para las reglas ASR de ATP</span><span class="sxs-lookup"><span data-stu-id="7fc97-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7fc97-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7fc97-105">**Applies to:**</span></span>

- [<span data-ttu-id="7fc97-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7fc97-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7fc97-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fc97-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="7fc97-108">El Microsoft 365 de seguridad es la nueva interfaz para supervisar y administrar la seguridad en todas las identidades, datos, dispositivos, aplicaciones e infraestructura de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7fc97-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="7fc97-109">Aquí podrá ver fácilmente el estado de seguridad de su organización; configurar dispositivos, usuarios y aplicaciones, así como recibir alertas sobre actividad sospechosa.</span><span class="sxs-lookup"><span data-stu-id="7fc97-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="7fc97-110">El Centro de seguridad de Microsoft 365 tiene como fin que los equipos de administración de seguridad y operaciones de seguridad administren y protejan mejor su organización.</span><span class="sxs-lookup"><span data-stu-id="7fc97-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="7fc97-111">Visite el centro Microsoft 365 seguridad en https://security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="7fc97-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="7fc97-112">En Microsoft 365 de seguridad, le ofrecemos una vista completa de la configuración y los eventos de reglas ASR actuales en su estado.</span><span class="sxs-lookup"><span data-stu-id="7fc97-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="7fc97-113">Tenga en cuenta que los dispositivos deben incorporarse al servicio Microsoft Defender para endpoints para que estos informes se rellenen.</span><span class="sxs-lookup"><span data-stu-id="7fc97-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="7fc97-114">Esta es una captura de pantalla del centro Microsoft 365 de seguridad (en **Reports**  >  **Devices**  >  **Attack surface reduction**).</span><span class="sxs-lookup"><span data-stu-id="7fc97-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="7fc97-115">En el nivel de dispositivo, selecciona **Configuración en** el panel Reglas de reducción de **superficie de** ataque.</span><span class="sxs-lookup"><span data-stu-id="7fc97-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="7fc97-116">Se muestra la siguiente pantalla, donde puedes seleccionar un dispositivo específico y comprobar su configuración de regla ASR individual.</span><span class="sxs-lookup"><span data-stu-id="7fc97-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="Pantalla de reglas ASR":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="7fc97-118">Microsoft Defender para endpoint: búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="7fc97-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="7fc97-119">Una de las características más eficaces de Microsoft Defender para Endpoint es la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="7fc97-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="7fc97-120">Si no estás familiarizado con la búsqueda avanzada, consulta búsqueda proactiva de [amenazas con búsqueda avanzada.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7fc97-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="7fc97-121">La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas (Kusto Query Language) que te permite explorar hasta 30 días de los datos capturados (sin procesar) que Defender for Endpoint recopila de tus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7fc97-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that Defender for Endpoint collects from your devices.</span></span> <span data-ttu-id="7fc97-122">A través de la búsqueda avanzada, puede inspeccionar proactivamente eventos para localizar indicadores y entidades interesantes.</span><span class="sxs-lookup"><span data-stu-id="7fc97-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="7fc97-123">El acceso flexible a los datos ayuda a la búsqueda sin restricciones de amenazas conocidas y potenciales.</span><span class="sxs-lookup"><span data-stu-id="7fc97-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="7fc97-124">Mediante la búsqueda avanzada, es posible extraer información de reglas ASR, crear informes y obtener información detallada sobre el contexto de un evento de bloqueo o auditoría de regla ASR determinado.</span><span class="sxs-lookup"><span data-stu-id="7fc97-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="7fc97-125">Los eventos de reglas ASR están disponibles para consultarse en la tabla DeviceEvents de la sección de búsqueda avanzada de la Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="7fc97-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="7fc97-126">Por ejemplo, una consulta sencilla, como la siguiente, puede informar de todos los eventos que tienen reglas ASR como origen de datos durante los últimos 30 días y los resumirá mediante el recuento ActionType, que en este caso será el nombre de código real de la regla ASR.</span><span class="sxs-lookup"><span data-stu-id="7fc97-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Consulta de búsqueda avanzada":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="pantalla de búsqueda avanzada":::

<span data-ttu-id="7fc97-129">Con la búsqueda avanzada puedes dar forma a las consultas a tu gusto, para que puedas ver lo que está sucediendo, independientemente de si quieres identificar algo en una máquina individual o quieres extraer información de todo el entorno.</span><span class="sxs-lookup"><span data-stu-id="7fc97-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="7fc97-130">Escala de tiempo de la máquina de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="7fc97-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="7fc97-131">Una alternativa a la búsqueda avanzada, pero con un ámbito más estrecho, es la escala de tiempo de la máquina de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="7fc97-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="7fc97-132">Puedes ver todos los eventos recopilados de un dispositivo, durante los últimos seis meses, en el Centro de seguridad de Microsoft Defender, yendo a la lista Máquinas, selecciona una máquina determinada y, a continuación, haz clic en la pestaña Escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="7fc97-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="7fc97-133">A continuación se muestra una captura de pantalla de la vista Escala de tiempo de estos eventos en un punto de conexión determinado.</span><span class="sxs-lookup"><span data-stu-id="7fc97-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="7fc97-134">Desde esta vista, puede filtrar la lista de eventos en función de cualquiera de los grupos de eventos a lo largo del panel derecho.</span><span class="sxs-lookup"><span data-stu-id="7fc97-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="7fc97-135">También puedes habilitar o deshabilitar eventos marcados y detallados al ver alertas y desplazarte por la escala de tiempo histórica.</span><span class="sxs-lookup"><span data-stu-id="7fc97-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Escala de tiempo del centro de seguridad de microsoft defender":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="7fc97-137">¿Cómo solucionar problemas de reglas ASR?</span><span class="sxs-lookup"><span data-stu-id="7fc97-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="7fc97-138">La primera y más inmediata forma es comprobar localmente, en un dispositivo Windows, qué reglas ASR están habilitadas (y su configuración) es mediante los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fc97-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="7fc97-139">Estas son algunas otras fuentes de información que Windows ofrece, para solucionar el impacto y el funcionamiento de las reglas ASR.</span><span class="sxs-lookup"><span data-stu-id="7fc97-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="7fc97-140">Consultar qué reglas están activas</span><span class="sxs-lookup"><span data-stu-id="7fc97-140">Querying which rules are active</span></span>
<span data-ttu-id="7fc97-141">Una de las formas más sencillas de determinar si las reglas ASR ya están habilitadas y, a través de un cmdlet de PowerShell, Get-MpPreference.</span><span class="sxs-lookup"><span data-stu-id="7fc97-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="7fc97-142">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7fc97-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="obtener script mppreference":::

<span data-ttu-id="7fc97-144">Hay varias reglas ASR activas, con distintas acciones configuradas.</span><span class="sxs-lookup"><span data-stu-id="7fc97-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="7fc97-145">Para expandir la información anterior sobre las reglas ASR, puede usar las propiedades **AttackSurfaceReductionRules_Ids** y/o **AttackSurfaceReductionRules_Actions**.</span><span class="sxs-lookup"><span data-stu-id="7fc97-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="7fc97-146">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7fc97-146">Example:</span></span>

<span data-ttu-id="7fc97-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="7fc97-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="ejemplo de obtener mpreference":::

<span data-ttu-id="7fc97-149">Lo anterior muestra todos los IDs de las reglas ASR que tienen una configuración diferente de 0 (No configurado).</span><span class="sxs-lookup"><span data-stu-id="7fc97-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="7fc97-150">A continuación, el siguiente paso es enumerar las acciones reales (Bloquear o Auditar) con las que se configura cada regla.</span><span class="sxs-lookup"><span data-stu-id="7fc97-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="7fc97-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="7fc97-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="7fc97-153">Consulta de eventos de bloqueo y auditoría</span><span class="sxs-lookup"><span data-stu-id="7fc97-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="7fc97-154">Los eventos de regla ASR se pueden ver en el Windows Defender registro.</span><span class="sxs-lookup"><span data-stu-id="7fc97-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="7fc97-155">Para acceder a él, abra Windows visor de eventos y vaya a Registros de aplicaciones y servicios  >  **de Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="7fc97-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="scr del visor de eventos":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="7fc97-157">Registros de Protección contra malware de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7fc97-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="7fc97-158">También puede ver eventos de regla Antivirus de Microsoft Defender la herramienta de línea de comandos dedicada, denominada , que se puede usar para administrar y configurar y automatizar tareas si `*mpcmdrun.exe*` es necesario.</span><span class="sxs-lookup"><span data-stu-id="7fc97-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="7fc97-159">Puede encontrar esta utilidad en *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span><span class="sxs-lookup"><span data-stu-id="7fc97-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="7fc97-160">Debe ejecutarlo desde un símbolo del sistema con privilegios elevados (es decir, ejecutar como administrador).</span><span class="sxs-lookup"><span data-stu-id="7fc97-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="7fc97-161">Para generar la información de compatibilidad, *escribaMpCmdRun.exe -getfiles*.</span><span class="sxs-lookup"><span data-stu-id="7fc97-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="7fc97-162">Después de un tiempo, varios registros se empaquetarán en un archivo (MpSupportFiles.cab) y estarán disponibles en *C:\ProgramData\Microsoft\Windows Defender\Support*.</span><span class="sxs-lookup"><span data-stu-id="7fc97-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="registros de protección contra malware":::

<span data-ttu-id="7fc97-164">Extrae ese archivo y tendrás muchos archivos disponibles para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="7fc97-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="7fc97-165">Los archivos más relevantes son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7fc97-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="7fc97-166">**MPOperationalEvents.txt:** este archivo contiene el mismo nivel de información que se encuentra en el Visor de eventos para Windows Defender registro operativo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7fc97-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="7fc97-167">**MPRegistry.txt:** en este archivo puede analizar todas las configuraciones de Windows Defender actuales, desde el momento en que se capturaron los registros de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="7fc97-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="7fc97-168">**MPLog.txt:** este registro contiene información más detallada acerca de todas las acciones y operaciones del Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="7fc97-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
