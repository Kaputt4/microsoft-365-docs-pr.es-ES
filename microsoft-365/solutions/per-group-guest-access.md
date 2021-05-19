---
title: Impedir que los invitados se agregó a un grupo específico
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre cómo evitar que los invitados se agregó a un grupo específico
ms.openlocfilehash: 1db2055f3e546c05905dbf4c854333387112f06e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538932"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="8b964-103">Impedir que los invitados se agregó a un grupo Microsoft 365 grupo o Microsoft Teams grupo</span><span class="sxs-lookup"><span data-stu-id="8b964-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="8b964-104">Si desea permitir el acceso de invitado a la mayoría de grupos y equipos, pero tiene algunos en los que desea impedir el acceso de invitado, puede bloquear el acceso de invitado para grupos y equipos individuales.</span><span class="sxs-lookup"><span data-stu-id="8b964-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="8b964-105">(Bloquear el acceso de invitado a un equipo se realiza bloqueando el acceso de invitado al grupo asociado). Esto evita que se agregó invitados nuevos, pero no quita los invitados que ya están en el grupo o el equipo.</span><span class="sxs-lookup"><span data-stu-id="8b964-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="8b964-106">Si usa etiquetas de confidencialidad en su organización, se recomienda usarlas para controlar el acceso de invitados por grupo.</span><span class="sxs-lookup"><span data-stu-id="8b964-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="8b964-107">Para obtener información sobre cómo hacerlo, use etiquetas de confidencialidad para proteger el contenido de [Microsoft Teams, Microsoft 365 grupos](../compliance/sensitivity-labels-teams-groups-sites.md)y SharePoint web .</span><span class="sxs-lookup"><span data-stu-id="8b964-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span> <span data-ttu-id="8b964-108">Este es el método recomendado.</span><span class="sxs-lookup"><span data-stu-id="8b964-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="8b964-109">Cambiar la configuración de grupo con Microsoft PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b964-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="8b964-110">También puede evitar la adición de nuevos invitados a grupos individuales mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b964-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="8b964-111">(Recuerde que el sitio asociado del equipo SharePoint cuenta con controles de uso [compartido de invitados independientes).)](/sharepoint/change-external-sharing-site)</span><span class="sxs-lookup"><span data-stu-id="8b964-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="8b964-112">Debe usar la versión preliminar de [Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2) para Graph (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado de nivel de grupo:</span><span class="sxs-lookup"><span data-stu-id="8b964-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="8b964-113">Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) y siga las instrucciones para instalar la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="8b964-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="8b964-114">Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="8b964-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="8b964-115">Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.</span><span class="sxs-lookup"><span data-stu-id="8b964-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="8b964-116">Debe tener derechos de administrador global para ejecutar estos comandos.</span><span class="sxs-lookup"><span data-stu-id="8b964-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="8b964-117">Ejecute el siguiente script, cambiando por el nombre del grupo en el */<GroupName/>* que desea bloquear el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="8b964-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="8b964-118">Para comprobar la configuración, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="8b964-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="8b964-119">La comprobación tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="8b964-119">The verification looks like this:</span></span>
    
![Captura de pantalla de la ventana de PowerShell que muestra que el acceso de grupo invitado se ha establecido en false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="8b964-121">Permitir o bloquear el acceso de invitado en función de su dominio</span><span class="sxs-lookup"><span data-stu-id="8b964-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="8b964-122">Puede permitir o bloquear invitados que usan un dominio específico.</span><span class="sxs-lookup"><span data-stu-id="8b964-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="8b964-123">Por ejemplo, si su empresa (Contoso) tiene una asociación con otra empresa (Fabrikam), puede agregar Fabrikam a la lista Permitir para que los usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="8b964-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="8b964-124">Para obtener más información, vea [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="8b964-124">For more information, see [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="8b964-125">Agregar invitados a la lista global de direcciones</span><span class="sxs-lookup"><span data-stu-id="8b964-125">Add guests to the global address list</span></span>

<span data-ttu-id="8b964-126">De forma predeterminada, los invitados no están visibles en la Exchange global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="8b964-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="8b964-127">Siga los pasos que se indican a continuación para que un invitado sea visible en la lista global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="8b964-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="8b964-128">Para buscar el ObjectID del invitado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="8b964-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="8b964-129">A continuación, ejecute lo siguiente con los valores adecuados para ObjectID, GivenName, Surname, DisplayName y TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="8b964-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="8b964-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8b964-130">Related topics</span></span>

[<span data-ttu-id="8b964-131">Planeación paso a paso de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="8b964-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="8b964-132">Crear el plan de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="8b964-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="8b964-133">Administrar la pertenencia a grupos en el centro Microsoft 365 administración</span><span class="sxs-lookup"><span data-stu-id="8b964-133">Manage Group membership in the Microsoft 365 admin center</span></span>](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="8b964-134">Azure Active Directory de acceso</span><span class="sxs-lookup"><span data-stu-id="8b964-134">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="8b964-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="8b964-135">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)