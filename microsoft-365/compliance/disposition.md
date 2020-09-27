---
title: Eliminación de contenido
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Supervise y administre la eliminación de contenido, independientemente de si usa una revisión para eliminación o el contenido se elimina automáticamente de acuerdo con la configuración que haya establecido.
ms.openlocfilehash: a0fd71aa1eb7c0a7eff97e783f4b0dfb8a50a915
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262243"
---
# <a name="disposition-of-content"></a><span data-ttu-id="bdbc5-103">Eliminación de contenido</span><span class="sxs-lookup"><span data-stu-id="bdbc5-103">Disposition of content</span></span>

><span data-ttu-id="bdbc5-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="bdbc5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="bdbc5-105">Use la pestaña **Eliminación** de **Administración de registros** en el Centro de cumplimiento de Microsoft 365 para administrar las revisiones de eliminación y ver [registros](records-management.md#records) que se hayan eliminado automáticamente al final de su período de retención.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="bdbc5-106">Requisitos previos para ver las eliminaciones de contenido</span><span class="sxs-lookup"><span data-stu-id="bdbc5-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="bdbc5-107">Para administrar las revisiones de eliminación y confirmar que los registros se han eliminado, debe tener los permisos necesarios y la auditoría debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="bdbc5-108">Permisos para la eliminación</span><span class="sxs-lookup"><span data-stu-id="bdbc5-108">Permissions for disposition</span></span>

<span data-ttu-id="bdbc5-109">Para acceder de forma satisfactoria a la pestaña **Eliminación** en el Centro de cumplimiento de Microsoft 365, los usuarios deben tener el rol de administrador de **Administración de eliminación**.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="bdbc5-110">Este rol está incluido en los grupos de roles de administrador predeterminados, **Administrador de cumplimiento** y **Administrador de datos de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-110">This role is included in the default admin role groups, **Compliance Administrator** and **Compliance Data Administrator**.</span></span>

<span data-ttu-id="bdbc5-111">Para conceder a los usuarios este rol de Administración de eliminación, agréguelos a uno de los grupos de roles predeterminados o cree un grupo de roles personalizado (por ejemplo, denominado "Revisores de eliminación") y conceda a este grupo el rol de Administración de eliminación.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-111">To grant users this required Disposition Management role, either add them to one of these default role groups, or create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>  

> [!NOTE]
> <span data-ttu-id="bdbc5-112">Incluso un administrador global necesita que se le otorgue el rol de **Administración de eliminación**.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="bdbc5-113">Para instrucciones, consulte [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bdbc5-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="bdbc5-114">Habilitar auditoría</span><span class="sxs-lookup"><span data-stu-id="bdbc5-114">Enable auditing</span></span>

<span data-ttu-id="bdbc5-115">Asegúrese de que la auditoría está activada al menos un día antes de la primera acción de eliminación.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-115">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="bdbc5-116">Para más información, vea [Buscar en el registro de auditoría del Centro de seguridad &amp; cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="bdbc5-116">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="bdbc5-117">Revisiones para eliminación</span><span class="sxs-lookup"><span data-stu-id="bdbc5-117">Disposition reviews</span></span>

<span data-ttu-id="bdbc5-118">Cuando el contenido llega al final de su período de retención, hay varios motivos por los que es posible que quiera revisar el contenido para decidir si se puede borrar de forma segura ("eliminar").</span><span class="sxs-lookup"><span data-stu-id="bdbc5-118">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="bdbc5-119">Por ejemplo, puede que necesite:</span><span class="sxs-lookup"><span data-stu-id="bdbc5-119">For example, you might need to:</span></span>
  
- <span data-ttu-id="bdbc5-120">Suspender la eliminación de contenido relevante en caso de litigio o una auditoría.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-120">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="bdbc5-121">Quitar el contenido de la lista de eliminación para almacenarlo en un archivo, si el contenido tiene un valor histórico o para investigación.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-121">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="bdbc5-122">Asignar un periodo de retención diferente al contenido, por ejemplo, porque las configuraciones de retención originales eran una solución temporal o provisional.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-122">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="bdbc5-123">Devolver el contenido a los clientes o transferirlo a otra organización.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-123">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="bdbc5-124">Cuando se activa una revisión para eliminación al final del período de retención:</span><span class="sxs-lookup"><span data-stu-id="bdbc5-124">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="bdbc5-125">Las personas que elija recibirán una notificación por correo electrónico de que tienen contenido para revisar.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-125">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="bdbc5-126">Estos revisores pueden ser usuarios individuales o grupos de seguridad habilitados para correo.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-126">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="bdbc5-127">Tenga en cuenta que las notificaciones se envían cada semana.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-127">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="bdbc5-128">Los revisores pueden ir a la pestaña **Eliminación** en el Centro de cumplimiento de Microsoft 365 para revisar el contenido y decidir si se elimina de forma permanente, se amplía el período de retención o se aplica una etiqueta de retención diferente.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-128">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="bdbc5-129">Una revisión para eliminación puede incluir contenido en buzones de Exchange, sitios de SharePoint, cuentas de OneDrive y grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-129">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="bdbc5-130">El contenido pendiente de una revisión para eliminación en esas ubicaciones se eliminará solo después de que un revisor elija eliminar el contenido de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-130">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="bdbc5-131">Un buzón debe tener al menos 10 MB de datos para admitir las revisiones para eliminación.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-131">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="bdbc5-132">Puede ver una descripción general de todas las eliminaciones pendientes en la pestaña **Información general**. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bdbc5-132">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Disposiciones pendientes en la información general de Administración de registros](../media/dispositions-overview.png)

<span data-ttu-id="bdbc5-134">Al seleccionar **Ver todas las eliminaciones pendientes**, se le dirigirá a la página **Eliminación**.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-134">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="bdbc5-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bdbc5-135">For example:</span></span>

![Página Eliminaciones en el Centro de cumplimiento de Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="bdbc5-137">Flujo de trabajo para una revisión para eliminación</span><span class="sxs-lookup"><span data-stu-id="bdbc5-137">Workflow for a disposition review</span></span>

<span data-ttu-id="bdbc5-138">El siguiente diagrama muestra el flujo de trabajo básico de una revisión para eliminación cuando se publica una etiqueta de retención y un usuario la aplica de forma manual.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-138">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="bdbc5-139">Como alternativa, puede aplicar automáticamente la etiqueta de retención configurada para una revisión para eliminación al contenido.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-139">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Gráfico que muestra el flujo de trabajo de eliminación](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="bdbc5-141">Desencadenar una revisión para eliminación al final del período de retención es una opción de configuración que solo está disponible con una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-141">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="bdbc5-142">Esta opción no está disponible para una directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-142">This option is not available for a retention policy.</span></span> <span data-ttu-id="bdbc5-143">Para más información sobre estas dos soluciones de retención, consulte [Obtener información sobre las directivas de retención y las etiquetas de retención](retention.md).</span><span class="sxs-lookup"><span data-stu-id="bdbc5-143">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="bdbc5-144">En la página **Definir la configuración de retención** de una etiqueta de retención:</span><span class="sxs-lookup"><span data-stu-id="bdbc5-144">From the **Define retention settings** page for a retention label:</span></span>

![Configuración de retención para una etiqueta](../media/disposition-review-option.png)
 
<span data-ttu-id="bdbc5-146">Después de seleccionar la opción **Desencadenar una revisión para eliminación**, especifique los revisores de eliminación en la siguiente página del asistente:</span><span class="sxs-lookup"><span data-stu-id="bdbc5-146">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![Especificar revisores de eliminación](../media/disposition-reviewers.png)

<span data-ttu-id="bdbc5-148">Para los revisores, especifique un usuario o un grupo de seguridad habilitado para correo.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-148">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="bdbc5-149">En esta opción no se admiten los grupos de Microsoft 365 ([anteriormente llamados grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span><span class="sxs-lookup"><span data-stu-id="bdbc5-149">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="bdbc5-150">Visualización y eliminación de contenido</span><span class="sxs-lookup"><span data-stu-id="bdbc5-150">Viewing and disposing of content</span></span>

<span data-ttu-id="bdbc5-151">Cuando un revisor recibe una notificación por correo electrónico de que el contenido está listo para su revisión, puede ir a la pestaña **Eliminación** de **Administración de registros** en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-151">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="bdbc5-152">Los revisores pueden ver cuántos elementos están esperando la eliminación para cada etiqueta de retención y seleccionar una etiqueta de retención para ver todo el contenido con esa etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-152">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="bdbc5-153">Después de seleccionar una etiqueta de retención, verá todas las eliminaciones pendientes para dicha etiqueta en la pestaña **Pendiente de eliminación**. Seleccione uno o más elementos, en los que puede elegir una acción y escribir un comentario de justificación:</span><span class="sxs-lookup"><span data-stu-id="bdbc5-153">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Opciones de eliminación](../media/retention-disposition-options.png)

<span data-ttu-id="bdbc5-155">Como puede ver en la imagen, las acciones compatibles son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="bdbc5-155">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="bdbc5-156">Eliminar permanentemente el elemento</span><span class="sxs-lookup"><span data-stu-id="bdbc5-156">Permanently delete the item</span></span>
- <span data-ttu-id="bdbc5-157">Extender el período de retención</span><span class="sxs-lookup"><span data-stu-id="bdbc5-157">Extend the retention period</span></span>
- <span data-ttu-id="bdbc5-158">Aplicar una etiqueta de retención diferente</span><span class="sxs-lookup"><span data-stu-id="bdbc5-158">Apply a different retention label</span></span>

<span data-ttu-id="bdbc5-159">Siempre que disponga de permisos para la ubicación y el contenido, puede usar el vínculo de la columna **Ubicación** para ver los documentos en su ubicación original.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-159">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="bdbc5-160">Durante una revisión para eliminación, el contenido nunca se mueve de su ubicación original y nunca se elimina hasta que el revisor elija hacerlo.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-160">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="bdbc5-161">Las notificaciones por correo electrónico se envían automáticamente a los revisores cada semana.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-161">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="bdbc5-162">Este proceso programado significa que cuando el contenido llega al final de su período de retención, es posible que los revisores tarden hasta siete días en recibir la notificación por correo electrónico de que el contenido está esperando la eliminación.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-162">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="bdbc5-163">Se pueden auditar todas las acciones de eliminación. Además, el texto de justificación introducido por el revisor se guarda y se muestra en la columna **Comentario** de la página **Elementos eliminados**.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-163">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="bdbc5-164">Cuánto tiempo tarda el contenido eliminado en borrarse permanentemente</span><span class="sxs-lookup"><span data-stu-id="bdbc5-164">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="bdbc5-165">El contenido que espera una revisión para eliminación solo se elimina después de que un revisor elija eliminar el contenido de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-165">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="bdbc5-166">Cuando el revisor elige esta opción, el contenido en el sitio de SharePoint o en la cuenta de OneDrive pasa a ser apto para el proceso de limpieza estándar descrito en [Cómo funciona la configuración de retención con el contenido local](retention.md#how-retention-settings-work-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="bdbc5-166">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="bdbc5-167">Eliminación de registros</span><span class="sxs-lookup"><span data-stu-id="bdbc5-167">Disposition of records</span></span>

<span data-ttu-id="bdbc5-168">Use la pestaña **Eliminación** en la página **Administración de registros** para identificar registros ya eliminados, ya sea automáticamente o después de una revisión para eliminación.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-168">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="bdbc5-169">Estos elementos muestran **Registros eliminados** en la columna **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-169">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="bdbc5-170">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bdbc5-170">For example:</span></span>

![Elementos que se eliminaron sin una revisión para eliminación](../media/records-disposed2.png)

<span data-ttu-id="bdbc5-172">Los elementos que se muestran en la pestaña **Elementos eliminados** para etiquetas de registro se guardan hasta siete años después de que se elimine el elemento, con un límite de un millón artículos por registro para ese período.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-172">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="bdbc5-173">Si ve que el número de **Recuento** está a punto de alcanzar este límite de un millón y necesita una prueba de eliminación de los registros, póngase en contacto con el [Soporte técnico de Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="bdbc5-173">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="bdbc5-174">Esta funcionalidad se basa en la información del [registro de auditoría unificado](search-the-audit-log-in-security-and-compliance.md) y, por lo tanto, requiere que la auditoría se [habilite y se pueda buscar](turn-audit-log-search-on-or-off.md) para que se puedan capturar los eventos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-174">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="bdbc5-175">Filtrar y exportar las vistas</span><span class="sxs-lookup"><span data-stu-id="bdbc5-175">Filter and export the views</span></span>

<span data-ttu-id="bdbc5-176">Al seleccionar una etiqueta de retención de la página **Eliminación**, la pestaña **Pendiente de eliminación** (si procede) y la pestaña **Elementos eliminados** le permiten filtrar las vistas para facilitar la búsqueda de elementos.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-176">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="bdbc5-177">Para las eliminaciones pendientes, el intervalo de tiempo se basa en la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-177">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="bdbc5-178">En el caso de los elementos eliminados, el intervalo de tiempo se basa en la fecha de eliminación.</span><span class="sxs-lookup"><span data-stu-id="bdbc5-178">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="bdbc5-179">Puede exportar información acerca de los elementos de cualquier vista como un archivo .csv que puede ordenar y administrar con Excel:</span><span class="sxs-lookup"><span data-stu-id="bdbc5-179">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Opción de exportación para la eliminación](../media/retention-export-option.png)

