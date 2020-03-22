---
title: Administrar el acceso de invitado en los grupos de Office 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Obtenga información sobre cómo agregar invitados a un grupo de Office 365, ver usuarios invitados y usar PowerShell para controlar el acceso de invitado.
ms.openlocfilehash: e76718ccb20843b252c939be48653c61c7c1f0a9
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894508"
---
# <a name="manage-guest-access-in-office-365-groups"></a><span data-ttu-id="7e6a5-103">Administrar el acceso de invitado en los grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="7e6a5-103">Manage guest access in Office 365 Groups</span></span>

<span data-ttu-id="7e6a5-104">De forma predeterminada, el acceso de invitado para los grupos de Office 365 está activado para su organización.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-104">By default, guest access for Office 365 groups is turned on for your organization.</span></span> <span data-ttu-id="7e6a5-105">Los administradores pueden controlar si se permite el acceso de invitado a grupos para toda la organización o para grupos individuales.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="7e6a5-106">Cuando está activada, los miembros del grupo pueden invitar a los usuarios invitados a un grupo de Office 365 a través de Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-106">When it's turned on, group members can invite guest users to an Office 365 group through Outlook on Web.</span></span> <span data-ttu-id="7e6a5-107">Las invitaciones se envían al propietario del grupo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-107">Invitations are sent to the group owner for approval.</span></span>

> [!Note]
> <span data-ttu-id="7e6a5-108">Las redes de Yammer Enterprise que están en modo nativo o el geográfico de la [UE](https://go.microsoft.com/fwlink/?linkid=2107357) no admiten invitados de red.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-108">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="7e6a5-109">Office 365 los grupos de Yammer conectados no admiten actualmente el acceso de invitado, pero puede crear grupos externos no conectados en su red Yammer.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-109">Office 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="7e6a5-110">Consulte [crear y administrar grupos externos en Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-110">See [Create and manage external groups in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) for instructions.</span></span>

### <a name="edit-guest-information"></a><span data-ttu-id="7e6a5-111">Editar información de invitado</span><span class="sxs-lookup"><span data-stu-id="7e6a5-111">Edit guest information</span></span>

<span data-ttu-id="7e6a5-112">Una vez aprobado, el usuario invitado se agrega al directorio y al grupo.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-112">Once approved, the guest user is added to the directory and the group.</span></span>

<span data-ttu-id="7e6a5-113">El acceso de invitado en grupos suele usarse como parte de un escenario más amplio que incluye SharePoint o Teams.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-113">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="7e6a5-114">Estos servicios tienen su propia configuración de uso compartido de invitado.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-114">These services have their own guest sharing settings.</span></span> <span data-ttu-id="7e6a5-115">Para obtener instrucciones completas sobre cómo configurar el uso compartido de invitado en grupos, SharePoint y Teams, vea:</span><span class="sxs-lookup"><span data-stu-id="7e6a5-115">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="7e6a5-116">Colaborar con invitados en un sitio</span><span class="sxs-lookup"><span data-stu-id="7e6a5-116">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="7e6a5-117">Colaborar con invitados en un equipo</span><span class="sxs-lookup"><span data-stu-id="7e6a5-117">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="7e6a5-118">Administrar grupos acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="7e6a5-118">Manage groups guest access</span></span>

<span data-ttu-id="7e6a5-119">Si desea habilitar o deshabilitar el acceso de invitado en grupos, puede hacerlo en el centro de administración de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-119">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="7e6a5-120">En el centro de administración, vaya a **Settings** \> **Settings** configuración y seleccione **Office 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-120">In the admin center, go to the **Settings** \> **Settings** and select **Office 365 Groups**.</span></span>
  
2. <span data-ttu-id="7e6a5-121">En la página **Office 365 grupos** , elija si desea permitir que los usuarios ajenos a la organización obtengan acceso a los recursos del grupo o permitir que los propietarios del grupo agreguen personas fuera de la organización a los grupos.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-121">On the **Office 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a><span data-ttu-id="7e6a5-122">Agregar invitados a un grupo de Office 365 desde el centro de administración</span><span class="sxs-lookup"><span data-stu-id="7e6a5-122">Add guests to an Office 365 group from the admin center</span></span>

<span data-ttu-id="7e6a5-123">Si el invitado ya existe en su directorio, puede agregarlo a los grupos desde el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-123">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="7e6a5-124">En el centro de administración, vaya a **la** > **Groups** página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="7e6a5-125">Haga clic en el grupo al que desea agregar el invitado y seleccione **Ver todos y administrar miembros** en la pestaña **miembros** .</span><span class="sxs-lookup"><span data-stu-id="7e6a5-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="7e6a5-126">Seleccione **Agregar miembros**y, a continuación, elija el nombre del invitado que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="7e6a5-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-127">Select **Save**.</span></span>

<span data-ttu-id="7e6a5-128">Si desea agregar un invitado directamente al directorio, puede [Agregar usuarios de colaboración B2B de Azure Active Directory en Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="7e6a5-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="7e6a5-129">Si desea editar la información de algún invitado, puede [Agregar o actualizar la información de Perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="7e6a5-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="7e6a5-130">Bloquear a usuarios invitados de un grupo específico</span><span class="sxs-lookup"><span data-stu-id="7e6a5-130">Block guest users from a specific group</span></span>

<span data-ttu-id="7e6a5-131">Si desea permitir el acceso de invitado a la mayoría de los grupos, pero tenga algunos en los que desea evitar el acceso de invitado, puede bloquear el acceso de invitado para grupos individuales mediante PowerShell de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-131">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="7e6a5-132">Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado en el nivel de Grupo:</span><span class="sxs-lookup"><span data-stu-id="7e6a5-132">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="7e6a5-133">Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) y siga las instrucciones para instalar la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-133">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="7e6a5-134">Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-134">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="7e6a5-135">Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-135">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="7e6a5-136">Debe tener derechos de administrador global para ejecutar estos comandos.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-136">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="7e6a5-137">Ejecute el siguiente script y cambie \* / \* al nombre del grupo en el que desea bloquear el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-137">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="7e6a5-138">Para comprobar la configuración, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="7e6a5-138">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="7e6a5-139">La comprobación tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e6a5-139">The verification looks like this:</span></span>
    
![Captura de pantalla de la ventana de PowerShell que muestra que el acceso al grupo de invitados se estableció en false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="7e6a5-141">Permitir o bloquear el acceso de invitado en función de su dominio</span><span class="sxs-lookup"><span data-stu-id="7e6a5-141">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="7e6a5-142">Puede permitir o bloquear a los usuarios invitados que usan un dominio específico.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-142">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="7e6a5-143">Por ejemplo, si su empresa (contoso) tiene una asociación con otro negocio (Fabrikam), puede Agregar a Fabrikam a la lista de permitidos para que los usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-143">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="7e6a5-144">Para obtener más información, vea [permitir o bloquear invitaciones a usuarios B2B desde organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="7e6a5-144">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="7e6a5-145">Agregar invitados a la lista global de direcciones</span><span class="sxs-lookup"><span data-stu-id="7e6a5-145">Add guests to the global address list</span></span>

<span data-ttu-id="7e6a5-146">De forma predeterminada, los invitados no están visibles en la lista global de direcciones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-146">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="7e6a5-147">Siga los pasos que se indican a continuación para hacer que un invitado esté visible en la lista global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-147">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="7e6a5-148">Para buscar el ObjectID del usuario Guest, ejecute:</span><span class="sxs-lookup"><span data-stu-id="7e6a5-148">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="7e6a5-149">A continuación, ejecute lo siguiente con los valores apropiados de ObjectID, GivenName, apellido, DisplayName y TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-149">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="7e6a5-150">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="7e6a5-150">Related articles</span></span>

[<span data-ttu-id="7e6a5-151">Administrar la pertenencia a grupos en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7e6a5-151">Manage Group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="7e6a5-152">Revisiones de acceso de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7e6a5-152">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="7e6a5-153">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="7e6a5-153">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
