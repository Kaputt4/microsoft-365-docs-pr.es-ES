---
title: Agregar orígenes de datos sin custodia a un Advanced eDiscovery caso
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
description: Puede agregar orígenes de datos que no son custodiados a Advanced eDiscovery caso y colocar una retención en el origen de datos. Los orígenes de datos que no son custodiados se reindexa, por lo que cualquier contenido que se marcó como parcialmente indizado se vuelve a procesar para que pueda realizar búsquedas de forma completa y rápida.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740357"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="95490-104">Agregar orígenes de datos sin custodia a un Advanced eDiscovery caso</span><span class="sxs-lookup"><span data-stu-id="95490-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="95490-105">En Advanced eDiscovery casos, no siempre satisface sus necesidades para asociar un origen de datos Microsoft 365 a un administrador en el caso.</span><span class="sxs-lookup"><span data-stu-id="95490-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="95490-106">Sin embargo, es posible que deba asociar los datos con un caso para poder buscarlos, agregarlos a un conjunto de revisión y analizarlos y revisarlos.</span><span class="sxs-lookup"><span data-stu-id="95490-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="95490-107">La característica de Advanced eDiscovery se  denomina orígenes de datos sin custodia y le permite agregar datos a un caso sin tener que asociarlos a un administrador.</span><span class="sxs-lookup"><span data-stu-id="95490-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="95490-108">También aplica la misma funcionalidad de Advanced eDiscovery a los datos que no son custodia que están disponibles para los datos asociados con el administrador.</span><span class="sxs-lookup"><span data-stu-id="95490-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="95490-109">Dos de las cosas más útiles que puede aplicar a los datos que no son custodia es colocarlos en espera y procesarlos mediante [la indización avanzada](indexing-custodian-data.md).</span><span class="sxs-lookup"><span data-stu-id="95490-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="95490-110">Agregar un origen de datos sin custodia</span><span class="sxs-lookup"><span data-stu-id="95490-110">Add a non-custodial data source</span></span>

<span data-ttu-id="95490-111">Siga estos pasos para agregar y administrar orígenes de datos sin custodia en un Advanced eDiscovery caso.</span><span class="sxs-lookup"><span data-stu-id="95490-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="95490-112">En la **Advanced eDiscovery** principal, haga clic en el caso al que desea agregar los datos.</span><span class="sxs-lookup"><span data-stu-id="95490-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="95490-113">Haga clic en **la pestaña Orígenes de** datos y, a continuación, haga clic en Agregar origen de **datos** Agregar ubicaciones  >  **de datos**.</span><span class="sxs-lookup"><span data-stu-id="95490-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="95490-114">En la **página desplegable Nuevas ubicaciones** de datos no custodiales, elija los orígenes de datos que desea agregar al caso.</span><span class="sxs-lookup"><span data-stu-id="95490-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="95490-115">Puede agregar varios buzones y sitios  expandiendo las secciones SharePoint o **Exchange** y, a continuación, haciendo clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="95490-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Agregar SharePoint sitios y Exchange buzones de correo como orígenes de datos sin custodia](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="95490-117">**SharePoint:** haga clic **en Editar** para agregar sitios.</span><span class="sxs-lookup"><span data-stu-id="95490-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="95490-118">Seleccione un sitio en la lista o puede buscar un sitio escribiendo la dirección URL del sitio en la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="95490-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="95490-119">Seleccione los sitios que desea agregar como orígenes de datos que no son custodios y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="95490-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="95490-120">**Exchange:** haga clic **en Editar** para agregar buzones.</span><span class="sxs-lookup"><span data-stu-id="95490-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="95490-121">Escriba un nombre o alias (un mínimo de tres caracteres) en el cuadro de búsqueda de buzones o grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="95490-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="95490-122">Seleccione los buzones que desea agregar como orígenes de datos no custodios y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="95490-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="95490-123">Puede usar las secciones **SharePoint** y **Exchange** para agregar sitios y buzones asociados con un grupo de servidores o Yammer como orígenes de datos sin custodia.</span><span class="sxs-lookup"><span data-stu-id="95490-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="95490-124">Debe agregar por separado el buzón y el sitio asociados con un grupo de Yammer grupo.</span><span class="sxs-lookup"><span data-stu-id="95490-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="95490-125">Después de agregar orígenes de datos sin custodia, tiene la opción de poner esas ubicaciones en espera o no.</span><span class="sxs-lookup"><span data-stu-id="95490-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="95490-126">Active o anule la selección **de la casilla De** retención situada junto al origen de datos para colocarla en espera.</span><span class="sxs-lookup"><span data-stu-id="95490-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="95490-127">Haga **clic en** Agregar en la parte inferior de la página desplegable Nuevas ubicaciones de datos no **custodiales** para agregar los orígenes de datos al caso.</span><span class="sxs-lookup"><span data-stu-id="95490-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="95490-128">Cada origen de datos no custodiado que agregó aparece en la **página Orígenes de** datos.</span><span class="sxs-lookup"><span data-stu-id="95490-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="95490-129">Los orígenes de datos que no son custodiados se identifican mediante el **valor Ubicación de** datos en la columna Tipo **de** origen.</span><span class="sxs-lookup"><span data-stu-id="95490-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Orígenes de datos no custodiados en la pestaña Orígenes de datos](../media/NonCustodialDataSources2.png)

<span data-ttu-id="95490-131">Después de agregar orígenes de datos no custodiales al caso, se crea un trabajo denominado  *Reindexing non-custodial data* y se muestra en la pestaña Trabajos del caso.</span><span class="sxs-lookup"><span data-stu-id="95490-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="95490-132">Una vez creado el trabajo, se inicia el proceso de indización avanzada y se vuelve a indizar los orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="95490-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="95490-133">Administrar la retención de orígenes de datos sin custodia</span><span class="sxs-lookup"><span data-stu-id="95490-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="95490-134">Después de realizar una retención en un origen de datos sin custodia, se crea automáticamente una directiva de retención que contiene los orígenes de datos sin custodia para el caso.</span><span class="sxs-lookup"><span data-stu-id="95490-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="95490-135">Al poner otros orígenes de datos no custodiados en espera, se agregan a esta directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="95490-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="95490-136">Abra el Advanced eDiscovery y seleccione la **pestaña** Retención.</span><span class="sxs-lookup"><span data-stu-id="95490-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="95490-137">Haga **clic en \<GUID\> NCDSHold-**, donde el valor GUID es único para el caso.</span><span class="sxs-lookup"><span data-stu-id="95490-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="95490-138">La página desplegable muestra información y estadísticas sobre los orígenes de datos no custodiados en espera.</span><span class="sxs-lookup"><span data-stu-id="95490-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![La página desplegable para la retención de orígenes de datos no custodiados muestra estadísticas](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="95490-140">Haga **clic en** Editar retención para ver los orígenes de datos que no son custodiados y realizar las siguientes tareas de administración:</span><span class="sxs-lookup"><span data-stu-id="95490-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="95490-141">En la **página** Ubicaciones, puede liberar un origen de datos sin custodia quitándoselo de la retención.</span><span class="sxs-lookup"><span data-stu-id="95490-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="95490-142">Liberar un origen de datos no quita el origen de datos que no es custodia del caso.</span><span class="sxs-lookup"><span data-stu-id="95490-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="95490-143">Solo quita la retención que se colocó en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="95490-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="95490-144">En la **página** Consulta, puede editar la retención para crear una retención basada en consultas que se aplique a todos los orígenes de datos que no son custodia en el caso.</span><span class="sxs-lookup"><span data-stu-id="95490-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
