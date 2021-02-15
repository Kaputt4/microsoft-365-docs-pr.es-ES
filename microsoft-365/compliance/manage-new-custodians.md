---
title: Administrar administradores en un caso de eDiscovery avanzado
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
description: Obtenga información sobre cómo ver detalles, editar y editar en masa la lista de administradores en un caso de eDiscovery avanzado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739873"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="fd672-103">Administrar administradores en un caso de eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="fd672-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="fd672-104">La página Administradores  de la pestaña Orígenes en un caso de eDiscovery avanzado contiene una lista de todos los administradores que se han agregado al caso.</span><span class="sxs-lookup"><span data-stu-id="fd672-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="fd672-105">Después de agregar administradores a un caso, los detalles sobre cada administrador se recopilan automáticamente desde Azure Active Directory y se pueden ver en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="fd672-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Administrar administradores](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="fd672-107">Ver detalles del administrador</span><span class="sxs-lookup"><span data-stu-id="fd672-107">View custodian details</span></span>

<span data-ttu-id="fd672-108">Para ver los detalles sobre un administrador, haga clic en el administrador de la lista en la **pestaña Administradores.** Se muestra una página desplegable que contiene la siguiente información sobre el administrador:</span><span class="sxs-lookup"><span data-stu-id="fd672-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="fd672-109">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="fd672-109">Contact information</span></span>

  - <span data-ttu-id="fd672-110">**Nombre para** mostrar: nombre que se muestra en la libreta de direcciones del administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="fd672-111">Suele ser la combinación del nombre del administrador, la inicial del segundo nombre y los apellidos.</span><span class="sxs-lookup"><span data-stu-id="fd672-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="fd672-112">**Correo/SMTP:** la dirección SMTP principal del administrador, por ejemplo, brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="fd672-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="fd672-113">También se muestra el nombre principal de usuario (UPN) del administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="fd672-114">**Título:** puesto del administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="fd672-115">**Departamento:** nombre del departamento en el que trabaja el administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="fd672-116">**Administrador:** administrador del administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="fd672-117">El administrador designado recibirá cualquier comunicación de escalamiento para este administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="fd672-118">Información de ubicación</span><span class="sxs-lookup"><span data-stu-id="fd672-118">Location information</span></span>

  - <span data-ttu-id="fd672-119">**Ciudad:** la ciudad en la que se encuentra el administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="fd672-120">**Estado:** el estado o la provincia en la dirección del administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="fd672-121">**País o región:** país o región donde se encuentra el administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="fd672-122">**Office:** la ubicación de la oficina en el lugar de trabajo del administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="fd672-123">Información de casos</span><span class="sxs-lookup"><span data-stu-id="fd672-123">Case information</span></span>

  - <span data-ttu-id="fd672-124">**Estado de retención:** indica si el administrador se ha puesto en retención.</span><span class="sxs-lookup"><span data-stu-id="fd672-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="fd672-125">**Estado de** comunicación: indica si se ha emitido un aviso de retención al administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="fd672-126">Si se ha emitido un aviso al administrador, este valor de esta propiedad **se publica.**</span><span class="sxs-lookup"><span data-stu-id="fd672-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="fd672-127">Si no se ha emitido un aviso al administrador, el estado es **No publicado.**</span><span class="sxs-lookup"><span data-stu-id="fd672-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="fd672-128">**Estado:** el estado del administrador dentro del caso.</span><span class="sxs-lookup"><span data-stu-id="fd672-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="fd672-129">Un estado **activo** indica que el administrador forma parte del caso.</span><span class="sxs-lookup"><span data-stu-id="fd672-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="fd672-130">Si un administrador se libera de un caso, el estado cambia a **Liberado.**</span><span class="sxs-lookup"><span data-stu-id="fd672-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="fd672-131">Orígenes de datos e información de indización</span><span class="sxs-lookup"><span data-stu-id="fd672-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="fd672-132">**Orígenes de** datos: muestra el recuento y el tipo de orígenes de datos (buzones, sitios y Teams) que están asociados con el administrador y forman parte del caso.</span><span class="sxs-lookup"><span data-stu-id="fd672-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="fd672-133">**Hora de actualización del índice:** indica la hora y la fecha de la última vez que se desencadenó el trabajo de indización avanzado.</span><span class="sxs-lookup"><span data-stu-id="fd672-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="fd672-134">Esta propiedad también indicará cuándo está en curso el proceso de indización avanzado.</span><span class="sxs-lookup"><span data-stu-id="fd672-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="fd672-135">Editar un administrador</span><span class="sxs-lookup"><span data-stu-id="fd672-135">Edit a custodian</span></span>

<span data-ttu-id="fd672-136">A medida que su caso avanza, puede descubrir que puede haber orígenes de datos adicionales relevantes para un administrador específico & su caso.</span><span class="sxs-lookup"><span data-stu-id="fd672-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="fd672-137">En otros escenarios, es posible que desee quitar determinados orígenes de datos que se han revisado y que se consideran no relevantes.</span><span class="sxs-lookup"><span data-stu-id="fd672-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="fd672-138">Para actualizar los orígenes de datos asociados con un administrador:</span><span class="sxs-lookup"><span data-stu-id="fd672-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="fd672-139">Vaya a  **eDiscovery > eDiscovery avanzado** y abra el caso.</span><span class="sxs-lookup"><span data-stu-id="fd672-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="fd672-140">Haga clic en **la pestaña** Orígenes.</span><span class="sxs-lookup"><span data-stu-id="fd672-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="fd672-141">En la **página Administradores,** seleccione un administrador de la lista y haga clic **en Editar** en la página desplegable.</span><span class="sxs-lookup"><span data-stu-id="fd672-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Editar orígenes de datos](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="fd672-143">Haga **clic en la pestaña Elegir** orígenes de datos para cambiar la configuración del buzón de Exchange del administrador y la cuenta de OneDrive, haga clic en Elegir orígenes de **datos.**</span><span class="sxs-lookup"><span data-stu-id="fd672-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="fd672-144">Haga clic **en la pestaña** Seleccionar orígenes de datos adicionales para agregar o quitar buzones de Teams, SharePoint o Exchange asociados con el administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="fd672-145">Para obtener más información acerca de los orígenes de datos asociados con un administrador, vea [Agregar administradores a un caso.](add-custodians-to-case.md)</span><span class="sxs-lookup"><span data-stu-id="fd672-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="fd672-146">Haga **clic en Colocar retenciones de** administrador para habilitar o deshabilitar la retención del administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="fd672-147">Volver a indizar datos de administrador</span><span class="sxs-lookup"><span data-stu-id="fd672-147">Re-index custodian data</span></span>

<span data-ttu-id="fd672-148">En la mayoría de los flujos de trabajo de exhibición de documentos electrónicos para investigaciones legales, se busca en un subconjunto de los datos de un administrador después de que el administrador se agrega a un caso legal.</span><span class="sxs-lookup"><span data-stu-id="fd672-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="fd672-149">Debido a tamaños de archivo muy grandes o a posibles daños en los datos, algunos elementos de los orígenes de datos asociados con un administrador se pueden indizar parcialmente.</span><span class="sxs-lookup"><span data-stu-id="fd672-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="fd672-150">Con la [capacidad de indización](indexing-custodian-data.md) avanzada en la exhibición avanzada de documentos electrónicos, la mayoría de los elementos parcialmente indizados se pueden corregir automáticamente mediante la indización de estos elementos a petición.</span><span class="sxs-lookup"><span data-stu-id="fd672-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="fd672-151">Cuando se agrega un administrador a un caso, los datos ubicados en los orígenes de datos asociados con el administrador se indizan automáticamente (por el proceso de indización avanzado).</span><span class="sxs-lookup"><span data-stu-id="fd672-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="fd672-152">Esto significa que puede dejar los datos en su lugar en lugar de tener que descargarlos y corregirlos y, a continuación, buscarlos sin conexión).</span><span class="sxs-lookup"><span data-stu-id="fd672-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="fd672-153">Sin embargo, durante el ciclo de vida de un caso legal, los nuevos orígenes de datos podrían asociarse con un administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="fd672-154">En este caso, puede volver a indizar los datos del administrador si vuelve a ejecutar el proceso de indización avanzado para corregir los elementos parcialmente indizados y actualizar el índice de los datos del administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="fd672-155">Para desencadenar el proceso de re indización para que se direccione a elementos parcialmente indizados:</span><span class="sxs-lookup"><span data-stu-id="fd672-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="fd672-156">Vaya a  **eDiscovery > eDiscovery avanzado** y abra el caso.</span><span class="sxs-lookup"><span data-stu-id="fd672-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="fd672-157">Haga clic en **la pestaña** Orígenes.</span><span class="sxs-lookup"><span data-stu-id="fd672-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="fd672-158">En la **página Administradores,** seleccione un administrador cuyos datos deben volver a indexarse.</span><span class="sxs-lookup"><span data-stu-id="fd672-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="fd672-159">En la página desplegable, haga clic **en Actualizar índice**.</span><span class="sxs-lookup"><span data-stu-id="fd672-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="fd672-160">Se muestra un cuadro de diálogo que dice que se ha creado el trabajo de índice.</span><span class="sxs-lookup"><span data-stu-id="fd672-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="fd672-161">Volver a indizar los datos de administrador es un proceso de larga duración; el trabajo correspondiente que se crea se denomina **Volver a indizar datos de administrador.**</span><span class="sxs-lookup"><span data-stu-id="fd672-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="fd672-162">Puede realizar un seguimiento  del progreso en la ficha Trabajos o en la ficha **Administradores** supervisando el estado en la columna Estado del trabajo **de indización.**</span><span class="sxs-lookup"><span data-stu-id="fd672-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="fd672-163">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="fd672-163">For more information, see:</span></span>

- [<span data-ttu-id="fd672-164">Trabajar con errores de proceso</span><span class="sxs-lookup"><span data-stu-id="fd672-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="fd672-165">Administrar trabajos</span><span class="sxs-lookup"><span data-stu-id="fd672-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="fd672-166">Liberar a un administrador de un caso</span><span class="sxs-lookup"><span data-stu-id="fd672-166">Release a custodian from a case</span></span>

<span data-ttu-id="fd672-167">Un administrador se libera en situaciones en las que un caso está cerrado, el administrador ya no tiene la obligación de conservar el contenido de un caso o cuando se considera que el administrador ya no es relevante para el caso.</span><span class="sxs-lookup"><span data-stu-id="fd672-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="fd672-168">Si libera a un administrador después de publicar un aviso de retención, se enviará un aviso de lanzamiento al administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="fd672-169">Además, se quitan las retenciones realizadas en orígenes de datos asociados con el administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="fd672-170">Si el administrador se colocó en una retención *silenciosa,* donde no se emitieron notificaciones de retención legal, no se enviará un aviso de liberación, pero se quitarán las retenciones realizadas en los orígenes de datos asociados con ese administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="fd672-171">Para liberar a un administrador:</span><span class="sxs-lookup"><span data-stu-id="fd672-171">To release a custodian:</span></span> 

1. <span data-ttu-id="fd672-172">Vaya a  **eDiscovery > eDiscovery avanzado** y abra el caso.</span><span class="sxs-lookup"><span data-stu-id="fd672-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="fd672-173">Haga clic en **la pestaña** Orígenes.</span><span class="sxs-lookup"><span data-stu-id="fd672-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="fd672-174">En la **página Administradores** y, a continuación, seleccione el administrador que se va a liberar del caso.</span><span class="sxs-lookup"><span data-stu-id="fd672-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="fd672-175">En la página desplegable, haga clic **en Liberar administrador.**</span><span class="sxs-lookup"><span data-stu-id="fd672-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="fd672-176">Se muestra una página de advertencia en la que se explica que si se coloca una retención en un origen de datos asociado con el administrador, se quitará la retención y se aplicará cualquier otra retención asociada con un caso de eDiscovery avanzado diferente.</span><span class="sxs-lookup"><span data-stu-id="fd672-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="fd672-177">Esto incluye otros tipos de características de conservación y retención (como una directiva de retención de Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="fd672-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="fd672-178">Haga **clic en** Sí para confirmar que desea liberar al administrador.</span><span class="sxs-lookup"><span data-stu-id="fd672-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="fd672-179">El estado de este usuario en la pestaña **Administradores** se establece en **Liberado** y el estado de retención en la página desplegable se cambia a **False**. </span><span class="sxs-lookup"><span data-stu-id="fd672-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="fd672-180">Un administrador puede estar involucrado simultáneamente en varios casos legales.</span><span class="sxs-lookup"><span data-stu-id="fd672-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="fd672-181">Cuando un administrador se libera de un caso, las retenciones y notificaciones en otros asuntos no se verán afectadas.</span><span class="sxs-lookup"><span data-stu-id="fd672-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="fd672-182">Administradores de edición masiva</span><span class="sxs-lookup"><span data-stu-id="fd672-182">Bulk-edit custodians</span></span>

<span data-ttu-id="fd672-183">Puede usar el editor masivo para editar varios administradores al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="fd672-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="fd672-184">Para ello, simplemente seleccione dos o más  administradores en la pestaña Administradores para mostrar el editor en masa y, a continuación, haga clic en una de las tareas.</span><span class="sxs-lookup"><span data-stu-id="fd672-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Página desplegable para editar la configuración de varios administradores](../media/AeDBulkEditCustodians.png)
