---
title: Configuración rápida de eDiscovery avanzado de Office 365
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
description: 'Obtenga información sobre cómo obtener acceso a eDiscovery avanzado de Office 365 desde el Centro de seguridad y cumplimiento de Office 365, así como revisar el flujo de trabajo típico para usar eDiscovery avanzado.  '
ms.openlocfilehash: 6df2d68639f2be9f6ba38ea7211654058bc73035
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597677"
---
# <a name="quick-setup-for-office-365-advanced-ediscovery"></a><span data-ttu-id="63533-103">Configuración rápida de eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="63533-103">Quick setup for Office 365 Advanced eDiscovery</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63533-104">Mientras seguimos invirtiendo en las versiones más recientes de Advanced eDiscovery, anunciamos la retirada de eDiscovery avanzado de Office 365 (también conocido como *eDiscovery avanzado v1.0*).</span><span class="sxs-lookup"><span data-stu-id="63533-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery (also known as *Advanced eDiscovery v1.0*).</span></span> <span data-ttu-id="63533-105">Si todavía está usando eDiscovery avanzado v1.0, cambie a [eDiscovery avanzado v2.0](overview-ediscovery-20.md) (también conocido como la *Solución de eDiscovery avanzado en Microsoft 365*) tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="63533-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="63533-106">eDiscovery avanzado 2.0 tiene funcionalidades similares a las que se encuentra en eDiscovery avanzado v1.0, pero también ofrece muchas características nuevas, como la administración de custodios, la administración de comunicaciones y los conjuntos de revisión.</span><span class="sxs-lookup"><span data-stu-id="63533-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="63533-107">Para obtener más información sobre la retirada de eDiscovery avanzado v1.0, consulte [Retirada de herramientas heredadas de eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="63533-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="63533-108">En esta sección de configuración, se muestra cómo un administrador de eDiscovery del Centro de seguridad y cumplimiento de Microsoft 365 puede empezar a usar eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="63533-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="63533-109">Se da por hecho un conocimiento práctico de ambas herramientas.</span><span class="sxs-lookup"><span data-stu-id="63533-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="63533-110">Obtener acceso a un caso en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="63533-110">Accessing a case in Advanced eDiscovery</span></span>


<span data-ttu-id="63533-p103">Puede obtener acceso a eDiscovery avanzado desde el Centro de seguridad y cumplimiento. Necesita ser miembro de un caso de eDiscovery en el Centro de seguridad y cumplimiento para poder obtener acceso a un caso en eDiscovery avanzado. Para obtener instrucciones sobre cómo asignar permisos de casos de eDiscovery y agregar usuarios a un caso de eDiscovery, vea [Administrar casos de eDiscovery en Office 365](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="63533-p103">You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="63533-114">Para ir a un caso en eDiscovery avanzado:</span><span class="sxs-lookup"><span data-stu-id="63533-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="63533-115">[Vaya al Centro de seguridad y cumplimiento de Office 365](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="63533-115">[Go to the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="63533-116">En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización.</span><span class="sxs-lookup"><span data-stu-id="63533-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="63533-117">En la página **eDiscovery**, haga clic en **Abrir** junto al caso al que quiera ir en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="63533-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span> 
    
4. <span data-ttu-id="63533-118">En la **página principal** del caso, haga clic en **eDiscovery avanzado**.</span><span class="sxs-lookup"><span data-stu-id="63533-118">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="63533-p104">Se mostrará la barra de progreso **Conectando a eDiscovery avanzado**. Cuando se establezca la conexión, el caso se abrirá en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="63533-p104">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="63533-121">Flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="63533-121">Workflow</span></span>

<span data-ttu-id="63533-122">En el diagrama siguiente, se muestra el flujo de trabajo común para administrar y usar casos de eDiscovery en el Centro de seguridad y cumplimiento y en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="63533-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span> 
  
![En el diagrama, se muestra el flujo de trabajo de eDiscovery avanzado de Office 365 de cuatro fases en la instalación, incluidos la configuración de usuarios y de casos, la identificación de los datos de casos, la exportación y el procesamiento y, después, las fases de análisis y exportación al equipo local.](media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="63533-p105">En esta sección de configuración, se describen los primeros cuatro pasos del flujo de trabajo. Para ver una descripción del resto de los pasos del flujo de trabajo, vea lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="63533-p105">This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="63533-126">Analizar</span><span class="sxs-lookup"><span data-stu-id="63533-126">Analyze</span></span>

<span data-ttu-id="63533-p106">[Analizar datos de casos](analyze-case-data-with-advanced-ediscovery.md) Identifica y organiza los archivos por varios parámetros, permite usar temas y muestra los resultados. El usuario puede personalizar la función de análisis para obtener mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="63533-p106">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="63533-129">Configuración de relevancia y Relevancia</span><span class="sxs-lookup"><span data-stu-id="63533-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="63533-p107">[Configuración de relevancia](manage-relevance-setup-in-advanced-ediscovery.md) y [Uso del módulo Relevancia](use-relevance-in-advanced-ediscovery.md) Permite la evaluación y el entrenamiento de Relevancia basándose en una muestra aleatoria de archivos y los usa para aplicar decisiones en el proceso de codificación predictiva. Calcula y muestra resultados provisionales al supervisar la validez estadística del proceso. Muestra los resultados para facilitar la toma de decisiones de revisión.</span><span class="sxs-lookup"><span data-stu-id="63533-p107">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="63533-133">Exportar</span><span class="sxs-lookup"><span data-stu-id="63533-133">Export</span></span>

<span data-ttu-id="63533-134">[Exportar datos de casos](export-case-data-in-advanced-ediscovery.md) Permite exportar el contenido de eDiscovery avanzado y los resultados para su revisión externa.</span><span class="sxs-lookup"><span data-stu-id="63533-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="63533-135">Informe</span><span class="sxs-lookup"><span data-stu-id="63533-135">Report</span></span>

<span data-ttu-id="63533-136">[Ejecutar informes](run-reports-in-advanced-ediscovery.md) Permite generar los informes seleccionados relacionados con el procesamiento de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="63533-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="63533-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="63533-137">See also</span></span>

[<span data-ttu-id="63533-138">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="63533-138">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="63533-139">Configurar usuarios y casos</span><span class="sxs-lookup"><span data-stu-id="63533-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="63533-140">Preparar datos</span><span class="sxs-lookup"><span data-stu-id="63533-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

