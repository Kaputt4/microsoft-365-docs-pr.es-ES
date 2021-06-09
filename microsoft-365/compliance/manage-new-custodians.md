---
title: Administrar custodios en un Advanced eDiscovery caso
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
description: Obtenga información sobre cómo ver detalles, editar y editar en masa la lista de custodios en un Advanced eDiscovery caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739873"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="6b605-103">Administrar custodios en un Advanced eDiscovery caso</span><span class="sxs-lookup"><span data-stu-id="6b605-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="6b605-104">La página Custodios de la pestaña Orígenes de un caso Advanced eDiscovery contiene una lista de todos los custodios que se han agregado al caso. </span><span class="sxs-lookup"><span data-stu-id="6b605-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="6b605-105">Después de agregar custodios a un caso, los detalles sobre cada custodio se recopilan automáticamente desde Azure Active Directory y se pueden ver en Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6b605-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Administrar custodios](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="6b605-107">Ver detalles del custodio</span><span class="sxs-lookup"><span data-stu-id="6b605-107">View custodian details</span></span>

<span data-ttu-id="6b605-108">Para ver los detalles sobre un custodio, haga clic en el custodio de la lista de la pestaña **Custodios.** Se muestra una página desplegable que contiene la siguiente información sobre el custodio:</span><span class="sxs-lookup"><span data-stu-id="6b605-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="6b605-109">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="6b605-109">Contact information</span></span>

  - <span data-ttu-id="6b605-110">**Nombre para mostrar:** el nombre que se muestra en la libreta de direcciones del custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="6b605-111">Esta suele ser la combinación del nombre, la inicial central y el apellido del custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="6b605-112">**Mail/SMTP:** la dirección SMTP principal del custodio, por ejemplo, brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="6b605-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="6b605-113">También se muestra el nombre principal de usuario (UPN) del custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="6b605-114">**Título:** título del trabajo del custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="6b605-115">**Departamento:** nombre del departamento en el que trabaja el custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="6b605-116">**Administrador:** administrador del custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="6b605-117">El administrador designado recibirá cualquier comunicación de escalamiento para este custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="6b605-118">Información de ubicación</span><span class="sxs-lookup"><span data-stu-id="6b605-118">Location information</span></span>

  - <span data-ttu-id="6b605-119">**Ciudad:** la ciudad en la que se encuentra el custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="6b605-120">**Estado:** el estado o la provincia en la dirección del custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="6b605-121">**País o región:** el país o región donde se encuentra el custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="6b605-122">**Office:** la ubicación de la oficina en el lugar de negocios del custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="6b605-123">Información del caso</span><span class="sxs-lookup"><span data-stu-id="6b605-123">Case information</span></span>

  - <span data-ttu-id="6b605-124">**Estado de** retención: indica si el custodio se ha puesto en espera.</span><span class="sxs-lookup"><span data-stu-id="6b605-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="6b605-125">**Estado de la** comunicación: indica si se ha emitido un aviso de retención al custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="6b605-126">Si se ha emitido un aviso al custodio, este valor de esta propiedad **se publica**.</span><span class="sxs-lookup"><span data-stu-id="6b605-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="6b605-127">Si no se ha emitido un aviso al custodio, el estado **es Un-published**.</span><span class="sxs-lookup"><span data-stu-id="6b605-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="6b605-128">**Status:** el estado del custodio dentro del caso.</span><span class="sxs-lookup"><span data-stu-id="6b605-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="6b605-129">Un estado **de Active** indica que el custodio forma parte del caso.</span><span class="sxs-lookup"><span data-stu-id="6b605-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="6b605-130">Si un custodio se libera de un caso, el estado cambia a **Liberado**.</span><span class="sxs-lookup"><span data-stu-id="6b605-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="6b605-131">Orígenes de datos e información de indización</span><span class="sxs-lookup"><span data-stu-id="6b605-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="6b605-132">**Orígenes de** datos: muestra el recuento y el tipo de orígenes de datos (buzones, sitios y Teams) que están asociados con el custodio y forman parte del caso.</span><span class="sxs-lookup"><span data-stu-id="6b605-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="6b605-133">**Hora de actualización del índice:** indica la hora y la fecha de la última vez que se desencadenó el trabajo de indización avanzada.</span><span class="sxs-lookup"><span data-stu-id="6b605-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="6b605-134">Esta propiedad también indicará cuándo está en curso el proceso de indización avanzado.</span><span class="sxs-lookup"><span data-stu-id="6b605-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="6b605-135">Editar un custodio</span><span class="sxs-lookup"><span data-stu-id="6b605-135">Edit a custodian</span></span>

<span data-ttu-id="6b605-136">A medida que avanza el caso, puede descubrir que puede haber orígenes de datos adicionales relevantes para un administrador específico & caso.</span><span class="sxs-lookup"><span data-stu-id="6b605-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="6b605-137">En otros escenarios, es posible que desee quitar determinados orígenes de datos que se han revisado y que se consideran no relevantes.</span><span class="sxs-lookup"><span data-stu-id="6b605-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="6b605-138">Para actualizar los orígenes de datos asociados con un custodio:</span><span class="sxs-lookup"><span data-stu-id="6b605-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="6b605-139">Vaya a **eDiscovery > Advanced eDiscovery** y abra el caso.</span><span class="sxs-lookup"><span data-stu-id="6b605-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="6b605-140">Haga clic en **la pestaña** Orígenes.</span><span class="sxs-lookup"><span data-stu-id="6b605-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="6b605-141">En la **página Custodios,** seleccione un custodio de la lista y haga clic **en Editar** en la página desplegable.</span><span class="sxs-lookup"><span data-stu-id="6b605-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Editar orígenes de datos](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="6b605-143">Haga **clic en La pestaña** Elegir orígenes de datos para cambiar la configuración del buzón de Exchange y la cuenta OneDrive, haga clic en Elegir orígenes de **datos**.</span><span class="sxs-lookup"><span data-stu-id="6b605-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="6b605-144">Haga clic **en** la pestaña Seleccionar orígenes de datos adicionales para agregar o quitar Teams, SharePoint o Exchange buzones asociados con el custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="6b605-145">Para obtener más información acerca de los orígenes de datos asociados con un custodio, vea [Agregar custodios a un caso](add-custodians-to-case.md).</span><span class="sxs-lookup"><span data-stu-id="6b605-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="6b605-146">Haga **clic en Colocar retenciones de custodia** para habilitar o deshabilitar la retención del custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="6b605-147">Volver a indizar los datos de custodia</span><span class="sxs-lookup"><span data-stu-id="6b605-147">Re-index custodian data</span></span>

<span data-ttu-id="6b605-148">En la mayoría de los flujos de trabajo de exhibición de documentos electrónicos para investigaciones legales, se busca un subconjunto de datos de un custodio después de agregarlo a un caso legal.</span><span class="sxs-lookup"><span data-stu-id="6b605-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="6b605-149">Debido a tamaños de archivo muy grandes o posibles daños en los datos, es posible que algunos elementos de los orígenes de datos asociados con un custodio se indexe parcialmente.</span><span class="sxs-lookup"><span data-stu-id="6b605-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="6b605-150">Con la [funcionalidad de indización](indexing-custodian-data.md) avanzada en el Advanced eDiscovery, la mayoría de los elementos parcialmente indizados se pueden corregir automáticamente al volver a indizar estos elementos a petición.</span><span class="sxs-lookup"><span data-stu-id="6b605-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="6b605-151">Cuando se agrega un custodio a un caso, los datos ubicados en los orígenes de datos asociados con el custodio se indizan automáticamente (mediante el proceso de indización avanzado).</span><span class="sxs-lookup"><span data-stu-id="6b605-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="6b605-152">Esto significa que puede dejar los datos en su lugar en lugar de tener que descargarlos y corregirlos y, a continuación, buscarlos sin conexión).</span><span class="sxs-lookup"><span data-stu-id="6b605-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="6b605-153">Sin embargo, durante el ciclo de vida de un caso legal, los nuevos orígenes de datos podrían asociarse con un custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="6b605-154">En este caso, puede volver a indizar los datos del custodio al volver a ejecutar el proceso de indización avanzada para corregir los elementos parcialmente indizados y actualizar el índice de los datos del custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="6b605-155">Para desencadenar el proceso de re indexación para que se alome a elementos parcialmente indizados:</span><span class="sxs-lookup"><span data-stu-id="6b605-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="6b605-156">Vaya a **eDiscovery > Advanced eDiscovery** y abra el caso.</span><span class="sxs-lookup"><span data-stu-id="6b605-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="6b605-157">Haga clic en **la pestaña** Orígenes.</span><span class="sxs-lookup"><span data-stu-id="6b605-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="6b605-158">En la **página Custodios,** seleccione un custodio cuyos datos deben volver a indizarse.</span><span class="sxs-lookup"><span data-stu-id="6b605-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="6b605-159">En la página desplegable, haga clic **en Actualizar índice**.</span><span class="sxs-lookup"><span data-stu-id="6b605-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="6b605-160">Se muestra un cuadro de diálogo que dice que se ha creado el trabajo de índice.</span><span class="sxs-lookup"><span data-stu-id="6b605-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="6b605-161">Volver a indizar los datos de custodia es un proceso de larga ejecución; el trabajo correspondiente que se crea se denomina **Re-indexing custodian data**.</span><span class="sxs-lookup"><span data-stu-id="6b605-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="6b605-162">Puede realizar un seguimiento del progreso en **la** pestaña Trabajos o en la pestaña **Custodios** supervisando el estado en la columna Estado del trabajo **de indización.**</span><span class="sxs-lookup"><span data-stu-id="6b605-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="6b605-163">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="6b605-163">For more information, see:</span></span>

- [<span data-ttu-id="6b605-164">Trabajar con errores de proceso</span><span class="sxs-lookup"><span data-stu-id="6b605-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="6b605-165">Administrar trabajos</span><span class="sxs-lookup"><span data-stu-id="6b605-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="6b605-166">Liberar a un custodio de un caso</span><span class="sxs-lookup"><span data-stu-id="6b605-166">Release a custodian from a case</span></span>

<span data-ttu-id="6b605-167">Un custodio se libera en situaciones en las que se cierra un caso, el custodio ya no tiene la obligación de conservar el contenido de un caso o cuando se considera que el custodio ya no es relevante para el caso.</span><span class="sxs-lookup"><span data-stu-id="6b605-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="6b605-168">Si libera a un custodio después de publicar un aviso de retención, se enviará un aviso de liberación al custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="6b605-169">Además, se quitan las retenciones realizadas en orígenes de datos asociados con el custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="6b605-170">Si el custodio se colocó en una retención silenciosa *,* donde no se emitieron notificaciones de retención legal, no se enviará un aviso de liberación, pero se quitarán las retenciones de los orígenes de datos asociados con ese custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="6b605-171">Para liberar a un custodio:</span><span class="sxs-lookup"><span data-stu-id="6b605-171">To release a custodian:</span></span> 

1. <span data-ttu-id="6b605-172">Vaya a **eDiscovery > Advanced eDiscovery** y abra el caso.</span><span class="sxs-lookup"><span data-stu-id="6b605-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="6b605-173">Haga clic en **la pestaña** Orígenes.</span><span class="sxs-lookup"><span data-stu-id="6b605-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="6b605-174">En la **página Custodios** y, a continuación, seleccione el custodio que está siendo liberado del caso.</span><span class="sxs-lookup"><span data-stu-id="6b605-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="6b605-175">En la página desplegable, haga clic **en Liberar custodio**.</span><span class="sxs-lookup"><span data-stu-id="6b605-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="6b605-176">Se muestra una página de advertencia que explica que si se coloca una retención en un origen de datos asociado con el custodio, se eliminará la retención y se aplicará cualquier otra retención asociada con un caso Advanced eDiscovery diferente.</span><span class="sxs-lookup"><span data-stu-id="6b605-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="6b605-177">Esto incluye otros tipos de características de conservación y retención (como una Microsoft 365 de retención).</span><span class="sxs-lookup"><span data-stu-id="6b605-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="6b605-178">Haga **clic en** Sí para confirmar que desea liberar al custodio.</span><span class="sxs-lookup"><span data-stu-id="6b605-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="6b605-179">El estado de este usuario en la pestaña **Custodios** se establece en **Liberado** y el estado de retención en la página desplegable se cambia a **False**. </span><span class="sxs-lookup"><span data-stu-id="6b605-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="6b605-180">Un custodio puede estar implicado simultáneamente en varios casos legales.</span><span class="sxs-lookup"><span data-stu-id="6b605-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="6b605-181">Cuando un custodio se libera de un caso, las retenciones y notificaciones en otros asuntos no se verán afectadas.</span><span class="sxs-lookup"><span data-stu-id="6b605-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="6b605-182">Custodios de edición masiva</span><span class="sxs-lookup"><span data-stu-id="6b605-182">Bulk-edit custodians</span></span>

<span data-ttu-id="6b605-183">Puede usar el editor en masa para editar varios custodios a la vez.</span><span class="sxs-lookup"><span data-stu-id="6b605-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="6b605-184">Para ello, solo tiene que seleccionar dos o más custodios en la pestaña **Custodios** para mostrar el editor en masa y, a continuación, haga clic en una de las tareas.</span><span class="sxs-lookup"><span data-stu-id="6b605-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Página desplegable para editar la configuración de varios custodios](../media/AeDBulkEditCustodians.png)
