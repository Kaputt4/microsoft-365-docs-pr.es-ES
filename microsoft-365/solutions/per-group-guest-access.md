---
title: Impedir que los invitados se agreguen a un grupo específico
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
description: Obtenga información sobre cómo impedir que los invitados se agreguen a un grupo específico.
ms.openlocfilehash: 99e78932b29d25054922b56fcadb608a7dfca432
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613061"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="715bf-103">Impedir que los invitados se agreguen a un grupo específico de Microsoft 365 o a un equipo de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="715bf-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="715bf-104">Si desea permitir el acceso de invitado a la mayoría de grupos y equipos, pero con algunos en los que desea evitar el acceso de invitado, puede bloquear el acceso de invitado a grupos y equipos individuales.</span><span class="sxs-lookup"><span data-stu-id="715bf-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="715bf-105">(Si se bloquea el acceso de invitado a un equipo, se bloquea el acceso de invitado al grupo asociado). Esto impide que se agreguen invitados nuevos, pero no quita los invitados que ya están en el grupo o equipo.</span><span class="sxs-lookup"><span data-stu-id="715bf-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="715bf-106">Si usa etiquetas de confidencialidad en su organización, se recomienda usarlas para controlar el acceso de invitado por grupo.</span><span class="sxs-lookup"><span data-stu-id="715bf-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="715bf-107">Para obtener información sobre cómo hacerlo, [use las etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de 365 de Microsoft y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="715bf-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="715bf-108">Este es el método recomendado.</span><span class="sxs-lookup"><span data-stu-id="715bf-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="715bf-109">Cambiar la configuración del grupo mediante PowerShell de Microsoft</span><span class="sxs-lookup"><span data-stu-id="715bf-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="715bf-110">También puede evitar la adición de nuevos invitados a grupos individuales mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="715bf-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span>

<span data-ttu-id="715bf-111">Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado en el nivel de Grupo:</span><span class="sxs-lookup"><span data-stu-id="715bf-111">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="715bf-112">Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) y siga las instrucciones para instalar la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="715bf-112">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="715bf-113">Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="715bf-113">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="715bf-114">Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.</span><span class="sxs-lookup"><span data-stu-id="715bf-114">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="715bf-115">Debe tener derechos de administrador global para ejecutar estos comandos.</span><span class="sxs-lookup"><span data-stu-id="715bf-115">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="715bf-116">Ejecute el siguiente script y cambie */<GroupName/>* al nombre del grupo en el que desea bloquear el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="715bf-116">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="715bf-117">Para comprobar la configuración, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="715bf-117">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="715bf-118">La comprobación tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="715bf-118">The verification looks like this:</span></span>
    
![Captura de pantalla de la ventana de PowerShell que muestra que el acceso al grupo de invitados se estableció en false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="715bf-120">Permitir o bloquear el acceso de invitado en función de su dominio</span><span class="sxs-lookup"><span data-stu-id="715bf-120">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="715bf-121">Puede permitir o bloquear a los invitados que usan un dominio específico.</span><span class="sxs-lookup"><span data-stu-id="715bf-121">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="715bf-122">Por ejemplo, si su empresa (contoso) tiene una asociación con otro negocio (Fabrikam), puede Agregar a Fabrikam a la lista de permitidos para que los usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="715bf-122">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="715bf-123">Para obtener más información, vea [permitir o bloquear invitaciones a usuarios B2B desde organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="715bf-123">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="715bf-124">Agregar invitados a la lista global de direcciones</span><span class="sxs-lookup"><span data-stu-id="715bf-124">Add guests to the global address list</span></span>

<span data-ttu-id="715bf-125">De forma predeterminada, los invitados no están visibles en la lista global de direcciones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="715bf-125">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="715bf-126">Siga los pasos que se indican a continuación para hacer que un invitado esté visible en la lista global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="715bf-126">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="715bf-127">Para buscar el ObjectID del invitado, ejecute:</span><span class="sxs-lookup"><span data-stu-id="715bf-127">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="715bf-128">A continuación, ejecute lo siguiente con los valores apropiados de ObjectID, GivenName, apellido, DisplayName y TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="715bf-128">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="715bf-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="715bf-129">Related topics</span></span>

[<span data-ttu-id="715bf-130">Paso a paso de la planeación del gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="715bf-130">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="715bf-131">Crear el plan de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="715bf-131">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="715bf-132">Administrar la pertenencia a grupos en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="715bf-132">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="715bf-133">Revisiones de acceso de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="715bf-133">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="715bf-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="715bf-134">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
