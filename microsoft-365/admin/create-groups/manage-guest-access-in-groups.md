---
title: Administrar el acceso de invitado en grupos de 365 de Microsoft
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
description: Obtenga información sobre cómo agregar invitados a un grupo de 365 de Microsoft, ver los usuarios invitados y usar PowerShell para controlar el acceso de invitados.
ms.openlocfilehash: 48f3339968040eeb82a93d6540c70f0bbea0754a
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140548"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="2c243-103">Administrar el acceso de invitado en grupos de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c243-103">Manage guest access in Microsoft 365 groups</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="2c243-104">El centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="2c243-104">The admin center is changing.</span></span> <span data-ttu-id="2c243-105">Si su experiencia no coincide con los detalles que se presentan aquí, vea [acerca del nuevo centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="2c243-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="2c243-106">De forma predeterminada, el acceso de invitado para los grupos de Microsoft 365 está activado para su organización.</span><span class="sxs-lookup"><span data-stu-id="2c243-106">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="2c243-107">Los administradores pueden controlar si se permite el acceso de invitado a grupos para toda la organización o para grupos individuales.</span><span class="sxs-lookup"><span data-stu-id="2c243-107">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="2c243-108">Cuando está activada, los miembros del grupo pueden invitar a los usuarios invitados a un grupo de Microsoft 365 a través de Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="2c243-108">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="2c243-109">Las invitaciones se envían al propietario del grupo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="2c243-109">Invitations are sent to the group owner for approval.</span></span>

> [!Note]
> <span data-ttu-id="2c243-110">Las redes de Yammer Enterprise que están en modo nativo o el geográfico de la [UE](https://go.microsoft.com/fwlink/?linkid=2107357) no admiten invitados de red.</span><span class="sxs-lookup"><span data-stu-id="2c243-110">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="2c243-111">Los grupos de Yammer conectados a Microsoft 365 no son compatibles actualmente con el acceso de invitado, pero puede crear grupos externos no conectados en su red de Yammer.</span><span class="sxs-lookup"><span data-stu-id="2c243-111">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="2c243-112">Consulte [crear y administrar grupos externos en Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2c243-112">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

### <a name="edit-guest-information"></a><span data-ttu-id="2c243-113">Editar información de invitado</span><span class="sxs-lookup"><span data-stu-id="2c243-113">Edit guest information</span></span>

<span data-ttu-id="2c243-114">Una vez aprobado, el usuario invitado se agrega al directorio y al grupo.</span><span class="sxs-lookup"><span data-stu-id="2c243-114">Once approved, the guest user is added to the directory and the group.</span></span>

<span data-ttu-id="2c243-115">El acceso de invitado en grupos suele usarse como parte de un escenario más amplio que incluye SharePoint o Teams.</span><span class="sxs-lookup"><span data-stu-id="2c243-115">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="2c243-116">Estos servicios tienen su propia configuración de uso compartido de invitado.</span><span class="sxs-lookup"><span data-stu-id="2c243-116">These services have their own guest sharing settings.</span></span> <span data-ttu-id="2c243-117">Para obtener instrucciones completas sobre cómo configurar el uso compartido de invitado en grupos, SharePoint y Teams, vea:</span><span class="sxs-lookup"><span data-stu-id="2c243-117">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="2c243-118">Colaborar con invitados en un sitio</span><span class="sxs-lookup"><span data-stu-id="2c243-118">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="2c243-119">Colaborar con invitados en un equipo</span><span class="sxs-lookup"><span data-stu-id="2c243-119">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="2c243-120">Administrar grupos acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="2c243-120">Manage groups guest access</span></span>

<span data-ttu-id="2c243-121">Si desea habilitar o deshabilitar el acceso de invitado en grupos, puede hacerlo en el centro de administración de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2c243-121">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="2c243-122">En el centro de administración, vaya a **Settings** \> **Settings** configuración y seleccione **Microsoft 365 Groups**.</span><span class="sxs-lookup"><span data-stu-id="2c243-122">In the admin center, go to the **Settings** \> **Settings** and select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="2c243-123">En la página **Microsoft 365 Groups** , elija si desea permitir que los usuarios ajenos a la organización obtengan acceso a los recursos del grupo o que los propietarios del grupo agreguen personas fuera de la organización a los grupos.</span><span class="sxs-lookup"><span data-stu-id="2c243-123">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="2c243-124">Agregar invitados a un grupo de Microsoft 365 desde el centro de administración</span><span class="sxs-lookup"><span data-stu-id="2c243-124">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="2c243-125">Si el invitado ya existe en su directorio, puede agregarlo a los grupos desde el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c243-125">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="2c243-126">En el centro de administración, vaya a **la** > **Groups** página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="2c243-126">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="2c243-127">Haga clic en el grupo al que desea agregar el invitado y seleccione **Ver todos y administrar miembros** en la pestaña **miembros** .</span><span class="sxs-lookup"><span data-stu-id="2c243-127">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="2c243-128">Seleccione **Agregar miembros**y, a continuación, elija el nombre del invitado que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="2c243-128">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="2c243-129">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2c243-129">Select **Save**.</span></span>

<span data-ttu-id="2c243-130">Si desea agregar un invitado directamente al directorio, puede [Agregar usuarios de colaboración B2B de Azure Active Directory en Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="2c243-130">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="2c243-131">Si desea editar la información de algún invitado, puede [Agregar o actualizar la información de Perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="2c243-131">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="2c243-132">Bloquear a usuarios invitados de un grupo específico</span><span class="sxs-lookup"><span data-stu-id="2c243-132">Block guest users from a specific group</span></span>

<span data-ttu-id="2c243-133">Si desea permitir el acceso de invitado a la mayoría de los grupos, pero tenga algunos en los que desea evitar el acceso de invitado, puede bloquear el acceso de invitado para grupos individuales mediante PowerShell de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2c243-133">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="2c243-134">Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado en el nivel de Grupo:</span><span class="sxs-lookup"><span data-stu-id="2c243-134">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="2c243-135">Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) y siga las instrucciones para instalar la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="2c243-135">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="2c243-136">Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="2c243-136">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="2c243-137">Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.</span><span class="sxs-lookup"><span data-stu-id="2c243-137">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="2c243-138">Debe tener derechos de administrador global para ejecutar estos comandos.</span><span class="sxs-lookup"><span data-stu-id="2c243-138">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="2c243-139">Ejecute el siguiente script y cambie \* / \* al nombre del grupo en el que desea bloquear el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="2c243-139">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="2c243-140">Para comprobar la configuración, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="2c243-140">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="2c243-141">La comprobación tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c243-141">The verification looks like this:</span></span>
    
![Captura de pantalla de la ventana de PowerShell que muestra que el acceso al grupo de invitados se estableció en false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="2c243-143">Permitir o bloquear el acceso de invitado en función de su dominio</span><span class="sxs-lookup"><span data-stu-id="2c243-143">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="2c243-144">Puede permitir o bloquear a los usuarios invitados que usan un dominio específico.</span><span class="sxs-lookup"><span data-stu-id="2c243-144">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="2c243-145">Por ejemplo, si su empresa (contoso) tiene una asociación con otro negocio (Fabrikam), puede Agregar a Fabrikam a la lista de permitidos para que los usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="2c243-145">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="2c243-146">Para obtener más información, vea [permitir o bloquear invitaciones a usuarios B2B desde organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="2c243-146">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="2c243-147">Agregar invitados a la lista global de direcciones</span><span class="sxs-lookup"><span data-stu-id="2c243-147">Add guests to the global address list</span></span>

<span data-ttu-id="2c243-148">De forma predeterminada, los invitados no están visibles en la lista global de direcciones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2c243-148">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="2c243-149">Siga los pasos que se indican a continuación para hacer que un invitado esté visible en la lista global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="2c243-149">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="2c243-150">Para buscar el ObjectID del usuario Guest, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2c243-150">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="2c243-151">A continuación, ejecute lo siguiente con los valores apropiados de ObjectID, GivenName, apellido, DisplayName y TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="2c243-151">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="2c243-152">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="2c243-152">Related articles</span></span>

[<span data-ttu-id="2c243-153">Administrar la pertenencia a grupos en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c243-153">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="2c243-154">Revisiones de acceso de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2c243-154">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="2c243-155">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="2c243-155">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
