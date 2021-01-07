---
title: Probar el análisis de relevancia en eDiscovery avanzado
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo usar la pestaña prueba tras el cálculo del lote en la exhibición avanzada de documentos electrónicos para probar, comparar y validar la calidad general de procesamiento.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769175"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a>Probar el análisis de relevancia en eDiscovery avanzado
  
La pestaña prueba de eDiscovery avanzado permite probar, comparar y validar la calidad general de procesamiento. Estas pruebas se realizan después del cálculo por lotes. Al etiquetar los archivos de la colección, un experto realiza la última decisión sobre si cada archivo etiquetado es relevante para el caso.
  
En escenarios únicos o de varios problemas, las pruebas se realizan normalmente por problema. Los resultados se pueden ver después de cada prueba y los resultados de la prueba se pueden volver a usar con los archivos de prueba de ejemplo especificados.
  
## <a name="testing-the-rest"></a>Probar el resto

La prueba "probar el resto" se usa para validar las decisiones de selección, por ejemplo, para revisar solo los archivos por encima de una puntuación de límite de relevancia específica basada en los resultados avanzados de eDiscovery avanzado. El experto revisa un ejemplo de archivos con una puntuación de límite seleccionada para evaluar el número de archivos relevantes dentro de ese conjunto.
  
Esta prueba proporciona estadísticas y una comparación entre el conjunto de revisión y la prueba de la población de REST. Los resultados del conjunto de revisión son los que se calculan por relevancia durante la formación. Los resultados incluyen cálculos basados en la configuración y los parámetros de entrada, como:
  
- Probar estadísticas de muestra del número de archivos de una muestra e identificado archivos relevantes.

- Comparación tabular de los parámetros de población del conjunto de revisión y el resto, por ejemplo, el número de archivos, el número estimado de archivos relevantes, la riqueza estimada y el costo medio de buscar otro archivo relevante. El administrador puede establecer la configuración del parámetro cost.

Para ejecutar la prueba "probar el resto":

1. Abra la **pestaña \> prueba de relevancia** .

2. En la pestaña **prueba** , haga clic en **nueva prueba**. Se muestra el cuadro de diálogo **crear prueba** , tal como se muestra en el siguiente ejemplo.

    ![Resultados de Probar el resto de relevancia](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. En **nombre** de la prueba y **Descripción**, escriba el nombre y la descripción.

4. En la lista **tipo de prueba** , seleccione **probar el resto**

5. En la lista **emisión/categoría** , seleccione el nombre del problema.

6. En la lista **cargar** , seleccione la carga. 

7. En el **% lectura**, acepte el valor predeterminado o seleccione un valor para la puntuación de relevancia de corte. 

8. En **establecer tamaño** o aceptar el valor predeterminado. Los iconos de restauración restaurarán los valores predeterminados.

9. Haga clic en **iniciar etiquetado**. Se genera una muestra de prueba.

10. Revise y etiquete cada uno de los archivos en la pestaña **\> etiqueta de relevancia** y, cuando haya terminado, haga clic en **calcular**.

11. En la pestaña prueba, puede hacer clic en **ver resultados** para ver los resultados de la prueba. En la siguiente captura de pantalla se muestra un ejemplo.

    ![Resultados de Probar el resto](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
En la captura de pantalla anterior, la sección **parámetros de ejemplo** de la tabla contiene detalles sobre el número de archivos en el ejemplo etiquetado por el experto y el número de archivos relevantes que se encuentran en ese ejemplo.
  
La sección **parámetros de rellenado** de la tabla contiene los resultados de la prueba, incluido el rellenado de la revisión del conjunto de archivos con una puntuación inferior al límite seleccionado y el rellenado "el resto" de los archivos con una puntuación superior al límite seleccionado. Para cada población, se muestran los siguientes resultados:
  
- Incluye archivos con el%-límite de lectura declarados

- El número total de archivos

- El número estimado de archivos relevantes

- La riqueza estimada

- El costo medio de revisión de buscar otro archivo relevante

## <a name="testing-the-slice"></a>Prueba del segmento

La prueba "probar el sector" realiza una prueba similar a la prueba "probar el resto", pero con un segmento del conjunto de archivos tal y como se especifica por% de lectura de relevancia.

Para ejecutar la prueba "probar el sector":
  
1. Abra la **pestaña \> prueba de relevancia** .

2. En la pestaña **prueba** , haga clic en **nueva prueba**. Se muestra el cuadro de diálogo **crear prueba** .

3. En **nombre** de la prueba y **Descripción**, escriba la información.

4. En la lista **tipo de prueba** , seleccione **probar el sector**.

5. En la lista de **problemas** , seleccione el nombre del problema.

6. En la lista **cargar** , seleccione la carga.

7. En **leer% entre**, acepte los valores predeterminados de rango bajo y alto o seleccione valores para los resultados de relevancia de corte.

8. En **establecer tamaño**, seleccione un valor o acepte el valor predeterminado.

    Los iconos de restauración restaurarán el valor predeterminado.

9. Haga clic en **iniciar etiquetado**. Se genera una muestra de prueba.

10. Revise y etiquete cada uno de los archivos en la pestaña **\> etiqueta de relevancia** y, cuando haya terminado, haga clic en **calcular**.

11. En la pestaña prueba, puede hacer clic en **ver resultados** para ver los resultados de la prueba.
