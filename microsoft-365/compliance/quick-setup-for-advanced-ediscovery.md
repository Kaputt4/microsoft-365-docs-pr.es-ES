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
# <a name="quick-setup-advanced-ediscovery-classic"></a>Configuración rápida Advanced eDiscovery (clásico)

> [!IMPORTANT]
> A medida que continuamos invirtiendo en nuevas versiones de eDiscovery avanzado, anunciamos la retirada de eDiscovery avanzado, también conocido como *eDiscovery avanzado (clásico)* o *eDiscovery avanzado v1.0* Si todavía está usando eDiscovery avanzado v1.0, cambie a [eDiscovery avanzado v2.0](overview-ediscovery-20.md) (también conocido como la *Solución de eDiscovery avanzado en Microsoft 365*) tan pronto como sea posible. eDiscovery avanzado 2.0 tiene funcionalidades similares a las que se encuentra en eDiscovery avanzado v1.0, pero también ofrece muchas características nuevas, como la administración de custodios, la administración de comunicaciones y los conjuntos de revisión. Para obtener más información sobre la retirada de eDiscovery avanzado v1.0, consulte [Retirada de herramientas heredadas de eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 

En esta sección de configuración, se muestra cómo un administrador de eDiscovery del Centro de seguridad y cumplimiento de Microsoft 365 puede empezar a usar eDiscovery avanzado. Se da por hecho un conocimiento práctico de ambas herramientas.
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a>Obtener acceso a un caso en eDiscovery avanzado

You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md). 
  
Para ir a un caso en eDiscovery avanzado: 
  
1. [Ir al Centro de seguridad y cumplimiento](go-to-the-securitycompliance-center.md) . 
    
2. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
3. En la página **eDiscovery**, haga clic en **Abrir** junto al caso al que quiera ir en eDiscovery avanzado.
    
4. En la **Página principal** del caso, haga clic en **Cambiar a eDiscovery avanzado**.
    
    The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery. 
    
## <a name="workflow"></a>Flujo de trabajo

En el diagrama siguiente, se muestra el flujo de trabajo común para administrar y usar casos de eDiscovery en el Centro de seguridad y cumplimiento y en eDiscovery avanzado.
  
![En el diagrama, se muestra el flujo de trabajo de eDiscovery avanzado de cuatro fases en la instalación, incluidos la configuración de usuarios y de casos, la identificación de los datos de casos, la exportación y el procesamiento y, después, las fases de análisis y exportación al equipo local.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.
  
## <a name="analyze"></a>Analizar

[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results. 
  
## <a name="relevance-setup-and-relevance"></a>Configuración de relevancia y Relevancia

[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions. 
  
## <a name="export"></a>Exportar

[Exportar datos de casos](export-case-data-in-advanced-ediscovery.md) Permite exportar el contenido de eDiscovery avanzado y los resultados para su revisión externa. 
  
## <a name="report"></a>Informe

[Ejecutar informes](run-reports-in-advanced-ediscovery.md) Permite generar los informes seleccionados relacionados con el procesamiento de eDiscovery avanzado. 
  
## <a name="see-also"></a>Vea también

[Advanced eDiscovery (clásico)](office-365-advanced-ediscovery.md)
  
[Configurar usuarios y casos](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Preparar datos](prepare-data-for-advanced-ediscovery.md)

