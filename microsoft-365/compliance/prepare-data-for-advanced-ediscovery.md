---
title: Preparar los datos para eDiscovery avanzado
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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 'Obtenga información sobre cómo usar el &amp; centro de seguridad y cumplimiento para preparar datos para el análisis con EDiscovery avanzado. '
ms.openlocfilehash: 31bf002c275b228de12b7ff9e39fabf7c72be74d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214288"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a>Preparar datos para la exhibición avanzada de documentos electrónicos (Classic)

En este tema se describe cómo cargar los resultados de una búsqueda de contenido en un caso en la exhibición avanzada de documentos electrónicos (Classic). 
  
> [!IMPORTANT]
> A medida que continuamos invirtiendo en nuevas versiones de eDiscovery avanzado, anunciamos la retirada de eDiscovery avanzado, también conocido como *eDiscovery avanzado (clásico)* o *eDiscovery avanzado v1.0* Si todavía está usando eDiscovery avanzado v1.0, cambie a [eDiscovery avanzado v2.0](overview-ediscovery-20.md) (también conocido como la *Solución de eDiscovery avanzado en Microsoft 365*) tan pronto como sea posible. eDiscovery avanzado 2.0 tiene funcionalidades similares a las que se encuentra en eDiscovery avanzado v1.0, pero también ofrece muchas características nuevas, como la administración de custodios, la administración de comunicaciones y los conjuntos de revisión. Para obtener más información sobre la retirada de eDiscovery avanzado v1.0, consulte [Retirada de herramientas heredadas de eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).  
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a>Paso 1: preparar datos para la exhibición avanzada de documentos electrónicos

Para analizar datos con la exhibición avanzada de documentos electrónicos, puede usar los resultados de una búsqueda de contenido que se ejecuta en el centro de seguridad y cumplimiento de Microsoft 365 &amp; (que aparece en la página **búsqueda de contenido** en el centro de seguridad y cumplimiento de Microsoft 365 &amp; ) o en una búsqueda asociada a un caso de exhibición de documentos electrónicos (en la página **eDiscovery** del centro de seguridad y &amp; cumplimiento). 
  
Para obtener los pasos detallados sobre cómo preparar los resultados de búsqueda para analizarlos en eDiscovery avanzado, consulte [preparar los resultados de la búsqueda para la exhibición avanzada](prepare-search-results-for-advanced-ediscovery.md)de documentos electrónicos.
  
> [!NOTE]
> Si tiene datos fuera de Microsoft 365 y desea importarlos a Microsoft 365 para poder prepararlo y analizarlo en la exhibición avanzada de documentos electrónicos, vea [información general sobre la importación de archivos PST a microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365) y el [archivado de datos de terceros](https://www.microsoft.com/?ref=go). 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>Paso 2: cargar datos de resultados de búsqueda en un caso en eDiscovery avanzado

Después de preparar los resultados de la búsqueda en el &amp; centro de seguridad y cumplimiento para el análisis, el siguiente paso consiste en cargar los resultados de la búsqueda en un caso en EDiscovery avanzado. Para obtener información más detallada, consulte [ejecutar el módulo de proceso](run-the-process-module-in-advanced-ediscovery.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión con su cuenta profesional o educativa.
    
3. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
4. Haga clic en **abrir** junto al caso en el que desea cargar datos en la exhibición avanzada de documentos electrónicos. 
    
5. En la **página principal** del caso, haga clic en **eDiscovery avanzado**. 
    
    ![Haga clic en cambiar a exhibición avanzada de documentos electrónicos para abrir el caso en eDiscovery avanzado.](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Se muestra la barra de progreso **conectarse a la exhibición avanzada de** documentos electrónicos. Cuando está conectado a la exhibición avanzada de documentos electrónicos, se muestra una lista de contenedores en la página de configuración del caso. 
    
    ![El caso se muestra en la exhibición avanzada de documentos electrónicos](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Estos contenedores representan los resultados de búsqueda que ha preparado para el análisis en la exhibición avanzada de documentos electrónicos en el paso 1. Tenga en cuenta que el nombre del contenedor tiene el mismo nombre que la búsqueda de contenido en el caso del centro de seguridad y &amp; cumplimiento. Los contenedores de la lista son los que ha preparado. Si un usuario diferente ha preparado los resultados de búsqueda para la exhibición avanzada de documentos electrónicos, los contenedores correspondientes no se incluirán en la lista. 
    
6. Para cargar los datos de resultados de búsqueda de un contenedor en el caso de eDiscovery avanzado, seleccione un contenedor y, a continuación, haga clic en **procesar**.
    
Una vez que se agregan los resultados de la búsqueda del centro de seguridad &amp; y cumplimiento al caso de la exhibición avanzada de documentos electrónicos, el siguiente paso consiste en usar las herramientas de la exhibición avanzada de documentos electrónicos para analizar y deselección de los datos relevantes para el caso. 
  
## <a name="see-also"></a>Vea también

[Advanced eDiscovery (clásico)](office-365-advanced-ediscovery.md)
  
[Configurar usuarios y casos](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Analizar datos de casos](analyze-case-data-with-advanced-ediscovery.md)
  
[Administración de la configuración de relevancia](manage-relevance-setup-in-advanced-ediscovery.md)
  
[Usar el módulo de relevancia](use-relevance-in-advanced-ediscovery.md)
  
[Exportar datos de casos](export-case-data-in-advanced-ediscovery.md)

