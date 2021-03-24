---
title: Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Los usuarios deben tener asignados permisos en el Centro de seguridad y cumplimiento de Microsoft 365 & para poder administrar cualquiera de sus características de seguridad o cumplimiento.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 16dbbe81d1131821dfdbf75caff5b5121f8cc45b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071416"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="6864a-103">Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6864a-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6864a-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="6864a-104">**Applies to**</span></span>
- [<span data-ttu-id="6864a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6864a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6864a-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6864a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6864a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6864a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6864a-108">Los usuarios deben tener asignados permisos en el Centro de seguridad & cumplimiento para poder administrar cualquiera de sus características de seguridad o cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6864a-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="6864a-109">Como administrador global o miembro del grupo de roles OrganizationManagement en el Centro de seguridad & cumplimiento, puede conceder estos permisos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6864a-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="6864a-110">Los usuarios solo podrán administrar las características de seguridad o cumplimiento a las que les proporcione acceso.</span><span class="sxs-lookup"><span data-stu-id="6864a-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="6864a-111">Para obtener más información acerca de los diferentes permisos que puede conceder a los usuarios en el Centro de seguridad & y cumplimiento, consulte Permisos en el Centro de [seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6864a-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6864a-112">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="6864a-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6864a-113">Debe ser administrador global o miembro del grupo de roles OrganizationManagement en el Centro de seguridad & cumplimiento, para completar los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="6864a-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="6864a-114">Los grupos de roles del Centro de & seguridad pueden tener nombres similares a los grupos de roles en Exchange Online, pero no son los mismos.</span><span class="sxs-lookup"><span data-stu-id="6864a-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="6864a-115">Las pertenencias a grupos de roles no se comparten entre Exchange Online y el Centro de & seguridad.</span><span class="sxs-lookup"><span data-stu-id="6864a-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="6864a-116">Los asociados de permisos de acceso delegados (DAP) con permisos Administrar en nombre de (AOBO) no pueden acceder al Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6864a-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="6864a-117">Usar el Centro de seguridad & cumplimiento para dar a otro usuario acceso al Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6864a-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="6864a-118">Abra el Centro de seguridad & cumplimiento en y, a <https://protection.office.com> continuación, vaya a **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="6864a-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="6864a-119">Para ir directamente a la **pestaña Permisos,** abra <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="6864a-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="6864a-120">En la lista de grupos de roles, elija el grupo de funciones y, a continuación, haga clic **en Editar** icono ![ Editar ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="6864a-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="6864a-121">En la página propiedades del grupo de roles en Miembros, haga clic en Agregar icono y seleccione el nombre del usuario ![ ](../../media/ITPro-EAC-AddIcon.gif) (o usuarios) que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="6864a-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="6864a-122">Cuando haya seleccionado todos los usuarios que desea agregar al grupo de roles, haga clic en **agregar \> y,** a continuación, **en Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6864a-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="6864a-123">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6864a-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="6864a-124">Usar PowerShell & centro de seguridad y cumplimiento para dar a otro usuario acceso al Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6864a-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="6864a-125">[Conectarse a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="6864a-125">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="6864a-126">Utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6864a-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="6864a-127">Para obtener información detallada acerca de los problemas de sintaxis y parámetros, [vea Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="6864a-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6864a-128">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="6864a-128">How do you know this worked?</span></span>

<span data-ttu-id="6864a-129">Para comprobar que ha concedido acceso correctamente al Centro de seguridad y & cumplimiento, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6864a-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="6864a-130">En el Centro de & cumplimiento, vaya a **Permisos** y seleccione el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="6864a-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="6864a-131">En el menú desplegable de detalles que se abre, compruebe los miembros del grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="6864a-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="6864a-132">En PowerShell & Centro de seguridad y cumplimiento, reemplace por el nombre del grupo de roles \<RoleGroupName\> y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="6864a-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="6864a-133">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="6864a-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).</span></span>