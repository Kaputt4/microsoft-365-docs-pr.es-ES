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
ms.openlocfilehash: ad06bf90f1ecb93d671bfcad6fad0b4f2a952cb2
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663612"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b971b-104">Etiquetas de usuario en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b971b-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="b971b-105">La característica de etiquetas de usuario está en versión preliminar, no está disponible para todos los usuarios y está sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="b971b-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="b971b-106">Para obtener información sobre la programación de versiones, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="b971b-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="b971b-107">Las etiquetas de usuario son identificadores para grupos de usuarios específicos en [Microsoft defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="b971b-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="b971b-108">Hay dos tipos de etiquetas de usuario:</span><span class="sxs-lookup"><span data-stu-id="b971b-108">There are two types of user tags:</span></span>

- <span data-ttu-id="b971b-109">**Etiquetas del sistema**: Actualmente, [cuentas prioritarias](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) es el único tipo de etiqueta de sistema.</span><span class="sxs-lookup"><span data-stu-id="b971b-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="b971b-110">**Etiquetas personalizadas**: usted mismo crea estas etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="b971b-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="b971b-111">Si su organización tiene defender for Office 365 plan 2 (incluido en su suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta accounts Priority.</span><span class="sxs-lookup"><span data-stu-id="b971b-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="b971b-112">Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:</span><span class="sxs-lookup"><span data-stu-id="b971b-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="b971b-113">Alertas del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b971b-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="b971b-114">Explorador de amenazas y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="b971b-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="b971b-115">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="b971b-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="b971b-116">Vistas de campañas</span><span class="sxs-lookup"><span data-stu-id="b971b-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="b971b-117">Para las cuentas prioritarias, puede usar el [Informe problemas de correo electrónico para cuentas prioritarias](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) en el centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="b971b-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="b971b-118">En este artículo se explica cómo configurar etiquetas de usuario en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b971b-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="b971b-119">No hay cmdlets en el centro de seguridad & cumplimiento para administrar las etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="b971b-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b971b-120">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="b971b-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b971b-121">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b971b-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b971b-122">Para ir directamente a la página **etiquetas de usuario** , Abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="b971b-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="b971b-123">Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento de Office 365 antes de que pueda usar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b971b-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b971b-124">Para crear, modificar y eliminar etiquetas de usuario, debe ser miembro de los grupos de roles **Administración** de la organización o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="b971b-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b971b-125">Para agregar y quitar miembros de las etiquetas de usuario existentes, debe ser miembro de los grupos de funciones de administración de la **organización**, **Administrador de seguridad** o operador de **seguridad** .</span><span class="sxs-lookup"><span data-stu-id="b971b-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="b971b-126">Para obtener acceso de solo lectura a las etiquetas del usuario, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="b971b-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b971b-127">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b971b-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="b971b-128">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="b971b-128">**Notes**:</span></span>

  - <span data-ttu-id="b971b-129">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b971b-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b971b-130">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="b971b-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="b971b-131">La administración de etiquetas de usuario está controlada por las funciones **lector** de etiquetas, **colaborador de etiquetas** y **Administrador de etiquetas** .</span><span class="sxs-lookup"><span data-stu-id="b971b-131">User tag management is controlled by the **Tag Reader**, **Tag Contributor**, and **Tag Manager** roles.</span></span>

- <span data-ttu-id="b971b-132">También puede administrar y supervisar cuentas prioritarias en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b971b-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b971b-133">Para obtener instrucciones, consulte [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="b971b-133">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="b971b-134">Usar el centro de seguridad para crear etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="b971b-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="b971b-135">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> .</span><span class="sxs-lookup"><span data-stu-id="b971b-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="b971b-136">En la página **etiquetas de usuario** que se abre, haga clic en **crear etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="b971b-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="b971b-137">El Asistente para **crear etiquetas** se abre en una nueva volar hacia fuera. En la página **definir etiqueta** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b971b-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="b971b-138">**Name**: escriba un nombre único y descriptivo para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="b971b-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="b971b-139">Este es el valor que verás y usarás.</span><span class="sxs-lookup"><span data-stu-id="b971b-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="b971b-140">**Descripción**: escriba una descripción opcional para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="b971b-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="b971b-141">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b971b-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b971b-142">En la página **asignar usuarios** , realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b971b-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="b971b-143">Haga clic en **Agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="b971b-143">Click **Add users**.</span></span> <span data-ttu-id="b971b-144">En la volar hacia fuera que aparece, realice uno de los siguientes pasos para agregar grupos o usuarios individuales:</span><span class="sxs-lookup"><span data-stu-id="b971b-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="b971b-145">Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="b971b-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="b971b-146">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="b971b-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="b971b-147">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="b971b-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="b971b-148">Para quitar entradas individuales del cuadro, haga clic en **quitar** ![ icono de eliminación ](../../media/scc-remove-icon.png) en el usuario o grupo en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="b971b-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="b971b-149">Para quitar las entradas existentes de la lista situada debajo del cuadro, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación de la entrada.</span><span class="sxs-lookup"><span data-stu-id="b971b-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="b971b-150">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b971b-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="b971b-151">Haga clic en **importar** para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="b971b-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="b971b-152">Asegúrese de que el archivo de texto contenga una entrada por línea.</span><span class="sxs-lookup"><span data-stu-id="b971b-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="b971b-153">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b971b-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b971b-154">En la página **revisar etiqueta** , revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="b971b-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="b971b-155">Puede hacer clic en **Editar** en la sección específica para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="b971b-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="b971b-156">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b971b-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="b971b-157">Usar el centro de seguridad para ver las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="b971b-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="b971b-158">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> .</span><span class="sxs-lookup"><span data-stu-id="b971b-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="b971b-159">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver (no haga clic en la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="b971b-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="b971b-160">En los detalles de solo lectura que aparecen, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="b971b-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="b971b-161">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b971b-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="b971b-162">Usar el centro de seguridad para modificar las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="b971b-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="b971b-163">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> .</span><span class="sxs-lookup"><span data-stu-id="b971b-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="b971b-164">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver y, a continuación, haga clic en **Editar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="b971b-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="b971b-165">El Asistente para directivas se abre en una **etiqueta de edición** hacia fuera. Haga clic en **siguiente** para revisar y modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="b971b-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="b971b-166">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b971b-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="b971b-167">Usar el centro de seguridad para quitar etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="b971b-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="b971b-168">**Nota**: no se puede quitar la etiqueta de **cuenta** integrada con prioridad.</span><span class="sxs-lookup"><span data-stu-id="b971b-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="b971b-169">En el centro de seguridad, vaya a etiquetas de usuario de administración de **amenazas** \> .</span><span class="sxs-lookup"><span data-stu-id="b971b-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="b971b-170">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea quitar, haga clic en **Eliminar etiqueta** y, a continuación, seleccione **sí, quitar** en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="b971b-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
