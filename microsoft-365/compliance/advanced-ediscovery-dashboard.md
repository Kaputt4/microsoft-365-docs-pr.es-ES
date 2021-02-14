---
title: Panel de eDiscovery avanzado para conjuntos de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el panel de eDiscovery avanzado para conjuntos de revisión para analizar rápidamente el corpus con el fin de identificar tendencias o estadísticas clave que le ayudarán a desarrollar su estrategia de revisión.
ms.openlocfilehash: 36f30689047eec7ff2c2c49c6b0d54f1a60470e4
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741697"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>Panel de eDiscovery avanzado para conjuntos de revisión

En algunos casos de eDiscovery avanzado, es posible que tenga un gran volumen de documentos y mensajes de correo electrónico que deben revisarse. Antes de iniciar el proceso de revisión, es posible que desee analizar rápidamente el corpus para identificar tendencias o estadísticas clave que le ayudarán a desarrollar su estrategia de revisión. Para ello, puede usar el panel de eDiscovery avanzado para conjuntos de revisión para analizar rápidamente el corpus.

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>Paso 1: Crear un widget en el panel del conjunto de revisión

1. En el Centro de & cumplimiento, vaya a **eDiscovery > eDiscovery** avanzado para mostrar la lista de casos de su organización.
  
2. Seleccione un caso existente.
  
3. Haga clic en **la pestaña Conjunto** de revisión y, a continuación, seleccione un conjunto de revisión.
  
4. En la lista **desplegable Resultados individuales,** haga clic **en Vista de perfil de búsqueda.** 

   ![DashbordPivot](../media/dashboardpivot.png)

   Se **muestra la página de vista** de perfil de búsqueda; La primera vez que se muestra esta página, se muestran tres widgets predeterminados.

   ![Panel](../media/dashboardonly.png)
  
5. Haga clic **en el widget** Nuevo y, a continuación, seleccione uno de los siguientes elementos:

   ![Lista desplegable de nuevos widget](../media/NewWidgetDropdownBox.png)

   - **Elija entre bibliotecas:** Muestra una biblioteca predeterminada de widgets. Haga clic en un widget **y,** a continuación, haga clic en Agregar para agregarlo a los widgets en la página de vista **de perfil de** búsqueda.
  
   - **Crear widget personalizado:** Muestra una página flotante que puede usar para configurar un widget personalizado. 

6. Para crear un widget personalizado, haga lo siguiente en la página desplegable Agregar **widget:**

   ![Crear widget](../media/addwidget.png)

    a. Escriba un nombre para el widget, que se muestra en la barra de título del widget. Es necesario asignar un nombre a un widget, pero resulta útil identificar los datos del widget.

    b. Seleccione una propiedad en la lista desplegable Elegir **tabla** dinámica que se usará para los datos del widget. Los elementos de esta lista son las propiedades que se pueden buscar para los elementos del conjunto de revisión. Para obtener una descripción de estas propiedades, vea [Campos de metadatos del documento en eDiscovery avanzado.](document-metadata-fields-in-Advanced-eDiscovery.md) Las opciones dinámicas para el widget se enumeran en la columna Nombre de campo que permite **búsquedas** de este tema.

    c. Seleccione un tipo de gráfico para mostrar los datos de la propiedad dinámica seleccionada.

  6. Haga **clic en** Agregar para crear el widget personalizado y mostrarlo en la página de vista de perfil **de** búsqueda.

## <a name="step-2-create-a-review-set-search-query"></a>Paso 2: Crear una consulta de búsqueda de conjunto de revisión

1. Haga **clic en ...** en la barra de título del widget y, a continuación, haga clic en Aplicar **condición**.

   ![Panel](../media/searchprofilehome.png)

2. En la página desplegable, haga clic en un elemento de la clave de widget o gráfico de widget para crear un filtro.

   ![CreateFilter](../media/applyconditionfilter.png)

3. Repita los pasos del 1 al 2 para otros widgets de varios widgets. 

4. Cuando haya terminado, haga clic en Guardar **como** consulta para guardar las condiciones como una nueva consulta de búsqueda para el conjunto de revisión.

   ![Consulta](../media/savequery.png)

5. Cierre la **vista de perfil de búsqueda** para volver a la vista de resultados de búsqueda.

   Si ha creado filtros visuales, la consulta resultante se aplica a los resultados de búsqueda que se muestran y la consulta de búsqueda que guardó en el paso 4 se muestra en Consultas **guardadas.** Para obtener más información acerca de las consultas de conjunto de revisión, vea [Consultar los datos de un conjunto de revisión.](review-set-search.md)
