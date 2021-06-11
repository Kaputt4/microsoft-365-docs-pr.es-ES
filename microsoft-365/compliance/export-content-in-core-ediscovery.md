---
title: Exportar y descargar contenido de un caso de exhibición de documentos electrónicos principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Describe cómo exportar y descargar contenido de un caso de exhibición de documentos electrónicos principal en Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310861"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="d1f1a-103">Exportar contenido desde un caso básico de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d1f1a-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="d1f1a-104">Después de ejecutar correctamente una búsqueda asociada a un caso de exhibición de documentos electrónicos principal, puede exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="d1f1a-105">Al exportar los resultados de la búsqueda, los elementos del buzón se descargan en archivos PST o como mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="d1f1a-106">Al exportar contenido de sitios SharePoint y OneDrive para la Empresa, se exportan copias de documentos Office documentos nativos y otros documentos.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="d1f1a-107">Un Results.csv que contiene información sobre cada elemento que se exporta y también se exporta un archivo de manifiesto (en formato XML) que contiene información sobre cada resultado de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="d1f1a-108">Exportar resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="d1f1a-108">Export search results</span></span>

1. <span data-ttu-id="d1f1a-109">Vaya a e inicie sesión con las credenciales de la cuenta de usuario a la que se han asignado los [https://compliance.microsoft.com](https://compliance.microsoft.com) permisos de exhibición de documentos electrónicos adecuados.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="d1f1a-110">En el panel de navegación izquierdo del centro de Microsoft 365 cumplimiento, haga clic en Mostrar todo **y,** a continuación, haga clic en **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="d1f1a-111">En la **página Exhibición de documentos electrónicos** principal, haga clic en el nombre del caso en el que desea crear la retención.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="d1f1a-112">En la **página principal** del caso, haga clic en la **pestaña** Búsquedas.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="d1f1a-113">En el **menú** Acciones de la parte inferior de la página desplegable, haga clic **en Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   ![Opción Exportar resultados en el menú Acciones](../media/ActionMenuExportResults.png)

   <span data-ttu-id="d1f1a-115">El flujo de trabajo para exportar los resultados de una búsqueda asociada a un caso de exhibición de documentos electrónicos principal es el mismo que exportar los resultados de búsqueda de una búsqueda en la página **Búsqueda de** contenido.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="d1f1a-116">Para obtener instrucciones paso a paso, vea [Exportar resultados de búsqueda de contenido](export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="d1f1a-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="d1f1a-117">Al exportar los resultados de búsqueda, tiene la opción de habilitar la desduplicación para que solo se exporte una copia de un mensaje de correo electrónico aunque se hayan encontrado varias instancias del mismo mensaje en los buzones de correo que se buscaron.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-117">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="d1f1a-118">Para obtener más información sobre la desduplicación y cómo se identifican los elementos duplicados, vea [Desduplicación en](de-duplication-in-ediscovery-search-results.md)los resultados de búsqueda de exhibición de documentos electrónicos .</span><span class="sxs-lookup"><span data-stu-id="d1f1a-118">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="d1f1a-119">Después de iniciar la exportación, los resultados de la búsqueda están preparados para su descarga, lo que significa que se transfieren a una ubicación Azure Storage proporcionada por Microsoft en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="d1f1a-120">Haga clic **en la pestaña** Exportaciones en el caso para mostrar la lista de trabajos de exportación.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![Exportar trabajos en la pestaña Exportar en el caso de exhibición de documentos electrónicos principales](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="d1f1a-122">Es posible que tenga que hacer clic **en Actualizar** para actualizar la lista de trabajos de exportación para que muestre el trabajo de exportación que creó.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="d1f1a-123">Los trabajos de exportación tienen el mismo nombre que la búsqueda correspondiente **_Export** anexado al nombre de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="d1f1a-124">Haga clic en el trabajo de exportación que creó para mostrar información de estado en la página desplegable.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="d1f1a-125">Esta información incluye el porcentaje de elementos que se han transferido a la Azure Storage ubicación.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="d1f1a-126">Después de transferir todos los elementos, haga clic en **Descargar resultados** para descargar los resultados de búsqueda en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="d1f1a-127">Para obtener más información sobre la descarga de resultados de búsqueda, vea el paso 2 en [Exportar resultados de búsqueda de contenido](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="d1f1a-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="d1f1a-128">Más información sobre cómo exportar búsquedas desde un caso</span><span class="sxs-lookup"><span data-stu-id="d1f1a-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="d1f1a-129">Para obtener más información acerca de los archivos de exportación que se incluyen al exportar resultados de búsqueda, vea [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="d1f1a-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="d1f1a-130">Si reinicia la exportación, los cambios en las consultas de las búsquedas que conste el trabajo de exportación no afectarán a los resultados de búsqueda que se recuperan.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="d1f1a-131">Al reiniciar una exportación, se volverá a ejecutar el mismo trabajo de consulta de búsqueda combinado que se ejecutaba cuando se creó el trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="d1f1a-132">Además, si reinicia una exportación, los resultados de búsqueda que se copian en la ubicación Azure Storage sobrescribe los resultados anteriores.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="d1f1a-133">Los resultados anteriores que se copiaron no estarán disponibles para su descarga.</span><span class="sxs-lookup"><span data-stu-id="d1f1a-133">The previous results that were copied won't be available to be downloaded.</span></span>
