---
title: Identificación y aprendizaje de relevancia en eDiscovery avanzado
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
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre los pasos para etiquetar y, a continuación, trabaje con una muestra de aprendizaje de 40 archivos durante la fase de aprendizaje de relevancia de eDiscovery avanzado.
ms.openlocfilehash: ae4a9f2e9fd87fdd0679bbfd8f287b6eaa98e41f
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769225"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery"></a>Identificación y aprendizaje de relevancia en eDiscovery avanzado
  
En este artículo se describe el procedimiento para trabajar con el módulo de aprendizaje de relevancia en la exhibición avanzada de documentos electrónicos.
  
Una vez completada la evaluación en la exhibición avanzada de documentos electrónicos y especifica la fase de aprendizaje de relevancia, se incluye una muestra de formación de 40 archivos en la pestaña etiqueta para el etiquetado.
  
## <a name="performing-relevance-training"></a>Realizar entrenamiento de relevancia

1. En la **pestaña \> etiqueta de relevancia** , el panel etiquetado se muestra de forma predeterminada en el panel izquierdo y se muestran los archivos de ejemplo, uno por vez, para el etiquetado.

    ![Panel de etiquetas de relevancia](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    En la ficha **etiqueta** , se muestra el nombre para mostrar del archivo. Puede ser la ruta de acceso, el asunto del correo electrónico, el título o el nombre definido por el usuario. El identificador, la ruta de acceso de archivo o la ruta de acceso de texto se pueden copiar haciendo clic con el botón secundario en la ruta de acceso del archivo.

    En las estadísticas de etiquetado de pestañas de **etiquetas** se muestra el número de muestra de archivo (en la parte superior del panel izquierdo), el número del archivo que se muestra actualmente de los archivos totales en el ejemplo (parte inferior del panel derecho) y el número total actual de archivos etiquetados en el ejemplo (parte inferior del panel izquierdo), que cambia cuando se etiquetan los archivos. Esto se aplica a cualquier etiquetado de relevancia realizado, ya sea en evaluación, formación, puesta en marcha o prueba.

    Los iconos que indican la existencia de comentarios, etiquetas y archivos de familia se muestran en la vista de archivo en una barra situada encima del archivo.

2. Determine la relevancia del archivo para el problema de caso y etiquete el archivo con los botones de iconos de opción de etiquetado o con los métodos abreviados de teclado, como se muestra en la siguiente tabla:

   |**Opción de etiquetado**|**Descripción**|**Método abreviado de teclado**|**Método abreviado de teclado para etiquetado en masa (para varios problemas)**|
   |-----|-----|-----|-----|
   |R  <br/> |Metabolito  <br/> |Z  <br/> |`Shift + Z`  <br/> |
   |Nº  <br/> |No relevante  <br/> |X  <br/> |`Shift + X`  <br/> |
   |Avanzar  <br/> |Avanzar  <br/> |C  <br/> |`Shift + A`  <br/> |
   |||||

   - Cuando hay varios problemas para un archivo, después de marcar un problema, la selección se mueve al siguiente problema (si lo hay).  

   - Las palabras clave definidas por el administrador o el administrador de casos al resaltar palabras clave ( \> palabras clave resaltadas de configuración de relevancia), se mostrarán (en los colores especificados) para ayudar a identificar los archivos relevantes al etiquetar. Si una palabra clave tiene un doble subrayado, se puede hacer clic para mostrar una sugerencia de herramienta con la descripción de la palabra clave.

     De forma opcional, en la pestaña **etiqueta** , haga clic en **configuración de etiqueta** para establecer las siguientes opciones:

      ![Configuración de etiquetas de relevancia](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
   - **Etiqueta masiva**: Use esta opción para asignar varios problemas a un archivo; para ello, seleccione **todos** para establecer la etiqueta del archivo seleccionado para todos los problemas (invalida los problemas ya etiquetados) o seleccione **el resto** para aplicar la etiqueta a los demás problemas sin etiquetar. La opción seleccionada permanece en vigor para todos los casos de este usuario hasta que la modifica el usuario (la configuración es por usuario para todos los casos del usuario).

   - **Etiqueta automática**: Active esta casilla para establecer otros problemas de un archivo como no relevante después de un único etiquetado relevante.

   - **Avance automático**: Active esta casilla de verificación para mover la selección de archivos que se muestra al siguiente archivo al etiquetar el último o único problema sin etiquetar.

    Los archivos omitidos no se tendrán en cuenta para la formación de relevancia y la puntuación de relevancia.

3. Los comentarios de texto libre, asociados a un archivo, se pueden ver y editar a través de la opción **Comentario** en la lista desplegable panel izquierdo. (opcional)

4. Las directrices para la etiquetación se pueden ver seleccionando la opción **pautas de etiquetado** en la lista desplegable del panel izquierdo.

5. Cuando termine de etiquetar todos los archivos de la lista y esté listo para calcular los resultados, haga clic en **calcular**. Se muestra la pestaña **seguimiento** .  

## <a name="working-with-the-sample-files-list"></a>Trabajar con la lista de archivos de ejemplo

La lista de archivos de muestra le permite ver una lista de los archivos en un ejemplo de aprendizaje y realizar diversas acciones en uno o más archivos. En la  \> ficha **etiqueta** de relevancia, el panel **archivos de ejemplo** izquierdo muestra una lista de archivos de ejemplo para el procesamiento con procesos de evaluación, formación, puesta en marcha e incoherencias.
  
1. En la **ficha \> etiqueta de relevancia** , seleccione los archivos de ejemplo en la lista desplegable del panel izquierdo. Los archivos de ejemplo se muestran en el panel izquierdo.

    ![Lista de archivos de ejemplo de etiqueta de relevancia](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Seleccione un ejemplo o un número de archivo específico especificando o seleccionando su número en los cuadros **muestra** o **archivo** .

   - Un número de secuencia de archivo aparece en la columna izquierda de la lista de archivos que se muestra en la ficha **etiqueta** . Al hacer clic en el encabezado, el orden original mostrado de los archivos vuelve a su orden original.

   - Al hacer clic en una fila de archivo, se muestra su contenido en el panel derecho.

   - Desplácese entre los archivos del ejemplo actual mediante las opciones de la barra de menús inferior. Además, los métodos abreviados de teclado de navegación están disponibles:
  
     - Para ir al primer archivo del ejemplo: `Shift + Ctrl + <`

     - Para ir al archivo anterior en el ejemplo: `Shift + <`

     - Para ir al siguiente archivo del ejemplo: `Shift + >`

     - Para ir al último archivo del ejemplo: `Shift + Ctrl + >`
