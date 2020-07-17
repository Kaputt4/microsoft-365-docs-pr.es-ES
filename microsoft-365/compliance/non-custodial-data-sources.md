---
title: Agregar orígenes de datos que no sean de Private a un caso de exhibición avanzada de documentos electrónicos
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
description: Puede Agregar orígenes de datos que no sean de Private a un caso de exhibición avanzada de documentos electrónicos y poner una retención en el origen de datos. Los orígenes de datos que no son de Private se reindizan, por lo que cualquier contenido que se considere como indizado parcialmente se reprocesa para que se pueda buscar de forma completa y rápida.
ms.openlocfilehash: 2009a8cc82dc9407e9871409e85cdcd321ea9bb0
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024750"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="3afba-104">Agregar orígenes de datos que no sean de Private a un caso de exhibición avanzada de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="3afba-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="3afba-105">En los casos de eDiscovery avanzado, no siempre satisface sus necesidades de asociar un origen de datos de Microsoft 365 con un custodio en el caso.</span><span class="sxs-lookup"><span data-stu-id="3afba-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="3afba-106">Pero es posible que tenga que asociar esos datos a un caso para que lo busque, agregue a un conjunto de revisión y lo revise.</span><span class="sxs-lookup"><span data-stu-id="3afba-106">But you may still need to associate that data with a case so that you search it, add it to review set, and review it.</span></span> <span data-ttu-id="3afba-107">La nueva característica denominada *orígenes de datos que no son de Private* permite agregar datos a un caso sin tener que asociar los datos a un custodio.</span><span class="sxs-lookup"><span data-stu-id="3afba-107">The new feature called *non-custodial data sources* lets you add data to a case without having to associate the data to a custodian.</span></span> <span data-ttu-id="3afba-108">También aplica la misma funcionalidad avanzada de exhibición de documentos electrónicos a los datos que no son de Private y que están disponibles para los datos asociados con custodio.</span><span class="sxs-lookup"><span data-stu-id="3afba-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="3afba-109">Dos de las características más útiles que se pueden aplicar a los datos que no son de Private son ponerla en suspensión y procesarla mediante una [indización avanzada](indexing-custodian-data.md).</span><span class="sxs-lookup"><span data-stu-id="3afba-109">Two of the most useful features that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="3afba-110">Agregar un origen de datos que no sea de privación</span><span class="sxs-lookup"><span data-stu-id="3afba-110">Add a non-custodial data source</span></span>

<span data-ttu-id="3afba-111">Siga estos pasos para agregar y administrar orígenes de datos que no sean de Private en un caso de exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="3afba-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="3afba-112">En la Página principal de **EDiscovery avanzado** , haga clic en el caso al que desea agregar los datos.</span><span class="sxs-lookup"><span data-stu-id="3afba-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="3afba-113">En la página **orígenes** , haga clic en la ficha **ubicaciones de datos** y, a continuación, haga clic en **Agregar ubicación de datos**.</span><span class="sxs-lookup"><span data-stu-id="3afba-113">On the **Sources** page, click the **Data locations** tab, and then click **Add data location**.</span></span>

3. <span data-ttu-id="3afba-114">Haga clic en **Agregar ubicación de datos** y elija los orígenes de datos que desea agregar al caso.</span><span class="sxs-lookup"><span data-stu-id="3afba-114">Click **Add data location** and choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="3afba-115">Puede agregar varios buzones y sitios.</span><span class="sxs-lookup"><span data-stu-id="3afba-115">You can add multiple mailboxes and sites.</span></span>

4. <span data-ttu-id="3afba-116">En la página **elegir ubicaciones** del asistente, agregue buzones o sitios (o ambos) como orígenes de datos que no son de privación al caso.</span><span class="sxs-lookup"><span data-stu-id="3afba-116">On the **Choose locations** page in the wizard, add mailboxes or sites (or both) as non-custodial data sources to the case.</span></span>

5. <span data-ttu-id="3afba-117">Después de agregar los orígenes de datos, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3afba-117">After adding the data sources, click **Next**.</span></span>

6. <span data-ttu-id="3afba-118">En la página **poner suspensiones** , elija los orígenes de datos que desea poner en espera activando o desactivando la casilla de verificación asociada.</span><span class="sxs-lookup"><span data-stu-id="3afba-118">On the **Place holds** page, choose which data sources you want to place on hold by selecting or unselecting the associated checkbox.</span></span>

7. <span data-ttu-id="3afba-119">Compruebe las selecciones de retención y, a continuación, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="3afba-119">Verify the hold selections and then click **Submit**.</span></span>

   <span data-ttu-id="3afba-120">Cada origen de datos no de Private que agregó aparece en la lista de la página de **orígenes de datos** .</span><span class="sxs-lookup"><span data-stu-id="3afba-120">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span>

   <span data-ttu-id="3afba-121">Además, se crea un trabajo llamado *reindizar datos que no son de Private* y se muestra en la ficha **trabajos** del caso.</span><span class="sxs-lookup"><span data-stu-id="3afba-121">Also, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="3afba-122">Una vez creado el trabajo, el proceso de indización avanzado en iniciado y los orígenes de datos se reindizan.</span><span class="sxs-lookup"><span data-stu-id="3afba-122">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="managing-the-hold-on-non-custodial-data-sources"></a><span data-ttu-id="3afba-123">Administración de la retención en orígenes de datos que no son de Private</span><span class="sxs-lookup"><span data-stu-id="3afba-123">Managing the hold on non-custodial data sources</span></span>

<span data-ttu-id="3afba-124">Después de poner una retención en un origen de datos que no sea de Private, se creará automáticamente una directiva de retención que contenga todos los orígenes de datos que no sean de privación para el caso.</span><span class="sxs-lookup"><span data-stu-id="3afba-124">After you place a hold on a non-custodial data source, a hold policy that contains all non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="3afba-125">Cuando se colocan orígenes de datos adicionales que no son de conservación, se agregan a esta directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="3afba-125">When you place additional non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="3afba-126">En la página **principal** del caso, haga clic en la pestaña **suspensiones** .</span><span class="sxs-lookup"><span data-stu-id="3afba-126">On the **Home** page of the case, click the **Holds** tab.</span></span>

2. <span data-ttu-id="3afba-127">En la página **suspensiones** , haga clic en \*\*NCDSHold- \<GUID\> \*\*, donde el valor de GUID es único en el caso.</span><span class="sxs-lookup"><span data-stu-id="3afba-127">On the **Holds** page, and click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

3. <span data-ttu-id="3afba-128">En la página de flotante, haga clic en **Editar suspensión** para ver todos los orígenes de datos que no son de Private que se encuentran en suspensión.</span><span class="sxs-lookup"><span data-stu-id="3afba-128">On the flyout page, click **Edit hold** to view all the non-custodial data sources that are placed on hold.</span></span>

<span data-ttu-id="3afba-129">Puede realizar la siguiente tarea de administración en orígenes de datos que no sean de Private:</span><span class="sxs-lookup"><span data-stu-id="3afba-129">You can perform the following management task on non-custodial data sources:</span></span>

- <span data-ttu-id="3afba-130">Puede editar la retención para crear una suspensión basada en consulta que se aplique a todos los orígenes de datos que no sean de Private en el caso.</span><span class="sxs-lookup"><span data-stu-id="3afba-130">You can edit the hold to create a query-based hold that is applied to all non-custodial data sources in the case.</span></span>

- <span data-ttu-id="3afba-131">Puede liberar un origen de datos que no sea de privación de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="3afba-131">You can release a non-custodial data source from the hold.</span></span> <span data-ttu-id="3afba-132">Al liberar un origen de datos, no se quita del caso el origen de datos que no es de tipo Private.</span><span class="sxs-lookup"><span data-stu-id="3afba-132">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="3afba-133">Solo quita la retención que se colocó en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3afba-133">It only removes the hold that was placed on the data source.</span></span>
