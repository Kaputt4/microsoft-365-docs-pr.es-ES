---
title: Etiquetado y formación de relevancia en eDiscovery (Premium)
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
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre los pasos para etiquetar y, a continuación, trabajar con un ejemplo de entrenamiento de 40 archivos durante la fase de entrenamiento de relevancia de eDiscovery (Premium).
ms.openlocfilehash: 8f3d92564d908344155b55b5f84dc6357324a388
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66627269"
---
# <a name="tagging-and-relevance-training-in-ediscovery-premium"></a>Etiquetado y formación de relevancia en eDiscovery (Premium)
  
En este artículo se describe el procedimiento para trabajar con el módulo de entrenamiento Relevancia en Microsoft Purview eDiscovery (Premium).
  
Una vez completada la evaluación en eDiscovery (Premium) y entra en la fase de entrenamiento Relevancia, se introduce un ejemplo de entrenamiento de 40 archivos en la pestaña Etiqueta para el etiquetado.
  
## <a name="performing-relevance-training"></a>Realización de un entrenamiento de relevancia

1. En la pestaña **Etiqueta de relevancia\>**, el panel Etiquetado se muestra de forma predeterminada en el panel izquierdo y se muestran los archivos de ejemplo, uno a uno para el etiquetado.

    ![Panel Etiqueta de relevancia.](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    En la pestaña **Etiqueta** , se muestra el nombre para mostrar del archivo. Podría ser la ruta de acceso, el asunto del correo electrónico, el título o el nombre definido por el usuario. El identificador, la ruta de acceso del archivo o la ruta de texto se pueden copiar haciendo clic con el botón derecho en la ruta de acceso del archivo.

    Las estadísticas de etiquetado de la pestaña **Etiqueta** muestran el número de ejemplo de archivo (en la parte superior del panel izquierdo), el número del archivo mostrado actualmente fuera del total de archivos del ejemplo (parte inferior del panel derecho) y el número total actual de archivos etiquetados en el ejemplo (parte inferior del panel izquierdo), que cambia a medida que se etiquetan los archivos. Esto se aplica a cualquier etiquetado de relevancia realizado, ya sea en Evaluación, Entrenamiento, Puesta al día o Prueba.

    Los iconos que indican la existencia de comentarios, etiquetas y archivos de familia se muestran en la vista de archivo de una barra situada encima del archivo.

2. Determine la relevancia del archivo para el problema del caso y etiquete el archivo mediante los botones de icono de opción Etiquetado o los métodos abreviados de teclado, como se muestra en la tabla siguiente:

   |**Opción de etiquetado**|**Description**|**Método abreviado de teclado**|**Método abreviado de teclado de etiquetado masivo (para varios problemas)**|
   |-----|-----|-----|-----|
   |R  <br/> |Relevante  <br/> |Z  <br/> |`Shift + Z`  <br/> |
   |NR  <br/> |No es relevante  <br/> |X  <br/> |`Shift + X`  <br/> |
   |Saltar  <br/> |Saltar  <br/> |C  <br/> |`Shift + A`  <br/> |
   |||||

   - Cuando existen varios problemas para un archivo, después de etiquetar un problema, la selección se mueve al siguiente problema (si existe).  

   - Las palabras clave definidas por el administrador o el administrador de casos al resaltar palabras clave (palabras clave resaltadas de configuración \> de relevancia) se mostrarán (en colores especificados) para ayudar a identificar los archivos pertinentes durante el etiquetado. Si una palabra clave tiene un subrayado doble, se puede hacer clic en ella para mostrar una sugerencia de herramientas con la descripción de la palabra clave.

     Opcionalmente, en la pestaña **Etiqueta** , haga clic en **Configuración de etiquetas** para establecer las siguientes opciones:

      ![Configuración de etiquetas de relevancia.](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
   - **Etiqueta masiva**: use esta opción para asignar varios problemas a un archivo seleccionando **Todos** para establecer la etiqueta del archivo seleccionado para todos los problemas (invalidaciones ya etiquetadas) o seleccionando **El resto** para aplicar la etiqueta a los problemas restantes sin etiquetar. La opción seleccionada permanece en vigor para todos los casos de este usuario hasta que ese usuario cambia (la configuración es por usuario para todos los casos del usuario).

   - **Etiqueta automática**: active esta casilla para establecer otros problemas para un archivo como No relevante después de un etiquetado relevante único.

   - **Avance automático**: active esta casilla para mover la selección de archivo mostrada al siguiente archivo al etiquetar el último problema o solo sin etiquetar.

    Los archivos omitidos no se tendrán en cuenta para el entrenamiento de relevancia y la puntuación de relevancia.

3. Los comentarios de texto libre, asociados a un archivo, se pueden ver y editar mediante la opción **Comentario** de la lista desplegable del panel izquierdo. (opcional)

4. Las directrices para el etiquetado se pueden ver seleccionando la opción **Directrices de etiquetado** en la lista desplegable del panel izquierdo.

5. Una vez que haya terminado de etiquetar todos los archivos de la lista y esté listo para calcular los resultados, haga clic en **Calcular**. Se muestra **la pestaña Seguimiento** .  

## <a name="working-with-the-sample-files-list"></a>Trabajar con la lista de archivos de ejemplo

La lista de archivos de ejemplo permite ver una lista de los archivos de un ejemplo de entrenamiento y realizar varias acciones en uno o varios archivos. En la pestaña **Etiqueta** de **relevancia**\>, el panel izquierdo **Archivos** de ejemplo muestra una lista de archivos de ejemplo para su procesamiento con procesos de evaluación, entrenamiento, puesta al día e incoherencias.
  
1. En la pestaña **Etiqueta de relevancia\>**, seleccione los archivos de ejemplo de la lista desplegable del panel izquierdo. Los archivos de ejemplo aparecen en el panel izquierdo.

    ![Lista de archivos de ejemplo de etiquetas de relevancia.](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Seleccione un ejemplo o número de archivo específico; para ello, escriba o seleccione su número en los cuadros **Ejemplo** o **Archivo** .

   - Un número de secuencia de archivo aparece en la columna izquierda de la lista de archivos mostrada en la pestaña **Etiqueta** . Al hacer clic en el encabezado, el orden original mostrado de los archivos vuelve a su orden original.

   - Al hacer clic en una fila de archivo, se muestra su contenido en el panel derecho.

   - Navegue entre los archivos del ejemplo actual mediante las opciones de la barra de menús inferior. Además, hay disponibles métodos abreviados de teclado de navegación:
  
     - Para ir al primer archivo del ejemplo: `Shift + Ctrl + <`

     - Para ir al archivo anterior en el ejemplo: `Shift + <`

     - Para ir al siguiente archivo del ejemplo: `Shift + >`

     - Para ir al último archivo del ejemplo: `Shift + Ctrl + >`
