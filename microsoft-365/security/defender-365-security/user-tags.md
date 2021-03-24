---
title: Etiquetas de usuario en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a identificar grupos específicos de usuarios con etiquetas de usuario en Microsoft Defender para Office 365 Plan 2. El filtrado de etiquetas está disponible en alertas, informes e investigaciones en Microsoft Defender para Office 365 para identificar rápidamente a los usuarios etiquetados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f98dcfe3e8c44e852134e7a12def4ff78c1bcdd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071051"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="d628f-104">Etiquetas de usuario en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d628f-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="d628f-105">La característica de etiquetas de usuario está en Versión preliminar, no está disponible para todos y está sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="d628f-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="d628f-106">Para obtener información acerca de la programación de lanzamiento, consulte la guía [básica de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="d628f-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="d628f-107">Las etiquetas de usuario son identificadores para grupos específicos de usuarios en [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d628f-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="d628f-108">Hay dos tipos de etiquetas de usuario:</span><span class="sxs-lookup"><span data-stu-id="d628f-108">There are two types of user tags:</span></span>

- <span data-ttu-id="d628f-109">**Etiquetas del** sistema: Actualmente, [las cuentas de prioridad](../../admin/setup/priority-accounts.md) son el único tipo de etiqueta del sistema.</span><span class="sxs-lookup"><span data-stu-id="d628f-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="d628f-110">**Etiquetas personalizadas:** puede crear estas etiquetas de usuario usted mismo.</span><span class="sxs-lookup"><span data-stu-id="d628f-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="d628f-111">Si su organización tiene Defender para Office 365 Plan 2 (incluido en la suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta de cuentas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="d628f-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="d628f-112">Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:</span><span class="sxs-lookup"><span data-stu-id="d628f-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="d628f-113">Alertas en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d628f-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="d628f-114">Explorador de amenazas y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="d628f-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="d628f-115">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="d628f-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="d628f-116">Vistas de campañas</span><span class="sxs-lookup"><span data-stu-id="d628f-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="d628f-117">Para las cuentas de prioridad, puede usar el informe Problemas de correo electrónico [para cuentas de prioridad](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) en el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="d628f-117">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="d628f-118">En este artículo se explica cómo configurar las etiquetas de usuario en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d628f-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="d628f-119">No hay cmdlets en el Centro de seguridad & cumplimiento para administrar etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="d628f-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="d628f-120">Para ver cómo las etiquetas de usuario forman parte de la estrategia para ayudar a proteger las cuentas de usuario de alto impacto, vea Recomendaciones de seguridad para cuentas de prioridad [en Microsoft 365](security-recommendations-for-priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="d628f-120">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d628f-121">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="d628f-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d628f-122">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d628f-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d628f-123">Para ir directamente a la **página Etiquetas de** usuario, abra <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="d628f-123">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="d628f-124">Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="d628f-124">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d628f-125">Para crear, modificar y eliminar etiquetas de usuario, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="d628f-125">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="d628f-126">Para agregar y quitar miembros de etiquetas de usuario existentes, debe ser miembro de los grupos de roles Administración de la **organización,** Administrador de seguridad **o** Operador de seguridad </span><span class="sxs-lookup"><span data-stu-id="d628f-126">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="d628f-127">Para obtener acceso de solo lectura a las etiquetas de usuario, debe ser miembro de los grupos de roles **Lector global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="d628f-127">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="d628f-128">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d628f-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="d628f-129">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="d628f-129">**Notes**:</span></span>

  - <span data-ttu-id="d628f-130">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d628f-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d628f-131">Para más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d628f-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="d628f-132">La administración de etiquetas de usuario está controlada por los roles **Lector de** etiquetas y **Administrador de etiquetas.**</span><span class="sxs-lookup"><span data-stu-id="d628f-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="d628f-133">También puede administrar y supervisar cuentas de prioridad en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d628f-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d628f-134">Para obtener instrucciones, vea [Administrar y supervisar cuentas de prioridad](../../admin/setup/priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="d628f-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="d628f-135">Usar el Centro de seguridad & cumplimiento para crear etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="d628f-135">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="d628f-136">En el Centro de seguridad & cumplimiento, vaya a **Administración de amenazas** \> **Etiquetas de usuario**.</span><span class="sxs-lookup"><span data-stu-id="d628f-136">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d628f-137">En la **página Etiquetas de** usuario que se abre, haga clic **en Crear etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="d628f-137">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="d628f-138">El **Asistente para crear** etiquetas se abre en un nuevo menú desplegable. En la **página Definir etiqueta,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d628f-138">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="d628f-139">**Nombre:** escriba un nombre descriptivo único para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="d628f-139">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="d628f-140">Este es el valor que verá y usará.</span><span class="sxs-lookup"><span data-stu-id="d628f-140">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="d628f-141">**Descripción:** escriba una descripción opcional para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="d628f-141">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="d628f-142">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d628f-142">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d628f-143">En la página Asignar **usuarios,** siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d628f-143">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="d628f-144">Haga clic **en Agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="d628f-144">Click **Add users**.</span></span> <span data-ttu-id="d628f-145">En el menú desplegable que aparece, siga uno de los pasos siguientes para agregar usuarios o grupos individuales:</span><span class="sxs-lookup"><span data-stu-id="d628f-145">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="d628f-146">Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="d628f-146">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="d628f-147">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="d628f-147">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="d628f-148">Para agregar valores adicionales, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="d628f-148">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="d628f-149">Para quitar entradas individuales del cuadro, haga clic en **Quitar** icono Quitar del ![ usuario o grupo del ](../../media/scc-remove-icon.png) cuadro.</span><span class="sxs-lookup"><span data-stu-id="d628f-149">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="d628f-150">Para quitar las entradas existentes de la lista debajo del cuadro, haga clic **en Quitar** icono de ![ la ](../../media/scc-remove-icon.png) entrada.</span><span class="sxs-lookup"><span data-stu-id="d628f-150">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="d628f-151">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d628f-151">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="d628f-152">Haga **clic en** Importar para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="d628f-152">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="d628f-153">Asegúrese de que el archivo de texto contiene una entrada por línea.</span><span class="sxs-lookup"><span data-stu-id="d628f-153">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="d628f-154">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d628f-154">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d628f-155">En la **página Revisar etiqueta,** revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="d628f-155">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="d628f-156">Puede hacer clic **en Editar** en la sección específica para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="d628f-156">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="d628f-157">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="d628f-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="d628f-158">Usar el Centro de seguridad & cumplimiento para ver etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="d628f-158">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="d628f-159">En el Centro de seguridad & cumplimiento, vaya a **Administración de amenazas** \> **Etiquetas de usuario**.</span><span class="sxs-lookup"><span data-stu-id="d628f-159">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d628f-160">En la **página Etiquetas de** usuario que se abre, seleccione la etiqueta de usuario que desea ver (no haga clic en la casilla).</span><span class="sxs-lookup"><span data-stu-id="d628f-160">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="d628f-161">En los detalles de solo lectura que aparecen, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="d628f-161">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="d628f-162">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d628f-162">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="d628f-163">Usar el Centro de seguridad & cumplimiento para modificar las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="d628f-163">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="d628f-164">En el Centro de seguridad & cumplimiento, vaya a **Administración de amenazas** \> **Etiquetas de usuario**.</span><span class="sxs-lookup"><span data-stu-id="d628f-164">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d628f-165">En la **página Etiquetas de** usuario que se abre, seleccione la etiqueta de usuario que desea ver y, a continuación, haga clic **en Editar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="d628f-165">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="d628f-166">El asistente para directivas se abre en un **control de salida de etiquetas** de edición. Haga **clic en** Siguiente para revisar y modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="d628f-166">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="d628f-167">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="d628f-167">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="d628f-168">Usar el Centro de seguridad & cumplimiento para quitar etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="d628f-168">Use the Security & Compliance Center to remove user tags</span></span>

<span data-ttu-id="d628f-169">**Nota:** No puede quitar la etiqueta de cuenta de **prioridad** integrada.</span><span class="sxs-lookup"><span data-stu-id="d628f-169">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="d628f-170">En el Centro de seguridad & cumplimiento, vaya a **Administración de amenazas** \> **Etiquetas de usuario**.</span><span class="sxs-lookup"><span data-stu-id="d628f-170">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d628f-171">En la **página Etiquetas de** usuario que se abre, seleccione la etiqueta de usuario que desea quitar, haga clic en **Eliminar** etiqueta y, a continuación, seleccione **Sí,** quite en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="d628f-171">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>