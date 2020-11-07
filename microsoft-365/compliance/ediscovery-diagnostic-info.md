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
description: Obtenga información sobre cómo recopilar información de diagnóstico de eDiscovery para un caso de soporte técnico de Microsoft.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944401"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="665d8-103">Recopilar información de diagnóstico de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="665d8-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="665d8-104">Ocasionalmente, los ingenieros de soporte técnico de Microsoft necesitan información específica sobre su problema al abrir un caso de soporte técnico relacionado con la exhibición de documentos electrónicos avanzada o la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="665d8-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="665d8-105">En este artículo se proporcionan instrucciones sobre cómo recopilar información de diagnóstico para ayudar a los ingenieros de soporte a investigar y resolver problemas.</span><span class="sxs-lookup"><span data-stu-id="665d8-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="665d8-106">Normalmente, no es necesario recopilar esta información hasta que lo solicite un ingeniero de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="665d8-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="665d8-107">El resultado de los cmdlets y la información de diagnóstico que se describe en este artículo puede incluir información confidencial sobre litigios o investigaciones internas de su organización.</span><span class="sxs-lookup"><span data-stu-id="665d8-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="665d8-108">Antes de enviar la información de diagnóstico sin formato a soporte técnico de Microsoft, debe revisar la información y censurar la información confidencial (por ejemplo, los nombres u otra información de las partes en los litigios o la investigación) reemplazándolo por `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="665d8-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="665d8-109">El uso de este método también indica al ingeniero de soporte técnico de Microsoft que la información se ha censurado.</span><span class="sxs-lookup"><span data-stu-id="665d8-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="665d8-110">Recopilar información de diagnóstico para la exhibición de documentos electrónicos principal</span><span class="sxs-lookup"><span data-stu-id="665d8-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="665d8-111">La recopilación de información de diagnóstico para la exhibición de documentos electrónicos principal está basada en cmdlet, por lo que tendrá que usar el PowerShell del centro de cumplimiento de & de seguridad.</span><span class="sxs-lookup"><span data-stu-id="665d8-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="665d8-112">Los siguientes ejemplos de PowerShell ejecutarán cmdlets y, a continuación, guardarán el resultado en un archivo de texto especificado.</span><span class="sxs-lookup"><span data-stu-id="665d8-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="665d8-113">En la mayoría de los casos de soporte técnico, solo debe ejecutar uno de estos comandos.</span><span class="sxs-lookup"><span data-stu-id="665d8-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="665d8-114">Para ejecutar los cmdlets siguientes, [Conéctese a PowerShell </span> del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="665d8-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="665d8-115">Una vez conectado, ejecute uno o varios de los siguientes comandos y asegúrese de reemplazar los marcadores de posición por los nombres reales del objeto.</span><span class="sxs-lookup"><span data-stu-id="665d8-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="665d8-116">Después de revisar el archivo de texto generado y censurar la información confidencial, envíelo al ingeniero de soporte técnico de Microsoft que trabaja en su caso.</span><span class="sxs-lookup"><span data-stu-id="665d8-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="665d8-117">También puede ejecutar los comandos de esta sección para recopilar información de diagnóstico para las búsquedas y exportaciones que aparecen en la página **búsqueda de contenido** en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="665d8-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="665d8-118">Recopilar información sobre las búsquedas</span><span class="sxs-lookup"><span data-stu-id="665d8-118">Collect information about searches</span></span>

<span data-ttu-id="665d8-119">El siguiente comando recopila información útil para investigar problemas con una búsqueda de contenido o una búsqueda asociada a un caso de eDiscovery principal.</span><span class="sxs-lookup"><span data-stu-id="665d8-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="665d8-120">Recopilar información sobre las acciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="665d8-120">Collect information about search actions</span></span>

<span data-ttu-id="665d8-121">El siguiente comando recopila información para investigar los problemas con la vista previa, la exportación o la depuración de los resultados de una búsqueda de contenido o una búsqueda asociada a un caso de exhibición de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="665d8-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="665d8-122">Puede identificar el nombre de la acción de búsqueda haciendo clic en una exportación que aparece en la ficha **exportaciones** . Para identificar los nombres de las acciones de vista previa y de depuración, puede ejecutar el cmdlet **Get-ComplianceSearchAction** para mostrar una lista de todas las acciones.</span><span class="sxs-lookup"><span data-stu-id="665d8-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="665d8-123">El formato del nombre de la acción de búsqueda se crea anexando `_Preview` , `_Export` o `_Purge` al nombre de la búsqueda correspondiente.</span><span class="sxs-lookup"><span data-stu-id="665d8-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="665d8-124">Recopilar información sobre las suspensiones de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="665d8-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="665d8-125">Cuando una retención de exhibición de documentos electrónicos asociada a un caso de exhibición de documentos electrónicos principal no funciona como se esperaba, ejecute el siguiente comando para recopilar información sobre la Directiva de suspensión de casos y la regla de suspensión de casos asociada para la retención de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="665d8-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="665d8-126">El *nombre* de la Directiva de suspensión de casos en el comando siguiente es el mismo que el nombre de la retención de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="665d8-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="665d8-127">Puede identificar este nombre en las pestañas **suspensiones** del caso principal de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="665d8-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="665d8-128">Recopilar toda la información del caso</span><span class="sxs-lookup"><span data-stu-id="665d8-128">Collect all case information</span></span>

<span data-ttu-id="665d8-129">A veces, no es evidente qué información necesita el soporte técnico de Microsoft para investigar su problema.</span><span class="sxs-lookup"><span data-stu-id="665d8-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="665d8-130">En esta situación, puede recopilar toda la información de diagnóstico para un caso principal de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="665d8-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="665d8-131">El *nombre del caso de eDiscovery principal* del siguiente comando es el mismo que el nombre de un caso que se muestra en la página **principal de eDiscovery** en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="665d8-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="665d8-132">Recopilar información de diagnóstico para eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="665d8-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="665d8-133">La pestaña **configuración** en un caso de exhibición avanzada de documentos electrónicos le permite copiar rápidamente la información de diagnóstico del caso.</span><span class="sxs-lookup"><span data-stu-id="665d8-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="665d8-134">La información de diagnóstico se guarda en el portapapeles para que se pueda pegar en un archivo de texto y enviar a soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="665d8-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="665d8-135">Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **Mostrar todos los > EDiscovery > avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="665d8-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="665d8-136">Seleccione un caso y, a continuación, haga clic en la pestaña **configuración** .</span><span class="sxs-lookup"><span data-stu-id="665d8-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="665d8-137">En **información de caso** , haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="665d8-137">Under **Case Information** , click **Select**.</span></span>

4. <span data-ttu-id="665d8-138">En la página de flotante, haga clic en **copiar información de diagnóstico** para copiar la información en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="665d8-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="665d8-139">Abra un archivo de texto (en el Bloc de notas) y, a continuación, pegue la información en el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="665d8-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="665d8-140">Guarde el archivo de texto y asígnele un nombre similar a `AeD Diagnostic Info YYYY.MM.DD` (por ejemplo, `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="665d8-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="665d8-141">Después de revisar el archivo y censurar la información confidencial, envíela al ingeniero de soporte técnico de Microsoft que esté trabajando en su caso.</span><span class="sxs-lookup"><span data-stu-id="665d8-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
