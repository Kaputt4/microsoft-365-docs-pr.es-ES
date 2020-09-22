---
title: Etiquetas de usuario
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
description: Los administradores pueden aprender a identificar grupos específicos de usuarios con etiquetas de usuario en Oiffce 365 ATP plan 2. El filtrado de etiquetas está disponible a través de alertas, informes e investigaciones en Office 365 ATP para identificar rápidamente los usuarios etiquetados.
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210035"
---
# <a name="user-tags-in-the-microsoft-security-center"></a><span data-ttu-id="5d6f5-104">Etiquetas de usuario en el centro de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5d6f5-104">User tags in the Microsoft Security Center</span></span>

<span data-ttu-id="5d6f5-105">Las etiquetas de usuario son identificadores para grupos de usuarios específicos en [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="5d6f5-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="5d6f5-106">[Las cuentas de prioridad](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) son un tipo de etiqueta de usuario.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="5d6f5-107">Si su organización tiene Office 365 ATP plan 2 (incluido en su suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta accounts Priority.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="5d6f5-108">Después de aplicar etiquetas a usuarios específicos, puede usarlas como filtros en alertas, informes e investigaciones:</span><span class="sxs-lookup"><span data-stu-id="5d6f5-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="5d6f5-109">Alertas del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="5d6f5-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="5d6f5-110">Explorador de amenazas y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="5d6f5-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="5d6f5-111">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="5d6f5-111">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="5d6f5-112">Vistas de campañas</span><span class="sxs-lookup"><span data-stu-id="5d6f5-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="5d6f5-113">En este artículo se explica cómo configurar etiquetas de usuario en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-113">This article explains how to configure user tags in the Security Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5d6f5-114">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="5d6f5-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5d6f5-115">Abra el centro de seguridad en <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="5d6f5-115">You open the Security Center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="5d6f5-116">Para ir directamente a la página **etiquetas de usuario** , Abra <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="5d6f5-116">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="5d6f5-117">Para crear, modificar o quitar etiquetas de usuario, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-117">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="5d6f5-118">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5d6f5-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="5d6f5-119">También puede administrar y supervisar cuentas prioritarias en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-119">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5d6f5-120">Para obtener instrucciones, consulte [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="5d6f5-120">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="5d6f5-121">Usar el centro de seguridad para crear etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="5d6f5-121">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="5d6f5-122">En el centro de seguridad, vaya a **configuración** \> **correo electrónico &** \> **etiquetas de usuario**de colaboración.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-122">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="5d6f5-123">En la página **etiquetas de usuario** que se abre, haga clic en **crear etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-123">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="5d6f5-124">El Asistente para **crear etiquetas** se abre en una nueva volar hacia fuera. En la página **definir etiqueta** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5d6f5-124">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="5d6f5-125">**Name**: escriba un nombre único y descriptivo para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-125">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="5d6f5-126">Este es el valor que verás y usarás.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-126">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="5d6f5-127">**Descripción**: escriba una descripción opcional para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-127">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="5d6f5-128">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-128">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="5d6f5-129">En la página **asignar buzones** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5d6f5-129">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="5d6f5-130">Haga clic en **Agregar buzones**.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-130">Click **Add mailboxes**.</span></span> <span data-ttu-id="5d6f5-131">En la volar hacia fuera que aparece, realice uno de los siguientes pasos para agregar grupos o usuarios individuales:</span><span class="sxs-lookup"><span data-stu-id="5d6f5-131">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="5d6f5-132">Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-132">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="5d6f5-133">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-133">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="5d6f5-134">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-134">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="5d6f5-135">Para quitar entradas individuales del cuadro, haga clic en **quitar** ![ icono de eliminación ](../../media/scc-remove-icon.png) en el usuario o grupo en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-135">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="5d6f5-136">Para quitar las entradas existentes de la lista situada debajo del cuadro, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación de la entrada.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-136">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="5d6f5-137">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-137">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="5d6f5-138">Haga clic en **importar** para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-138">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="5d6f5-139">Asegúrese de que el archivo de texto contenga una entrada por línea.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-139">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="5d6f5-140">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-140">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="5d6f5-141">En la página **revisar etiqueta** , revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-141">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="5d6f5-142">Puede hacer clic en **Editar** en la sección específica para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-142">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="5d6f5-143">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-143">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="5d6f5-144">Usar el centro de seguridad para ver las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="5d6f5-144">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="5d6f5-145">En el centro de seguridad, vaya a **configuración** \> **correo electrónico &** \> **etiquetas de usuario**de colaboración.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-145">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="5d6f5-146">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver (no haga clic en la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d6f5-146">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="5d6f5-147">En los detalles de solo lectura que aparecen, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-147">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="5d6f5-148">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-148">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="5d6f5-149">Usar el centro de seguridad para modificar las etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="5d6f5-149">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="5d6f5-150">En el centro de seguridad, vaya a **configuración** \> **correo electrónico &** \> **etiquetas de usuario**de colaboración.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-150">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="5d6f5-151">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea ver y, a continuación, haga clic en **Editar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-151">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="5d6f5-152">El Asistente para directivas se abre en una **etiqueta de edición** hacia fuera. Haga clic en **siguiente** para revisar y modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-152">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="5d6f5-153">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-153">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="5d6f5-154">Usar el centro de seguridad para quitar etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="5d6f5-154">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="5d6f5-155">**Nota**: no se puede quitar la etiqueta de **cuenta** integrada con prioridad.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-155">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="5d6f5-156">En el centro de seguridad, vaya a **configuración** \> **correo electrónico &** \> **etiquetas de usuario**de colaboración.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-156">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="5d6f5-157">En la página **etiquetas de usuario** que se abre, seleccione la etiqueta de usuario que desea quitar, haga clic en **Eliminar etiqueta**y, a continuación, seleccione **sí, quitar** en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="5d6f5-157">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
