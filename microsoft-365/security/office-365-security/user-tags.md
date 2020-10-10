---
title: Etiquetas de usuario en la ATP de Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a identificar grupos específicos de usuarios con etiquetas de usuario en Office 365 ATP plan 2. El filtrado de etiquetas está disponible a través de alertas, informes e investigaciones en Office 365 ATP para identificar rápidamente los usuarios etiquetados.
ms.openlocfilehash: 475bf976a71fb688df8db9ac25f3b397c078d79a
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417276"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="6e1e0-104">Etiquetas de usuario en la ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="6e1e0-104">User tags in Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="6e1e0-105">La característica de etiquetas de usuario está en versión preliminar, no está disponible para todos los usuarios y está sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="6e1e0-106">Para obtener información sobre la programación de versiones, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="6e1e0-107">Las etiquetas de usuario son identificadores para grupos de usuarios específicos en [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-107">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="6e1e0-108">Hay dos tipos de etiquetas de usuario:</span><span class="sxs-lookup"><span data-stu-id="6e1e0-108">There are two types of user tags:</span></span>

- <span data-ttu-id="6e1e0-109">**Etiquetas del sistema**: Actualmente, [cuentas prioritarias](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) es el único tipo de etiqueta de sistema.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="6e1e0-110">**Etiquetas personalizadas**: usted mismo crea estas etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="6e1e0-111">Si su organización tiene Office 365 ATP plan 2 (incluido en su suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta accounts Priority.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-111">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="6e1e0-112">Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:</span><span class="sxs-lookup"><span data-stu-id="6e1e0-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="6e1e0-113">Alertas del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6e1e0-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="6e1e0-114">Explorador de amenazas y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="6e1e0-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="6e1e0-115">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="6e1e0-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="6e1e0-116">Vistas de campañas</span><span class="sxs-lookup"><span data-stu-id="6e1e0-116">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="6e1e0-117">En este artículo se explica cómo configurar etiquetas de usuario en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-117">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="6e1e0-118">No hay cmdlets en el centro de seguridad & cumplimiento para administrar las etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-118">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6e1e0-119">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="6e1e0-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6e1e0-120">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6e1e0-121">Para ir directamente a la página **etiquetas de usuario** , Abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="6e1e0-121">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="6e1e0-122">Para crear, modificar o quitar **etiquetas de usuario personalizadas**, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-122">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="6e1e0-123">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-123">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="6e1e0-124">Para configurar las cuentas prioritarias (etiquetas del sistema), debe ser [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o [Administrador de Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-124">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="6e1e0-125">También puede administrar y supervisar cuentas prioritarias en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-125">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6e1e0-126">Para obtener instrucciones, consulte [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-126">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="6e1e0-127">Usar el centro de seguridad para crear etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="6e1e0-127">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="6e1e0-128">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-128">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6e1e0-129">En la página **etiquetas de usuario** que se abre, haga clic en **crear etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-129">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="6e1e0-130">El Asistente para **crear etiquetas** se abre en una nueva volar hacia fuera. En la página **definir etiqueta** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6e1e0-130">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="6e1e0-131">**Name**: escriba un nombre único y descriptivo para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-131">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="6e1e0-132">Este es el valor que verás y usarás.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-132">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="6e1e0-133">**Descripción**: escriba una descripción opcional para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-133">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="6e1e0-134">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-134">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6e1e0-135">En la página **asignar buzones** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6e1e0-135">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="6e1e0-136">Haga clic en **Agregar buzones**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-136">Click **Add mailboxes**.</span></span> <span data-ttu-id="6e1e0-137">En la volar hacia fuera que aparece, realice uno de los siguientes pasos para agregar grupos o usuarios individuales:</span><span class="sxs-lookup"><span data-stu-id="6e1e0-137">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="6e1e0-138">Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-138">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="6e1e0-139">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-139">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="6e1e0-140">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-140">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="6e1e0-141">Para quitar entradas individuales del cuadro, haga clic en **quitar** ![ icono de eliminación ](../../media/scc-remove-icon.png) en el usuario o grupo en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-141">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="6e1e0-142">Para quitar las entradas existentes de la lista situada debajo del cuadro, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación de la entrada.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-142">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="6e1e0-143">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-143">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="6e1e0-144">Haga clic en **importar** para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-144">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="6e1e0-145">Asegúrese de que el archivo de texto contenga una entrada por línea.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-145">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="6e1e0-146">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-146">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6e1e0-147">En la página **revisar etiqueta** , revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-147">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="6e1e0-148">Puede hacer clic en **Editar** en la sección específica para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-148">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="6e1e0-149">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-149">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="6e1e0-150">Usar el centro de seguridad para ver las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="6e1e0-150">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="6e1e0-151">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6e1e0-152">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver (no haga clic en la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="6e1e0-152">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="6e1e0-153">En los detalles de solo lectura que aparecen, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-153">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="6e1e0-154">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-154">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="6e1e0-155">Usar el centro de seguridad para modificar las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="6e1e0-155">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="6e1e0-156">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-156">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6e1e0-157">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver y, a continuación, haga clic en **Editar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-157">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="6e1e0-158">El Asistente para directivas se abre en una **etiqueta de edición** hacia fuera. Haga clic en **siguiente** para revisar y modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-158">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="6e1e0-159">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="6e1e0-160">Usar el centro de seguridad para quitar etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="6e1e0-160">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="6e1e0-161">**Nota**: no se puede quitar la etiqueta de **cuenta** integrada con prioridad.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-161">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="6e1e0-162">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-162">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="6e1e0-163">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea quitar, haga clic en **Eliminar etiqueta**y, a continuación, seleccione **sí, quitar** en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="6e1e0-163">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
