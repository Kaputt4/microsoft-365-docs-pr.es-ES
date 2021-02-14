---
title: Usar el módulo Relevancia para analizar datos en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre cómo el módulo relevancia analiza los datos en evidencia con una descripción del flujo de trabajo de relevancia y los pasos de aprendizaje en eDiscovery avanzado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286066"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a>Usar el módulo Relevancia para analizar datos en eDiscovery avanzado

En eDiscovery avanzado, el módulo Relevancia incluye la formación de relevancia y la revisión de archivos relacionados con un caso. Para usar el flujo de trabajo relevancia, vaya a Administrar conjunto de revisión dentro de un conjunto de revisión y haga clic en Mostrar relevancia. Hay un par de pasos que debe completar para poder iniciar el flujo de trabajo:

- Proceso: cada conjunto de carga agregado al conjunto de revisión se mostrará como un "contenedor" aquí. Debe procesar estos documentos para poder agregarlos al módulo Relevancia; aquí también es donde puedes marcarlos como seed o etiquetados previamente para un problema específico.

- Agregar a relevancia: en cargas de relevancia, puede agregar documentos que se hayan procesado a Relevancia para que \> estén disponibles para la formación.

El flujo de trabajo relevancia se muestra y describe de la siguiente manera:
  
![Flujo de trabajo de relevancia](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Ciclos de evaluación y seguimiento:**
    
  - **Evaluación:** habilita la evaluación anticipada en función de una muestra aleatoria de archivos y usa esta evaluación para aplicar decisiones para determinar el rendimiento del proceso de codificación predictiva. 
    
  - **Seguimiento:** calcular y mostrar los resultados provisionales de la evaluación mientras se supervisa la validez estadística del proceso. 
    
- **Ciclos de aprendizaje y seguimiento**
    
  - **Etiqueta:** eDiscovery avanzado aprende los criterios de relevancia específicos de cada problema en función de la revisión iterativa del experto y el etiquetado de archivos individuales.
    
  - **Seguimiento:** calcular y mostrar los resultados provisionales de la formación de relevancia mientras se supervisa la validez estadística del proceso. 
    
- **Cálculo por** lotes: los criterios de relevancia acumulados y aprendidos se aplican a toda la colección de archivos y se genera una puntuación de relevancia para cada archivo.
    
- **Decidir:** los resultados del análisis aplicado a todo el caso se muestran después del cálculo por lotes y se muestran los datos usados para tomar decisiones de revisión de documentos.
    
- **Prueba:** los resultados se pueden probar para comprobar la validez y la eficacia del procesamiento de eDiscovery avanzado.

- **Búsqueda:** una vez completado el flujo de trabajo relevancia, puede usar el resultado como el percentil de lectura de un documento para su problema al ejecutar una consulta dentro del conjunto de revisión.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Directrices para el entrenamiento y revisión de relevancia

A continuación se ofrece información general sobre las directrices para la formación y revisión de relevancia:
  
- **Errores e incoherencias:** si se producen errores de etiquetado durante el aprendizaje, vuelva a los ejemplos de archivo anteriores para corregirlos. Si hay demasiados errores para corregir o hay una nueva perspectiva del caso o problema, el administrador debe volver a definir los criterios de relevancia y se reiniciará la formación de relevancia.
    
- **Etiquetado y aprendizaje:** 
    
  - Los archivos deben etiquetarse solo en función del contenido. No considere metadatos, como administrador, fecha o ruta de acceso de archivo. 
    
  - No tenga en cuenta las indicaciones del intervalo de fechas en el texto al etiquetar archivos.
    
  - No tenga en cuenta las imágenes gráficas incrustadas al etiquetar archivos.
     
  - Omitir el texto aplicado a Relevancia se quitará en el contenido del archivo mostrado en la vista de texto de Relevancia. Si los valores de Omitir texto se definieron después de que el entrenamiento de relevancia ya se haya iniciado, el nuevo texto omitido se aplicará a los archivos de ejemplo creados desde el punto en que se definió. La característica Omitir texto debe usarse con precaución, ya que su uso puede reducir el rendimiento del análisis de archivos
    
  - Use la **opción Omitir etiquetado** solo cuando sea necesario. EDiscovery avanzado no se entrena en función de los archivos omitido. En la evaluación, si es difícil saber si un archivo es relevante, es mejor etiquetar como relevante (R) o no relevante (NR) siempre que sea posible en lugar de seleccionar Omitir **.** Cuando eDiscovery avanzado evalúa la formación, se puede ver cómo se procesaron estos tipos de archivos.
    
  - Incluso los archivos con una cantidad muy pequeña de texto extraído deben etiquetarse en el entrenamiento como R/NR, en lugar de como "Omitir", siempre que sea posible. 
    
  - El etiquetado puede afectar al clasificador siempre que el archivo sea legible y se pueda etiquetar como R/NR.
    
  - El número de secuencia de archivos de  la lista de archivos de muestra que se muestra en la pestaña Etiqueta permite al usuario volver al orden original mostrado de los archivos. 
    
  - Puede volver a cualquier ejemplo y cambiar el etiquetado de los archivos del conjunto de evaluación y aprendizaje. Los cambios se aplicarán al crear el siguiente ejemplo.
    
  - Los archivos de Excel examinados en formato PDF deben tratarse igual que los archivos nativos de Excel al etiquetar archivos.
    
  - Cuando haya dudas sobre el etiquetado de relevancia de un archivo, consulte a un experto. El etiquetado incorrecto durante la formación de relevancia puede provocar pérdidas de tiempo más adelante en el proceso y también puede tener un impacto negativo en la calidad de los resultados generales.
    
  - Las palabras clave que se definieron en las listas de palabras clave se mostrarán en colores para ayudar al usuario a identificar los archivos relevantes durante el etiquetado.
    
- **Cálculo por** lotes: los archivos etiquetados como R/NR por el experto recibirán una puntuación de 0 o 100. Esto se aplica a las etiquetas realizadas antes del cálculo por lotes. Si el experto cambió el problema a Inactivo después del cálculo por lotes y siguió etiquetando este problema, las puntuaciones recién etiquetadas no serán 100/0, sino la puntuación original.
    
- **Modo** de muestreo y problemas: los problemas normalmente se apagan cuando se completa el trabajo en ellos (se estabiliza el entrenamiento de relevancia y se realiza el cálculo por lotes), cuando se cancelan los problemas o cuando otro usuario está trabajando en los problemas.
    
## <a name="steps-in-relevance-training"></a>Pasos de la formación de relevancia

En la **pestaña \> Seguimiento de** relevancia, eDiscovery avanzado proporciona recomendaciones sobre cómo continuar con el procesamiento, con los siguientes pasos. Las implicaciones se describen a continuación cuando se recomienda cada uno de los siguientes pasos en el proceso de entrenamiento de relevancia. 
  
- Etiquetado /Continuar etiquetado: revisión de archivos y etiquetas de relevancia realizadas por un experto para cada archivo y problema dentro de un ejemplo.
    
  - Implicación: debe etiquetarse un ejemplo existente.
    
- Evaluación o evaluación continua: permite la validación anticipada de la relevancia de los asuntos y una vista preliminar de la relevancia de la población de archivos importada para el caso actual.
    
  - Implicación: se requiere o se recomienda realizar más evaluaciones.
    
- Aprendizaje y formación continua: proceso durante el cual eDiscovery avanzado aprende del experto que etiqueta los ejemplos de archivos y adquiere la capacidad de identificar los criterios de relevancia pertinentes para cada problema dentro del contexto de cada caso.
    
  - Implicación: el problema necesita más formación; Se debe crear y etiquetar el siguiente ejemplo. 
    
- Cálculo por lotes: proceso de relevancia en el que eDiscovery avanzado toma los conocimientos adquiridos durante la fase de aprendizaje y lo aplica a toda la población de archivos. Todos los archivos del grupo de archivos pertinente se evalúan para la relevancia y se les asigna una puntuación de relevancia.
    
  - Implicación: el problema se ha estabilizado y se puede realizar el cálculo por lotes.
    
- Ponerse al día: la relevancia indica cuándo un experto revisa y etiqueta una muestra de archivos seleccionados de una carga de archivos adicional durante un escenario de carga gradual.
    
  - Implicación: se ha agregado una nueva carga y es necesario ponerse al día para seguir funcionando.
    
- Incoherencias de etiquetas: el proceso identifica, a través de un algoritmo de eDiscovery avanzado, incoherencias en el proceso de etiquetado de archivos que pueden afectar negativamente al análisis.
    
  - Implicación: en el siguiente ejemplo se incluirán los archivos que se etiquetaron en ejemplos anteriores y su etiquetado debe reetiquetado.
    
- Clasificador de actualización: permite al usuario aplicar cambios de etiquetado o edización.
    
  - Implicación: los cambios de etiquetado y edización se pueden aplicar sin necesidad de ejecutar manualmente otro ejemplo de relevancia.
    
- En espera: se ha completado el proceso de formación de relevancia.
    
  - Implicación: no se requiere ninguna formación de relevancia en este momento.
    
Aunque eDiscovery avanzado le guía a lo largo del proceso, con los siguientes pasos recomendados en distintas etapas, también le permite navegar entre pestañas y páginas, y tomar decisiones para abordar situaciones que pueden ser pertinentes para su proceso individual de revisión de casos, problemas o documentos. 
  
Es posible aceptar o invalidar las opciones de procesamiento del paso siguiente de eDiscovery avanzado. Si desea realizar un paso distinto del paso  siguiente recomendado, haga clic en el paso  siguiente que aparece en la presentación del problema expandido en el cuadro de diálogo, haga clic en el botón Modificar situado junto al paso siguiente y seleccione otra opción de paso siguiente. 
  
> [!NOTE]
> Algunas opciones pueden permanecer deshabilitadas después del desbloqueo, ya que no se admiten para su uso en ese punto del proceso. 
  
## <a name="more-information"></a>Más información

[Descripción de la evaluación en relevancia](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Etiquetado y evaluación](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Formación de etiquetas y relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Seguimiento del análisis de relevancia](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidir en función de los resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Prueba del análisis de relevancia](test-relevance-analysis-in-advanced-ediscovery.md)

[Consultar los datos de un conjunto de revisión](review-set-search.md)
