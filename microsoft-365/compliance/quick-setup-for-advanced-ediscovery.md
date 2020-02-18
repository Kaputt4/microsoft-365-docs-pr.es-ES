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
ms.openlocfilehash: e1af09caf57509bf472a766c9d9124ea969acc4e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42070307"
---
# <a name="quick-setup-for-office-365-advanced-ediscovery"></a>Configuración rápida de eDiscovery avanzado de Office 365

> [!IMPORTANT]
> Mientras seguimos invirtiendo en las versiones más recientes de Advanced eDiscovery, anunciamos la retirada de eDiscovery avanzado de Office 365 (también conocido como *eDiscovery avanzado v1.0*). Si todavía está usando eDiscovery avanzado v1.0, cambie a [eDiscovery avanzado v2.0](overview-ediscovery-20.md) (también conocido como la *Solución de eDiscovery avanzado en Microsoft 365*) tan pronto como sea posible. eDiscovery avanzado 2.0 tiene funcionalidades similares a las que se encuentra en eDiscovery avanzado v1.0, pero también ofrece muchas características nuevas, como la administración de custodios, la administración de comunicaciones y los conjuntos de revisión. Para obtener más información sobre la retirada de eDiscovery avanzado v1.0, consulte [Retirada de herramientas heredadas de eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 

En esta sección de configuración, se muestra cómo un administrador de eDiscovery del Centro de seguridad y cumplimiento de Microsoft 365 puede empezar a usar eDiscovery avanzado. Se da por hecho un conocimiento práctico de ambas herramientas.
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a>Obtener acceso a un caso en eDiscovery avanzado


Puede obtener acceso a eDiscovery avanzado desde el Centro de seguridad y cumplimiento. Necesita ser miembro de un caso de eDiscovery en el Centro de seguridad y cumplimiento para poder obtener acceso a un caso en eDiscovery avanzado. Para obtener instrucciones sobre cómo asignar permisos de casos de eDiscovery y agregar usuarios a un caso de eDiscovery, vea [Administrar casos de eDiscovery en Office 365](ediscovery-cases.md). 
  
Para ir a un caso en eDiscovery avanzado: 
  
1. [Vaya al Centro de seguridad y cumplimiento de Office 365](go-to-the-securitycompliance-center.md). 
    
2. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
3. En la página **eDiscovery**, haga clic en **Abrir** junto al caso al que quiera ir en eDiscovery avanzado. 
    
4. En la **página principal** del caso, haga clic en **eDiscovery avanzado**.
    
    Se mostrará la barra de progreso **Conectando a eDiscovery avanzado**. Cuando se establezca la conexión, el caso se abrirá en eDiscovery avanzado. 
    
## <a name="workflow"></a>Flujo de trabajo

En el diagrama siguiente, se muestra el flujo de trabajo común para administrar y usar casos de eDiscovery en el Centro de seguridad y cumplimiento y en eDiscovery avanzado. 
  
![En el diagrama, se muestra el flujo de trabajo de eDiscovery avanzado de Office 365 de cuatro fases en la instalación, incluidos la configuración de usuarios y de casos, la identificación de los datos de casos, la exportación y el procesamiento y, después, las fases de análisis y exportación al equipo local.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
En esta sección de configuración, se describen los primeros cuatro pasos del flujo de trabajo. Para ver una descripción del resto de los pasos del flujo de trabajo, vea lo siguiente.
  
## <a name="analyze"></a>Analizar

[Analizar datos de casos](analyze-case-data-with-advanced-ediscovery.md) Identifica y organiza los archivos por varios parámetros, permite usar temas y muestra los resultados. El usuario puede personalizar la función de análisis para obtener mejores resultados. 
  
## <a name="relevance-setup-and-relevance"></a>Configuración de relevancia y Relevancia

[Configuración de relevancia](manage-relevance-setup-in-advanced-ediscovery.md) y [Uso del módulo Relevancia](use-relevance-in-advanced-ediscovery.md) Permite la evaluación y el entrenamiento de Relevancia basándose en una muestra aleatoria de archivos y los usa para aplicar decisiones en el proceso de codificación predictiva. Calcula y muestra resultados provisionales al supervisar la validez estadística del proceso. Muestra los resultados para facilitar la toma de decisiones de revisión. 
  
## <a name="export"></a>Exportar

[Exportar datos de casos](export-case-data-in-advanced-ediscovery.md) Permite exportar el contenido de eDiscovery avanzado y los resultados para su revisión externa. 
  
## <a name="report"></a>Informe

[Ejecutar informes](run-reports-in-advanced-ediscovery.md) Permite generar los informes seleccionados relacionados con el procesamiento de eDiscovery avanzado. 
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Configurar usuarios y casos](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Preparar datos](prepare-data-for-advanced-ediscovery.md)

