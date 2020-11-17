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
ms.openlocfilehash: 14ebcebeb8081a2de341fd06facabd9f7d55b119
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123624"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a53e9-104">Etiquetas de usuario en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a53e9-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="a53e9-105">La característica de etiquetas de usuario está en versión preliminar, no está disponible para todos los usuarios y está sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="a53e9-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="a53e9-106">Para obtener información sobre la programación de versiones, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="a53e9-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="a53e9-107">Las etiquetas de usuario son identificadores para grupos de usuarios específicos en [Microsoft defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="a53e9-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="a53e9-108">Hay dos tipos de etiquetas de usuario:</span><span class="sxs-lookup"><span data-stu-id="a53e9-108">There are two types of user tags:</span></span>

- <span data-ttu-id="a53e9-109">**Etiquetas del sistema**: Actualmente, [cuentas prioritarias](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) es el único tipo de etiqueta de sistema.</span><span class="sxs-lookup"><span data-stu-id="a53e9-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="a53e9-110">**Etiquetas personalizadas**: usted mismo crea estas etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="a53e9-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="a53e9-111">Si su organización tiene defender for Office 365 plan 2 (incluido en su suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta accounts Priority.</span><span class="sxs-lookup"><span data-stu-id="a53e9-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="a53e9-112">Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:</span><span class="sxs-lookup"><span data-stu-id="a53e9-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="a53e9-113">Alertas del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a53e9-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="a53e9-114">Explorador de amenazas y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="a53e9-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="a53e9-115">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="a53e9-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="a53e9-116">Vistas de campañas</span><span class="sxs-lookup"><span data-stu-id="a53e9-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="a53e9-117">Para las cuentas prioritarias, puede usar el [Informe problemas de correo electrónico para cuentas prioritarias](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) en el centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="a53e9-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="a53e9-118">En este artículo se explica cómo configurar etiquetas de usuario en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a53e9-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="a53e9-119">No hay cmdlets en el centro de seguridad & cumplimiento para administrar las etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="a53e9-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a53e9-120">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="a53e9-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a53e9-121">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a53e9-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a53e9-122">Para ir directamente a la página **etiquetas de usuario** , Abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="a53e9-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="a53e9-123">Para crear, modificar o quitar **etiquetas de usuario personalizadas**, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a53e9-123">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="a53e9-124">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a53e9-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a53e9-125">Para configurar las cuentas prioritarias (etiquetas del sistema), debe ser [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o [Administrador de Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span><span class="sxs-lookup"><span data-stu-id="a53e9-125">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="a53e9-126">También puede administrar y supervisar cuentas prioritarias en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a53e9-126">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a53e9-127">Para obtener instrucciones, consulte [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="a53e9-127">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="a53e9-128">Usar el centro de seguridad para crear etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="a53e9-128">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="a53e9-129">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-129">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a53e9-130">En la página **etiquetas de usuario** que se abre, haga clic en **crear etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-130">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="a53e9-131">El Asistente para **crear etiquetas** se abre en una nueva volar hacia fuera. En la página **definir etiqueta** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a53e9-131">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="a53e9-132">**Name**: escriba un nombre único y descriptivo para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="a53e9-132">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="a53e9-133">Este es el valor que verás y usarás.</span><span class="sxs-lookup"><span data-stu-id="a53e9-133">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="a53e9-134">**Descripción**: escriba una descripción opcional para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="a53e9-134">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="a53e9-135">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-135">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a53e9-136">En la página **asignar buzones** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a53e9-136">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="a53e9-137">Haga clic en **Agregar buzones**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-137">Click **Add mailboxes**.</span></span> <span data-ttu-id="a53e9-138">En la volar hacia fuera que aparece, realice uno de los siguientes pasos para agregar grupos o usuarios individuales:</span><span class="sxs-lookup"><span data-stu-id="a53e9-138">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="a53e9-139">Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="a53e9-139">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="a53e9-140">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="a53e9-140">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="a53e9-141">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="a53e9-141">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="a53e9-142">Para quitar entradas individuales del cuadro, haga clic en **quitar** ![ icono de eliminación ](../../media/scc-remove-icon.png) en el usuario o grupo en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="a53e9-142">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="a53e9-143">Para quitar las entradas existentes de la lista situada debajo del cuadro, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación de la entrada.</span><span class="sxs-lookup"><span data-stu-id="a53e9-143">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="a53e9-144">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-144">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="a53e9-145">Haga clic en **importar** para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="a53e9-145">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="a53e9-146">Asegúrese de que el archivo de texto contenga una entrada por línea.</span><span class="sxs-lookup"><span data-stu-id="a53e9-146">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="a53e9-147">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-147">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a53e9-148">En la página **revisar etiqueta** , revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="a53e9-148">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="a53e9-149">Puede hacer clic en **Editar** en la sección específica para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="a53e9-149">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="a53e9-150">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-150">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="a53e9-151">Usar el centro de seguridad para ver las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="a53e9-151">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="a53e9-152">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-152">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a53e9-153">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver (no haga clic en la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="a53e9-153">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="a53e9-154">En los detalles de solo lectura que aparecen, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="a53e9-154">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="a53e9-155">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-155">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="a53e9-156">Usar el centro de seguridad para modificar las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="a53e9-156">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="a53e9-157">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a53e9-158">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver y, a continuación, haga clic en **Editar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-158">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="a53e9-159">El Asistente para directivas se abre en una **etiqueta de edición** hacia fuera. Haga clic en **siguiente** para revisar y modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="a53e9-159">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="a53e9-160">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-160">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="a53e9-161">Usar el centro de seguridad para quitar etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="a53e9-161">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="a53e9-162">**Nota**: no se puede quitar la etiqueta de **cuenta** integrada con prioridad.</span><span class="sxs-lookup"><span data-stu-id="a53e9-162">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="a53e9-163">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="a53e9-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="a53e9-164">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea quitar, haga clic en **Eliminar etiqueta** y, a continuación, seleccione **sí, quitar** en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="a53e9-164">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
