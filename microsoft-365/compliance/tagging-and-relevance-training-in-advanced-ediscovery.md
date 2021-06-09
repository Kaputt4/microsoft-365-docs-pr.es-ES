---
title: Formación de etiquetas y relevancia en Advanced eDiscovery
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
description: Aprenda los pasos para etiquetar y, a continuación, trabajar con una muestra de aprendizaje de 40 archivos durante la fase de aprendizaje de relevancia de Advanced eDiscovery.
ms.openlocfilehash: ae4a9f2e9fd87fdd0679bbfd8f287b6eaa98e41f
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769225"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery"></a>Formación de etiquetas y relevancia en Advanced eDiscovery
  
En este artículo se describe el procedimiento para trabajar con el módulo de aprendizaje relevancia en Advanced eDiscovery.
  
Una vez completada la evaluación en Advanced eDiscovery y entras en la fase de aprendizaje relevancia, se incluye una muestra de aprendizaje de 40 archivos en la pestaña Etiqueta para el etiquetado.
  
## <a name="performing-relevance-training"></a>Realizar cursos de relevancia

1. En la **pestaña Etiqueta \>** de relevancia, el panel Etiquetado se muestra de forma predeterminada en el panel izquierdo y se muestran los archivos de ejemplo, uno a uno para el etiquetado.

    ![Panel de etiquetas de relevancia](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    En la **pestaña Etiqueta,** se muestra el nombre para mostrar del archivo. Podría ser la ruta de acceso, el asunto del correo electrónico, el título o el nombre definido por el usuario. El identificador, la ruta de acceso de archivo o la ruta de texto se pueden copiar haciendo clic con el botón secundario en la ruta de acceso del archivo.

    Las  estadísticas de etiquetado de la pestaña Etiqueta muestran el número de ejemplo de archivo (en la parte superior del panel izquierdo), el número del archivo mostrado actualmente fuera del total de archivos del ejemplo (parte inferior del panel derecho) y el número total actual de archivos etiquetados en el ejemplo (parte inferior del panel izquierdo), que cambia a medida que etiqueta archivos. Esto se aplica a cualquier etiquetado de relevancia realizado, ya sea en Evaluación, Aprendizaje, Ponerse al día o Probar.

    Los iconos que indican la existencia de comentarios, etiquetas y archivos de familia se muestran en la vista de archivos en una barra encima del archivo.

2. Determine la relevancia del archivo para el problema de caso y etiquete el archivo mediante los botones de icono de la opción Etiquetar o los métodos abreviados de teclado, como se muestra en la tabla siguiente:

   |**Opción de etiquetado**|**Descripción**|**Método abreviado de teclado**|**Método abreviado de teclado de etiquetado masivo (para varios problemas)**|
   |-----|-----|-----|-----|
   |R  <br/> |Relevante  <br/> |Z  <br/> |`Shift + Z`  <br/> |
   |NR  <br/> |No relevante  <br/> |X  <br/> |`Shift + X`  <br/> |
   |Omitir  <br/> |Omitir  <br/> |C  <br/> |`Shift + A`  <br/> |
   |||||

   - Cuando existen varios problemas para un archivo, después de etiquetar un problema, la selección pasa al siguiente problema (si existe).  

   - Las palabras clave definidas por el administrador o el administrador de casos al resaltar palabras clave (palabras clave resaltadas del programa de configuración de relevancia) se mostrarán (en colores especificados) para ayudar a identificar los archivos relevantes durante el \> etiquetado. Si una palabra clave tiene un subrayado doble, se puede hacer clic para mostrar una sugerencia de herramienta con la descripción de la palabra clave.

     Opcionalmente, en la **pestaña Etiqueta,** haga clic en **Configuración de etiqueta** para establecer las siguientes opciones:

      ![Configuración de etiquetas de relevancia](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
   - **Etiqueta masiva:** use esta opción para asignar varios  problemas a un archivo seleccionando Todo para establecer la etiqueta del  archivo seleccionado para todos los problemas (invalida problemas ya etiquetados) o seleccionando El resto para aplicar la etiqueta a los problemas no etiquetados restantes. La opción seleccionada permanece en vigor para todos los casos de este usuario hasta que ese usuario lo cambie (la configuración es por usuario para todos los casos del usuario).

   - **Etiqueta automática:** active esta casilla para establecer otros problemas para un archivo como No relevantes después de un único etiquetado relevante.

   - **Avance automático:** active esta casilla para mover la selección de archivo mostrada al siguiente archivo al etiquetar el último o solo problema sin etiquetar.

    Los archivos omitido no se considerarán para fines de puntuación de relevancia y aprendizaje por relevancia.

3. Los comentarios de texto libre, asociados con un  archivo, se pueden ver y editar a través de la opción Comentario de la lista desplegable del panel izquierdo. (opcional)

4. Las directrices para el etiquetado se  pueden ver seleccionando la opción Directrices de etiquetado en la lista desplegable del panel izquierdo.

5. Una vez que termine de etiquetar todos los archivos de la lista y esté listo para calcular los resultados, haga clic en **Calcular**. Se **muestra la** pestaña Pista.  

## <a name="working-with-the-sample-files-list"></a>Trabajar con la lista de archivos de ejemplo

La lista de archivos de ejemplo permite ver una lista de los archivos de un ejemplo de aprendizaje y realizar varias acciones en uno o varios archivos. En la pestaña **Etiqueta** de relevancia, el panel izquierdo Archivos de ejemplo muestra una lista de archivos de ejemplo para procesarlos con procesos de evaluación, aprendizaje, ponerse al día e \>  incoherencias. 
  
1. En la **pestaña Etiqueta \> de** relevancia, seleccione los archivos de ejemplo de la lista desplegable panel izquierdo. Los archivos de ejemplo se enumeran en el panel izquierdo.

    ![Lista de archivos de ejemplo de etiqueta de relevancia](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Seleccione un ejemplo específico o un número de archivo especificando o seleccionando su número en los cuadros **Ejemplo** **o** Archivo.

   - Un número de secuencia de archivos aparece en la columna izquierda de la lista de archivos mostrada en la **pestaña** Etiqueta. Al hacer clic en el encabezado, el orden original mostrado de los archivos vuelve a su orden original.

   - Al hacer clic en una fila de archivo, se muestra su contenido en el panel derecho.

   - Navegue entre los archivos del ejemplo actual mediante las opciones de la barra de menú inferior. Además, los métodos abreviados de teclado de navegación están disponibles:
  
     - Para ir al primer archivo del ejemplo: `Shift + Ctrl + <`

     - Para ir al archivo anterior en el ejemplo: `Shift + <`

     - Para ir al siguiente archivo del ejemplo: `Shift + >`

     - Para ir al último archivo del ejemplo: `Shift + Ctrl + >`
