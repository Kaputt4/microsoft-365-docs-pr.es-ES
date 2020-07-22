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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Obtenga información sobre cómo agregar invitados a un grupo de 365 de Microsoft, ver los usuarios invitados y usar PowerShell para controlar el acceso de invitados.
ms.openlocfilehash: a56d9599824ac1436c6f875661bcd573c1f6b1ca
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204748"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="0696f-103">Administrar el acceso de invitado en grupos de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0696f-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="0696f-104">De forma predeterminada, el acceso de invitado para los grupos de Microsoft 365 está activado para su organización.</span><span class="sxs-lookup"><span data-stu-id="0696f-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="0696f-105">Los administradores pueden controlar si se permite el acceso de invitado a grupos para toda la organización o para grupos individuales.</span><span class="sxs-lookup"><span data-stu-id="0696f-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="0696f-106">Cuando está activada, los miembros del grupo pueden invitar a los usuarios invitados a un grupo de Microsoft 365 a través de Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="0696f-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="0696f-107">Las invitaciones se envían al propietario del grupo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="0696f-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="0696f-108">Una vez aprobado, el usuario invitado se agrega al directorio y al grupo.</span><span class="sxs-lookup"><span data-stu-id="0696f-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="0696f-109">Las redes de Yammer Enterprise que están en modo nativo o el geográfico de la [UE](https://go.microsoft.com/fwlink/?linkid=2107357) no admiten invitados de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="0696f-110">Los grupos de Yammer conectados a Microsoft 365 no son compatibles actualmente con el acceso de invitado, pero puede crear grupos externos no conectados en su red de Yammer.</span><span class="sxs-lookup"><span data-stu-id="0696f-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="0696f-111">Consulte [crear y administrar grupos externos en Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="0696f-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="0696f-112">El acceso de invitado en grupos suele usarse como parte de un escenario más amplio que incluye SharePoint o Teams.</span><span class="sxs-lookup"><span data-stu-id="0696f-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="0696f-113">Estos servicios tienen su propia configuración de uso compartido de invitado.</span><span class="sxs-lookup"><span data-stu-id="0696f-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="0696f-114">Para obtener instrucciones completas sobre cómo configurar el uso compartido de invitado en grupos, SharePoint y Teams, vea:</span><span class="sxs-lookup"><span data-stu-id="0696f-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="0696f-115">Colaborar con invitados en un sitio</span><span class="sxs-lookup"><span data-stu-id="0696f-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="0696f-116">Colaborar con invitados en un equipo</span><span class="sxs-lookup"><span data-stu-id="0696f-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="0696f-117">Administrar grupos acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="0696f-117">Manage groups guest access</span></span>

<span data-ttu-id="0696f-118">Si desea habilitar o deshabilitar el acceso de invitado en grupos, puede hacerlo en el centro de administración de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0696f-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="0696f-119">En el centro de administración, vaya a **Mostrar todas las** opciones de configuración de \> **Settings** \> la **organización** y, en la pestaña **servicios** , seleccione **Microsoft 365 Groups**.</span><span class="sxs-lookup"><span data-stu-id="0696f-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="0696f-120">En la página **Microsoft 365 Groups** , elija si desea permitir que los usuarios ajenos a la organización obtengan acceso a los recursos del grupo o que los propietarios del grupo agreguen personas fuera de la organización a los grupos.</span><span class="sxs-lookup"><span data-stu-id="0696f-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="0696f-121">Agregar invitados a un grupo de Microsoft 365 desde el centro de administración</span><span class="sxs-lookup"><span data-stu-id="0696f-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="0696f-122">Si el invitado ya existe en su directorio, puede agregarlo a los grupos desde el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0696f-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="0696f-123">En el centro de administración, vaya a **la**página grupos de grupos  >  **Groups** .</span><span class="sxs-lookup"><span data-stu-id="0696f-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="0696f-124">Haga clic en el grupo al que desea agregar el invitado y seleccione **Ver todos y administrar miembros** en la pestaña **miembros** .</span><span class="sxs-lookup"><span data-stu-id="0696f-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="0696f-125">Seleccione **Agregar miembros**y, a continuación, elija el nombre del invitado que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="0696f-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="0696f-126">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0696f-126">Select **Save**.</span></span>

<span data-ttu-id="0696f-127">Si desea agregar un invitado directamente al directorio, puede [Agregar usuarios de colaboración B2B de Azure Active Directory en Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="0696f-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="0696f-128">Si desea editar la información de algún invitado, puede [Agregar o actualizar la información de Perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="0696f-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="0696f-129">Bloquear a usuarios invitados de un grupo específico</span><span class="sxs-lookup"><span data-stu-id="0696f-129">Block guest users from a specific group</span></span>

<span data-ttu-id="0696f-130">Si desea permitir el acceso de invitado a la mayoría de los grupos, pero tenga algunos en los que desea evitar el acceso de invitado, puede bloquear el acceso de invitado para grupos individuales mediante PowerShell de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0696f-130">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="0696f-131">Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado en el nivel de Grupo:</span><span class="sxs-lookup"><span data-stu-id="0696f-131">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="0696f-132">Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) y siga las instrucciones para instalar la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="0696f-132">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="0696f-133">Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="0696f-133">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="0696f-134">Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.</span><span class="sxs-lookup"><span data-stu-id="0696f-134">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="0696f-135">Debe tener derechos de administrador global para ejecutar estos comandos.</span><span class="sxs-lookup"><span data-stu-id="0696f-135">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="0696f-136">Ejecute el siguiente script y cambie */<GroupName/>* al nombre del grupo en el que desea bloquear el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="0696f-136">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="0696f-137">Para comprobar la configuración, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="0696f-137">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="0696f-138">La comprobación tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="0696f-138">The verification looks like this:</span></span>
    
![Captura de pantalla de la ventana de PowerShell que muestra que el acceso al grupo de invitados se estableció en false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="0696f-140">Permitir o bloquear el acceso de invitado en función de su dominio</span><span class="sxs-lookup"><span data-stu-id="0696f-140">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="0696f-141">Puede permitir o bloquear a los usuarios invitados que usan un dominio específico.</span><span class="sxs-lookup"><span data-stu-id="0696f-141">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="0696f-142">Por ejemplo, si su empresa (contoso) tiene una asociación con otro negocio (Fabrikam), puede Agregar a Fabrikam a la lista de permitidos para que los usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="0696f-142">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="0696f-143">Para obtener más información, vea [permitir o bloquear invitaciones a usuarios B2B desde organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="0696f-143">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="0696f-144">Agregar invitados a la lista global de direcciones</span><span class="sxs-lookup"><span data-stu-id="0696f-144">Add guests to the global address list</span></span>

<span data-ttu-id="0696f-145">De forma predeterminada, los invitados no están visibles en la lista global de direcciones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0696f-145">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="0696f-146">Siga los pasos que se indican a continuación para hacer que un invitado esté visible en la lista global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="0696f-146">Use the steps listed below to make a guest visible in the global address list.</span></span> <span data-ttu-id="0696f-147">Asegúrese de que el invitado está visible en el centro de administración de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0696f-147">Be sure the guest is visible in the Exchange Online admin center.</span></span> <span data-ttu-id="0696f-148">Los invitados nuevos pueden tardar un poco en aparecer después de que se hayan agregado.</span><span class="sxs-lookup"><span data-stu-id="0696f-148">New guests may take a short time to appear there after they're added.</span></span>

<span data-ttu-id="0696f-149">Para buscar el ObjectID del usuario Guest, ejecute:</span><span class="sxs-lookup"><span data-stu-id="0696f-149">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="0696f-150">A continuación, ejecute lo siguiente con los valores apropiados de ObjectID, GivenName, apellido, DisplayName y TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="0696f-150">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="0696f-151">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="0696f-151">Related articles</span></span>

[<span data-ttu-id="0696f-152">Administrar la pertenencia a grupos en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0696f-152">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="0696f-153">Revisiones de acceso de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0696f-153">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="0696f-154">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="0696f-154">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
