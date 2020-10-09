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
ms.openlocfilehash: 16e756b95e16e40f4df738e825e842681c67e22c
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399390"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="20cff-104">Etiquetas de usuario en la ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="20cff-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="20cff-105">Las etiquetas de usuario son identificadores para grupos de usuarios específicos en [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="20cff-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="20cff-106">Hay dos tipos de etiquetas de usuario:</span><span class="sxs-lookup"><span data-stu-id="20cff-106">There are two types of user tags:</span></span>

- <span data-ttu-id="20cff-107">**Etiquetas del sistema**: Actualmente, [cuentas prioritarias](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) es el único tipo de etiqueta de sistema.</span><span class="sxs-lookup"><span data-stu-id="20cff-107">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="20cff-108">**Etiquetas personalizadas**: usted mismo crea estas etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="20cff-108">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="20cff-109">Si su organización tiene Office 365 ATP plan 2 (incluido en su suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta accounts Priority.</span><span class="sxs-lookup"><span data-stu-id="20cff-109">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="20cff-110">Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:</span><span class="sxs-lookup"><span data-stu-id="20cff-110">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="20cff-111">Alertas del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="20cff-111">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="20cff-112">Explorador de amenazas y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="20cff-112">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="20cff-113">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="20cff-113">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="20cff-114">Vistas de campañas</span><span class="sxs-lookup"><span data-stu-id="20cff-114">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="20cff-115">En este artículo se explica cómo configurar etiquetas de usuario en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="20cff-115">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="20cff-116">No hay cmdlets en el centro de seguridad & cumplimiento para administrar las etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="20cff-116">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20cff-117">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="20cff-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20cff-118">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="20cff-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="20cff-119">Para ir directamente a la página **etiquetas de usuario** , Abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="20cff-119">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="20cff-120">Para crear, modificar o quitar **etiquetas de usuario personalizadas**, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="20cff-120">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="20cff-121">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="20cff-121">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="20cff-122">Para configurar las cuentas prioritarias (etiquetas del sistema), debe ser [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o [Administrador de Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span><span class="sxs-lookup"><span data-stu-id="20cff-122">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="20cff-123">También puede administrar y supervisar cuentas prioritarias en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20cff-123">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="20cff-124">Para obtener instrucciones, consulte [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="20cff-124">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="20cff-125">Usar el centro de seguridad para crear etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="20cff-125">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="20cff-126">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="20cff-126">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="20cff-127">En la página **etiquetas de usuario** que se abre, haga clic en **crear etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="20cff-127">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="20cff-128">El Asistente para **crear etiquetas** se abre en una nueva volar hacia fuera. En la página **definir etiqueta** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="20cff-128">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="20cff-129">**Name**: escriba un nombre único y descriptivo para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="20cff-129">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="20cff-130">Este es el valor que verás y usarás.</span><span class="sxs-lookup"><span data-stu-id="20cff-130">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="20cff-131">**Descripción**: escriba una descripción opcional para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="20cff-131">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="20cff-132">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="20cff-132">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="20cff-133">En la página **asignar buzones** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="20cff-133">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="20cff-134">Haga clic en **Agregar buzones**.</span><span class="sxs-lookup"><span data-stu-id="20cff-134">Click **Add mailboxes**.</span></span> <span data-ttu-id="20cff-135">En la volar hacia fuera que aparece, realice uno de los siguientes pasos para agregar grupos o usuarios individuales:</span><span class="sxs-lookup"><span data-stu-id="20cff-135">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="20cff-136">Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="20cff-136">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="20cff-137">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="20cff-137">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="20cff-138">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="20cff-138">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="20cff-139">Para quitar entradas individuales del cuadro, haga clic en **quitar** ![ icono de eliminación ](../../media/scc-remove-icon.png) en el usuario o grupo en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="20cff-139">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="20cff-140">Para quitar las entradas existentes de la lista situada debajo del cuadro, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación de la entrada.</span><span class="sxs-lookup"><span data-stu-id="20cff-140">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="20cff-141">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="20cff-141">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="20cff-142">Haga clic en **importar** para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="20cff-142">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="20cff-143">Asegúrese de que el archivo de texto contenga una entrada por línea.</span><span class="sxs-lookup"><span data-stu-id="20cff-143">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="20cff-144">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="20cff-144">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="20cff-145">En la página **revisar etiqueta** , revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="20cff-145">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="20cff-146">Puede hacer clic en **Editar** en la sección específica para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="20cff-146">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="20cff-147">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="20cff-147">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="20cff-148">Usar el centro de seguridad para ver las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="20cff-148">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="20cff-149">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="20cff-149">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="20cff-150">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver (no haga clic en la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="20cff-150">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="20cff-151">En los detalles de solo lectura que aparecen, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="20cff-151">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="20cff-152">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="20cff-152">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="20cff-153">Usar el centro de seguridad para modificar las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="20cff-153">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="20cff-154">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="20cff-154">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="20cff-155">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver y, a continuación, haga clic en **Editar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="20cff-155">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="20cff-156">El Asistente para directivas se abre en una **etiqueta de edición** hacia fuera. Haga clic en **siguiente** para revisar y modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="20cff-156">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="20cff-157">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="20cff-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="20cff-158">Usar el centro de seguridad para quitar etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="20cff-158">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="20cff-159">**Nota**: no se puede quitar la etiqueta de **cuenta** integrada con prioridad.</span><span class="sxs-lookup"><span data-stu-id="20cff-159">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="20cff-160">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="20cff-160">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="20cff-161">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea quitar, haga clic en **Eliminar etiqueta**y, a continuación, seleccione **sí, quitar** en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="20cff-161">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
