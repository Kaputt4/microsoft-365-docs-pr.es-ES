---
title: Administrar grupos en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Los administradores de organizaciones independientes de Exchange Online Protection (EOP) pueden obtener información sobre cómo crear, modificar y quitar grupos de distribución y grupos de seguridad habilitados para correo en el centro de administración de Exchange (EAC) y en PowerShell de Exchange Online Protection (EOP) independientes.
ms.openlocfilehash: 42086b67e22df4725bf07bf227853c070f936f24
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616507"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="9811e-103">Administrar grupos en EOP</span><span class="sxs-lookup"><span data-stu-id="9811e-103">Manage groups in EOP</span></span>

<span data-ttu-id="9811e-104">En las organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, puede crear, modificar y quitar los siguientes tipos de grupos:</span><span class="sxs-lookup"><span data-stu-id="9811e-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="9811e-105">**Grupos de distribución**: una colección de usuarios de correo u otros grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="9811e-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="9811e-106">Por ejemplo, Microsoft Teams u otros grupos ad hoc que necesiten recibir o enviar correo electrónico en un área común de interés.</span><span class="sxs-lookup"><span data-stu-id="9811e-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="9811e-107">Los grupos de distribución están exclusivamente destinados a la distribución de mensajes de correo electrónico y no son entidades de seguridad (no pueden tener permisos asignados).</span><span class="sxs-lookup"><span data-stu-id="9811e-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="9811e-108">**Grupos de seguridad habilitados para correo**: una colección de usuarios de correo y otros grupos de seguridad que necesitan permisos de acceso para los roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="9811e-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="9811e-109">Por ejemplo, es posible que desee conceder a un grupo específico de permisos de administrador de usuarios para que puedan configurar las opciones de protección contra correo electrónico no deseado y antimalware.</span><span class="sxs-lookup"><span data-stu-id="9811e-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <ul><li><span data-ttu-id="9811e-110">De forma predeterminada, los grupos de seguridad habilitados para correo nuevos rechazan los mensajes de remitentes externos (sin autenticar).</span><span class="sxs-lookup"><span data-stu-id="9811e-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span></li><li><span data-ttu-id="9811e-111">No agregue grupos de distribución a grupos de seguridad habilitados para correo.</span><span class="sxs-lookup"><span data-stu-id="9811e-111">Don't add distribution groups to mail-enabled security groups.</span></span></li></ul><span data-ttu-id="9811e-112">.</span><span class="sxs-lookup"><span data-stu-id="9811e-112">.</span></span>

<span data-ttu-id="9811e-113">Puede administrar los grupos en el centro de administración de Exchange (EAC) y en PowerShell independiente de EOP.</span><span class="sxs-lookup"><span data-stu-id="9811e-113">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9811e-114">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="9811e-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9811e-115">Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9811e-115">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="9811e-116">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="9811e-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9811e-117">Al administrar grupos en PowerShell independiente de EOP, puede encontrarse con limitaciones.</span><span class="sxs-lookup"><span data-stu-id="9811e-117">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="9811e-118">Los procedimientos de PowerShell de este tema usan un método de procesamiento por lotes que da como resultado un retraso en la propagación de unos minutos antes de que los resultados de los comandos estén visibles.</span><span class="sxs-lookup"><span data-stu-id="9811e-118">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="9811e-119">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="9811e-119">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="9811e-120">En concreto, necesita el rol grupos de distribución, que se asigna a los grupos de roles OrganizationManagement (administradores globales) y RecipientManagement de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9811e-120">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="9811e-121">Para obtener más información, vea [permisos en EOP independiente](feature-permissions-in-eop.md) y [usar el EAC para modificar la lista de miembros de los grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="9811e-121">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="9811e-122">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="9811e-122">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="9811e-123">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="9811e-123">Having problems?</span></span> <span data-ttu-id="9811e-124">Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="9811e-124">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="9811e-125">Usar el centro de administración de Exchange para administrar grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="9811e-125">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="9811e-126">Usar el EAC para crear grupos</span><span class="sxs-lookup"><span data-stu-id="9811e-126">Use the EAC to create groups</span></span>

1. <span data-ttu-id="9811e-127">En el EAC, vaya a grupos de **destinatarios** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="9811e-127">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="9811e-128">Haga clic en **nuevo** ![ icono nuevo ](../../media/ITPro-EAC-AddIcon.png) y, a continuación, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9811e-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="9811e-129">**Grupo de distribución**</span><span class="sxs-lookup"><span data-stu-id="9811e-129">**Distribution group**</span></span>

   - <span data-ttu-id="9811e-130">**Grupo de seguridad habilitado para correo**</span><span class="sxs-lookup"><span data-stu-id="9811e-130">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="9811e-131">En la página nuevo grupo que se abre, configure las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="9811e-131">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="9811e-132">La configuración marcada con un <sup>\*</sup> es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9811e-132">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="9811e-133"><sup>\*</sup>**Nombre para mostrar**: este nombre aparece en la libreta de direcciones de la organización, en la línea para: cuando se envía un correo electrónico a este grupo y en la lista **grupos** del EAC.</span><span class="sxs-lookup"><span data-stu-id="9811e-133"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="9811e-134">El nombre para mostrar es obligatorio, debe ser único y debe ser fácil de usar para que los usuarios reconozcan lo que es.</span><span class="sxs-lookup"><span data-stu-id="9811e-134">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="9811e-135"><sup>\*</sup>**Alias**: Use este cuadro para escribir el nombre del alias para el grupo.</span><span class="sxs-lookup"><span data-stu-id="9811e-135"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="9811e-136">El alias no puede superar los 64 caracteres y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="9811e-136">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="9811e-137">Cuando un usuario escribe el alias en la línea para de un mensaje de correo electrónico, se resuelve en el nombre para mostrar del grupo.</span><span class="sxs-lookup"><span data-stu-id="9811e-137">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="9811e-138"><sup>\*</sup>**Dirección de correo electrónico**: la dirección de correo electrónico consta del alias del lado izquierdo del símbolo arroba (@) y de un dominio en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="9811e-138"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="9811e-139">De forma predeterminada, el valor de **alias** se usa para el valor de alias, pero puede cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="9811e-139">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="9811e-140">Para el valor dominio, haga clic en la lista desplegable y seleccione el dominio y el aceptado en su organización.</span><span class="sxs-lookup"><span data-stu-id="9811e-140">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="9811e-141">**Descripción**: esta descripción aparece en la libreta de direcciones y en el panel de detalles del EAC.</span><span class="sxs-lookup"><span data-stu-id="9811e-141">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="9811e-142"><sup>\*</sup>**Propietarios**: un propietario de grupo puede administrar la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="9811e-142"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="9811e-143">De forma predeterminada, la persona que crea un grupo pasa a ser el propietario.</span><span class="sxs-lookup"><span data-stu-id="9811e-143">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="9811e-144">Todos los grupos deben tener al menos un propietario.</span><span class="sxs-lookup"><span data-stu-id="9811e-144">All groups must have at least one owner.</span></span>

     <span data-ttu-id="9811e-145">Para agregar propietarios, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9811e-145">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9811e-146">En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic en **agregar >**.</span><span class="sxs-lookup"><span data-stu-id="9811e-146">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="9811e-147">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9811e-147">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="9811e-148">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9811e-148">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="9811e-149">Para quitar un propietario, seleccione el propietario y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="9811e-149">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="9811e-150">**Miembros**: agregar y quitar miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="9811e-150">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="9811e-151">Para agregar miembros, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9811e-151">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9811e-152">En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic en **agregar >**.</span><span class="sxs-lookup"><span data-stu-id="9811e-152">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="9811e-153">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9811e-153">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="9811e-154">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9811e-154">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="9811e-155">Para quitar un miembro, selecciónelo y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="9811e-155">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="9811e-156">Cuando haya terminado, haga clic en **Guardar** para crear el grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="9811e-156">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="9811e-157">Usar el EAC para modificar grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="9811e-157">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="9811e-158">En el EAC, vaya a grupos de **destinatarios** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="9811e-158">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="9811e-159">En la lista de grupos, seleccione el grupo de distribución o grupo de seguridad habilitado para correo que desea modificar y, a continuación, haga clic en **Editar** ![ icono de edición ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9811e-159">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="9811e-160">En la página de propiedades del grupo de distribución que se abre, haga clic en una de las siguientes pestañas para ver o cambiar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="9811e-160">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="9811e-161">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9811e-161">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="9811e-162">General</span><span class="sxs-lookup"><span data-stu-id="9811e-162">General</span></span>

<span data-ttu-id="9811e-163">Use esta ficha para ver o cambiar la información básica sobre el grupo.</span><span class="sxs-lookup"><span data-stu-id="9811e-163">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="9811e-164">**Nombre para mostrar**: este nombre aparece en la libreta de direcciones, en la línea para cuando se envía un correo electrónico a este grupo, y en la **lista grupos**.</span><span class="sxs-lookup"><span data-stu-id="9811e-164">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="9811e-165">El nombre para mostrar es obligatorio y debe ser sencillo para que los usuarios puedan identificarlo.</span><span class="sxs-lookup"><span data-stu-id="9811e-165">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="9811e-166">También tiene que ser único en su dominio.</span><span class="sxs-lookup"><span data-stu-id="9811e-166">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="9811e-167">Si ha implementado una directiva de nomenclatura de grupo, el nombre para mostrar tiene que cumplir al formato de nomenclatura definido por la directiva.</span><span class="sxs-lookup"><span data-stu-id="9811e-167">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="9811e-168">**Alias**: es la parte de la dirección de correo electrónico que aparece a la izquierda del símbolo arroba (@).</span><span class="sxs-lookup"><span data-stu-id="9811e-168">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="9811e-169">Si cambia el alias, la dirección SMTP primaria para el grupo también cambiará y contendrá el nuevo alias.</span><span class="sxs-lookup"><span data-stu-id="9811e-169">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="9811e-170">Además, la dirección de correo electrónico con el alias anterior se mantendrá como dirección proxy para el grupo.</span><span class="sxs-lookup"><span data-stu-id="9811e-170">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="9811e-171">**Dirección de correo electrónico**: la dirección de correo electrónico consta del alias del lado izquierdo del símbolo arroba (@) y de un dominio en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="9811e-171">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="9811e-172">De forma predeterminada, el valor de **alias** se usa para el valor de alias, pero puede cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="9811e-172">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="9811e-173">Para el valor dominio, haga clic en la lista desplegable y seleccione el dominio y el aceptado en su organización.</span><span class="sxs-lookup"><span data-stu-id="9811e-173">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="9811e-174">**Descripción**: esta descripción aparece en la libreta de direcciones y en el panel de detalles del EAC.</span><span class="sxs-lookup"><span data-stu-id="9811e-174">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="9811e-175">Ownership</span><span class="sxs-lookup"><span data-stu-id="9811e-175">Ownership</span></span>

<span data-ttu-id="9811e-176">Use esta ficha para asignar propietarios de grupo.</span><span class="sxs-lookup"><span data-stu-id="9811e-176">Use this tab to assign group owners.</span></span> <span data-ttu-id="9811e-177">Un propietario de grupo puede administrar la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="9811e-177">A group owner can manage group membership.</span></span> <span data-ttu-id="9811e-178">De forma predeterminada, la persona que crea un grupo pasa a ser el propietario.</span><span class="sxs-lookup"><span data-stu-id="9811e-178">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="9811e-179">Todos los grupos deben tener al menos un propietario.</span><span class="sxs-lookup"><span data-stu-id="9811e-179">All groups must have at least one owner.</span></span>

<span data-ttu-id="9811e-180">Para agregar propietarios, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9811e-180">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9811e-181">En el cuadro de diálogo que aparece, busque y seleccione un destinatario y, a continuación, haga clic en **agregar >**.</span><span class="sxs-lookup"><span data-stu-id="9811e-181">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="9811e-182">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9811e-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="9811e-183">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9811e-183">When you're finished, click **OK**.</span></span>

<span data-ttu-id="9811e-184">Para quitar un propietario, seleccione el propietario y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="9811e-184">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="9811e-185">Pertenencia</span><span class="sxs-lookup"><span data-stu-id="9811e-185">Membership</span></span>

<span data-ttu-id="9811e-186">Use esta ficha para agregar o quitar miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="9811e-186">Use this tab to add or remove group members.</span></span> <span data-ttu-id="9811e-187">No es necesario que los propietarios del grupo sean miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="9811e-187">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="9811e-188">Para agregar miembros, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9811e-188">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9811e-189">En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic en **agregar >**.</span><span class="sxs-lookup"><span data-stu-id="9811e-189">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="9811e-190">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9811e-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="9811e-191">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9811e-191">When you're finished, click **OK**.</span></span>

<span data-ttu-id="9811e-192">Para quitar un miembro, selecciónelo y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="9811e-192">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="9811e-193">Usar el EAC para quitar grupos</span><span class="sxs-lookup"><span data-stu-id="9811e-193">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="9811e-194">En el EAC, vaya a grupos de **destinatarios** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="9811e-194">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="9811e-195">En la lista de grupos, seleccione el grupo de distribución que desea quitar y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="9811e-195">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="9811e-196">Usar PowerShell para administrar grupos</span><span class="sxs-lookup"><span data-stu-id="9811e-196">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="9811e-197">Usar PowerShell independiente de EOP para ver grupos</span><span class="sxs-lookup"><span data-stu-id="9811e-197">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="9811e-198">Para obtener una lista resumida de todos los grupos de distribución y grupos de seguridad habilitados para correo en el PowerShell independiente de EOP, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9811e-198">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="9811e-199">Para devolver la lista de miembros del grupo, reemplace \<GroupIdentity\> por el nombre, el alias o la dirección de correo electrónico del grupo y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9811e-199">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="9811e-200">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) y [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="9811e-200">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="9811e-201">Usar un PowerShell independiente de EOP para crear grupos</span><span class="sxs-lookup"><span data-stu-id="9811e-201">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="9811e-202">Para crear grupos de distribución o grupos de seguridad habilitados para correo en el PowerShell independiente de EOP, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="9811e-202">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="9811e-203">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="9811e-203">**Notes**:</span></span>

- <span data-ttu-id="9811e-204">El parámetro _Name_ es obligatorio, tiene una longitud máxima de 64 caracteres y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="9811e-204">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="9811e-205">Si no usa el parámetro _DisplayName_, se emplea el valor del parámetro _Name_ para el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="9811e-205">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="9811e-206">Si no usa el parámetro _alias_ , se usa el parámetro _Name_ para el valor alias.</span><span class="sxs-lookup"><span data-stu-id="9811e-206">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="9811e-207">Los espacios se quitan y los caracteres no admitidos se convierten en signos de interrogación (?).</span><span class="sxs-lookup"><span data-stu-id="9811e-207">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="9811e-208">Si no usa el parámetro _PrimarySmtpAddress_ , el valor de alias se usa en el parámetro _PrimarySmtpAddress_ .</span><span class="sxs-lookup"><span data-stu-id="9811e-208">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="9811e-209">Si no usa el parámetro _Type_ , el valor predeterminado es Distribution.</span><span class="sxs-lookup"><span data-stu-id="9811e-209">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="9811e-210">En este ejemplo se crea un grupo de distribución denominado administradores de TI con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="9811e-210">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="9811e-211">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="9811e-211">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="9811e-212">Usar PowerShell independiente de EOP para modificar grupos</span><span class="sxs-lookup"><span data-stu-id="9811e-212">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="9811e-213">Para modificar grupos en PowerShell independiente de EOP, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="9811e-213">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="9811e-214">En este ejemplo se usan los cambios en la dirección SMTP principal (también denominada dirección de respuesta) del grupo empleados de Seattle en sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9811e-214">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="9811e-215">En este ejemplo se reemplazan los miembros actuales del grupo de equipo de seguridad por Kitty Petersen y Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="9811e-215">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="9811e-216">En este ejemplo se agrega un nuevo usuario denominado Tyson Fawcett al grupo denominado equipo de seguridad y se conservan los miembros actuales del grupo.</span><span class="sxs-lookup"><span data-stu-id="9811e-216">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="9811e-217">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) y [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="9811e-217">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="9811e-218">Quitar un grupo mediante Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="9811e-218">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="9811e-219">En este ejemplo se quita el grupo de distribución denominado administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="9811e-219">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="9811e-220">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="9811e-220">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9811e-221">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="9811e-221">How do you know these procedures worked?</span></span>

<span data-ttu-id="9811e-222">Para comprobar que ha creado, modificado o quitado correctamente un grupo de distribución o un grupo de seguridad habilitado para correo, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9811e-222">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="9811e-223">En el EAC, vaya a grupos de **destinatarios** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="9811e-223">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="9811e-224">Compruebe que el grupo aparece (o no aparece en la lista) y compruebe el valor del **tipo de grupo** .</span><span class="sxs-lookup"><span data-stu-id="9811e-224">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="9811e-225">Seleccione el grupo y vea la información en el panel de detalles o haga clic en **Editar** ![ icono Editar ](../../media/ITPro-EAC-AddIcon.png) para ver la configuración.</span><span class="sxs-lookup"><span data-stu-id="9811e-225">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="9811e-226">En PowerShell independiente de EOP, ejecute el siguiente comando para comprobar que el grupo aparece (o no aparece en la lista):</span><span class="sxs-lookup"><span data-stu-id="9811e-226">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="9811e-227">Reemplace \<GroupIdentity\> por el nombre, el alias o la dirección de correo electrónico del grupo y ejecute el siguiente comando para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="9811e-227">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="9811e-228">Para ver los miembros del grupo, reemplace \<GroupIdentity\> por el nombre, el alias o la dirección de correo electrónico del grupo y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9811e-228">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
