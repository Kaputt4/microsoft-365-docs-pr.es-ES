---
title: Análisis de relevancia de prueba en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo usar la pestaña Prueba después del cálculo por lotes en eDiscovery (Premium) para probar, comparar y validar la calidad general del procesamiento.
ms.openlocfilehash: 5c1fabf677dd305fb91d77e94af0e18304280d45
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66637051"
---
# <a name="test-relevance-analysis-in-ediscovery-premium"></a>Análisis de relevancia de prueba en eDiscovery (Premium)
  
La pestaña Prueba de Microsoft Purview eDiscovery (Premium) permite probar, comparar y validar la calidad general del procesamiento. Estas pruebas se realizan después del cálculo de Batch. Al etiquetar los archivos de la colección, un experto toma la decisión final sobre si cada archivo etiquetado es relevante para el caso.
  
En escenarios únicos y de varios problemas, las pruebas se realizan normalmente por problema. Los resultados se pueden ver después de cada prueba y los resultados de las pruebas se pueden volver a trabajar con los archivos de prueba de ejemplo especificados.
  
## <a name="testing-the-rest"></a>Prueba del resto

La prueba "Probar el resto" se usa para validar las decisiones de selección, por ejemplo, para revisar solo los archivos que superen una puntuación de límite de relevancia específica en función de los resultados finales de eDiscovery (Premium). El experto revisa una muestra de archivos en una puntuación de límite seleccionada para evaluar el número de archivos pertinentes dentro de ese conjunto.
  
Esta prueba proporciona estadísticas y una comparación entre el conjunto de revisión y el rellenado Probar el resto. Los resultados del conjunto de revisión son los calculados por relevancia durante el entrenamiento. Los resultados incluyen cálculos basados en la configuración y los parámetros de entrada, como:
  
- Pruebe las estadísticas de ejemplo del número de archivos de un ejemplo y los archivos pertinentes identificados.

- Comparación tabular de los parámetros Population del conjunto de revisión y rest, por ejemplo, el número de archivos, el número estimado de archivos pertinentes, la riqueza estimada y el costo medio de buscar otro archivo pertinente. El administrador puede establecer la configuración del parámetro de costo.

Para ejecutar la prueba "Probar el resto":

1. Abra la pestaña **Prueba de relevancia\>**.

2. En la pestaña **Prueba** , haga clic en **Nueva prueba**. Se muestra el cuadro de diálogo **Crear prueba** , como se muestra en el ejemplo siguiente.

    ![Relevancia Pruebe los resultados del resto.](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. En **Nombre de prueba** y **Descripción**, escriba el nombre y la descripción.

4. En la lista **Tipo de prueba** , seleccione **Probar el resto.**

5. En la lista **Problema/Categoría** , seleccione el nombre del problema.

6. En la lista **Cargar** , seleccione la carga. 

7. En **%de lectura**, acepte el valor predeterminado o seleccione un valor para la puntuación de relevancia de corte. 

8. En **Establecer tamaño**, o acepte el valor predeterminado. Los iconos de restauración restaurarán los valores predeterminados.

9. Haga clic en **Iniciar etiquetado**. Se genera un ejemplo de prueba.

10. Revise y etiquete cada uno de los archivos en la pestaña **Etiqueta de relevancia \>** y, cuando haya terminado, haga clic en **Calcular**.

11. En la pestaña Prueba, puede hacer clic en **Ver resultados** para ver los resultados de la prueba. En la captura de pantalla siguiente se muestra un ejemplo.

    ![Pruebe los resultados restantes.](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
En la captura de pantalla anterior, la sección **Parámetros** de ejemplo de la tabla contiene detalles sobre el número de archivos del ejemplo etiquetado por el experto y el número de archivos pertinentes que se encuentran en ese ejemplo.
  
La sección **Parámetros de población** de la tabla contiene los resultados de la prueba, incluido el rellenado del conjunto de revisiones de archivos con una puntuación por debajo del límite seleccionado y el rellenado "El resto" de archivos con una puntuación por encima del límite seleccionado. Para cada población, se muestran los resultados siguientes:
  
- Incluye archivos con % de lectura: límite indicado

- El número total de archivos

- Número estimado de archivos pertinentes

- La riqueza estimada

- El costo medio de revisión de buscar otro archivo pertinente

## <a name="testing-the-slice"></a>Prueba del segmento

La prueba "Probar el segmento" realiza pruebas similares a la prueba "Probar el resto", pero a un segmento del conjunto de archivos especificado por %de lectura de relevancia.

Para ejecutar la prueba "Probar el segmento":
  
1. Abra la pestaña **Prueba de relevancia\>**.

2. En la pestaña **Prueba** , haga clic en **Nueva prueba**. Se muestra el cuadro de diálogo **Crear prueba** .

3. En **Nombre de prueba** y **Descripción**, escriba la información.

4. En la lista **Tipo de prueba** , seleccione **Probar el segmento**.

5. En la lista **Problema** , seleccione el nombre del problema.

6. En la lista **Cargar** , seleccione la carga.

7. En **Porcentaje de lectura entre**, acepte los valores predeterminados de rango bajo y alto o seleccione valores para las puntuaciones de relevancia de corte.

8. En **Establecer tamaño**, seleccione un valor o acepte el valor predeterminado.

    Los iconos de restauración restaurarán el valor predeterminado.

9. Haga clic en **Iniciar etiquetado**. Se genera un ejemplo de prueba.

10. Revise y etiquete cada uno de los archivos en la pestaña **Etiqueta de relevancia \>** y, cuando haya terminado, haga clic en **Calcular**.

11. En la pestaña Prueba, puede hacer clic en **Ver resultados** para ver los resultados de la prueba.
