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
description: Use un archivo CSV de una búsqueda de contenido existente para crear una búsqueda de lista de identificadores que devuelva elementos de correo electrónico específicos.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311557"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="c513b-103">Preparar un archivo CSV para una búsqueda de contenido de lista de identificadores</span><span class="sxs-lookup"><span data-stu-id="c513b-103">Prepare a CSV file for an ID list Content search</span></span>

<span data-ttu-id="c513b-104">Puede buscar mensajes de correo electrónico de buzones de correo específicos y otros elementos de buzón mediante una lista de Exchange de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c513b-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="c513b-105">Para crear una búsqueda por lista de id., debe enviar un archivo CSV que identifique los elementos de buzón específicos que desee buscar.</span><span class="sxs-lookup"><span data-stu-id="c513b-105">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="c513b-106">Para este archivo CSV, se usa el archivo **Results.csv** o el archivo **Items.csv** sin indizar que se incluyen al exportar los resultados de búsqueda de contenido o exportar un informe de búsqueda de contenido de una búsqueda de contenido existente.</span><span class="sxs-lookup"><span data-stu-id="c513b-106">For this CSV file, you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content search results or export a Content search report from an existing Content search.</span></span> <span data-ttu-id="c513b-107">A continuación, edite uno de estos archivos para indicar los elementos específicos que se buscarán, cree una nueva búsqueda de lista de identificadores y envíe el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c513b-107">Then you edit one of these files to indicate the specific items to search for, create a new ID list search, and submit the CSV file.</span></span>

<span data-ttu-id="c513b-108">**¿Por qué crear una búsqueda de lista de identificadores?**</span><span class="sxs-lookup"><span data-stu-id="c513b-108">**Why create an ID list search?**</span></span> <span data-ttu-id="c513b-109">Si no puede determinar si un elemento responde a una solicitud de exhibición de documentos electrónicos en función de los metadatos de los archivos **Items.csv** o **Results.csv** sin indizar, puede usar una búsqueda de lista de identificadores para buscar, obtener una vista previa y exportar ese elemento para determinar si responde al caso que está investigando.</span><span class="sxs-lookup"><span data-stu-id="c513b-109">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="c513b-110">Las búsquedas de lista de identificadores se suelen usar para buscar y devolver un conjunto específico de elementos sin indizar.</span><span class="sxs-lookup"><span data-stu-id="c513b-110">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

<span data-ttu-id="c513b-111">Este es un resumen rápido del proceso para crear una búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-111">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="c513b-112">Cree y ejecute una nueva búsqueda en el centro Microsoft 365 cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c513b-112">Create and run a new search in the Microsoft 365 compliance center.</span></span>

2. <span data-ttu-id="c513b-113">Exporte los resultados de búsqueda de contenido o el informe de búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="c513b-113">Export the content search results or the content search report.</span></span> <span data-ttu-id="c513b-114">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="c513b-114">For more information, see:</span></span>

    - [<span data-ttu-id="c513b-115">Exportar resultados de la búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="c513b-115">Export Content search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="c513b-116">Exportar un informe de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="c513b-116">Export a Content search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="c513b-117">Edite **elResults.csv** o archivo **de** Items.csvsin indizar e identifique los elementos de buzón específicos que se incluirán en la búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-117">Edit the **Results.csv** file or **Unindexed Items.csv** file and identify the specific mailbox items to include in the ID list search.</span></span> <span data-ttu-id="c513b-118">Consulta las [instrucciones para](#prepare-the-csv-file-for-an-id-list-search) preparar un archivo CSV para una búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-118">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="c513b-119">Cree una nueva búsqueda de lista de identificadores (vea las [instrucciones)](#create-an-id-list-search)y envíe el archivo CSV que preparó.</span><span class="sxs-lookup"><span data-stu-id="c513b-119">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="c513b-120">La consulta de búsqueda creada solo buscará los elementos seleccionados en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c513b-120">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="c513b-121">Las búsquedas de lista de identificadores solo se admiten para elementos de buzón.</span><span class="sxs-lookup"><span data-stu-id="c513b-121">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="c513b-122">No puede buscar documentos SharePoint y OneDrive en una búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-122">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="c513b-123">Preparar el archivo CSV para una búsqueda de lista de identificadores</span><span class="sxs-lookup"><span data-stu-id="c513b-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="c513b-124">Después de exportar los resultados de búsqueda o el informe de una búsqueda, siga estos pasos para preparar el archivo CSV para una búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-124">After you export the search results or report for a search, perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="c513b-125">Este archivo CSV identifica todos los elementos de la búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-125">This CSV file identifies every item in the ID list search.</span></span>

<span data-ttu-id="c513b-126">Puede usar un archivo CSV de una búsqueda que incluye sitios SharePoint y cuentas OneDrive, pero solo puede seleccionar elementos de buzón para una búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-126">You can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can only select mailbox items for an ID list search.</span></span> <span data-ttu-id="c513b-127">Si selecciona un documento en SharePoint o OneDrive, el archivo CSV producirá un error de validación al crear una búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="c513b-128">Abra el **archivoResults.csv** **o Unindexed Items.csv** en Excel.</span><span class="sxs-lookup"><span data-stu-id="c513b-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="c513b-129">En la **columna Seleccionada,** escriba **Sí** en la celda que corresponde al elemento que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="c513b-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="c513b-130">Repita este paso para cada elemento que desee buscar.</span><span class="sxs-lookup"><span data-stu-id="c513b-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c513b-131">Al abrir el archivo CSV en Excel, es posible que el formato de datos de la columna **Id.** de documento se haya cambiado a **General**.</span><span class="sxs-lookup"><span data-stu-id="c513b-131">When you open the CSV file in Excel, the data format for the **Document ID** column may have been changed to **General**.</span></span> <span data-ttu-id="c513b-132">Esto da como resultado mostrar el identificador de documento de un elemento en la notación científica.</span><span class="sxs-lookup"><span data-stu-id="c513b-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="c513b-133">Por ejemplo, el identificador de documento de "481037338205" se muestra como "4.81037E+11".</span><span class="sxs-lookup"><span data-stu-id="c513b-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11".</span></span> <span data-ttu-id="c513b-134">Si esto sucede, debe realizar los pasos siguientes para cambiar el formato de datos de la columna **Id.** de documento a **Número** para restaurar el formato correcto para el identificador del documento.</span><span class="sxs-lookup"><span data-stu-id="c513b-134">If this happens, you have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="c513b-135">Si no lo hace, se producirá un error en la búsqueda de la lista de identificadores que usa el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c513b-135">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="c513b-136">Haga clic con el botón secundario en toda **la columna Id. de** documento y seleccione Formato de **celdas**.</span><span class="sxs-lookup"><span data-stu-id="c513b-136">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="c513b-137">En el **cuadro Categoría,** haga clic en **Número**.</span><span class="sxs-lookup"><span data-stu-id="c513b-137">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="c513b-138">Cambie el número de decimales a **0** y, a continuación, haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="c513b-138">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="c513b-139">Observe que los valores de la columna Id. de documento se cambian a números.</span><span class="sxs-lookup"><span data-stu-id="c513b-139">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="c513b-140">Este es un ejemplo de un archivo CSV que está listo para enviarse para una búsqueda de contenido de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-140">Here's an example of a CSV file that's ready to be submitted for an ID list content search.</span></span>

    ![Ejemplo de un archivo CSV para una búsqueda de contenido de destino](../media/SearchIDListCSVFile.png)

6. <span data-ttu-id="c513b-142">Guarde el archivo CSV o use **Guardar como** para guardar el archivo con un nombre de archivo diferente.</span><span class="sxs-lookup"><span data-stu-id="c513b-142">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="c513b-143">En ambos casos, asegúrese de guardar el archivo con el formato CSV.</span><span class="sxs-lookup"><span data-stu-id="c513b-143">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="c513b-144">Crear una búsqueda de lista de identificadores</span><span class="sxs-lookup"><span data-stu-id="c513b-144">Create an ID list search</span></span>

<span data-ttu-id="c513b-145">El siguiente paso es crear una nueva búsqueda de lista de identificadores y enviar el archivo CSV que preparó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="c513b-145">The next step is to create a new ID list search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c513b-146">Debe crear una búsqueda de lista de identificadores no más de 2 días después de exportar los resultados o el informe de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c513b-146">You should create an ID list search no more than 2 days after exporting the search results or report.</span></span> <span data-ttu-id="c513b-147">Si los resultados de búsqueda o el informe donde se exportaron hace más de 2 días, debe volver a exportar los resultados de búsqueda o el informe para generar archivos CSV actualizados.</span><span class="sxs-lookup"><span data-stu-id="c513b-147">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="c513b-148">A continuación, puede preparar uno de los archivos CSV actualizados y usarlo para crear una búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-148">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="c513b-149">Vaya a <https://compliance.microsoft.com> e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="c513b-149">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="c513b-150">En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo** y, luego, seleccione **Búsqueda de contenido**.</span><span class="sxs-lookup"><span data-stu-id="c513b-150">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="c513b-151">En la **página Búsqueda de contenido,** haga clic **en Buscar por lista de identificadores.**</span><span class="sxs-lookup"><span data-stu-id="c513b-151">On the **Content search** page, click **Search by ID List**.</span></span>

4. <span data-ttu-id="c513b-152">En **el** menú desplegable Buscar por lista de identificadores, asigne  un nombre a la búsqueda (y, opcionalmente, describenla) y, a continuación, haga clic en Examinar y seleccione el archivo CSV que preparó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="c513b-152">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="c513b-153">Microsoft 365 intentos de validar el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c513b-153">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="c513b-154">Si la validación no se realiza correctamente, se muestra un mensaje de error que puede ayudarle a solucionar los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="c513b-154">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="c513b-155">El archivo CSV debe validarse correctamente para crear una búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-155">The CSV file has to be successfully validated to create an ID list search.</span></span>

5. <span data-ttu-id="c513b-156">Después de validar correctamente el archivo CSV, haga clic **en Buscar** para crear la búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-156">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="c513b-157">Este es un ejemplo de la página desplegable de una búsqueda de lista de identificadores que muestra la consulta generada y el número estimado de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c513b-157">Here's an example of the flyout page from an ID list search that shows the query that's generated and the estimated number of search results.</span></span>

    ![Consulta de búsqueda de búsqueda de lista de identificadores](../media/SearchIDListFlyout.png)

    <span data-ttu-id="c513b-159">El número de elementos estimados que se muestran en las estadísticas para la búsqueda de id. debe coincidir con el número de elementos seleccionados en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c513b-159">The number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

6. <span data-ttu-id="c513b-160">Obtenga una vista previa o exporte los elementos devueltos por la búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-160">Preview or export the items returned by the ID list search.</span></span>

## <a name="more-information"></a><span data-ttu-id="c513b-161">Más información</span><span class="sxs-lookup"><span data-stu-id="c513b-161">More information</span></span>

<span data-ttu-id="c513b-162">Si mueve un buzón después de crear una búsqueda de lista de identificadores, la consulta de la búsqueda no devolverá los elementos especificados.</span><span class="sxs-lookup"><span data-stu-id="c513b-162">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="c513b-163">Esto se debe a que la **propiedad DocumentId** de los elementos de buzón se cambia cuando se mueve un buzón.</span><span class="sxs-lookup"><span data-stu-id="c513b-163">That's because the **DocumentId** property for mailbox items is changed when a mailbox is moved.</span></span> <span data-ttu-id="c513b-164">En la rara instancia cuando se mueve un buzón después de crear una búsqueda de lista de identificadores, debe crear una nueva búsqueda de contenido (o actualizar los resultados de búsqueda de una búsqueda existente) y, a continuación, exportar los resultados o el informe de búsqueda para generar archivos CSV actualizados que se pueden usar para crear una nueva búsqueda de lista de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c513b-164">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new Content search (or update the search results for an existing search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
