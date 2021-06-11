---
title: Etiquetas de usuario en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a identificar grupos específicos de usuarios con etiquetas de usuario en Microsoft Defender para Office 365 Plan 2. El filtrado de etiquetas está disponible en alertas, informes e investigaciones en Microsoft Defender para Office 365 identificar rápidamente a los usuarios etiquetados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1fb948d63f7bc42839d6fae8a2138d4ad48d81f6
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879173"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="aa298-104">Etiquetas de usuario en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="aa298-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="aa298-105">La característica de etiquetas de usuario está en Versión preliminar, no está disponible para todos y está sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="aa298-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="aa298-106">Para obtener información acerca de la programación de lanzamiento, consulte el [mapa Microsoft 365 ruta de trabajo](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="aa298-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="aa298-107">Las etiquetas de usuario son identificadores de grupos específicos de usuarios en [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="aa298-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="aa298-108">Hay dos tipos de etiquetas de usuario:</span><span class="sxs-lookup"><span data-stu-id="aa298-108">There are two types of user tags:</span></span>

- <span data-ttu-id="aa298-109">**Etiquetas del** sistema: Actualmente, [las cuentas de prioridad](../../admin/setup/priority-accounts.md) son el único tipo de etiqueta del sistema.</span><span class="sxs-lookup"><span data-stu-id="aa298-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="aa298-110">**Etiquetas personalizadas:** puede crear estas etiquetas de usuario usted mismo.</span><span class="sxs-lookup"><span data-stu-id="aa298-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="aa298-111">Si su organización tiene Defender para Office 365 Plan 2 (incluido en la suscripción o como complemento), puede crear etiquetas de usuario personalizadas además de usar la etiqueta cuentas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="aa298-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="aa298-112">Actualmente, solo puede aplicar etiquetas de usuario a los usuarios de buzones.</span><span class="sxs-lookup"><span data-stu-id="aa298-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="aa298-113">Después de aplicar etiquetas del sistema o etiquetas personalizadas a los usuarios, puede usar esas etiquetas como filtros en alertas, informes e investigaciones:</span><span class="sxs-lookup"><span data-stu-id="aa298-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="aa298-114">Alertas</span><span class="sxs-lookup"><span data-stu-id="aa298-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="aa298-115">Explorador de amenazas y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="aa298-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="aa298-116">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="aa298-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="aa298-117">Vistas de campañas</span><span class="sxs-lookup"><span data-stu-id="aa298-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="aa298-118">Para las cuentas de prioridad, puede usar el [informe](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) Problemas de correo electrónico para cuentas de prioridad en el Centro Exchange administración (EAC).</span><span class="sxs-lookup"><span data-stu-id="aa298-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="aa298-119">En este artículo se explica cómo configurar etiquetas de usuario en el portal de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="aa298-119">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="aa298-120">No hay cmdlets en el portal Microsoft 365 Defender para administrar etiquetas de usuario.</span><span class="sxs-lookup"><span data-stu-id="aa298-120">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="aa298-121">Para ver cómo las etiquetas de usuario forman parte de la estrategia para ayudar a proteger las cuentas de usuario de alto impacto, vea Recomendaciones de seguridad para cuentas [de prioridad en Microsoft 365](security-recommendations-for-priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="aa298-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aa298-122">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="aa298-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="aa298-123">Abra el portal Microsoft 365 Defender en <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="aa298-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="aa298-124">Para ir directamente a la **página Etiquetas de** usuario, abra <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="aa298-124">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="aa298-125">Debe tener asignados permisos en el portal de Microsoft 365 Defender antes de poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="aa298-125">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="aa298-126">Para crear, modificar y eliminar etiquetas de usuario, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="aa298-126">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="aa298-127">Para agregar y quitar miembros de etiquetas de usuario existentes, debe ser miembro de los grupos de roles Administración de la **organización,** Administrador de seguridad **o** Operador de seguridad </span><span class="sxs-lookup"><span data-stu-id="aa298-127">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="aa298-128">Para obtener acceso de solo lectura a las etiquetas de usuario, debe ser miembro de los grupos de roles **Lector global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="aa298-128">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="aa298-129">Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="aa298-129">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="aa298-130">Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aa298-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="aa298-131">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="aa298-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="aa298-132">La administración de etiquetas de usuario está controlada por los roles **Lector de** etiquetas y **Administrador de etiquetas.**</span><span class="sxs-lookup"><span data-stu-id="aa298-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="aa298-133">También puede administrar y supervisar cuentas de prioridad en el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="aa298-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="aa298-134">Para obtener instrucciones, vea [Administrar y supervisar cuentas de prioridad](../../admin/setup/priority-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="aa298-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="aa298-135">Para obtener información sobre cómo proteger _cuentas con privilegios_ (cuentas de administrador), vea [este tema](/azure/architecture/framework/security/critical-impact-accounts).</span><span class="sxs-lookup"><span data-stu-id="aa298-135">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="aa298-136">Usar el portal Microsoft 365 Defender para crear etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="aa298-136">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="aa298-137">En el portal de Microsoft 365 Defender, vaya **a** Configuración \> **Correo &** \> **etiquetas de usuario de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="aa298-137">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="aa298-138">En la **página Etiquetas de** usuario, haga clic ![ en Crear icono de etiqueta Crear ](../../media/m365-cc-sc-create-icon.png) **etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="aa298-138">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="aa298-139">El **Asistente para crear** etiquetas se abre en un nuevo menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="aa298-139">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="aa298-140">En la **página Definir etiqueta,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="aa298-140">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="aa298-141">**Nombre:** escriba un nombre descriptivo único para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="aa298-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="aa298-142">Este es el valor que verá y usará.</span><span class="sxs-lookup"><span data-stu-id="aa298-142">This is the value that you'll see and use.</span></span> <span data-ttu-id="aa298-143">Tenga en cuenta que no puede cambiar el nombre de una etiqueta después de crearla.</span><span class="sxs-lookup"><span data-stu-id="aa298-143">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="aa298-144">**Descripción:** escriba una descripción opcional para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="aa298-144">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="aa298-145">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="aa298-145">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="aa298-146">En la página Asignar **miembros,** realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa298-146">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="aa298-147">Haga ![ clic en Agregar miembros icono Agregar ](../../media/m365-cc-sc-create-icon.png) **miembros**.</span><span class="sxs-lookup"><span data-stu-id="aa298-147">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="aa298-148">En el menú desplegable que aparece, siga uno de los pasos siguientes para agregar usuarios o grupos individuales:</span><span class="sxs-lookup"><span data-stu-id="aa298-148">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="aa298-149">Haga clic en el cuadro y desplácese por la lista para seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="aa298-149">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="aa298-150">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="aa298-150">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="aa298-151">Para agregar valores adicionales, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="aa298-151">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="aa298-152">Para quitar entradas individuales, haga clic en</span><span class="sxs-lookup"><span data-stu-id="aa298-152">To remove individual entries, click</span></span> ![Quitar icono de entrada](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="aa298-154">junto a la entrada del cuadro.</span><span class="sxs-lookup"><span data-stu-id="aa298-154">next to the entry in the box.</span></span>
     - <span data-ttu-id="aa298-155">Para quitar todas las entradas, haga clic en Quitar icono de entrada en el elemento Usuarios nn seleccionados y ![ ](../../media/m365-cc-sc-remove-selection-icon.png) **nn grupos** situado debajo del cuadro.</span><span class="sxs-lookup"><span data-stu-id="aa298-155">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="aa298-156">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="aa298-156">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="aa298-157">Back on the **Assign members** page, you can also remove entries by clicking Delete icon next to ![ the ](../../media/m365-cc-sc-delete-icon.png) entry.</span><span class="sxs-lookup"><span data-stu-id="aa298-157">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="aa298-158">Haga **clic en** Importar para seleccionar un archivo de texto que contenga las direcciones de correo electrónico de los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="aa298-158">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="aa298-159">Asegúrese de que el archivo de texto contiene una entrada por línea.</span><span class="sxs-lookup"><span data-stu-id="aa298-159">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="aa298-160">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="aa298-160">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="aa298-161">En la **página Revisar etiqueta** que aparece, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="aa298-161">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="aa298-162">Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="aa298-162">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="aa298-163">También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.</span><span class="sxs-lookup"><span data-stu-id="aa298-163">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="aa298-164">Cuando haya terminado, haga clic en **Enviar** y, a continuación, haga clic **en Listo.**</span><span class="sxs-lookup"><span data-stu-id="aa298-164">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="aa298-165">Usar el portal Microsoft 365 Defender para ver etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="aa298-165">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="aa298-166">En el portal de Microsoft 365 Defender, vaya **a** Configuración \> **Correo &** \> **etiquetas de usuario de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="aa298-166">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="aa298-167">En la **página Etiquetas de** usuario, se muestran las siguientes propiedades en la lista de etiquetas de usuario:</span><span class="sxs-lookup"><span data-stu-id="aa298-167">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="aa298-168">**Tag:** el nombre de la etiqueta de usuario.</span><span class="sxs-lookup"><span data-stu-id="aa298-168">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="aa298-169">Tenga en cuenta que esto incluye la etiqueta del sistema de cuentas **de prioridad** integrada.</span><span class="sxs-lookup"><span data-stu-id="aa298-169">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="aa298-170">**Se aplica a**: El número de miembros</span><span class="sxs-lookup"><span data-stu-id="aa298-170">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="aa298-171">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="aa298-171">**Last modified**</span></span>
   - <span data-ttu-id="aa298-172">**Creado en**</span><span class="sxs-lookup"><span data-stu-id="aa298-172">**Created on**</span></span>

3. <span data-ttu-id="aa298-173">Al seleccionar una etiqueta de usuario haciendo clic en el nombre, los detalles se muestran en un control desplegable.</span><span class="sxs-lookup"><span data-stu-id="aa298-173">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="aa298-174">Usar el portal Microsoft 365 Defender para modificar etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="aa298-174">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="aa298-175">En el portal de Microsoft 365 Defender, vaya **a** Configuración \> **Correo &** \> **etiquetas de usuario de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="aa298-175">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="aa298-176">En la **página Etiquetas de** usuario, seleccione la etiqueta de usuario de la lista y, a continuación, haga clic en Editar icono ![ de etiqueta Editar ](../../media/m365-cc-sc-edit-icon.png) **etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="aa298-176">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="aa298-177">En el control desplegable de detalles que aparece, el mismo asistente y la misma configuración están disponibles como se describe en la sección Usar el portal de [Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-user-tags) para crear etiquetas de usuario anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="aa298-177">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="aa298-178">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="aa298-178">**Notes**:</span></span>

   - <span data-ttu-id="aa298-179">La **página Definir etiqueta** no está  disponible para la etiqueta del sistema de cuentas de prioridad integrada, por lo que no puede cambiar el nombre de esta etiqueta ni cambiar la descripción.</span><span class="sxs-lookup"><span data-stu-id="aa298-179">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="aa298-180">No puede cambiar el nombre de una etiqueta personalizada, pero puede cambiar la descripción.</span><span class="sxs-lookup"><span data-stu-id="aa298-180">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="aa298-181">Usar el portal Microsoft 365 Defender para quitar etiquetas de usuario</span><span class="sxs-lookup"><span data-stu-id="aa298-181">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="aa298-182">No puede quitar la etiqueta del sistema de cuenta de **prioridad** integrada.</span><span class="sxs-lookup"><span data-stu-id="aa298-182">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="aa298-183">En el portal de Microsoft 365 Defender, vaya **a** Configuración \> **Correo &** \> **etiquetas de usuario de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="aa298-183">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="aa298-184">En la **página Etiquetas de** usuario, seleccione la etiqueta de usuario de la lista y, a continuación, haga clic en Eliminar icono ![ de etiqueta Eliminar ](../../media/m365-cc-sc-delete-icon.png) **etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="aa298-184">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="aa298-185">Lea la advertencia en el cuadro de diálogo de confirmación que aparece y, a continuación, haga clic **en Sí, quite**.</span><span class="sxs-lookup"><span data-stu-id="aa298-185">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
