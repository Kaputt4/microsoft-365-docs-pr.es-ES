---
title: Ejecutar el módulo de proceso en Office 365 Advanced eDiscovery
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 'Obtenga información sobre las directrices para preparar archivos de casos de Office 365 datos para analizar con Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: eb608eeac33e0d5d06dce9d0c35cd86f4e0bc280
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557820"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a>Ejecutar el módulo de proceso en la exhibición avanzada de documentos electrónicos (Classic)

Los archivos de casos se cargan en la exhibición avanzada de documentos electrónicos durante el **proceso**de **preparación** \> . 
  
> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>Instrucciones: preparación de datos para la exhibición avanzada de documentos electrónicos

- **Quality**: identifique claramente la población de archivos de caso pertinente para el caso.
    
- **Carga**: Cargue los archivos en una ubicación que sea accesible para la exhibición avanzada de documentos electrónicos.
    
- **Identificador de archivo**: un identificador de archivo único en la exhibición avanzada de documentos electrónicos. Si no se importa ningún identificador de archivo, la exhibición de documentos electrónicos avanzada genera automáticamente el identificador. Si asigna el identificador en una carga de proceso posterior y asigna una ruta de acceso diferente a la carga de proceso inicial, la exhibición avanzada de documentos electrónicos reemplazará la ruta de acceso (en lugar de agregar una nueva entrada de archivo). El identificador puede usarse como referencia en el proceso de exportación. El valor del identificador no debe ser "-1".
    
- **MD5**: esta firma se usa para diferenciar archivos (dos archivos no se consideran duplicados exactos a menos que tengan el mismo MD5). De forma predeterminada, eDiscovery avanzado calcula el MD5 de los archivos. Cuando los archivos cargados son archivos de texto, se recomienda cargar y asignar el valor MD5 original en lugar de calcularlo en la exhibición avanzada de documentos electrónicos.
    
- **Tipo de archivo y nombre**:
    
  - EDiscovery avanzado puede procesar archivos de distintos formatos y extraer archivos nativos cargados en un formato estándar, como \*. TXT, HTML o. XML. El procesamiento de archivos de texto es más rápido que los archivos nativos. Los archivos de texto extraídos se almacenan en la carpeta Case.
    
  - No cargue archivos que no se puedan extraer, como archivos del sistema o imágenes gráficas. Estos archivos pueden retrasar el procesamiento.
    
  - Compruebe que los nombres de archivo tengan un nombre significativo y que las rutas sean correctas.
    
- **Ruta**de acceso al archivo: eDiscovery avanzado puede cargar archivos con longitudes de ruta de hasta 400 caracteres.
    
- **Extracción de texto**: al extraer texto de archivos nativos, además del texto normal, también se extraen los siguientes elementos: texto oculto (Excel y. doc), columnas ocultas (Excel), control de cambios (. doc), notas del orador (. ppt), objetos incrustados (por ejemplo, objetos de Excel en a. ppt). Se pueden ver en el editor de texto.
    
- **Omitir texto**: esta característica opcional se define después de ejecutar el proceso y antes de analizar. Ignore Text debe usarse con cuidado porque su uso puede reducir el rendimiento del análisis de archivos.
    
- **Texto multilingüe**: la exhibición avanzada de documentos electrónicos no controla actualmente los nombres multilingües de etiquetas, custodios y problemas.
    
- **Metadata**: Determine si hay metadatos que desea guardar en la base de datos de casos para futuras referencias, como intervalo de fechas, tamaño de archivo, tipo de archivo, custodio y asunto. Los metadatos se pueden cargar después de que los archivos se hayan cargado sin tener que volver a ejecutar el inventario o agregar la sobrecarga de reprocesamiento. 
    
  - Si los archivos se cargaron originalmente por ruta de acceso, asigne la columna Path cuando más adelante importando metadatos. Es posible hacer referencia al archivo por su identificador y asignar una ruta de acceso diferente. Este es un escenario útil cuando las rutas de archivo cambian.
    
  - Si los archivos se cargaron originalmente por identificador de archivo, asigne la columna ID al cargar metadatos. Si se hace referencia al archivo por ruta de acceso (en lugar de ID.), los archivos se volverán a cargar con un identificador diferente. EDiscovery avanzado crea copias de los archivos en lugar de cargar los metadatos de los archivos existentes.
    
- **Familias**: no se puede cargar una familia sin su principal (encabezado de familia). 
    
- **Tamaño de archivo**: no hay ninguna limitación en el tamaño de los archivos cargados en la exhibición avanzada de documentos electrónicos. Para el análisis (analizar, relevancia, etc.), el límite es de 5.242.880 caracteres de texto extraído. Los archivos de mayor tamaño se ignoran (por ejemplo, en relevancia, los archivos no participan en el proceso de entrenamiento de relevancia y no reciben una puntuación de relevancia tras el cálculo del lote).
    
- **Cantidad de archivo**: no hay ningún límite recomendado en el número de archivos que se pueden administrar en un único caso. El rendimiento depende de los recursos del sistema. 
    
## <a name="filtering-files"></a>Filtrado de archivos

Una etiqueta definida por el usuario puede asociarse a un conjunto de archivos para excluirlos del proceso u otras tareas. Cada sesión de proceso está asociada a un identificador de lote. Aunque el identificador del lote no es visible para el experto en relevancia, esto se puede hacer con una herramienta de búsqueda, agregando un filtro para el lote actual y etiquetando todos los archivos apropiados con una etiqueta definida por el usuario. 
  
## <a name="see-also"></a>Vea también

[Exhibición avanzada de documentos electrónicos (Classic)](office-365-advanced-ediscovery.md)
  
[Ejecutar el módulo de proceso y cargar datos](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[Visualización de los resultados del módulo de proceso](view-process-module-results-in-advanced-ediscovery.md)

