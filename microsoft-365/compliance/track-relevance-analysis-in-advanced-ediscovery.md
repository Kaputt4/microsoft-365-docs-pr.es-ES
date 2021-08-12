---
title: Realizar un seguimiento del análisis de relevancia en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo ver e interpretar el estado de aprendizaje de relevancia y los resultados de los problemas de casos en Advanced eDiscovery.
ms.openlocfilehash: f0c0ab94b328a715739c7c8aec32ac041b6dc97f6fd998865a5b2e282bff42eb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53801739"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a>Realizar un seguimiento del análisis de relevancia en Advanced eDiscovery
  
En Advanced eDiscovery, la pestaña Pista de relevancia muestra la validez calculada del aprendizaje de relevancia realizado en la pestaña Etiqueta e indica el siguiente paso para realizar el proceso de aprendizaje iterativo en Relevancia. 
  
## <a name="tracking-relevance-training-status"></a>Seguimiento del estado de aprendizaje de relevancia

1. Vea los siguientes detalles en El seguimiento de relevancia para los problemas de caso, como se muestra en el siguiente ejemplo de un cuadro de diálogo **Nombre de** problema a continuación.

   - **Evaluación:** este indicador de progreso muestra hasta qué punto el aprendizaje de relevancia realizado hasta este punto ha alcanzado el objetivo de evaluación en términos de margen de error. También se muestra la riqueza de los resultados del aprendizaje de relevancia.

   - **Aprendizaje:** este indicador de progreso codificado por colores y la sugerencia de herramienta indican la estabilidad de los resultados del aprendizaje de relevancia y una escala numérica que muestra el número de muestras de aprendizaje de relevancia etiquetadas para cada problema. El experto supervisa el progreso del proceso de aprendizaje de relevancia iterativa. 
  
   - **Cálculo por lotes:** este indicador de progreso proporciona información sobre la finalización del cálculo por lotes.
  
   - **Paso siguiente:** muestra la recomendación para el siguiente paso que se va a realizar. 
  
    En el ejemplo, se muestra una evaluación completada correctamente para un problema, indicada por el indicador de progreso de color completado y la marca de verificación. El etiquetado está en curso, pero el caso aún se considera inestable (el estado de estabilidad también se muestra en una sugerencia de herramienta). El siguiente paso recomendado es "Training". 
  
    ![Formación del seguimiento de relevancia paso 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    La vista expandida muestra información y opciones adicionales. El margen de error actual mostrado es el margen de error de la recuperación en el estado actual de evaluación, dados los archivos de evaluación existentes (ya etiquetados).
  
    > [!NOTE]
    >  La fase de evaluación se puede omitir desactivando **la** casilla Evaluación por problema y, a continuación, para "todos los problemas". Sin embargo, como resultado, no habrá estadísticas para este problema. > desactivar la **casilla Evaluación** solo se puede hacer antes de realizar la evaluación. Cuando existen varios problemas en un caso, la evaluación solo se omite si la casilla está desactivada para cada problema 
  
    Cuando la evaluación no se completa con el primer conjunto de archivos de ejemplo, la evaluación puede ser el siguiente paso para etiquetar más archivos.
  
    En **Pista de** \> **relevancia,** el indicador de progreso de aprendizaje y la sugerencia de herramienta indican el número estimado de muestras adicionales necesarias para alcanzar la estabilidad. Esta estimación proporciona una guía para la formación adicional necesaria.
  
    ![Formación del seguimiento de relevancia](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Cuando haya terminado de etiquetar y si necesita continuar con el aprendizaje, haga clic en **Aprendizaje**. Otro conjunto de archivos de ejemplo se genera a partir del conjunto de archivos cargado para un aprendizaje adicional. A continuación, se le devuelve a la pestaña Etiqueta para etiquetar y entrenar más archivos.

### <a name="reaching-stable-training-levels"></a>Alcanzar niveles de aprendizaje estables

Una vez que los archivos de evaluación han alcanzado un nivel estable de aprendizaje, Advanced eDiscovery está listo para el cálculo por lotes.
  
> [!NOTE]
> Normalmente, después de tres muestras de aprendizaje estables, el siguiente paso es "Cálculo por lotes". Puede haber excepciones, por ejemplo, cuando hubo cambios en el etiquetado de archivos de ejemplos anteriores o cuando se agregaron archivos de ed. 
  
### <a name="performing-batch-calculation"></a>Realizar cálculos por lotes

El cálculo por lotes se ejecuta como el siguiente paso después de completar correctamente el aprendizaje (cuando la barra de progreso muestra un estado de aprendizaje estable, una marca de verificación y un estado estable en la sugerencia de herramienta). El cálculo por lotes aplica los conocimientos adquiridos durante el aprendizaje de relevancia a toda la población de archivos, para evaluar la relevancia de los archivos y asignar puntuaciones de relevancia.
  
Cuando hay más de un problema, el cálculo por lotes se realiza por problema. Durante el cálculo por lotes, el progreso se supervisa al procesar todos los archivos. 
  
Aquí, el siguiente paso recomendado es "Ninguno", lo que indica que no se requiere ningún aprendizaje de relevancia iterativo adicional en este momento. La siguiente fase es la pestaña **Decisión \> de** relevancia. 
  
Si desea importar nuevos archivos después del cálculo por lotes, el administrador puede agregar los archivos importados a una nueva carga.
  
> [!NOTE]
> Si hace clic **en Cancelar** durante el cálculo por lotes, el proceso guarda lo que ya se ejecutó. Si vuelve a ejecutar el cálculo por lotes, el proceso continuará desde el último punto ejecutado. 
  
### <a name="assessing-tagging-consistency"></a>Evaluar la coherencia de etiquetado

Si hay incoherencias en el etiquetado de archivos, puede afectar al análisis. El Advanced eDiscovery de coherencia de etiquetado se puede usar cuando los resultados no son óptimos o la coherencia está en duda. Se devuelve una lista de posibles archivos etiquetados incoherentemente y se pueden revisar y volver a etiquetar, según sea necesario.
  
> [!NOTE]
> Después de siete o más rondas de aprendizaje después de la evaluación, la coherencia de etiquetado se puede ver en **Resultados** detallados del seguimiento de relevancia Progreso de \>  \>  \>  \> **la formación.** Esta revisión se realiza por un problema a la vez.
  
1. En **Pista \> de relevancia,** expanda la fila de un problema.
  
2. A la derecha del **paso Siguiente,** haga clic **en Modificar**.
  
3. Seleccione **Etiquetar incoherencias** como **la** opción Paso siguiente, después de siete ejemplos de aprendizaje y haga clic en **Aceptar**.
  
4. Seleccione **Incoherencias de etiqueta.** La **pestaña** Etiqueta se abre mostrando una lista de las incoherencias para volver a etiquetar según sea necesario.
  
5. Haga **clic en** Calcular para enviar los cambios. El siguiente paso después de etiquetar incoherencias es "Training". 
  
## <a name="viewing-and-using-relevance-results"></a>Visualización y uso de resultados de relevancia

En la **pestaña Pista \> de** relevancia, expanda la fila de un problema y, junto a **Resultados detallados,** haga clic en **Ver**. Se muestran los paneles de resultados detallados, como se muestra y se describe a continuación.
  
![Resultados detallados de la formación de relevancia](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Resumen de etiquetado

 En el ejemplo siguiente, el resumen de etiquetado muestra totales para cada uno de los procesos de etiquetado de archivos de evaluación, aprendizaje y ponerse al día. 
  
![Resumen de etiquetado del seguimiento de relevancia](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Palabras clave

Una palabra clave es una cadena, palabra, frase o secuencia única de palabras en un archivo identificado por Advanced eDiscovery como un indicador significativo de si un archivo es relevante. Las columnas "Incluir" enumeran palabras clave y grosores en archivos etiquetados como Relevantes y las columnas "Excluir" enumeran palabras clave y ponderaciones en archivos etiquetados como No relevantes.
  
Advanced eDiscovery asigna valores de peso de palabras clave negativos o positivos. Cuanto mayor sea el peso, mayor será la probabilidad de que un archivo en el que aparece la palabra clave se asigne una puntuación de relevancia más alta durante el cálculo por lotes.
  
La Advanced eDiscovery lista de palabras clave se puede usar para complementar una lista creada por un experto o como una comprobación indirecta de la cordura en cualquier momento del proceso de revisión de archivos.
  
### <a name="training-progress"></a>Progreso de la formación

El **panel Progreso de** aprendizaje incluye un gráfico de progreso de aprendizaje y una presentación del indicador de calidad, como se muestra en el ejemplo siguiente.
  
![Progreso de formación del seguimiento de relevancia](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
**Indicador de calidad de aprendizaje:** muestra la clasificación de la coherencia de etiquetado de la siguiente manera:
  
- **Bueno:** los archivos se etiquetan de forma coherente. (Se muestra la luz verde)
  
- **Medium:** es posible que algunos archivos se etiquete de forma incoherente. (Se muestra luz amarilla)

- **Advertencia:** muchos archivos pueden etiquetarse de forma incoherente. (Se muestra la luz roja)

**Gráfico de progreso del** aprendizaje: muestra el grado de estabilidad del aprendizaje de relevancia después de muchos ciclos de aprendizaje de relevancia en comparación con el valor de la medida F. A medida que nos movemos de la izquierda a la derecha a través del gráfico, el intervalo de confianza se estrecha y se usa, junto con la medida F, mediante Advanced eDiscovery Relevancia para determinar la estabilidad cuando se optimizan los resultados del aprendizaje de relevancia.
  
> [!NOTE]
> Relevancia usa F2, una métrica de medida F donde Recall recibe el doble de peso que Precision. Para los casos con alta riqueza (más del 25%), Relevancia usa F1 (relación 1:1). La relación de medida F se puede configurar en **Configuración de** \> **relevancia Configuración avanzada**.
  
### <a name="batch-calculation-results"></a>Resultados del cálculo por lotes

El **panel de resultados del** cálculo por lotes incluye el número de archivos que se puntuaron para Relevancia, de la siguiente manera: 
  
- **Success**
  
- **Empty**: No contiene texto, por ejemplo, solo espacios/pestañas
  
- **Error:** debido a un tamaño excesivo o no se pudo leer
  
- **Ignored**: Debido a un tamaño excesivo
  
- **Nebulous:** contiene texto sin sentido o sin características relevantes para el problema
  
> [!NOTE]
> Empty, Failed, Ignored o Nebulous recibirán una puntuación de relevancia de -1.
  
### <a name="training-statistics"></a>Estadísticas de aprendizaje

El **panel Estadísticas de aprendizaje** muestra estadísticas y gráficos basados en los resultados del Advanced eDiscovery de relevancia. 
  
![Estadísticas de formación del seguimiento de relevancia](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Esta vista muestra lo siguiente:
  
- **Relación revisión-recuperación:** comparación de resultados según las puntuaciones de relevancia en una revisión hipotéticamente lineal. La recuperación se calcula teniendo en cuenta el conjunto de tamaños del conjunto de revisión.
  
- **Parámetros:** estadísticas calculadas acumulativas relativas al conjunto de revisión en relación con la población de archivos para todo el caso.
  
- **Review**: Percentage of files to review based on this cutoff.
  
- **Recall**: Porcentaje de archivos relevantes en el conjunto de revisión. 
  
- **Distribución por puntuación de relevancia:** los archivos de la pantalla gris oscuro a la izquierda están por debajo de la puntuación de límite. Una sugerencia de herramienta muestra la puntuación relevancia y el porcentaje relacionado de archivos en el conjunto de archivos de revisión en relación con el total de archivos.
