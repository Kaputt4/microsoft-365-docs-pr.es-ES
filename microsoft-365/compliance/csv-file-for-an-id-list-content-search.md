---
title: Preparar un archivo CSV para una búsqueda de contenido de lista de identificadores
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
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Use archivos CSV de una búsqueda de contenido existente para crear una búsqueda de lista de identificadores que devuelva mensajes de correo electrónico específicos.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817979"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>Preparar un archivo CSV para una búsqueda de contenido de lista de identificadores

Puede buscar mensajes de correo electrónico de buzones de correo específicos y otros elementos de buzón mediante una lista de los IDs de Exchange. Para crear una búsqueda de lista de identificadores (denominada formalmente búsqueda dirigida), envíe un archivo de valores separados por comas (CSV) que identifique los elementos de buzón específicos que se deben buscar. Para este archivo CSV se usa el archivo **Results.csv** o el archivo **Items.csv** sin indexar que se incluyen al exportar los resultados de la búsqueda de contenido o exportar un informe de búsqueda de contenido y la búsqueda de contenido existente. A continuación, edita uno de estos archivos para indicar los elementos específicos que se deben buscar y, a continuación, crea una nueva búsqueda de lista de identificadores y envía el archivo CSV.

Esta es una introducción rápida del proceso para crear una búsqueda de lista de identificadores.

1. Cree y ejecute una búsqueda de contenido nueva o guiada en el Centro de & cumplimiento.

2. Exporte los resultados de la búsqueda de contenido o exporte el informe de búsqueda de contenido. Para obtener más información, vea:

    - [Exportar resultados de la búsqueda de contenido](export-search-results.md)

    - [Exportar un informe de búsqueda de contenido](export-a-content-search-report.md)

3. Edite **elResults.csv** o el archivo **Items.csv** sin indexar e identifique los elementos de buzón específicos que desea incluir en la búsqueda de la lista de identificadores. Vea las [instrucciones para](#prepare-the-csv-file-for-an-id-list-search) preparar un archivo CSV para una búsqueda de lista de identificadores.

4. Cree una nueva búsqueda de lista de identificadores (vea las [instrucciones)](#create-an-id-list-search)y envíe el archivo CSV que preparó. La consulta de búsqueda que se crea solo buscará los elementos seleccionados en el archivo CSV.

> [!NOTE]
> Las búsquedas de lista de identificadores solo se admiten para elementos de buzón. No puede buscar documentos de SharePoint y OneDrive en una búsqueda de lista de identificadores.

 **¿Por qué crear una búsqueda de lista de identificadores?** Si no puede determinar si un elemento responde a una solicitud de exhibición de documentos electrónicos basada en los metadatos de los archivos **Results.csv** o **Unindexed Items.csv,** puede usar una búsqueda de lista de identificadores para buscar, obtener una vista previa y exportar ese elemento para determinar si responde al caso que está investigando. Las búsquedas de lista de identificadores se suelen usar para buscar y devolver un conjunto específico de elementos no indexados.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Preparar el archivo CSV para una búsqueda de lista de identificadores

Después de exportar los resultados de la búsqueda o el informe de una búsqueda de contenido, puede realizar los siguientes pasos para preparar el archivo CSV para una búsqueda de lista de identificadores. Este archivo CSV identificará todos los elementos de la búsqueda de la lista de identificadores.

Tenga en cuenta que puede usar un archivo CSV de una búsqueda que  incluye sitios de SharePoint y cuentas de OneDrive, pero solo puede seleccionar elementos de buzón para una búsqueda de lista de identificadores. Si selecciona un documento en SharePoint o OneDrive, el archivo CSV no pasará la validación al crear una búsqueda de lista de identificadores.

1. Abra el **archivoResults.csv** **o Unindexed Items.csv** en Excel.

2. En la **columna Seleccionada,** escriba **Sí** en la celda que corresponda al elemento que desea buscar. Repita este paso para cada elemento que desee buscar.

    > [!IMPORTANT]
    > Al abrir el archivo CSV en Excel, el formato de datos de la columna **Id.** de documento se cambia a **General**. Esto da como resultado mostrar el identificador de documento de un elemento en la notación científica. Por ejemplo, el identificador de documento de "481037338205" se muestra como "4.81037E+11" Debe  realizar los pasos siguientes para cambiar el formato de datos de la columna Id. de documento a **Número** para restaurar el formato correcto para el identificador del documento. Si no lo hace, se producirá un error en la búsqueda de la lista de identificadores que usa el archivo CSV.

3. Haga clic con el botón secundario en toda **la columna Id.** de documento y seleccione **Formato de celdas**.

4. En el **cuadro** Categoría, haga clic en **Número**.

5. Cambie el número de posiciones decimales a **0** y, a continuación, haga clic en **Aceptar** para guardar los cambios. Observe que los valores de la columna Id. de documento se cambian a números.

    Este es un ejemplo del archivo CSV que está listo para enviarse para una búsqueda de contenido de lista de identificadores.

    ![Ejemplo de un archivo CSV para una búsqueda de contenido de destino](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. Guarde el archivo CSV o use **Guardar como** para guardar el archivo con un nombre de archivo diferente. En ambos casos, asegúrese de guardar el archivo con el formato CSV.

## <a name="create-an-id-list-search"></a>Crear una búsqueda de lista de identificadores

El siguiente paso es crear una nueva búsqueda de contenido de lista de identificadores y enviar el archivo CSV que preparó en el paso anterior.

> [!IMPORTANT]
> Debe crear una búsqueda de lista de identificadores no más de 2 días después de exportar los resultados o informes de una búsqueda de contenido. Si los resultados de la búsqueda o el informe donde se exportaron hace más de 2 días, debe volver a exportar los resultados de la búsqueda o el informe para generar archivos CSV actualizados. A continuación, puede preparar uno de los archivos CSV actualizados y usarlo para crear una búsqueda de lista de identificadores.

1. En el Centro de & cumplimiento, vaya **a** Búsqueda \> **de contenido.**

2. En la **página Buscar,** haga clic en la flecha junto a Agregar icono Nueva búsqueda y, a continuación, haga clic ![ en Buscar por lista de ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)  **identificadores.**

    ![Haga clic en Buscar por lista de identificadores en la lista desplegable Nueva búsqueda](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. En **el** menú desplegable Buscar por lista de identificadores, asigne  un nombre a la búsqueda (y, opcionalmente, descríbala) y, a continuación, haga clic en Examinar y seleccione el archivo CSV que preparó en el paso anterior.

    Microsoft 365 intenta validar el archivo CSV. Si la validación no se realiza correctamente, se muestra un mensaje de error que puede ayudarle a solucionar los errores de validación. El archivo CSV debe validarse correctamente para crear una búsqueda de lista de identificadores.

4. Después de validar correctamente el archivo CSV, haga clic en **Buscar** para crear la búsqueda de la lista de identificadores.

    Este es un ejemplo de los resultados de búsqueda estimados y la consulta que se genera para una búsqueda de lista de identificadores.

    ![Consulta de búsqueda para una búsqueda de contenido de destino en el panel de detalles](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    Tenga en cuenta que el número de elementos estimados que se muestran en las estadísticas para la búsqueda de id. debe coincidir con el número de elementos que seleccionó en el archivo CSV.

5. Obtenga una vista previa o exporte los elementos devueltos por la búsqueda de la lista de identificadores.

> [!NOTE]
> Si mueve un buzón después de crear una búsqueda de lista de identificadores, la consulta de la búsqueda no devolverá los elementos especificados. Esto se debe a que la **propiedad DocumentId** de los elementos del buzón se cambia cuando se mueve un buzón. En el caso poco frecuente cuando se mueve un buzón después de crear una búsqueda de lista de identificadores, debe crear una nueva búsqueda de contenido (o actualizar los resultados de búsqueda para la búsqueda de contenido existente) y, a continuación, exportar los resultados de la búsqueda o el informe para generar archivos CSV actualizados que se pueden usar para crear una nueva búsqueda de lista de identificadores.
