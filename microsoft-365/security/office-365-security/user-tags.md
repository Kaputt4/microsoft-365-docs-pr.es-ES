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
ms.openlocfilehash: 9522499b3861f0f0e44fcbf09896a5c93feed95d
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337258"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="33298-104">Etiquetas de usuario en la ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="33298-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="33298-105">Las etiquetas de usuario son identificadores para grupos de usuarios específicos en [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="33298-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="33298-106">[Las cuentas de prioridad](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) son un tipo de etiqueta de usuario.</span><span class="sxs-lookup"><span data-stu-id="33298-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="33298-107">Si su organización tiene Office 365 ATP plan 2 (incluido en su suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta accounts Priority.</span><span class="sxs-lookup"><span data-stu-id="33298-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="33298-108">Después de aplicar etiquetas a usuarios específicos, puede usarlas como filtros en alertas, informes e investigaciones:</span><span class="sxs-lookup"><span data-stu-id="33298-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="33298-109">Alertas del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="33298-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="33298-110">Explorador de amenazas y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="33298-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="33298-111">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="33298-111">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="33298-112">Vistas de campañas</span><span class="sxs-lookup"><span data-stu-id="33298-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="33298-113">En este artículo se explica cómo configurar etiquetas de usuario en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="33298-113">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="33298-114">No hay cmdlets en el centro de seguridad & cumplimiento para administrar las etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="33298-114">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33298-115">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="33298-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33298-116">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="33298-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="33298-117">Para ir directamente a la página **etiquetas de usuario** , Abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="33298-117">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="33298-118">Para crear, modificar o quitar etiquetas de usuario, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="33298-118">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="33298-119">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="33298-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="33298-120">También puede administrar y supervisar cuentas prioritarias en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33298-120">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="33298-121">Para obtener instrucciones, consulte [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="33298-121">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="33298-122">Usar el centro de seguridad para crear etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="33298-122">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="33298-123">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="33298-123">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="33298-124">En la página **etiquetas de usuario** que se abre, haga clic en **crear etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="33298-124">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="33298-125">El Asistente para **crear etiquetas** se abre en una nueva volar hacia fuera. En la página **definir etiqueta** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="33298-125">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="33298-126">**Name**: escriba un nombre único y descriptivo para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="33298-126">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="33298-127">Este es el valor que verás y usarás.</span><span class="sxs-lookup"><span data-stu-id="33298-127">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="33298-128">**Descripción**: escriba una descripción opcional para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="33298-128">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="33298-129">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="33298-129">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="33298-130">En la página **asignar buzones** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="33298-130">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="33298-131">Haga clic en **Agregar buzones**.</span><span class="sxs-lookup"><span data-stu-id="33298-131">Click **Add mailboxes**.</span></span> <span data-ttu-id="33298-132">En la volar hacia fuera que aparece, realice uno de los siguientes pasos para agregar grupos o usuarios individuales:</span><span class="sxs-lookup"><span data-stu-id="33298-132">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="33298-133">Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="33298-133">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="33298-134">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="33298-134">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="33298-135">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="33298-135">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="33298-136">Para quitar entradas individuales del cuadro, haga clic en **quitar** ![ icono de eliminación ](../../media/scc-remove-icon.png) en el usuario o grupo en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="33298-136">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="33298-137">Para quitar las entradas existentes de la lista situada debajo del cuadro, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación de la entrada.</span><span class="sxs-lookup"><span data-stu-id="33298-137">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="33298-138">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="33298-138">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="33298-139">Haga clic en **importar** para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="33298-139">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="33298-140">Asegúrese de que el archivo de texto contenga una entrada por línea.</span><span class="sxs-lookup"><span data-stu-id="33298-140">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="33298-141">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="33298-141">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="33298-142">En la página **revisar etiqueta** , revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="33298-142">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="33298-143">Puede hacer clic en **Editar** en la sección específica para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="33298-143">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="33298-144">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="33298-144">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="33298-145">Usar el centro de seguridad para ver las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="33298-145">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="33298-146">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="33298-146">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="33298-147">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver (no haga clic en la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="33298-147">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="33298-148">En los detalles de solo lectura que aparecen, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="33298-148">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="33298-149">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="33298-149">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="33298-150">Usar el centro de seguridad para modificar las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="33298-150">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="33298-151">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="33298-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="33298-152">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver y, a continuación, haga clic en **Editar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="33298-152">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="33298-153">El Asistente para directivas se abre en una **etiqueta de edición** hacia fuera. Haga clic en **siguiente** para revisar y modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="33298-153">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="33298-154">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="33298-154">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="33298-155">Usar el centro de seguridad para quitar etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="33298-155">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="33298-156">**Nota**: no se puede quitar la etiqueta de **cuenta** integrada con prioridad.</span><span class="sxs-lookup"><span data-stu-id="33298-156">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="33298-157">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> **User tags**.</span><span class="sxs-lookup"><span data-stu-id="33298-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="33298-158">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea quitar, haga clic en **Eliminar etiqueta**y, a continuación, seleccione **sí, quitar** en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="33298-158">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
