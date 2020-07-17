---
title: Disposición del contenido
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Supervisar y administrar la eliminación de contenido, independientemente de si usa una revisión de disposición o el contenido se elimina automáticamente de acuerdo con la configuración que haya configurado.
ms.openlocfilehash: 5c8c8c4e99edbc32bbca4b3efbe79325f53a3380
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127017"
---
# <a name="disposition-of-content"></a><span data-ttu-id="60e4e-103">Disposición del contenido</span><span class="sxs-lookup"><span data-stu-id="60e4e-103">Disposition of content</span></span>

><span data-ttu-id="60e4e-104">*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="60e4e-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="60e4e-105">Use la pestaña **disposición** de la **Administración de registros** en el centro de cumplimiento de Microsoft 365 para administrar las revisiones de disposición y ver [los registros](records.md) que se han eliminado automáticamente al final del período de retención.</span><span class="sxs-lookup"><span data-stu-id="60e4e-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records.md) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="60e4e-106">Requisitos previos para ver las disposiciones de contenido</span><span class="sxs-lookup"><span data-stu-id="60e4e-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="60e4e-107">Para administrar las revisiones de disposición y confirmar que los registros se han eliminado, debe tener permisos suficientes y la auditoría debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="60e4e-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="60e4e-108">Permisos para disposición</span><span class="sxs-lookup"><span data-stu-id="60e4e-108">Permissions for disposition</span></span>

<span data-ttu-id="60e4e-109">Para obtener acceso correctamente a la pestaña **disposición** del centro de cumplimiento de Microsoft 365, los usuarios deben tener el rol de **Administración de disposición** y el rol **registros de auditoría con permiso de vista** .</span><span class="sxs-lookup"><span data-stu-id="60e4e-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="60e4e-110">Aunque el aviso estándar es agregar usuarios a los grupos de roles predeterminados, en este caso, se recomienda crear un nuevo grupo de funciones denominado **revisores de disposición** con estos dos roles y agregar usuarios a este grupo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="60e4e-110">Although the standard advice is to add users to the default role groups, in this case, we recommend you create a new role group called **Disposition Reviewers** that has these two roles and add users to this group as needed.</span></span> <span data-ttu-id="60e4e-111">Un solo grupo de roles para la disposición reduce los gastos generales de administración y facilita a los usuarios los permisos combinados que necesitan.</span><span class="sxs-lookup"><span data-stu-id="60e4e-111">A single role group for disposition reduces administration overheads and makes it easier for users have the combined permissions that they need.</span></span>

> [!NOTE]
> <span data-ttu-id="60e4e-112">Incluso un administrador global debe recibir la función de **Administración de disposición** .</span><span class="sxs-lookup"><span data-stu-id="60e4e-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> <span data-ttu-id="60e4e-113">Por lo tanto, los administradores globales deben tener acceso a la ficha disposición como miembros del grupo de roles **Reviewers de disposición** .</span><span class="sxs-lookup"><span data-stu-id="60e4e-113">So if global admins need to access the disposition tab, them as members of the **Disposition Reviewers** role group.</span></span> 

<span data-ttu-id="60e4e-114">Específica del rol **registros de auditoría con permiso de vista** :</span><span class="sxs-lookup"><span data-stu-id="60e4e-114">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="60e4e-115">Dado que el cmdlet subyacente que se usa para buscar en el registro de auditoría es un cmdlet de Exchange Online, debe asignar a los usuarios este rol mediante el [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), en lugar de usar la página **permisos** del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="60e4e-115">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="60e4e-116">Para obtener instrucciones, vea [administrar grupos de roles en Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="60e4e-116">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="60e4e-117">Los grupos de 365 de Microsoft ([anteriormente los grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) no se admiten para este rol.</span><span class="sxs-lookup"><span data-stu-id="60e4e-117">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) aren't supported for this role.</span></span> <span data-ttu-id="60e4e-118">En su lugar, asigne buzones de usuario, usuarios de correo o grupos de seguridad habilitados para correo.</span><span class="sxs-lookup"><span data-stu-id="60e4e-118">Instead, assign user mailboxes, mail users, or mail-enabled security groups.</span></span>

<span data-ttu-id="60e4e-119">Para obtener instrucciones sobre cómo conceder a los usuarios la función de **Administración de disposición** y crear su nueva función de **revisores de disposición** , vea [conceder acceso a los usuarios al &amp; centro de seguridad y cumplimiento de Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="60e4e-119">For instructions to grant users the **Disposition Management** role and create your new **Disposition Reviewers** role, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="60e4e-120">Habilitar la auditoría</span><span class="sxs-lookup"><span data-stu-id="60e4e-120">Enable auditing</span></span>

<span data-ttu-id="60e4e-121">Asegúrese de que la auditoría esté habilitada al menos un día antes de la primera acción de disposición.</span><span class="sxs-lookup"><span data-stu-id="60e4e-121">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="60e4e-122">Para obtener más información, vea [Buscar en el registro de auditoría del &amp; centro de seguridad y cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="60e4e-122">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="60e4e-123">Revisiones para eliminación</span><span class="sxs-lookup"><span data-stu-id="60e4e-123">Disposition reviews</span></span>

<span data-ttu-id="60e4e-124">Cuando el contenido alcanza el final de su período de retención, existen varios motivos por los que puede que desee revisar el contenido para decidir si se puede eliminar de forma segura ("eliminado").</span><span class="sxs-lookup"><span data-stu-id="60e4e-124">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="60e4e-125">Por ejemplo, es posible que deba:</span><span class="sxs-lookup"><span data-stu-id="60e4e-125">For example, you might need to:</span></span>
  
- <span data-ttu-id="60e4e-126">Suspender la eliminación del contenido relevante en caso de litigio o una auditoría.</span><span class="sxs-lookup"><span data-stu-id="60e4e-126">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="60e4e-127">Quitar contenido de la lista de disposición para almacenarla en un archivo, si el contenido tiene un valor histórico o de investigación.</span><span class="sxs-lookup"><span data-stu-id="60e4e-127">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="60e4e-128">Asigne un período de retención diferente al contenido, quizá porque la configuración de retención original era una solución temporal o provisional.</span><span class="sxs-lookup"><span data-stu-id="60e4e-128">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="60e4e-129">Devolver el contenido a los clientes o transferirlo a otra organización.</span><span class="sxs-lookup"><span data-stu-id="60e4e-129">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="60e4e-130">Cuando se activa una revisión de disposición al final del período de retención:</span><span class="sxs-lookup"><span data-stu-id="60e4e-130">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="60e4e-131">Las personas que elija reciben una notificación por correo electrónico de que tienen contenido que revisar.</span><span class="sxs-lookup"><span data-stu-id="60e4e-131">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="60e4e-132">Estos revisores pueden ser usuarios individuales, grupos de distribución o de seguridad o grupos de 365 de Microsoft ([anteriormente grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span><span class="sxs-lookup"><span data-stu-id="60e4e-132">These reviewers can be individual users, distribution or security groups, or Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span></span> <span data-ttu-id="60e4e-133">Tenga en cuenta que las notificaciones se envían cada semana.</span><span class="sxs-lookup"><span data-stu-id="60e4e-133">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="60e4e-134">Los revisores van a la pestaña **disposición** del centro de cumplimiento de Microsoft 365 para revisar el contenido y decidir si desea eliminarlo permanentemente, ampliar el período de retención o aplicar una etiqueta de retención diferente.</span><span class="sxs-lookup"><span data-stu-id="60e4e-134">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="60e4e-135">Una revisión de disposición puede incluir contenido en buzones de Exchange, sitios de SharePoint, cuentas de OneDrive y grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60e4e-135">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="60e4e-136">El contenido que espera una revisión de disposición en esas ubicaciones se elimina solo después de que un revisor elige eliminar el contenido de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="60e4e-136">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="60e4e-137">Un buzón de correo debe tener al menos 10 MB de datos para admitir revisiones de disposición.</span><span class="sxs-lookup"><span data-stu-id="60e4e-137">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="60e4e-138">Puede ver una descripción general de todas las disposiciones pendientes en la ficha **información general** . Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60e4e-138">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Información general sobre las disposiciones pendientes en la administración de registros](../media/dispositions-overview.png)

<span data-ttu-id="60e4e-140">Al seleccionar **ver todas las disposiciones pendientes**, se le lleva a la página de **disposición** .</span><span class="sxs-lookup"><span data-stu-id="60e4e-140">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="60e4e-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60e4e-141">For example:</span></span>

![Página disposiciones del centro de cumplimiento de Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="60e4e-143">Flujo de trabajo para una revisión de disposición</span><span class="sxs-lookup"><span data-stu-id="60e4e-143">Workflow for a disposition review</span></span>

<span data-ttu-id="60e4e-144">El siguiente diagrama muestra el flujo de trabajo básico para una revisión de disposición cuando una etiqueta de retención se publica y, a continuación, un usuario la aplica manualmente.</span><span class="sxs-lookup"><span data-stu-id="60e4e-144">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="60e4e-145">Como alternativa, una etiqueta de retención configurada para una revisión de disposición se puede aplicar automáticamente al contenido.</span><span class="sxs-lookup"><span data-stu-id="60e4e-145">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Gráfico que muestra el flujo de trabajo de disposición](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="60e4e-147">Desencadenar una revisión de disposición al final del período de retención es una opción de configuración que solo está disponible con una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="60e4e-147">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="60e4e-148">Esta opción no está disponible para una directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="60e4e-148">This option is not available for a retention policy.</span></span> <span data-ttu-id="60e4e-149">Para obtener más información acerca de estas dos soluciones de retención, consulte [información sobre las directivas de retención y las etiquetas de retención](retention.md).</span><span class="sxs-lookup"><span data-stu-id="60e4e-149">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
![Configuración de retención de una etiqueta](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="60e4e-151">Cuando seleccione la opción **notificar a estas personas cuando hay elementos listos para revisar**, especifique un usuario o un grupo de seguridad habilitado para correo.</span><span class="sxs-lookup"><span data-stu-id="60e4e-151">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="60e4e-152">Para esta opción no se admiten grupos de 365 de Microsoft ([anteriormente los grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span><span class="sxs-lookup"><span data-stu-id="60e4e-152">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="60e4e-153">Visualización y eliminación de contenido</span><span class="sxs-lookup"><span data-stu-id="60e4e-153">Viewing and disposing of content</span></span>

<span data-ttu-id="60e4e-154">Cuando se notifica a un revisor por correo electrónico que el contenido está preparado para revisarlo, se dirige a la pestaña **disposición** de **Administración de registros** en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60e4e-154">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="60e4e-155">Los revisores pueden ver cuántos elementos tiene la etiqueta de retención en espera de disposición y, a continuación, seleccionar una etiqueta de retención para ver todo el contenido con esa etiqueta.</span><span class="sxs-lookup"><span data-stu-id="60e4e-155">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="60e4e-156">Después de seleccionar una etiqueta de retención, verá todas las coposiciones pendientes para esa etiqueta de la pestaña de **disposición pendiente** . Seleccione uno o más elementos en los que podrá elegir una acción y escriba un Comentario de justificación:</span><span class="sxs-lookup"><span data-stu-id="60e4e-156">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Opciones de disposición](../media/retention-disposition-options.png)

<span data-ttu-id="60e4e-158">Como puede ver en la imagen, las acciones admitidas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="60e4e-158">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="60e4e-159">Eliminar permanentemente el elemento</span><span class="sxs-lookup"><span data-stu-id="60e4e-159">Permanently delete the item</span></span>
- <span data-ttu-id="60e4e-160">Ampliación del período de retención</span><span class="sxs-lookup"><span data-stu-id="60e4e-160">Extend the retention period</span></span>
- <span data-ttu-id="60e4e-161">Aplicar una etiqueta de retención diferente</span><span class="sxs-lookup"><span data-stu-id="60e4e-161">Apply a different retention label</span></span>

<span data-ttu-id="60e4e-162">Siempre que tenga permisos para la ubicación y el contenido, puede usar el vínculo de la columna **Ubicación** para ver los documentos en su ubicación original.</span><span class="sxs-lookup"><span data-stu-id="60e4e-162">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="60e4e-163">Durante una revisión de disposición, el contenido nunca se mueve desde su ubicación original, y nunca se elimina hasta que el revisor elige hacerlo.</span><span class="sxs-lookup"><span data-stu-id="60e4e-163">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="60e4e-164">Las notificaciones por correo electrónico se envían de forma automática a los revisores cada semana.</span><span class="sxs-lookup"><span data-stu-id="60e4e-164">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="60e4e-165">Este proceso programado significa que cuando el contenido alcanza el final de su período de retención, los revisores pueden tardar hasta siete días en recibir la notificación por correo electrónico de que el contenido espera la disposición.</span><span class="sxs-lookup"><span data-stu-id="60e4e-165">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="60e4e-166">Todas las acciones de disposición se pueden auditar y el texto de justificación escrito por el revisor se guarda y se muestra en la columna **Comentario** de la página **elementos desechados** .</span><span class="sxs-lookup"><span data-stu-id="60e4e-166">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="60e4e-167">Cuánto tiempo se eliminará permanentemente el contenido desechado</span><span class="sxs-lookup"><span data-stu-id="60e4e-167">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="60e4e-168">El contenido que espera una revisión de disposición se elimina solo después de que un revisor elige eliminar el contenido de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="60e4e-168">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="60e4e-169">Cuando el revisor elige esta opción, el contenido en el sitio de SharePoint o la cuenta de OneDrive pasa a ser apto para el proceso de limpieza estándar descrito en [Cómo funciona la configuración de retención con el contenido en su lugar](retention.md#how-retention-settings-work-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="60e4e-169">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="60e4e-170">Disposición de los registros</span><span class="sxs-lookup"><span data-stu-id="60e4e-170">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="60e4e-171">La capacidad para ver los registros que se eliminaron automáticamente sin una revisión de disposición se distribuye gradualmente a los inquilinos de abril y mayo de 2020, por lo que es posible que no vea esta experiencia de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="60e4e-171">The ability to see records that were automatically deleted without a disposition review is gradually rolling out to tenants during April and May 2020, so you might not see this experience immediately.</span></span>

<span data-ttu-id="60e4e-172">Use la pestaña **disposición** de la página **Administración de registros** para identificar los registros que se eliminan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="60e4e-172">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="60e4e-173">Estos elementos muestran **los registros eliminados** en la columna **tipo** .</span><span class="sxs-lookup"><span data-stu-id="60e4e-173">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="60e4e-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60e4e-174">For example:</span></span>

![Elementos eliminados sin una revisión de disposición](../media/records-disposed2.png)

<span data-ttu-id="60e4e-176">Los elementos que se muestran en la ficha **elementos desechados** para las etiquetas de registro se conservan durante un máximo de 7 años después de que se eliminó el elemento, con un límite de 1 millón elementos por registro para ese período.</span><span class="sxs-lookup"><span data-stu-id="60e4e-176">Items that are shown in the **Disposed Items** tab for record labels are kept for up to 7 years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="60e4e-177">Si ve el número de **recuento** cerca de este límite de 1 millón y necesita probar la disposición de sus registros, póngase en contacto [con el soporte técnico de Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="60e4e-177">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="60e4e-178">Esta funcionalidad se basa en la información del [registro de auditoría unificado](search-the-audit-log-in-security-and-compliance.md) y, por lo tanto, requiere que la auditoría esté [habilitada y sea buscada](turn-audit-log-search-on-or-off.md) para que se capturen los eventos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="60e4e-178">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="60e4e-179">Filtrar y exportar las vistas</span><span class="sxs-lookup"><span data-stu-id="60e4e-179">Filter and export the views</span></span>

<span data-ttu-id="60e4e-180">Cuando se selecciona una etiqueta de retención de la página de **disposición** , la ficha de **disposición pendiente** (si procede) y la ficha **elementos desechados** le permiten filtrar las vistas para facilitar la búsqueda de elementos.</span><span class="sxs-lookup"><span data-stu-id="60e4e-180">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="60e4e-181">Para las disposiciones pendientes, el intervalo de tiempo se basa en la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="60e4e-181">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="60e4e-182">Para los elementos eliminados, el intervalo de tiempo se basa en la fecha de eliminación.</span><span class="sxs-lookup"><span data-stu-id="60e4e-182">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="60e4e-183">Puede exportar la información sobre los elementos en cualquiera de las vistas como un archivo. csv que puede ordenar y administrar mediante Excel:</span><span class="sxs-lookup"><span data-stu-id="60e4e-183">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Opción de exportación para la disposición](../media/retention-export-option.png)
  
![Datos de disposición exportados en Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


