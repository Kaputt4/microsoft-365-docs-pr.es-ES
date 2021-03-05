---
title: Administrar el acceso de invitado en grupos de Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Obtenga información sobre cómo agregar invitados a un grupo de Microsoft 365, ver usuarios invitados y usar PowerShell para controlar el acceso de invitados.
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453662"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="eb495-103">Administrar el acceso de invitado en grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eb495-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="eb495-104">De forma predeterminada, el acceso de invitado para grupos de Microsoft 365 está activado para su organización.</span><span class="sxs-lookup"><span data-stu-id="eb495-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="eb495-105">Los administradores pueden controlar si se permite el acceso de invitados a grupos para toda la organización o para grupos individuales.</span><span class="sxs-lookup"><span data-stu-id="eb495-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="eb495-106">Cuando está activado, los miembros del grupo pueden invitar a los usuarios invitados a un grupo de Microsoft 365 a través de Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="eb495-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="eb495-107">Las invitaciones se envían al propietario del grupo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="eb495-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="eb495-108">Una vez aprobado, el usuario invitado se agrega al directorio y al grupo.</span><span class="sxs-lookup"><span data-stu-id="eb495-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="eb495-109">Las redes de Yammer Enterprise que están en modo nativo o en la [geo](https://go.microsoft.com/fwlink/?linkid=2107357) de la UE no admiten invitados de red.</span><span class="sxs-lookup"><span data-stu-id="eb495-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="eb495-110">Los grupos de Yammer conectados de Microsoft 365 no admiten actualmente el acceso de invitado, pero puede crear grupos externos no conectados en la red de Yammer.</span><span class="sxs-lookup"><span data-stu-id="eb495-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="eb495-111">Consulta [Crear y administrar grupos externos en Yammer para](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="eb495-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="eb495-112">El acceso de invitado en grupos suele usarse como parte de un escenario más amplio que incluye SharePoint o Teams.</span><span class="sxs-lookup"><span data-stu-id="eb495-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="eb495-113">Estos servicios tienen su propia configuración de uso compartido de invitados.</span><span class="sxs-lookup"><span data-stu-id="eb495-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="eb495-114">Para obtener instrucciones completas para configurar el uso compartido de invitados entre grupos, SharePoint y Teams, vea:</span><span class="sxs-lookup"><span data-stu-id="eb495-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="eb495-115">Colaborar con invitados en un sitio</span><span class="sxs-lookup"><span data-stu-id="eb495-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="eb495-116">Colaborar con invitados en un equipo</span><span class="sxs-lookup"><span data-stu-id="eb495-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="eb495-117">Administrar el acceso de invitado de grupos</span><span class="sxs-lookup"><span data-stu-id="eb495-117">Manage groups guest access</span></span>

<span data-ttu-id="eb495-118">Si desea habilitar o deshabilitar el acceso de invitado en grupos, puede hacerlo en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb495-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="eb495-119">En el Centro de administración, vaya **a Mostrar** toda la configuración de la organización de configuración y, en la pestaña \>  \>  Servicios, seleccione Grupos de **Microsoft 365**. </span><span class="sxs-lookup"><span data-stu-id="eb495-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="eb495-120">En la página Grupos de **Microsoft 365,** elija si desea permitir que los usuarios externos a la organización accedan a los recursos de grupo o permitir que los propietarios de grupos agreguen personas fuera de la organización a los grupos.</span><span class="sxs-lookup"><span data-stu-id="eb495-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="eb495-121">Agregar invitados a un grupo de Microsoft 365 desde el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="eb495-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="eb495-122">Si el invitado ya existe en el directorio, puede agregarlos a los grupos desde el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb495-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="eb495-123">(Los grupos con pertenencia dinámica deben [administrarse en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).)</span><span class="sxs-lookup"><span data-stu-id="eb495-123">(Groups with dynamic membership must be [managed in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="eb495-124">En el Centro de administración, vaya a la **página Grupos.**  >  </span><span class="sxs-lookup"><span data-stu-id="eb495-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="eb495-125">Haga clic en el grupo al que desea agregar el invitado y seleccione Ver todos y **administrar miembros** en la **pestaña** Miembros.</span><span class="sxs-lookup"><span data-stu-id="eb495-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="eb495-126">Seleccione **Agregar miembros** y elija el nombre del invitado que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="eb495-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="eb495-127">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="eb495-127">Select **Save**.</span></span>

<span data-ttu-id="eb495-128">Si desea agregar un invitado al directorio directamente, puede agregar usuarios de colaboración [B2B](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)de Azure Active Directory en Azure Portal .</span><span class="sxs-lookup"><span data-stu-id="eb495-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="eb495-129">Si desea editar cualquiera de la información de un invitado, puede agregar o actualizar la información de perfil de un usuario [mediante Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="eb495-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="eb495-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb495-130">See also</span></span>

[<span data-ttu-id="eb495-131">Bloquear usuarios invitados de un grupo específico</span><span class="sxs-lookup"><span data-stu-id="eb495-131">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="eb495-132">Administrar la pertenencia a grupos en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eb495-132">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="eb495-133">Revisiones de acceso a Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="eb495-133">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="eb495-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="eb495-134">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
