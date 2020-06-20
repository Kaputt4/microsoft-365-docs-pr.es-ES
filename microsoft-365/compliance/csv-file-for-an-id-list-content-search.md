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
description: Use archivos CSV de una búsqueda de contenido existente para crear una búsqueda de lista de IDENTIFICADOres que devuelva mensajes de correo electrónico específicos.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817979"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>Preparar un archivo CSV para una búsqueda de contenido de lista de identificadores

Puede buscar mensajes de correo electrónico específicos de buzones de correo y otros elementos de buzón mediante una lista de identificadores de Exchange. Para crear una búsqueda de lista de IDENTIFICADOres (anteriormente denominada búsqueda dirigida), envíe un archivo de valores separados por comas (CSV) que identifique los elementos de buzón específicos que se van a buscar. Para este archivo CSV, use el archivo de **Results.csv** o el archivo no **indizado Items.csv** que se incluyen al exportar los resultados de la búsqueda de contenido o a exportar un informe de búsqueda de contenido desde y búsqueda de contenido existente. A continuación, edite uno de estos archivos para indicar los elementos específicos que se deben buscar y, a continuación, cree una nueva búsqueda de la lista de IDENTIFICADOres y envíe el archivo CSV.

A continuación se muestra una introducción rápida del proceso para crear una búsqueda de lista de IDENTIFICADOres.

1. Cree y ejecute una búsqueda de contenido nueva o guiada en el centro de seguridad & cumplimiento.

2. Exportar los resultados de la búsqueda de contenido o exportar el informe de búsqueda de contenido. Para obtener más información, vea:

    - [Exportar resultados de la búsqueda de contenido](export-search-results.md)

    - [Exportar un informe de búsqueda de contenido](export-a-content-search-report.md)

3. Edite el archivo de **Results.csv** o la **Items.csvsin indizar** e identifique los elementos de buzón específicos que desea incluir en la búsqueda de la lista de ID. Vea las [instrucciones](#prepare-the-csv-file-for-an-id-list-search) para preparar un archivo CSV para una búsqueda de lista de ID.

4. Crear una nueva búsqueda de la lista de IDENTIFICADOres (consulte las [instrucciones](#create-an-id-list-search)) y enviar el archivo CSV que preparó. La consulta de búsqueda que se crea solo buscará los elementos seleccionados en el archivo CSV.

> [!NOTE]
> Las búsquedas de listas de IDENTIFICADOres solo se admiten para elementos de buzón. No puede buscar documentos de SharePoint y OneDrive en una búsqueda de lista de ID.

 **¿Por qué crear una búsqueda de lista de IDENTIFICADOres?** Si no puede determinar si un elemento responde a una solicitud de exhibición de documentos electrónicos en función de los metadatos de los archivos de Items.csv**Results.csv** o sin **indexar** , puede usar una búsqueda de lista de identificadores para buscar, obtener una vista previa y, a continuación, exportar el elemento para determinar si responde al caso que está investigando. Las búsquedas de listas de IDENTIFICADOres se usan normalmente para buscar y devolver un conjunto específico de elementos sin indizar.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Preparar el archivo CSV para una búsqueda de lista de ID

Después de exportar los resultados de búsqueda o el informe para una búsqueda de contenido, puede realizar los siguientes pasos para preparar el archivo CSV para una búsqueda de lista de ID. Este archivo CSV identificará todos los elementos de la búsqueda de la lista de IDENTIFICADOres.

Tenga en cuenta que puede usar un archivo CSV desde una búsqueda que incluya sitios de SharePoint y cuentas de OneDrive, pero *solo* puede seleccionar elementos de buzón para una búsqueda de lista de ID. Si selecciona un documento en SharePoint o OneDrive, el archivo CSV no superará la validación cuando se crea una búsqueda de lista de ID.

1. Abra el archivo de Items.csv**Results.csv** o sin **indizar** en Excel.

2. En la columna **seleccionada** , escriba **yes** en la celda que corresponda al elemento que desea buscar. Repita este paso para cada elemento que desee buscar.

    > [!IMPORTANT]
    > Al abrir el archivo CSV en Excel, el formato de datos de la columna **identificador de documento** cambia a **General**. Esto da como resultado que se muestre el identificador de documento de un elemento en notación científica. Por ejemplo, el identificador de documento "481037338205" se muestra como "4.81037 E + 11" debe realizar los pasos siguientes para cambiar el formato de datos de la columna **identificador de documento** a **número** para restaurar el formato correcto para el identificador de documento. Si no lo hace, se producirá un error en la búsqueda de la lista de IDENTIFICADOres que usa el archivo CSV.

3. Haga clic con el botón secundario en la columna **identificador de documento** completo y seleccione **formato de celdas**.

4. En el cuadro **categoría** , haga clic en **número**.

5. Cambie el número de posiciones decimales a **0**y, a continuación, haga clic en **Aceptar** para guardar los cambios. Observe que los valores de la columna identificador de documento cambian a números.

    Este es un ejemplo del archivo CSV que está listo para enviarse para una búsqueda de contenido de la lista de IDENTIFICADOres.

    ![Ejemplo de un archivo CSV para una búsqueda de contenido de destino](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. Guarde el archivo CSV o use **Guardar como** para guardar el archivo con otro nombre de archivo. En ambos casos, asegúrese de guardar el archivo con el formato CSV.

## <a name="create-an-id-list-search"></a>Crear una búsqueda de lista de IDENTIFICADOres

El siguiente paso es crear una nueva búsqueda de contenido de la lista de IDENTIFICADOres y enviar el archivo CSV que preparó en el paso anterior.

> [!IMPORTANT]
> Debe crear una búsqueda de lista de IDENTIFICADOres de más de 2 días después de exportar los resultados o el informe de una búsqueda de contenido. Si los resultados de la búsqueda o el informe en el que se exportó hace más de 2 días, debe volver a exportar los resultados de la búsqueda o informar para generar archivos. CSV actualizados. A continuación, puede preparar uno de los archivos CSV actualizados y utilizarlo para crear una búsqueda de lista de ID.

1. En el centro de seguridad & cumplimiento, vaya a búsqueda de contenido de **búsqueda** \> **Content search**.

2. En la página **Buscar** , haga clic en la flecha junto a ![ Agregar icono ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nueva búsqueda**y, a continuación, haga clic en **Buscar por lista de identificadores**.

    ![Haga clic en buscar por lista de IDENTIFICADOres en la nueva lista desplegable de búsqueda](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. En el control flotante de la **lista Buscar por identificador** , asigne un nombre a la búsqueda (y, opcionalmente, describa) y, a continuación, haga clic en **examinar** y seleccione el archivo CSV que preparó en el paso anterior.

    Microsoft 365 intenta validar el archivo CSV. Si la validación no se realiza correctamente, se muestra un mensaje de error que puede ayudarle a solucionar los errores de validación. El archivo CSV tiene que validarse correctamente para crear una búsqueda de lista de ID.

4. Una vez validado correctamente el archivo CSV, haga clic en **Buscar** para crear la búsqueda de la lista de identificadores.

    Este es un ejemplo de los resultados de búsqueda estimados y la consulta que se genera para una búsqueda de lista de ID.

    ![Consulta de búsqueda para una búsqueda de contenido dirigida en el panel de detalles](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    Tenga en cuenta que el número de elementos estimados que se muestran en las estadísticas para la búsqueda ID debe coincidir con el número de elementos que seleccionó en el archivo CSV.

5. Obtenga una vista previa o exporte los elementos devueltos por la búsqueda de lista de ID.

> [!NOTE]
> Si mueve un buzón después de crear una búsqueda de lista de IDENTIFICADOres, la consulta de la búsqueda no devolverá los elementos especificados. Esto se debe a que la propiedad **DocumentId** para los elementos del buzón de correo se cambia cuando se mueve un buzón. En la instancia poco común, cuando un buzón se mueve después de crear una búsqueda de lista de IDENTIFICADOres, debe crear una nueva búsqueda de contenido (o actualizar los resultados de búsqueda para la búsqueda de contenido existente) y, a continuación, exportar los resultados de la búsqueda o el informe para generar archivos. CSV actualizados que se puedan usar para crear una nueva búsqueda de la lista de IDENTIFICADOres.
