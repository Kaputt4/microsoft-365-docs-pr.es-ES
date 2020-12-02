---
title: Etiquetas de usuario en Microsoft defender para Office 365
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
description: Los administradores pueden aprender a identificar grupos específicos de usuarios con etiquetas de usuario en Microsoft defender para Office 365 plan 2. El filtrado de etiquetas está disponible a través de alertas, informes e investigaciones en Microsoft defender para Office 365 para identificar rápidamente los usuarios etiquetados.
ms.openlocfilehash: 136de95addae7dcd48de2c6ac1f30ce67714817c
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552024"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4e333-104">Etiquetas de usuario en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="4e333-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="4e333-105">La característica de etiquetas de usuario está en versión preliminar, no está disponible para todos los usuarios y está sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="4e333-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="4e333-106">Para obtener información sobre la programación de versiones, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="4e333-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="4e333-107">Las etiquetas de usuario son identificadores para grupos de usuarios específicos en [Microsoft defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="4e333-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="4e333-108">Hay dos tipos de etiquetas de usuario:</span><span class="sxs-lookup"><span data-stu-id="4e333-108">There are two types of user tags:</span></span>

- <span data-ttu-id="4e333-109">**Etiquetas del sistema**: Actualmente, [cuentas prioritarias](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) es el único tipo de etiqueta de sistema.</span><span class="sxs-lookup"><span data-stu-id="4e333-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="4e333-110">**Etiquetas personalizadas**: usted mismo crea estas etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="4e333-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="4e333-111">Si su organización tiene defender for Office 365 plan 2 (incluido en su suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta accounts Priority.</span><span class="sxs-lookup"><span data-stu-id="4e333-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="4e333-112">Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:</span><span class="sxs-lookup"><span data-stu-id="4e333-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="4e333-113">Alertas del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="4e333-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="4e333-114">Explorador de amenazas y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="4e333-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="4e333-115">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="4e333-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="4e333-116">Vistas de campañas</span><span class="sxs-lookup"><span data-stu-id="4e333-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="4e333-117">Para las cuentas prioritarias, puede usar el [Informe problemas de correo electrónico para cuentas prioritarias](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) en el centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="4e333-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="4e333-118">En este artículo se explica cómo configurar etiquetas de usuario en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4e333-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="4e333-119">No hay cmdlets en el centro de seguridad & cumplimiento para administrar las etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="4e333-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4e333-120">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="4e333-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4e333-121">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4e333-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4e333-122">Para ir directamente a la página **etiquetas de usuario** , Abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="4e333-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="4e333-123">Para crear, modificar o quitar **etiquetas de usuario personalizadas**, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4e333-123">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="4e333-124">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4e333-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="4e333-125">Para configurar las cuentas prioritarias (etiquetas del sistema), debe ser [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o [Administrador de Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span><span class="sxs-lookup"><span data-stu-id="4e333-125">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="4e333-126">También puede administrar y supervisar cuentas prioritarias en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e333-126">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4e333-127">Para obtener instrucciones, consulte [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="4e333-127">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="4e333-128">Usar el centro de seguridad para crear etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="4e333-128">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="4e333-129">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4e333-129">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4e333-130">En la página **etiquetas de usuario** que se abre, haga clic en **crear etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="4e333-130">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="4e333-131">El Asistente para **crear etiquetas** se abre en una nueva volar hacia fuera. En la página **definir etiqueta** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4e333-131">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="4e333-132">**Name**: escriba un nombre único y descriptivo para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="4e333-132">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="4e333-133">Este es el valor que verás y usarás.</span><span class="sxs-lookup"><span data-stu-id="4e333-133">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="4e333-134">**Descripción**: escriba una descripción opcional para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="4e333-134">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="4e333-135">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4e333-135">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="4e333-136">En la página **asignar usuarios** , realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e333-136">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="4e333-137">Haga clic en **Agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4e333-137">Click **Add users**.</span></span> <span data-ttu-id="4e333-138">En la volar hacia fuera que aparece, realice uno de los siguientes pasos para agregar grupos o usuarios individuales:</span><span class="sxs-lookup"><span data-stu-id="4e333-138">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="4e333-139">Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="4e333-139">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="4e333-140">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="4e333-140">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="4e333-141">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="4e333-141">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="4e333-142">Para quitar entradas individuales del cuadro, haga clic en **quitar** ![ icono de eliminación ](../../media/scc-remove-icon.png) en el usuario o grupo en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="4e333-142">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="4e333-143">Para quitar las entradas existentes de la lista situada debajo del cuadro, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación de la entrada.</span><span class="sxs-lookup"><span data-stu-id="4e333-143">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="4e333-144">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4e333-144">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="4e333-145">Haga clic en **importar** para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="4e333-145">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="4e333-146">Asegúrese de que el archivo de texto contenga una entrada por línea.</span><span class="sxs-lookup"><span data-stu-id="4e333-146">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="4e333-147">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4e333-147">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="4e333-148">En la página **revisar etiqueta** , revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="4e333-148">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="4e333-149">Puede hacer clic en **Editar** en la sección específica para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="4e333-149">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="4e333-150">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="4e333-150">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="4e333-151">Usar el centro de seguridad para ver las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="4e333-151">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="4e333-152">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4e333-152">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4e333-153">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver (no haga clic en la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="4e333-153">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="4e333-154">En los detalles de solo lectura que aparecen, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="4e333-154">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="4e333-155">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4e333-155">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="4e333-156">Usar el centro de seguridad para modificar las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="4e333-156">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="4e333-157">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4e333-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4e333-158">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver y, a continuación, haga clic en **Editar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="4e333-158">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="4e333-159">El Asistente para directivas se abre en una **etiqueta de edición** hacia fuera. Haga clic en **siguiente** para revisar y modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="4e333-159">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="4e333-160">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="4e333-160">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="4e333-161">Usar el centro de seguridad para quitar etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="4e333-161">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="4e333-162">**Nota**: no se puede quitar la etiqueta de **cuenta** integrada con prioridad.</span><span class="sxs-lookup"><span data-stu-id="4e333-162">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="4e333-163">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="4e333-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="4e333-164">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea quitar, haga clic en **Eliminar etiqueta** y, a continuación, seleccione **sí, quitar** en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="4e333-164">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
