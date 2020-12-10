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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Los usuarios deben tener asignados permisos en el centro de seguridad & cumplimiento de Microsoft 365 para que puedan administrar cualquiera de sus características de seguridad o cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1bf8da85a0e090a9d74934ea5084f547d6a8794f
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616613"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="587de-103">Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="587de-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="587de-104">Los usuarios deben tener asignados permisos en el centro de seguridad & cumplimiento antes de que puedan administrar cualquiera de sus características de seguridad o cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="587de-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="587de-105">Como administrador global o miembro del grupo de funciones OrganizationManagement en el centro de seguridad & cumplimiento, puede conceder estos permisos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="587de-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="587de-106">Los usuarios solo podrán administrar las características de seguridad o cumplimiento a las que les proporcione acceso.</span><span class="sxs-lookup"><span data-stu-id="587de-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="587de-107">Para obtener más información acerca de los distintos permisos que puede conceder a los usuarios en el centro de seguridad & cumplimiento, consulte [permisos en el centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="587de-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="587de-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="587de-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="587de-109">Debe ser un administrador global o miembro del grupo de funciones OrganizationManagement en el centro de seguridad & cumplimiento para completar los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="587de-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="587de-110">Los grupos de roles para el centro de seguridad & cumplimiento pueden tener nombres similares a los grupos de roles en Exchange Online, pero no son los mismos.</span><span class="sxs-lookup"><span data-stu-id="587de-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="587de-111">Las pertenencias a grupos de roles no se comparten entre Exchange Online y el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="587de-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="587de-112">Los permisos de acceso delegado (DAP) asociados con administrar en nombre de (AOBO) no pueden obtener acceso al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="587de-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="587de-113">Usar el centro de seguridad & cumplimiento para conceder a otro usuario acceso al centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="587de-113">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="587de-114">Abra el centro de seguridad & cumplimiento en <https://protection.office.com> y vaya a **permisos**.</span><span class="sxs-lookup"><span data-stu-id="587de-114">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="587de-115">Para ir directamente a la pestaña **permisos** , Abra <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="587de-115">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="587de-116">En la lista de grupos de roles, elija el grupo de roles y, a continuación, haga clic en **Editar** ![ icono de edición ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="587de-116">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="587de-117">En la página de propiedades del grupo de roles, en **miembros**, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.gif) y seleccione el nombre del usuario (o usuarios) que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="587de-117">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="587de-118">Cuando haya seleccionado todos los usuarios que desee agregar al grupo de roles, haga clic en **agregar \>** y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="587de-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="587de-119">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="587de-119">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="587de-120">Usar el PowerShell del centro de cumplimiento de & de seguridad para proporcionar a otro usuario acceso al centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="587de-120">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="587de-121">[Conéctese al Centro de seguridad y cumplimiento de PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="587de-121">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="587de-122">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="587de-122">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="587de-123">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="587de-123">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="587de-124">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="587de-124">How do you know this worked?</span></span>

<span data-ttu-id="587de-125">Para comprobar que se ha concedido correctamente el acceso al centro de seguridad & cumplimiento, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="587de-125">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="587de-126">En el centro de seguridad & cumplimiento, vaya a **permisos** y seleccione el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="587de-126">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="587de-127">En el control flotante detalles que se abre, compruebe los miembros del grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="587de-127">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="587de-128">En el PowerShell del centro de cumplimiento de & de seguridad, reemplace \<RoleGroupName\> por el nombre del grupo de roles y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="587de-128">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="587de-129">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="587de-129">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
