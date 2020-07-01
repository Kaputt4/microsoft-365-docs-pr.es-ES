---
title: Ver los resultados del módulo de proceso en la exhibición avanzada de documentos electrónicos
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: Obtenga información sobre cómo encontrar los resultados de un módulo de proceso ejecutado en la exhibición avanzada de documentos electrónicos, incluido el estado de la tarea y el resumen del proceso.
ms.openlocfilehash: 26ef87c762fc5c77f2374978bf4a425940dd5f37
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936173"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a>Ver los resultados del módulo de proceso en eDiscovery avanzado (clásico)

Una **Prepare** vez iniciado el \> **proceso** de preparación, puede ver el progreso y los resultados. 
  
> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="process-task-status"></a>Procesar el estado de la tarea

En **preparar** los resultados del \> **proceso** \> **Results**, la página muestra el estado actual (si el proceso se está ejecutando actualmente) o el estado de la tarea de estado de proceso último como se muestra en el siguiente ejemplo.
  
![Estado de la tarea del módulo de proceso](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
Las tareas mostradas pueden variar en función de las opciones de proceso seleccionadas. 
  
- **Inventory**: Advanced eDiscovery recorre en iteración todos los archivos seleccionados para procesar y realiza la recopilación de datos básica.
    
- **Calcular firmas**: calcula las firmas digitales MD5.
    
- **Extracción de compuestos**: extrae archivos internos o contenidos de forma recursiva de archivos compuestos (por ejemplo, PST, zip, MSG). Los archivos extraídos se almacenan en la carpeta Case del caso.
    
- **Sincronización de base de datos**: proceso de base de datos interno.
    
- **Copia de archivos**: copia los archivos de proceso. Esta tarea se muestra siempre, incluso cuando está seleccionada la opción copias avanzadas de archivos.
    
- **Extracción de texto**: cuando hay archivos nativos, eDiscovery avanzado extrae texto de estos archivos mediante dtSearch. El texto extraído de estos archivos se almacena como archivos de texto en la carpeta Case.
    
- **Actualización de metadatos**: procesa los metadatos cargados. 
    
- **Finalización**: procesamiento interno que finaliza los datos de los archivos de mayúsculas y minúsculas cargados (por ejemplo, identificar los archivos de errores y correctos). 
    
Estado de la tarea: se muestra después de la finalización de la tarea. Mientras se ejecutan las tareas, se muestra la duración de ejecución.
  
> [!NOTE]
> Las tareas completadas también pueden incluir los totales de los archivos que han completado el procesamiento o los archivos con errores. 
  
> [!TIP]
> "Cancelar" proporciona una opción de reversión para detener la ejecución del proceso y, a continuación, volver a la población de datos anterior o a los datos procesados guardados. Rollback borra todos los datos procesados. Si no desea que se pierdan los datos procesados (por ejemplo, si planea volver a cargar estos archivos), seleccione la opción "Cancelar" en esta ventana para elegir no revertirlos. 
  
## <a name="process-summary"></a>Resumen del proceso

En preparar \> \> \> Resumen de proceso de resultados del proceso, se muestra un desglose de los resultados de los archivos cargados de acuerdo con resultados de errores y procesamiento de archivos correctos.
  
Los paneles presentan una representación gráfica de las estadísticas del archivo importado, de la siguiente manera:
  
- **Resumen de proceso acumula**d: todos los archivos en el caso.
    
- **Resumen del proceso en último lugar**: archivos cargados desde la última sesión o acción. 
    
- **Últimas familias**: información de la familia en el caso (en caso de que haya).
    
- Si se agregaron archivos de **inicialización** , el número de archivos de inicialización se enumera por problema que se definió para los archivos. 
    
    Si se produce un error en la marcación de los archivos de **inicialización** , también se indica. 
    
- Si se agregaron archivos **etiquetados previamente** , el número de archivos predefinidos se enumera por problema que se definió para los archivos. 
    
    Si se produce un error en la marcación de archivos **predefinidos** , también se indica. 
    
![Resumen del módulo de proceso](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>Gráficos acumulativos y último resumen del proceso

La barra izquierda incluye el origen y los archivos extraídos: que son todos los archivos encontrados. 
  
La barra derecha, procesada, incluye:
  
- Archivos con errores de carga
    
- Archivos cargados correctamente, que pueden incluir: 
    
  - **Existente**: archivos que se cargaron antes y que ahora se cargan de nuevo (incluidos duplicados).
    
  - **Text**: archivos únicos con texto.
    
  - **No texto**: archivos de texto vacíos, archivos de texto nativos vacíos, archivos nativos que no son de texto. 
    
  - S **duplicados**: archivos duplicados con texto.
    
## <a name="last-process-errors"></a>Errores del último proceso

En \> \> la sección preparar los resultados \> del proceso último error, se muestran detalles de los errores de la última sesión o acción realizada.
  
![Errores del módulo de proceso](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>Vea también

[Advanced eDiscovery (clásico)](office-365-advanced-ediscovery.md)
  
[Ejecutar el módulo de proceso y cargar datos](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

