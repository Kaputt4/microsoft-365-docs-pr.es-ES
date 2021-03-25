---
title: Administrar grupos en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Los administradores de organizaciones independientes de Exchange Online Protection (EOP) pueden aprender a crear, modificar y quitar grupos de distribución y grupos de seguridad habilitados para correo en el Centro de administración de Exchange (EAC) y en PowerShell independiente de Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b97e3fac0840753edada964252875a6e3a4fa04
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205059"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="922c3-103">Administrar grupos en EOP</span><span class="sxs-lookup"><span data-stu-id="922c3-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="922c3-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="922c3-104">**Applies to**</span></span>
-  [<span data-ttu-id="922c3-105">Exchange Online Protection independiente</span><span class="sxs-lookup"><span data-stu-id="922c3-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="922c3-106">En organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, puede crear, modificar y quitar los siguientes tipos de grupos:</span><span class="sxs-lookup"><span data-stu-id="922c3-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="922c3-107">**Grupos de distribución:** una colección de usuarios de correo u otros grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="922c3-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="922c3-108">Por ejemplo, equipos u otros grupos ad hoc que necesitan recibir o enviar correo electrónico en un área común de interés.</span><span class="sxs-lookup"><span data-stu-id="922c3-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="922c3-109">Los grupos de distribución son exclusivamente para distribuir mensajes de correo electrónico y no son entidades de seguridad (no pueden tener permisos asignados).</span><span class="sxs-lookup"><span data-stu-id="922c3-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="922c3-110">**Grupos de seguridad habilitados para correo:** una colección de usuarios de correo y otros grupos de seguridad que necesitan permisos de acceso para roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="922c3-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="922c3-111">Por ejemplo, es posible que desee conceder permisos de administrador a un grupo específico de usuarios para que puedan configurar la configuración contra correo no deseado y antimalware.</span><span class="sxs-lookup"><span data-stu-id="922c3-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="922c3-112">De forma predeterminada, los nuevos grupos de seguridad habilitados para correo rechazan mensajes de remitentes externos (no autenticados).</span><span class="sxs-lookup"><span data-stu-id="922c3-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="922c3-113">No agregue grupos de distribución a grupos de seguridad habilitados para correo.</span><span class="sxs-lookup"><span data-stu-id="922c3-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="922c3-114">Puede administrar grupos en el Centro de administración de Exchange (EAC) y en PowerShell independiente de EOP.</span><span class="sxs-lookup"><span data-stu-id="922c3-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="922c3-115">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="922c3-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="922c3-116">Para abrir el Centro de administración de Exchange, vea [Centro de administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="922c3-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="922c3-117">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="922c3-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="922c3-118">Al administrar grupos en PowerShell de EOP independiente, es posible que encuentre limitación.</span><span class="sxs-lookup"><span data-stu-id="922c3-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="922c3-119">Los procedimientos de PowerShell de este artículo usan un método de procesamiento por lotes que da como resultado un retraso de propagación de unos minutos antes de que los resultados de los comandos estén visibles.</span><span class="sxs-lookup"><span data-stu-id="922c3-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="922c3-120">Debe tener asignados permisos en Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="922c3-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="922c3-121">En concreto, necesita el rol Grupos de  **distribución,** que está asignado a los grupos de roles Administración de la organización y **Administración** de destinatarios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="922c3-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="922c3-122">Para obtener más información, vea [Permissions in standalone EOP](feature-permissions-in-eop.md) y [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="922c3-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="922c3-123">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este artículo, vea [Métodos abreviados](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para el Centro de administración de Exchange en Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="922c3-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="922c3-124">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="922c3-124">Having problems?</span></span> <span data-ttu-id="922c3-125">Pida ayuda en el foro de [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) .</span><span class="sxs-lookup"><span data-stu-id="922c3-125">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="922c3-126">Usar el Centro de administración de Exchange para administrar grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="922c3-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="922c3-127">Usar el EAC para crear grupos</span><span class="sxs-lookup"><span data-stu-id="922c3-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="922c3-128">En el EAC, vaya a **Grupos de** \> **destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="922c3-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="922c3-129">Haga **clic en** Nuevo icono Nuevo ![ ](../../media/ITPro-EAC-AddIcon.png) y, a continuación, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="922c3-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="922c3-130">**Grupo de distribución**</span><span class="sxs-lookup"><span data-stu-id="922c3-130">**Distribution group**</span></span>

   - <span data-ttu-id="922c3-131">**Grupo de seguridad habilitado para correo**</span><span class="sxs-lookup"><span data-stu-id="922c3-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="922c3-132">En la nueva página de grupo que se abre, configure las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="922c3-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="922c3-133">Se requiere una configuración <sup>\*</sup> marcada con una.</span><span class="sxs-lookup"><span data-stu-id="922c3-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="922c3-134"><sup>\*</sup>**Nombre para** mostrar: este nombre aparece en la libreta de direcciones de la organización,  en la línea Para: cuando se envía correo electrónico a este grupo y en la lista Grupos del EAC.</span><span class="sxs-lookup"><span data-stu-id="922c3-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="922c3-135">El nombre para mostrar es obligatorio, debe ser único y debe ser fácil de usar para que las personas reconozcan lo que es.</span><span class="sxs-lookup"><span data-stu-id="922c3-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="922c3-136"><sup>\*</sup>**Alias:** use este cuadro para escribir el nombre del alias del grupo.</span><span class="sxs-lookup"><span data-stu-id="922c3-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="922c3-137">El alias no puede superar los 64 caracteres y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="922c3-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="922c3-138">Cuando un usuario tipos el alias en la línea Para de un mensaje de correo electrónico, se resuelve en el nombre para mostrar del grupo.</span><span class="sxs-lookup"><span data-stu-id="922c3-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="922c3-139"><sup>\*</sup>**Dirección de correo** electrónico: la dirección de correo electrónico consta del alias en el lado izquierdo del símbolo at (@) y un dominio en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="922c3-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="922c3-140">De forma predeterminada, el valor de **Alias** se usa para el valor de alias, pero puede cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="922c3-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="922c3-141">Para el valor de dominio, haga clic en el menú desplegable y seleccione y acepte el dominio en su organización.</span><span class="sxs-lookup"><span data-stu-id="922c3-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="922c3-142">**Descripción:** esta descripción aparece en la libreta de direcciones y en el panel Detalles del EAC.</span><span class="sxs-lookup"><span data-stu-id="922c3-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="922c3-143"><sup>\*</sup>**Propietarios:** un propietario de grupo puede administrar la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="922c3-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="922c3-144">De forma predeterminada, la persona que crea un grupo pasa a ser el propietario.</span><span class="sxs-lookup"><span data-stu-id="922c3-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="922c3-145">Todos los grupos deben tener al menos un propietario.</span><span class="sxs-lookup"><span data-stu-id="922c3-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="922c3-146">Para agregar propietarios, haga clic **en Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="922c3-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="922c3-147">En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic **en Agregar ->**.</span><span class="sxs-lookup"><span data-stu-id="922c3-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="922c3-148">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="922c3-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="922c3-149">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="922c3-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="922c3-150">Para quitar un propietario, seleccione el propietario y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="922c3-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="922c3-151">**Miembros:** agregar y quitar miembros de grupo.</span><span class="sxs-lookup"><span data-stu-id="922c3-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="922c3-152">Para agregar miembros, haga clic **en Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="922c3-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="922c3-153">En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic **en Agregar ->**.</span><span class="sxs-lookup"><span data-stu-id="922c3-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="922c3-154">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="922c3-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="922c3-155">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="922c3-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="922c3-156">Para quitar un miembro, seleccione el miembro y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="922c3-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="922c3-157">Cuando haya terminado, haga clic en **Guardar** para crear el grupo de distribución.</span><span class="sxs-lookup"><span data-stu-id="922c3-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="922c3-158">Usar el EAC para modificar grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="922c3-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="922c3-159">En el EAC, vaya a **Grupos de** \> **destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="922c3-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="922c3-160">En la lista de grupos, seleccione el grupo de distribución o el grupo de seguridad habilitado para correo que desea modificar y, a continuación, haga clic **en Editar** icono ![ Editar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="922c3-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="922c3-161">En la página de propiedades del grupo de distribución que se abre, haga clic en una de las siguientes pestañas para ver o cambiar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="922c3-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="922c3-162">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="922c3-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="922c3-163">General</span><span class="sxs-lookup"><span data-stu-id="922c3-163">General</span></span>

<span data-ttu-id="922c3-164">Use esta pestaña para ver o cambiar información básica sobre el grupo.</span><span class="sxs-lookup"><span data-stu-id="922c3-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="922c3-165">**Nombre para** mostrar: este nombre aparece en la libreta de direcciones, en la línea Para cuando se envía correo electrónico a este grupo y en la **lista Grupos**.</span><span class="sxs-lookup"><span data-stu-id="922c3-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="922c3-166">El nombre para mostrar es obligatorio y debe ser sencillo para que los usuarios puedan identificarlo.</span><span class="sxs-lookup"><span data-stu-id="922c3-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="922c3-167">También tiene que ser único en su dominio.</span><span class="sxs-lookup"><span data-stu-id="922c3-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="922c3-168">Si ha implementado una directiva de nomenclatura de grupo, el nombre para mostrar tiene que cumplir al formato de nomenclatura definido por la directiva.</span><span class="sxs-lookup"><span data-stu-id="922c3-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="922c3-169">**Alias:** esta es la parte de la dirección de correo electrónico que aparece a la izquierda del símbolo at (@).</span><span class="sxs-lookup"><span data-stu-id="922c3-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="922c3-170">Si cambia el alias, la dirección SMTP primaria para el grupo también cambiará y contendrá el nuevo alias.</span><span class="sxs-lookup"><span data-stu-id="922c3-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="922c3-171">Además, la dirección de correo electrónico con el alias anterior se mantendrá como dirección proxy para el grupo.</span><span class="sxs-lookup"><span data-stu-id="922c3-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="922c3-172">**Dirección de correo** electrónico: la dirección de correo electrónico consta del alias en el lado izquierdo del símbolo at (@) y un dominio en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="922c3-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="922c3-173">De forma predeterminada, el valor de **Alias** se usa para el valor de alias, pero puede cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="922c3-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="922c3-174">Para el valor de dominio, haga clic en el menú desplegable y seleccione y acepte el dominio en su organización.</span><span class="sxs-lookup"><span data-stu-id="922c3-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="922c3-175">**Descripción:** esta descripción aparece en la libreta de direcciones y en el panel Detalles del EAC.</span><span class="sxs-lookup"><span data-stu-id="922c3-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="922c3-176">Ownership</span><span class="sxs-lookup"><span data-stu-id="922c3-176">Ownership</span></span>

<span data-ttu-id="922c3-177">Use esta pestaña para asignar propietarios de grupos.</span><span class="sxs-lookup"><span data-stu-id="922c3-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="922c3-178">Un propietario de grupo puede administrar la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="922c3-178">A group owner can manage group membership.</span></span> <span data-ttu-id="922c3-179">De forma predeterminada, la persona que crea un grupo pasa a ser el propietario.</span><span class="sxs-lookup"><span data-stu-id="922c3-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="922c3-180">Todos los grupos deben tener al menos un propietario.</span><span class="sxs-lookup"><span data-stu-id="922c3-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="922c3-181">Para agregar propietarios, haga clic **en Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="922c3-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="922c3-182">En el cuadro de diálogo que aparece, busque y seleccione un destinatario y, a continuación, haga clic **en Agregar ->**.</span><span class="sxs-lookup"><span data-stu-id="922c3-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="922c3-183">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="922c3-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="922c3-184">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="922c3-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="922c3-185">Para quitar un propietario, seleccione el propietario y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="922c3-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="922c3-186">Pertenencia</span><span class="sxs-lookup"><span data-stu-id="922c3-186">Membership</span></span>

<span data-ttu-id="922c3-187">Use esta pestaña para agregar o quitar miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="922c3-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="922c3-188">Los propietarios de grupos no necesitan ser miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="922c3-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="922c3-189">Para agregar miembros, haga clic **en Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="922c3-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="922c3-190">En el cuadro de diálogo que aparece, busque y seleccione un destinatario o grupo y, a continuación, haga clic **en Agregar ->**.</span><span class="sxs-lookup"><span data-stu-id="922c3-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="922c3-191">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="922c3-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="922c3-192">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="922c3-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="922c3-193">Para quitar un miembro, seleccione el miembro y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="922c3-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="922c3-194">Usar el EAC para quitar grupos</span><span class="sxs-lookup"><span data-stu-id="922c3-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="922c3-195">En el EAC, vaya a **Grupos de** \> **destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="922c3-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="922c3-196">En la lista de grupos, seleccione el grupo de distribución que desea quitar y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="922c3-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="922c3-197">Usar PowerShell para administrar grupos</span><span class="sxs-lookup"><span data-stu-id="922c3-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="922c3-198">Usar PowerShell de EOP independiente para ver grupos</span><span class="sxs-lookup"><span data-stu-id="922c3-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="922c3-199">Para devolver una lista resumida de todos los grupos de distribución y grupos de seguridad habilitados para correo en PowerShell de EOP independiente, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="922c3-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="922c3-200">Para devolver la lista de miembros del grupo, reemplace por el nombre, alias o dirección de correo electrónico del grupo \<GroupIdentity\> y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="922c3-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="922c3-201">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-Recipient](/powershell/module/exchange/get-recipient) y [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="922c3-201">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="922c3-202">Usar PowerShell de EOP independiente para crear grupos</span><span class="sxs-lookup"><span data-stu-id="922c3-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="922c3-203">Para crear grupos de distribución o grupos de seguridad habilitados para correo en PowerShell de EOP independiente, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="922c3-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="922c3-204">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="922c3-204">**Notes**:</span></span>

- <span data-ttu-id="922c3-205">El _parámetro Name_ es obligatorio, tiene una longitud máxima de 64 caracteres y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="922c3-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="922c3-206">Si no usa el parámetro _DisplayName_, se emplea el valor del parámetro _Name_ para el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="922c3-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="922c3-207">Si no usa el parámetro _Alias,_ se usará el parámetro _Name_ para el valor de alias.</span><span class="sxs-lookup"><span data-stu-id="922c3-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="922c3-208">Los espacios se quitan y los caracteres no compatibles se convierten en signos de interrogación (?).</span><span class="sxs-lookup"><span data-stu-id="922c3-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="922c3-209">Si no usa el parámetro _PrimarySmtpAddress,_ el valor de alias se usa en el _parámetro PrimarySmtpAddress._</span><span class="sxs-lookup"><span data-stu-id="922c3-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="922c3-210">Si no usa el parámetro _Type,_ el valor predeterminado es Distribution.</span><span class="sxs-lookup"><span data-stu-id="922c3-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="922c3-211">En este ejemplo se crea un grupo de distribución denominado Administradores de TI con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="922c3-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="922c3-212">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="922c3-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="922c3-213">Usar PowerShell de EOP independiente para modificar grupos</span><span class="sxs-lookup"><span data-stu-id="922c3-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="922c3-214">Para modificar grupos en PowerShell de EOP independiente, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="922c3-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="922c3-215">En este ejemplo se cambia la dirección SMTP principal (también denominada dirección de respuesta) del grupo Empleados de Seattle a sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="922c3-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="922c3-216">En este ejemplo se reemplazan los miembros actuales del grupo equipo de seguridad por Kitty Petersen y Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="922c3-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="922c3-217">En este ejemplo, se agrega un nuevo usuario denominado Tyson Fawcett al grupo denominado Equipo de seguridad mientras se conservan los miembros actuales del grupo.</span><span class="sxs-lookup"><span data-stu-id="922c3-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="922c3-218">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) y [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="922c3-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="922c3-219">Quitar un grupo mediante una Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="922c3-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="922c3-220">En este ejemplo se quita el grupo de distribución denominado Administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="922c3-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="922c3-221">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="922c3-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="922c3-222">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="922c3-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="922c3-223">Para comprobar que ha creado, modificado o quitado correctamente un grupo de distribución o un grupo de seguridad habilitado para correo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="922c3-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="922c3-224">En el EAC, vaya a **Grupos de** \> **destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="922c3-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="922c3-225">Compruebe que el grupo aparece (o no aparece) y compruebe el **valor tipo de** grupo.</span><span class="sxs-lookup"><span data-stu-id="922c3-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="922c3-226">Seleccione el grupo y vea la información en el panel Detalles o haga clic **en Editar** icono Editar para ver ![ la ](../../media/ITPro-EAC-AddIcon.png) configuración.</span><span class="sxs-lookup"><span data-stu-id="922c3-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="922c3-227">En PowerShell de EOP independiente, ejecute el siguiente comando para comprobar que el grupo aparece (o no aparece):</span><span class="sxs-lookup"><span data-stu-id="922c3-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="922c3-228">Reemplace por el nombre, alias o dirección de correo electrónico del grupo y \<GroupIdentity\> ejecute el siguiente comando para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="922c3-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="922c3-229">Para ver los miembros del grupo, reemplace por el nombre, alias o dirección de correo electrónico del grupo y \<GroupIdentity\> ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="922c3-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```