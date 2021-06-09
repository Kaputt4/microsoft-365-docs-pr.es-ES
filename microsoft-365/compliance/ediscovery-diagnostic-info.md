---
title: Recopilar información de diagnóstico de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo recopilar información de diagnóstico de exhibición de documentos electrónicos para un caso de soporte técnico de Microsoft.
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926560"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="d2fd4-103">Recopilar información de diagnóstico de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d2fd4-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="d2fd4-104">En ocasiones, los ingenieros de soporte técnico de Microsoft requieren información específica sobre el problema al abrir un caso de soporte técnico relacionado con la exhibición de documentos electrónicos principal o Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="d2fd4-105">En este artículo se proporcionan instrucciones sobre cómo recopilar información de diagnóstico para ayudar a los ingenieros a investigar y resolver problemas.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="d2fd4-106">Normalmente, no es necesario recopilar esta información hasta que un ingeniero de soporte técnico de Microsoft lo pida.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2fd4-107">El resultado de los cmdlets y la información de diagnóstico que se describe en este artículo puede incluir información confidencial sobre litigios o investigaciones internas en su organización.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="d2fd4-108">Antes de enviar la información de diagnóstico sin procesar al Soporte técnico de Microsoft, debe revisar la información y redactar cualquier información confidencial (como nombres u otra información sobre partes en litigio o investigación) reemplazando por `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="d2fd4-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="d2fd4-109">El uso de este método también indicará al ingeniero de soporte técnico de Microsoft que se redactó la información.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="d2fd4-110">Recopilar información de diagnóstico para eDiscovery principal</span><span class="sxs-lookup"><span data-stu-id="d2fd4-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="d2fd4-111">La recopilación de información de diagnóstico para eDiscovery principal está basada en cmdlets, por lo que tendrá que usar PowerShell del Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="d2fd4-112">Los siguientes ejemplos de PowerShell ejecutarán cmdlets y, a continuación, guardarán el resultado en un archivo de texto especificado.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="d2fd4-113">En la mayoría de los casos de compatibilidad, solo debe ejecutar uno de estos comandos.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="d2fd4-114">Para ejecutar los cmdlets siguientes, [conéctese a </span> PowerShell & Centro de](/powershell/exchange/connect-to-scc-powershell)seguridad y cumplimiento .</span><span class="sxs-lookup"><span data-stu-id="d2fd4-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="d2fd4-115">Después de conectarse, ejecute uno o varios de los siguientes comandos y asegúrese de reemplazar los marcadores de posición por los nombres de objeto reales.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="d2fd4-116">Después de revisar el archivo de texto generado y de redactar información confidencial, envíelo al ingeniero de soporte técnico de Microsoft que trabaja en su caso.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="d2fd4-117">También puede ejecutar los comandos de esta sección para recopilar información  de diagnóstico de las búsquedas y exportaciones que aparecen en la página Búsqueda de contenido en el centro de Microsoft 365 cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="d2fd4-118">Recopilar información sobre búsquedas</span><span class="sxs-lookup"><span data-stu-id="d2fd4-118">Collect information about searches</span></span>

<span data-ttu-id="d2fd4-119">El siguiente comando recopila información útil al investigar problemas con una búsqueda de contenido o una búsqueda asociada con un caso de exhibición de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="d2fd4-120">Recopilar información sobre acciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="d2fd4-120">Collect information about search actions</span></span>

<span data-ttu-id="d2fd4-121">El siguiente comando recopila información para investigar problemas con la vista previa, la exportación o la depuración de los resultados de una búsqueda de contenido o una búsqueda asociada con un caso de exhibición de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="d2fd4-122">Puede identificar el nombre de la acción de búsqueda haciendo clic en una exportación que aparece en la **pestaña** Exportaciones. Para identificar los nombres de las acciones de vista previa y purga, puede ejecutar el cmdlet **Get-ComplianceSearchAction** para mostrar una lista de todas las acciones.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="d2fd4-123">El formato del nombre de la acción de búsqueda se construye anexando , o al `_Preview` nombre de la búsqueda `_Export` `_Purge` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="d2fd4-124">Recopilar información sobre las retenciones de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="d2fd4-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="d2fd4-125">Cuando una retención de exhibición de documentos electrónicos asociada a un caso de exhibición de documentos electrónicos principal no funciona como se esperaba, ejecute el siguiente comando para recopilar información sobre la directiva de retención de casos y la regla de retención de casos asociada para la retención de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="d2fd4-126">El *nombre de la directiva de retención case* en el siguiente comando es el mismo que el nombre de la retención de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="d2fd4-127">Puede identificar este nombre en las **pestañas Retenciones** en el caso de exhibición de documentos electrónicos principales.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="d2fd4-128">Recopilar toda la información de casos</span><span class="sxs-lookup"><span data-stu-id="d2fd4-128">Collect all case information</span></span>

<span data-ttu-id="d2fd4-129">A veces, no es aparente qué información requiere el soporte técnico de Microsoft para investigar el problema.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="d2fd4-130">En esta situación, puede recopilar toda la información de diagnóstico para un caso de exhibición de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="d2fd4-131">El *nombre* del caso de exhibición de documentos electrónicos principal en el siguiente  comando es el mismo que el nombre de un caso que se muestra en la página Exhibición de documentos electrónicos principales en el centro de cumplimiento de Microsoft 365 de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="d2fd4-132">Recopilar información de diagnóstico para Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d2fd4-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="d2fd4-133">La **Configuración** en un caso Advanced eDiscovery permite copiar rápidamente la información de diagnóstico del caso.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="d2fd4-134">La información de diagnóstico se guarda en el Portapapeles para que puedas pegarla en un archivo de texto y enviarla al Soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="d2fd4-135">Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Mostrar > eDiscovery > Advanced**.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="d2fd4-136">Seleccione un caso y, a **continuación, haga** clic en Configuración pestaña.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="d2fd4-137">En **Información de casos**, haga clic **en Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="d2fd4-138">En la página desplegable, haz clic en **Copiar información de diagnóstico** para copiar la información en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="d2fd4-139">Abra un archivo de texto (en Bloc de notas) y pegue la información en el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="d2fd4-140">Guarde el archivo de texto y así lo asigne un nombre `AeD Diagnostic Info YYYY.MM.DD` parecido (por ejemplo, `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="d2fd4-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="d2fd4-141">Después de revisar el archivo y redactar información confidencial, envíelo al ingeniero de soporte técnico de Microsoft que trabaja en su caso.</span><span class="sxs-lookup"><span data-stu-id="d2fd4-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>