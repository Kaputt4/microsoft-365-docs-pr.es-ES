---
title: Panel de eDiscovery (Premium) para conjuntos de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 04/05/2022
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el panel de Microsoft Purview eDiscovery (Premium) para los conjuntos de revisión para analizar rápidamente el corpus con el fin de identificar tendencias o estadísticas clave que le ayudarán a desarrollar su estrategia de revisión.
ms.openlocfilehash: 1412df381fff228c37052a6d75113c3a4c4cfcba
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64995896"
---
# <a name="ediscovery-premium-dashboard-for-review-sets"></a>Panel de eDiscovery (Premium) para conjuntos de revisión

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

En algunos casos en microsoft Purview eDiscovery (Premium), es posible que tenga un gran volumen de documentos y mensajes de correo electrónico que deben revisarse. Antes de iniciar el proceso de revisión, es posible que desee analizar rápidamente el corpus para identificar tendencias o estadísticas clave que le ayudarán a desarrollar su estrategia de revisión. Para ello, puede usar el panel eDiscovery (Premium) para revisar los conjuntos con el fin de analizar rápidamente el corpus.

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>Paso 1: Crear un widget en el panel del conjunto de revisión

1. En el portal de cumplimiento de Microsoft Purview, vaya a **eDiscovery > eDiscovery (Premium)** para mostrar la lista de casos de su organización.
  
2. Seleccione un caso existente.
  
3. Haga clic en la pestaña **Revisar conjunto** y, a continuación, seleccione un conjunto de revisión.
  
4. En la lista desplegable de **Resultados individuales**, haga clic en **Vista de perfil de búsqueda**. 

   ![DashbordPivot.](../media/dashboardpivot.png)

   Se muestra la página **Buscar vista de perfil** ; la primera vez que se muestra esta página, se muestran tres widgets predeterminados.

   ![Tablero.](../media/dashboardonly.png)
  
5. Haga clic en el **widget Nuevo** y, a continuación, seleccione uno de los siguientes elementos:

   ![Nueva lista desplegable de widgets.](../media/NewWidgetDropdownBox.png)

   - **Elija entre bibliotecas:** Muestra una biblioteca predeterminada de widgets. Haga clic en un widget y, a continuación, haga clic en **Agregar** para agregarlo a los widgets en la página **Buscar vista de perfil** .
  
   - **Crear widget personalizado:** Muestra una página de control flotante que puede usar para configurar un widget personalizado. 

6. Para crear un widget personalizado, haga lo siguiente en la página desplegable **Agregar widget** :

   ![Crear widget.](../media/addwidget.png)

    a. Escriba un nombre para el widget, que se muestra en la barra de título del widget. Se requiere asignar un nombre a un widget, pero resulta útil identificar los datos del widget.

    b. Seleccione una propiedad en la lista desplegable **Elegir dinámica** que se usará para los datos del widget. Los elementos de esta lista son las propiedades que se pueden buscar para los elementos del conjunto de revisión. Para obtener una descripción de estas propiedades, vea [Campos de metadatos del documento en eDiscovery (Premium)](document-metadata-fields-in-Advanced-eDiscovery.md). Las opciones dinámicas del widget se enumeran en la columna **Nombre de campo que se puede buscar** en este tema.

    c. Seleccione un tipo de gráfico para mostrar los datos de la propiedad dinámica seleccionada.

  6. Haga clic en **Agregar** para crear el widget personalizado y mostrarlo en la página **Buscar vista de perfil** .

## <a name="step-2-create-a-review-set-search-query"></a>Paso 2: Crear una consulta de búsqueda de conjunto de revisión

1. Haga clic en **...** en la barra de título del widget y, a continuación, haga clic en **Aplicar condición**.

   ![Tablero.](../media/searchprofilehome.png)

2. En la página de control flotante, haga clic en un elemento en la clave del widget o en el gráfico del widget para crear un filtro.

   ![CreateFilter.](../media/applyconditionfilter.png)

3. Repita los pasos del 1 al 2 para otros widgets con varios widgets. 

4. Cuando haya terminado, haga clic en **Guardar como consulta** para guardar las condiciones como una nueva consulta de búsqueda para el conjunto de revisión.

   ![Consulta.](../media/savequery.png)

5. Cierre la **vista Perfil de búsqueda** para volver a la vista de resultados de búsqueda.

   Si ha creado filtros visuales, la consulta resultante se aplica a los resultados de búsqueda que se muestran y la consulta de búsqueda que guardó en el paso 4 se muestra en **Consultas guardadas**. Para obtener más información sobre las consultas de conjuntos de revisión, consulte [Consulta de los datos de un conjunto de revisión](review-set-search.md).
