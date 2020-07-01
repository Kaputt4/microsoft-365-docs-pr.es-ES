---
title: Configuración rápida de eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: Obtenga información sobre cómo obtener acceso a eDiscovery avanzado desde el Centro de seguridad y cumplimiento, así como revisar el flujo de trabajo típico para usar eDiscovery avanzado.
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936263"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a><span data-ttu-id="53b21-103">Configuración rápida Advanced eDiscovery (clásico)</span><span class="sxs-lookup"><span data-stu-id="53b21-103">Quick setup Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53b21-104">A medida que continuamos invirtiendo en nuevas versiones de eDiscovery avanzado, anunciamos la retirada de eDiscovery avanzado, también conocido como *eDiscovery avanzado (clásico)* o *eDiscovery avanzado v1.0*</span><span class="sxs-lookup"><span data-stu-id="53b21-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="53b21-105">Si todavía está usando eDiscovery avanzado v1.0, cambie a [eDiscovery avanzado v2.0](overview-ediscovery-20.md) (también conocido como la *Solución de eDiscovery avanzado en Microsoft 365*) tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="53b21-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="53b21-106">eDiscovery avanzado 2.0 tiene funcionalidades similares a las que se encuentra en eDiscovery avanzado v1.0, pero también ofrece muchas características nuevas, como la administración de custodios, la administración de comunicaciones y los conjuntos de revisión.</span><span class="sxs-lookup"><span data-stu-id="53b21-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="53b21-107">Para obtener más información sobre la retirada de eDiscovery avanzado v1.0, consulte [Retirada de herramientas heredadas de eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="53b21-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="53b21-108">En esta sección de configuración, se muestra cómo un administrador de eDiscovery del Centro de seguridad y cumplimiento de Microsoft 365 puede empezar a usar eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="53b21-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="53b21-109">Se da por hecho un conocimiento práctico de ambas herramientas.</span><span class="sxs-lookup"><span data-stu-id="53b21-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="53b21-110">Obtener acceso a un caso en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="53b21-110">Accessing a case in Advanced eDiscovery</span></span>

<span data-ttu-id="53b21-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="53b21-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span></span> <span data-ttu-id="53b21-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="53b21-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span></span> <span data-ttu-id="53b21-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="53b21-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="53b21-114">Para ir a un caso en eDiscovery avanzado:</span><span class="sxs-lookup"><span data-stu-id="53b21-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="53b21-115">[Ir al Centro de seguridad y cumplimiento](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="53b21-115">[Go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="53b21-116">En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización.</span><span class="sxs-lookup"><span data-stu-id="53b21-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="53b21-117">En la página **eDiscovery**, haga clic en **Abrir** junto al caso al que quiera ir en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="53b21-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span>
    
4. <span data-ttu-id="53b21-118">En la **Página principal** del caso, haga clic en **Cambiar a eDiscovery avanzado**.</span><span class="sxs-lookup"><span data-stu-id="53b21-118">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="53b21-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span><span class="sxs-lookup"><span data-stu-id="53b21-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="53b21-120">When you're connected, the case is opened in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="53b21-120">When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="53b21-121">Flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="53b21-121">Workflow</span></span>

<span data-ttu-id="53b21-122">En el diagrama siguiente, se muestra el flujo de trabajo común para administrar y usar casos de eDiscovery en el Centro de seguridad y cumplimiento y en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="53b21-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span>
  
![En el diagrama, se muestra el flujo de trabajo de eDiscovery avanzado de cuatro fases en la instalación, incluidos la configuración de usuarios y de casos, la identificación de los datos de casos, la exportación y el procesamiento y, después, las fases de análisis y exportación al equipo local.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="53b21-124">This setup section describes the first four steps in the workflow.</span><span class="sxs-lookup"><span data-stu-id="53b21-124">This setup section describes the first four steps in the workflow.</span></span> <span data-ttu-id="53b21-125">For a description of the other steps in the workflow, see the following.</span><span class="sxs-lookup"><span data-stu-id="53b21-125">For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="53b21-126">Analizar</span><span class="sxs-lookup"><span data-stu-id="53b21-126">Analyze</span></span>

<span data-ttu-id="53b21-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span><span class="sxs-lookup"><span data-stu-id="53b21-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span></span> <span data-ttu-id="53b21-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span><span class="sxs-lookup"><span data-stu-id="53b21-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="53b21-129">Configuración de relevancia y Relevancia</span><span class="sxs-lookup"><span data-stu-id="53b21-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="53b21-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span><span class="sxs-lookup"><span data-stu-id="53b21-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span></span> <span data-ttu-id="53b21-131">Calculates and displays interim results while monitoring statistical validity of the process.</span><span class="sxs-lookup"><span data-stu-id="53b21-131">Calculates and displays interim results while monitoring statistical validity of the process.</span></span> <span data-ttu-id="53b21-132">Displays the results to facilitate in making review decisions.</span><span class="sxs-lookup"><span data-stu-id="53b21-132">Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="53b21-133">Exportar</span><span class="sxs-lookup"><span data-stu-id="53b21-133">Export</span></span>

<span data-ttu-id="53b21-134">[Exportar datos de casos](export-case-data-in-advanced-ediscovery.md) Permite exportar el contenido de eDiscovery avanzado y los resultados para su revisión externa.</span><span class="sxs-lookup"><span data-stu-id="53b21-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="53b21-135">Informe</span><span class="sxs-lookup"><span data-stu-id="53b21-135">Report</span></span>

<span data-ttu-id="53b21-136">[Ejecutar informes](run-reports-in-advanced-ediscovery.md) Permite generar los informes seleccionados relacionados con el procesamiento de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="53b21-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="53b21-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="53b21-137">See also</span></span>

[<span data-ttu-id="53b21-138">Advanced eDiscovery (clásico)</span><span class="sxs-lookup"><span data-stu-id="53b21-138">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="53b21-139">Configurar usuarios y casos</span><span class="sxs-lookup"><span data-stu-id="53b21-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="53b21-140">Preparar datos</span><span class="sxs-lookup"><span data-stu-id="53b21-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

