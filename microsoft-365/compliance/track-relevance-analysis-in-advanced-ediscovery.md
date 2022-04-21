---
title: Seguimiento del análisis de relevancia en eDiscovery (Premium)
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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo ver e interpretar el estado de entrenamiento de relevancia y los resultados de los problemas de casos en eDiscovery (Premium).
ms.openlocfilehash: 72e12fe54b30c3d766f7a198e5e3417ff9d48a22
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "65000958"
---
# <a name="track-relevance-analysis-in-ediscovery-premium"></a>Seguimiento del análisis de relevancia en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]
  
En Microsoft Purview eDiscovery (Premium), la pestaña Seguimiento de relevancia muestra la validez calculada del entrenamiento de relevancia realizado en la pestaña Etiqueta e indica el siguiente paso que se debe realizar en el proceso de entrenamiento iterativo en Relevancia. 
  
## <a name="tracking-relevance-training-status"></a>Seguimiento del estado de entrenamiento de relevancia

1. Vea los detalles siguientes en Seguimiento de relevancia para los problemas de caso, como se muestra en el ejemplo siguiente de un cuadro de diálogo **Nombre de problema** a continuación.

   - **Evaluación**: este indicador de progreso muestra hasta qué punto la formación de relevancia realizada hasta el momento ha alcanzado el objetivo de evaluación en términos de margen de error. También se muestra la riqueza de los resultados de entrenamiento de relevancia.

   - **Entrenamiento**: este indicador de progreso codificado por colores y sugerencia de herramientas indica la estabilidad de los resultados del entrenamiento de relevancia y una escala numérica que muestra el número de ejemplos de entrenamiento de relevancia etiquetados para cada problema. El experto supervisa el progreso del proceso de entrenamiento de relevancia iterativa. 
  
   - **Cálculo por lotes**: este indicador de progreso proporciona información sobre la finalización del cálculo de Batch.
  
   - **Paso siguiente**: muestra la recomendación para el paso siguiente que se va a realizar. 
  
    En el ejemplo, se muestra una evaluación completada correctamente para un problema, indicada por el indicador de progreso de color completado y la marca de verificación. El etiquetado está en curso, pero el caso todavía se considera inestable (el estado de estabilidad también se muestra en una sugerencia de herramientas). La recomendación del siguiente paso es "Entrenamiento". 
  
    ![Paso 1 de entrenamiento de Seguimiento de relevancia.](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    La vista expandida muestra información y opciones adicionales. El margen de error actual mostrado es el margen de error de la recuperación en el estado actual de evaluación, dados los archivos de evaluación existentes (ya etiquetados).
  
    > [!NOTE]
    >  La fase evaluación se puede omitir desactivando la casilla **Evaluación** por problema y, a continuación, para "todos los problemas". Sin embargo, como resultado, no habrá estadísticas para este problema. > La desactivación de la casilla **Evaluación** solo se puede realizar antes de realizar la evaluación. Cuando existen varios problemas en un caso, la evaluación solo se omite si la casilla está desactivada para cada problema. 
  
    Cuando la evaluación no se completa con el primer conjunto de archivos de ejemplo, la evaluación podría ser el siguiente paso para etiquetar más archivos.
  
    En La **pista** **de relevancia**\>, el indicador de progreso de entrenamiento y la sugerencia de herramientas indican el número estimado de muestras adicionales necesarias para alcanzar la estabilidad. Esta estimación proporciona una guía para el entrenamiento adicional necesario.
  
    ![Formación de seguimiento de relevancia.](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Cuando haya terminado de etiquetar y si necesita continuar el entrenamiento, haga clic en **Entrenamiento**. Otro conjunto de archivos de ejemplo se genera a partir del conjunto de archivos cargados para el entrenamiento adicional. A continuación, se le devuelve a la pestaña Etiqueta para etiquetar y entrenar más archivos.

### <a name="reaching-stable-training-levels"></a>Alcanzar niveles de entrenamiento estables

Una vez que los archivos de evaluación han alcanzado un nivel estable de entrenamiento, eDiscovery (Premium) está listo para el cálculo de Batch.
  
> [!NOTE]
> Normalmente, después de tres ejemplos de entrenamiento estables, el siguiente paso es "Cálculo por lotes". Puede haber excepciones, por ejemplo, cuando se produjeron cambios en el etiquetado de archivos de ejemplos anteriores o cuando se agregaron archivos de inicialización. 
  
### <a name="performing-batch-calculation"></a>Realización del cálculo por lotes

El cálculo por lotes se ejecuta como el siguiente paso después de que el entrenamiento se complete correctamente (cuando la barra de progreso muestra un estado de entrenamiento estable, una marca de verificación y un estado estable en la información sobre herramientas). El cálculo por lotes aplica el conocimiento adquirido durante el entrenamiento de relevancia a toda la población de archivos, para evaluar la relevancia de los archivos y asignar puntuaciones de relevancia.
  
Cuando hay más de un problema, el cálculo de Batch se realiza por problema. Durante el cálculo de Batch, el progreso se supervisa mientras se procesan todos los archivos. 
  
Aquí, el siguiente paso recomendado es "Ninguno", lo que indica que no se requiere ningún entrenamiento de relevancia iterativo adicional en este momento. La siguiente fase es la pestaña **Decisión de relevancia\>**. 
  
Si desea importar nuevos archivos después del cálculo de Batch, el administrador puede agregar los archivos importados a una nueva carga.
  
> [!NOTE]
> Si hace clic en **Cancelar** durante el cálculo de Batch, el proceso guarda lo que ya se ha ejecutado. Si vuelve a ejecutar el cálculo de Batch, el proceso continuará desde el último punto ejecutado. 
  
### <a name="assessing-tagging-consistency"></a>Evaluación de la coherencia del etiquetado

Si hay incoherencias en el etiquetado de archivos, puede afectar al análisis. El proceso de coherencia de etiquetado de eDiscovery (Premium) se puede usar cuando los resultados no son óptimos o la coherencia está en duda. Se devuelve una lista de posibles archivos etiquetados incoherentes y se pueden revisar y volver a tomar, según sea necesario.
  
> [!NOTE]
> Después de siete o más rondas de entrenamiento después de la evaluación, la coherencia del etiquetado se puede ver en Resultados **detallados** \> del problema  de **seguimiento** \> \> de **relevancia** \> **Progreso de entrenamiento**. Esta revisión se realiza para un problema a la vez.
  
1. En **Seguimiento de relevancia\>**, expanda la fila de un problema.
  
2. A la derecha del **paso Siguiente**, haga clic en **Modificar**.
  
3. Seleccione **Etiquetar incoherencias** como la opción **Paso siguiente** , después de siete ejemplos de entrenamiento y haga clic en **Aceptar**.
  
4. Seleccione **Etiquetar incoherencias**. Se abre la pestaña **Etiqueta** que muestra una lista de las incoherencias que se van a volver a etiquetar según sea necesario.
  
5. Haga clic en **Calcular** para enviar los cambios. El siguiente paso después de etiquetar las incoherencias es "Entrenamiento". 
  
## <a name="viewing-and-using-relevance-results"></a>Visualización y uso de resultados de relevancia

En la pestaña **Seguimiento de relevancia\>**, expanda la fila de un problema y, junto a **Resultados detallados**, haga clic en **Ver**. Se muestran los paneles de resultados detallados, como se muestra y se describe a continuación.
  
![Resultados detallados del entrenamiento de relevancia.](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Resumen de etiquetado

 En el ejemplo que se muestra a continuación, el **resumen de etiquetado** muestra los totales de cada uno de los procesos de etiquetado de archivos de evaluación, entrenamiento y puesta al día.
  
![Resumen de etiquetado de seguimiento de relevancia.](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Palabras clave

Una palabra clave es una cadena única, palabra, frase o secuencia de palabras en un archivo identificado por eDiscovery (Premium) como un indicador significativo de si un archivo es relevante. Las columnas "Include" enumeran la palabra clave y los pesos de los archivos etiquetados como Pertinentes, y las columnas "Excluir" enumeran las palabras clave y los pesos de los archivos etiquetados como No pertinentes.
  
eDiscovery (Premium) asigna valores de peso de palabras clave negativos o positivos. Cuanto mayor sea el peso, mayor será la probabilidad de que un archivo en el que aparece la palabra clave tenga asignada una puntuación de relevancia mayor durante el cálculo de Batch.
  
La lista de palabras clave de eDiscovery (Premium) se puede usar para complementar una lista creada por un experto o como una comprobación indirecta de cordura en cualquier punto del proceso de revisión de archivos.
  
### <a name="training-progress"></a>Progreso del entrenamiento

El panel **Progreso del** entrenamiento incluye un gráfico de progreso de entrenamiento y una pantalla de indicador de calidad, como se muestra en el ejemplo siguiente.
  
![Relevancia Realice un seguimiento del progreso del entrenamiento.](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
**Indicador de calidad de entrenamiento**: muestra la clasificación de la coherencia del etiquetado de la siguiente manera:
  
- **Correcto**: Los archivos se etiquetan de forma coherente. (Se muestra luz verde)
  
- **Medio**: algunos archivos pueden etiquetarse de forma incoherente. (Se muestra luz amarilla)

- **Advertencia**: Muchos archivos pueden etiquetarse de forma incoherente. (Se muestra la luz roja)

**Gráfico de progreso del entrenamiento**: muestra el grado de estabilidad del entrenamiento de relevancia después de muchos ciclos de entrenamiento de relevancia en comparación con el valor de la medida F. A medida que nos movemos de izquierda a derecha a través del gráfico, el intervalo de confianza se reduce y se usa, junto con la medida F, por eDiscovery (Premium) Relevancia para determinar la estabilidad cuando se optimizan los resultados del entrenamiento de relevancia.
  
> [!NOTE]
> Relevancia usa F2, una métrica de medida F en la que Recall recibe el doble de peso que Precisión. En los casos con alta riqueza (más del 25%), Relevancia usa F1 (relación 1:1). La relación de medida F se puede configurar en **Configuración de relevancia** \> **Configuración avanzada**.
  
### <a name="batch-calculation-results"></a>Resultados del cálculo por lotes

El panel **Resultados del cálculo de Batch** incluye el número de archivos puntuados para Relevancia, como se indica a continuación: 
  
- **Success**
  
- **Vacío**: no contiene texto, por ejemplo, solo espacios o pestañas.
  
- **Error**: debido a un tamaño excesivo o no se pudo leer
  
- **Omitido**: debido a un tamaño excesivo
  
- **Nebulous**: contiene texto sin sentido o ninguna característica relevante para el problema.
  
> [!NOTE]
> Empty, Failed, Ignore o Nebulous recibirán una puntuación de relevancia de -1.
  
### <a name="training-statistics"></a>Estadísticas de entrenamiento

El panel **Estadísticas de entrenamiento** muestra estadísticas y gráficos basados en los resultados del entrenamiento de relevancia de eDiscovery (Premium). 
  
![Relevancia Realice un seguimiento de las estadísticas de entrenamiento.](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Esta vista muestra lo siguiente:
  
- **Relación revisión-recuperación**: comparación de los resultados según las puntuaciones de relevancia en una revisión hipotéticamente lineal. La recuperación se calcula según el conjunto de tamaños del conjunto de revisiones.
  
- **Parámetros**: estadísticas calculadas acumulativas relativas al conjunto de revisión en relación con el rellenado de archivos para todo el caso.
  
- **Revisión**: porcentaje de archivos que se van a revisar en función de este límite.
  
- **Recordar**: Porcentaje de archivos relevantes en el conjunto de revisión. 
  
- **Distribución por puntuación de relevancia**: los archivos de la pantalla gris oscuro a la izquierda están por debajo de la puntuación de límite. Una sugerencia de herramienta muestra la puntuación de relevancia y el porcentaje relacionado de archivos en el conjunto de archivos de revisión en relación con el total de archivos.
