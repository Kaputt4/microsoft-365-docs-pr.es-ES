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
ms.openlocfilehash: b64db336aa619313f2ff744e94d48e44c13856a0
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296761"
---
# <a name="disposition-of-content"></a><span data-ttu-id="e7a9e-103">Eliminación de contenido</span><span class="sxs-lookup"><span data-stu-id="e7a9e-103">Disposition of content</span></span>

><span data-ttu-id="e7a9e-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="e7a9e-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="e7a9e-105">Use la pestaña **Eliminación** de **Administración de registros** en el Centro de cumplimiento de Microsoft 365 para administrar las revisiones de eliminación y ver [registros](records-management.md#records) que se hayan eliminado automáticamente al final de su período de retención.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="e7a9e-106">Requisitos previos para ver las eliminaciones de contenido</span><span class="sxs-lookup"><span data-stu-id="e7a9e-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="e7a9e-107">Para administrar las revisiones de eliminación y confirmar que los registros se han eliminado, debe tener los permisos necesarios y la auditoría debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="e7a9e-108">Permisos para la eliminación</span><span class="sxs-lookup"><span data-stu-id="e7a9e-108">Permissions for disposition</span></span>

<span data-ttu-id="e7a9e-109">Para acceder de forma satisfactoria a la pestaña **Eliminación** en el Centro de cumplimiento de Microsoft 365, los usuarios deben tener el rol de administrador de **Administración de eliminación**.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="e7a9e-110">Desde diciembre de 2020, este rol está ahora incluido en el grupo de roles de administrador predeterminado **Administración de registros**.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-110">From December 2020, this role is now included in the **Records Management** default admin role group.</span></span>

> [!NOTE]
> <span data-ttu-id="e7a9e-111">De lmanera predeterminada, un administrador global no tiene concedido el rol de **Administración de eliminación**.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-111">By default, a global admin isn't granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="e7a9e-112">Para conceder a los usuarios solo los permisos que necesitan para las revisiones de disposición sin concederles permisos para ver y configurar otras características para la retención y la gestión de registros, cree un grupo de funciones personalizado (por ejemplo, denominado "Revisores de disposición") y conceda a este grupo la función de gestión de disposición.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-112">To grant users just the permissions they need for disposition reviews without granting them permissions to view and configure other features for retention and records management, create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>

<span data-ttu-id="e7a9e-113">Además, para ver el contenido de los elementos durante el proceso de eliminación, agregue usuarios a los dos grupos de roles siguientes: **Visor de contenido del explorador de contenido** y **Visor de listas del explorador de contenido**.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-113">Additionally, to view the contents of items during the disposition process, add users to the following two role groups: **Content Explorer Content Viewer** and **Content Explorer List Viewer**.</span></span> <span data-ttu-id="e7a9e-114">Si los usuarios no tienen los permisos para estos grupos de roles, aún pueden seleccionar una acción de revisión de eliminación para completar la revisión de eliminación, pero deberán hacerlo sin poder ver el contenido del elemento desde el centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-114">If users don't have the permissions from these role groups, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the compliance center.</span></span>

<span data-ttu-id="e7a9e-115">Para obtener instrucciones sobre la configuración de estos permisos, consulte [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e7a9e-115">For instructions to configure these permissions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="e7a9e-116">Habilitar auditoría</span><span class="sxs-lookup"><span data-stu-id="e7a9e-116">Enable auditing</span></span>

<span data-ttu-id="e7a9e-117">Asegúrese de que la auditoría está activada al menos un día antes de la primera acción de eliminación.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-117">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="e7a9e-118">Para más información, vea [Buscar en el registro de auditoría del Centro de seguridad &amp; cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="e7a9e-118">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="e7a9e-119">Revisiones para eliminación</span><span class="sxs-lookup"><span data-stu-id="e7a9e-119">Disposition reviews</span></span>

<span data-ttu-id="e7a9e-p104">Cuando el contenido llegue al final de su período de retención, hay varios motivos por los que puede que quiera revisarlo y confirmar si se puede borrar de forma permanente ("eliminar"). Por ejemplo, en vez de eliminar el contenido, puede que deba:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-p104">When content reaches the end of its retention period, there are several reasons why you might want to review that content and confirm whether it can be permanently deleted ("disposed"). For example, instead of deleting the content, you might need to:</span></span>
  
- <span data-ttu-id="e7a9e-122">Suspender la eliminación de contenido relevante en caso de litigio o una auditoría.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-122">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>

- <span data-ttu-id="e7a9e-123">Asignar un periodo de retención diferente al contenido, por ejemplo, porque las configuraciones de retención originales eran una solución temporal o provisional.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-123">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>

- <span data-ttu-id="e7a9e-124">Mover el contenido desde su ubicación existente a una ubicación de archivo. Por ejemplo, si ese contenido tiene valor histórico o de investigación.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-124">Move the content from its existing location to an archive location, for example, if that content has research or historical value.</span></span>

<span data-ttu-id="e7a9e-125">Cuando se activa una revisión para eliminación al final del período de retención:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-125">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="e7a9e-126">Las personas que elija recibirán una notificación por correo electrónico de que tienen contenido para revisar.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-126">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="e7a9e-127">Estos revisores pueden ser usuarios individuales o grupos de seguridad habilitados para correo.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-127">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="e7a9e-128">Tenga en cuenta que las notificaciones se envían cada semana.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-128">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="e7a9e-129">Los revisores pueden ir a la pestaña **Eliminación** en el Centro de cumplimiento de Microsoft 365 para revisar el contenido y decidir si se elimina de forma permanente, se amplía el período de retención o se aplica una etiqueta de retención diferente.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-129">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="e7a9e-130">Una revisión para eliminación puede incluir contenido en buzones de Exchange, sitios de SharePoint, cuentas de OneDrive y grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-130">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="e7a9e-131">El contenido pendiente de una revisión para eliminación en esas ubicaciones se eliminará solo después de que un revisor elija eliminar el contenido de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-131">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="e7a9e-132">Un buzón debe tener al menos 10 MB de datos para admitir las revisiones para eliminación.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-132">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="e7a9e-133">Puede ver una descripción general de todas las eliminaciones pendientes en la pestaña **Información general**. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-133">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Disposiciones pendientes en la información general de Administración de registros](../media/dispositions-overview.png)

<span data-ttu-id="e7a9e-135">Al seleccionar **Ver todas las eliminaciones pendientes**, se le dirigirá a la página **Eliminación**.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-135">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="e7a9e-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-136">For example:</span></span>

![Página Eliminaciones en el Centro de cumplimiento de Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="e7a9e-138">Flujo de trabajo para una revisión para eliminación</span><span class="sxs-lookup"><span data-stu-id="e7a9e-138">Workflow for a disposition review</span></span>

<span data-ttu-id="e7a9e-139">El siguiente diagrama muestra el flujo de trabajo básico de una revisión para eliminación cuando se publica una etiqueta de retención y un usuario la aplica de forma manual.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-139">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="e7a9e-140">Como alternativa, puede aplicar automáticamente la etiqueta de retención configurada para una revisión para eliminación al contenido.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-140">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Gráfico que muestra el flujo de trabajo de eliminación](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="e7a9e-142">Desencadenar una revisión para eliminación al final del período de retención es una opción de configuración que solo está disponible con una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-142">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="e7a9e-143">Esta opción no está disponible para una directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-143">This option is not available for a retention policy.</span></span> <span data-ttu-id="e7a9e-144">Para más información sobre estas dos soluciones de retención, consulte [Obtener información sobre las directivas de retención y las etiquetas de retención](retention.md).</span><span class="sxs-lookup"><span data-stu-id="e7a9e-144">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="e7a9e-145">En la página **Definir la configuración de retención** de una etiqueta de retención:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-145">From the **Define retention settings** page for a retention label:</span></span>

![Configuración de retención para una etiqueta](../media/disposition-review-option.png)
 
<span data-ttu-id="e7a9e-147">Después de seleccionar la opción **Desencadenar una revisión para eliminación**, especifique los revisores de eliminación en la siguiente página del asistente:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-147">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![Especificar revisores de eliminación](../media/disposition-reviewers.png)

<span data-ttu-id="e7a9e-149">Para los revisores, especifique un usuario o un grupo de seguridad habilitado para correo.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-149">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="e7a9e-150">En esta opción no se admiten los grupos de Microsoft 365 ([anteriormente llamados grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span><span class="sxs-lookup"><span data-stu-id="e7a9e-150">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="e7a9e-151">Visualización y eliminación de contenido</span><span class="sxs-lookup"><span data-stu-id="e7a9e-151">Viewing and disposing of content</span></span>

<span data-ttu-id="e7a9e-152">Cuando un revisor recibe una notificación por correo electrónico de que el contenido está listo para su revisión, puede ir a la pestaña **Eliminación** de **Administración de registros** en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-152">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e7a9e-153">Los revisores pueden ver cuántos elementos están esperando la eliminación para cada etiqueta de retención y seleccionar una etiqueta de retención para ver todo el contenido con esa etiqueta.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-153">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="e7a9e-154">Después de seleccionar una etiqueta de retención, verá todas las eliminaciones pendientes para dicha etiqueta en la pestaña **Pendiente de eliminación**. Seleccione uno o más elementos, en los que puede elegir una acción y escribir un comentario de justificación:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-154">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Opciones de eliminación](../media/retention-disposition-options.png)

<span data-ttu-id="e7a9e-156">Como puede ver en la imagen, las acciones compatibles son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-156">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="e7a9e-157">Eliminar permanentemente el elemento</span><span class="sxs-lookup"><span data-stu-id="e7a9e-157">Permanently delete the item</span></span>
- <span data-ttu-id="e7a9e-158">Extender el período de retención</span><span class="sxs-lookup"><span data-stu-id="e7a9e-158">Extend the retention period</span></span>
- <span data-ttu-id="e7a9e-159">Aplicar una etiqueta de retención diferente</span><span class="sxs-lookup"><span data-stu-id="e7a9e-159">Apply a different retention label</span></span>

<span data-ttu-id="e7a9e-160">Siempre que disponga de permisos para la ubicación y el contenido, puede usar el vínculo de la columna **Ubicación** para ver los documentos en su ubicación original.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-160">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="e7a9e-161">Durante una revisión para eliminación, el contenido nunca se mueve de su ubicación original y nunca se elimina hasta que el revisor elija hacerlo.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-161">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="e7a9e-p113">Las notificaciones por correo electrónico se envían automáticamente a los revisores cada semana. Este proceso programado significa que cuando el contenido llega al final de su período de retención, es posible que los revisores tarden hasta siete días en recibir la notificación por correo electrónico de que el contenido está esperando a ser eliminado.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-p113">The email notifications are sent automatically to reviewers on a weekly basis. This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="e7a9e-164">Se pueden auditar todas las acciones de eliminación. Además, el texto de justificación introducido por el revisor se guarda y se muestra en la columna **Comentario** de la página **Elementos eliminados**.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-164">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="e7a9e-165">Cuánto tiempo tarda el contenido eliminado en borrarse permanentemente</span><span class="sxs-lookup"><span data-stu-id="e7a9e-165">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="e7a9e-166">El contenido que espera una revisión para eliminación solo se elimina después de que un revisor elija eliminar el contenido de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-166">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="e7a9e-167">Cuando el revisor elige esta opción, el contenido en el sitio de SharePoint o en la cuenta de OneDrive pasa a ser apto para el proceso de limpieza estándar descrito en [Cómo funciona la configuración de retención con el contenido local](retention.md#how-retention-settings-work-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="e7a9e-167">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="e7a9e-168">Eliminación de registros</span><span class="sxs-lookup"><span data-stu-id="e7a9e-168">Disposition of records</span></span>

<span data-ttu-id="e7a9e-169">Use la pestaña **Eliminación** en la página **Administración de registros** para identificar:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-169">Use the **Disposition** tab from the **Records Management** page to identify:</span></span>

- <span data-ttu-id="e7a9e-170">Los elementos eliminados como resultado de una revisión para eliminación.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-170">Items deleted as a result of a disposition review.</span></span>
- <span data-ttu-id="e7a9e-171">Elementos marcados como un registro o un registro normativo que se eliminaron automáticamente al final de su periodo de retención.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-171">Items marked as a record or regulatory record that were automatically deleted at the end of their retention period.</span></span>

<span data-ttu-id="e7a9e-172">Estos elementos muestran **Registros eliminados** en la columna **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-172">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="e7a9e-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-173">For example:</span></span>

![Elementos que se eliminaron sin una revisión para eliminación](../media/records-disposed2.png)

<span data-ttu-id="e7a9e-175">Los elementos que se muestran en la pestaña **Elementos eliminados** se guardan hasta siete años después de que se elimine el elemento, con un límite de un millón artículos por registro para ese período.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-175">Items that are shown in the **Disposed Items** tab are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="e7a9e-176">Si ve que el número de **Recuento** está a punto de alcanzar este límite de un millón y necesita una prueba de eliminación de los registros, póngase en contacto con el [Soporte técnico de Microsoft](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="e7a9e-176">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](../business-video/get-help-support.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e7a9e-177">Esta funcionalidad usa la información del [registro de auditoría unificado](search-the-audit-log-in-security-and-compliance.md) y, por lo tanto, requiere que la auditoría se [habilite y se pueda buscar](turn-audit-log-search-on-or-off.md) para que se puedan capturar los eventos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-177">This functionality uses information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="e7a9e-178">Para auditar los elementos eliminados marcados como registros o registros normativos, busque un **Archivo eliminado marcado como un registro** en la categoría **Actividades de archivo y página**.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-178">For auditing of deleted items that were marked as records or regulatory records, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="e7a9e-179">Este evento de auditoría se aplica a documentos y mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-179">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="e7a9e-180">Filtrar y exportar las vistas</span><span class="sxs-lookup"><span data-stu-id="e7a9e-180">Filter and export the views</span></span>

<span data-ttu-id="e7a9e-181">Al seleccionar una etiqueta de retención de la página **Eliminación**, la pestaña **Pendiente de eliminación** (si procede) y la pestaña **Elementos eliminados** le permiten filtrar las vistas para facilitar la búsqueda de elementos.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-181">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="e7a9e-182">Para las eliminaciones pendientes, el intervalo de tiempo se basa en la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-182">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="e7a9e-183">En el caso de los elementos eliminados, el intervalo de tiempo se basa en la fecha de eliminación.</span><span class="sxs-lookup"><span data-stu-id="e7a9e-183">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="e7a9e-184">Puede exportar información acerca de los elementos de cualquier vista como un archivo .csv que puede ordenar y administrar con Excel:</span><span class="sxs-lookup"><span data-stu-id="e7a9e-184">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Opción de exportación para la eliminación](../media/retention-export-option.png)