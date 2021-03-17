---
title: Administrar quién puede crear grupos de Microsoft 365
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Obtenga información sobre cómo controlar qué usuarios pueden crear grupos de Microsoft 365.
ms.openlocfilehash: 04c2b6e738ed41f8d4a2bf96716fb74b1d260497
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838644"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="7928d-103">Administrar quién puede crear grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7928d-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="7928d-104">De forma predeterminada, todos los usuarios pueden crear grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7928d-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="7928d-105">Este es el enfoque recomendado porque permite a los usuarios empezar a colaborar sin necesidad de asistencia de TI.</span><span class="sxs-lookup"><span data-stu-id="7928d-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="7928d-106">Si su empresa requiere restringir quién puede crear grupos, puede restringir la creación de grupos de Microsoft 365 a los miembros de un grupo o grupo de seguridad de Microsoft 365 en particular.</span><span class="sxs-lookup"><span data-stu-id="7928d-106">If your business requires that you restrict who can create groups, you can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span>

<span data-ttu-id="7928d-107">Si le preocupa que los usuarios creen equipos o grupos que no cumplan con los estándares empresariales, considere la posibilidad de requerir a los usuarios que completen un curso de formación y, a continuación, agregarlos al grupo de usuarios permitidos.</span><span class="sxs-lookup"><span data-stu-id="7928d-107">If you're concerned about users creating teams or groups that don't comply with your business standards, consider requiring users to complete a training course and then adding them to the group of allowed users.</span></span>

<span data-ttu-id="7928d-108">Cuando se limita quién puede crear un grupo, afecta a todos los servicios que dependen de grupos para el acceso, incluidos:</span><span class="sxs-lookup"><span data-stu-id="7928d-108">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="7928d-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="7928d-109">Outlook</span></span>
- <span data-ttu-id="7928d-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7928d-110">SharePoint</span></span>
- <span data-ttu-id="7928d-111">Yammer</span><span class="sxs-lookup"><span data-stu-id="7928d-111">Yammer</span></span>
- <span data-ttu-id="7928d-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7928d-112">Microsoft Teams</span></span>
- <span data-ttu-id="7928d-113">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="7928d-113">Microsoft Stream</span></span>
- <span data-ttu-id="7928d-114">Planner</span><span class="sxs-lookup"><span data-stu-id="7928d-114">Planner</span></span>
- <span data-ttu-id="7928d-115">Power BI (clásico)</span><span class="sxs-lookup"><span data-stu-id="7928d-115">Power BI (classic)</span></span>
- <span data-ttu-id="7928d-116">Project for the web /Roadmap</span><span class="sxs-lookup"><span data-stu-id="7928d-116">Project for the web / Roadmap</span></span>

<span data-ttu-id="7928d-117">Los pasos de este artículo no impedirán que los miembros de determinados roles creen grupos.</span><span class="sxs-lookup"><span data-stu-id="7928d-117">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="7928d-118">Los administradores globales de Office 365 pueden crear grupos por cualquier medio, como el Centro de administración de Microsoft 365, Planner, Teams, Exchange y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7928d-118">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="7928d-119">Otros roles pueden crear grupos a través de medios limitados, que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="7928d-119">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="7928d-120">Administrador de Exchange: Centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7928d-120">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="7928d-121">Soporte técnico de nivel 1 de partner: Centro de administración de Microsoft 365, Centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7928d-121">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="7928d-122">Soporte técnico de nivel 2 de partner: Centro de administración de Microsoft 365, Centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7928d-122">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="7928d-123">Escritores de directorios: Azure AD</span><span class="sxs-lookup"><span data-stu-id="7928d-123">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="7928d-124">Administrador de SharePoint: Centro de administración de SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7928d-124">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="7928d-125">Administrador de servicio de Teams: Centro de administración de Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7928d-125">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="7928d-126">Administrador de usuarios: Centro de administración de Microsoft 365, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7928d-126">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="7928d-127">Si es miembro de uno de estos roles, puede crear grupos de Microsoft 365 para usuarios restringidos y, a continuación, asignar al usuario como propietario del grupo.</span><span class="sxs-lookup"><span data-stu-id="7928d-127">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7928d-128">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="7928d-128">Licensing requirements</span></span>

<span data-ttu-id="7928d-129">Para administrar quién crea grupos, las siguientes personas necesitan licencias de Azure AD Premium o licencias EDU básicas de Azure AD asignadas:</span><span class="sxs-lookup"><span data-stu-id="7928d-129">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7928d-130">El administrador que configura estas opciones de creación de grupos</span><span class="sxs-lookup"><span data-stu-id="7928d-130">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="7928d-131">Los miembros del grupo a los que se les permite crear grupos</span><span class="sxs-lookup"><span data-stu-id="7928d-131">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="7928d-132">Consulta [Asignar o quitar licencias en el portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) de Azure Active Directory para obtener más información sobre cómo asignar licencias de Azure.</span><span class="sxs-lookup"><span data-stu-id="7928d-132">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="7928d-133">Las siguientes personas no necesitan licencias EDU de Azure AD Premium o Azure AD Basic asignadas:</span><span class="sxs-lookup"><span data-stu-id="7928d-133">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7928d-134">Personas que son miembros de grupos de Microsoft 365 y que no tienen la capacidad de crear otros grupos.</span><span class="sxs-lookup"><span data-stu-id="7928d-134">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="7928d-135">Paso 1: Crear un grupo para usuarios que necesiten crear grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7928d-135">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="7928d-136">Solo se puede usar un grupo de la organización para controlar quién puede crear grupos.</span><span class="sxs-lookup"><span data-stu-id="7928d-136">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="7928d-137">Sin embargo, puede anidar otros grupos como miembros de este grupo.</span><span class="sxs-lookup"><span data-stu-id="7928d-137">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="7928d-138">Los administradores de los roles enumerados anteriormente no necesitan ser miembros de este grupo: conservan su capacidad para crear grupos.</span><span class="sxs-lookup"><span data-stu-id="7928d-138">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="7928d-139">En el Centro de administración, vaya a la [página Grupos](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="7928d-139">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="7928d-140">Haga clic **en Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="7928d-140">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="7928d-141">Elija el tipo de grupo que desee.</span><span class="sxs-lookup"><span data-stu-id="7928d-141">Choose the group type you want.</span></span> <span data-ttu-id="7928d-142">Recuerde que el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="7928d-142">Remember the name of the group!</span></span> <span data-ttu-id="7928d-143">Lo necesitará más adelante.</span><span class="sxs-lookup"><span data-stu-id="7928d-143">You'll need it later.</span></span>

4. <span data-ttu-id="7928d-144">Termina de configurar el grupo, agregando personas u otros grupos que quieras que puedan crear grupos en tu organización.</span><span class="sxs-lookup"><span data-stu-id="7928d-144">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="7928d-145">Para obtener instrucciones detalladas, vea Crear, editar o eliminar un grupo de seguridad en el Centro de administración [de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="7928d-145">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="7928d-146">Paso 2: Ejecutar los comandos de PowerShell</span><span class="sxs-lookup"><span data-stu-id="7928d-146">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="7928d-147">Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado de nivel de grupo:</span><span class="sxs-lookup"><span data-stu-id="7928d-147">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="7928d-148">Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) y siga las instrucciones para instalar la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="7928d-148">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="7928d-149">Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="7928d-149">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="7928d-150">Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.</span><span class="sxs-lookup"><span data-stu-id="7928d-150">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="7928d-151">Copie el script siguiente en un editor de texto, como bloc de notas, o el [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="7928d-151">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="7928d-152">Reemplace *\<GroupName\>* por el nombre del grupo que creó.</span><span class="sxs-lookup"><span data-stu-id="7928d-152">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="7928d-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7928d-153">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="7928d-154">Guarde el archivo como GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="7928d-154">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="7928d-155">En la ventana de PowerShell, vaya a la ubicación donde guardó el archivo (escriba <FileLocation> "CD").</span><span class="sxs-lookup"><span data-stu-id="7928d-155">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="7928d-156">Ejecute el script escribiendo:</span><span class="sxs-lookup"><span data-stu-id="7928d-156">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="7928d-157">e [inicie sesión con su cuenta de administrador](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="7928d-157">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
    $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="7928d-158">La última línea del script mostrará la configuración actualizada:</span><span class="sxs-lookup"><span data-stu-id="7928d-158">The last line of the script will display the updated settings:</span></span>

![Captura de pantalla del resultado del script de PowerShell.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="7928d-160">Si en el futuro desea cambiar el grupo que se usa, puede volver a ejecutar el script con el nombre del nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="7928d-160">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="7928d-161">Si desea desactivar la restricción de creación de grupos y volver a permitir que todos los usuarios creen grupos, establezca $GroupName en "" y $AllowGroupCreation en "True" y vuelva a ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="7928d-161">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="7928d-162">Paso 3: Comprobar que funciona correctamente</span><span class="sxs-lookup"><span data-stu-id="7928d-162">Step 3: Verify that it works</span></span>

<span data-ttu-id="7928d-163">Los cambios pueden tardar treinta minutos o más en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="7928d-163">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="7928d-164">Para comprobar la nueva configuración, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7928d-164">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="7928d-165">Inicie sesión en Microsoft 365 con una cuenta de usuario de alguien que NO debería tener la capacidad de crear grupos.</span><span class="sxs-lookup"><span data-stu-id="7928d-165">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="7928d-166">Es decir, no son miembros del grupo que ha creado ni de un administrador.</span><span class="sxs-lookup"><span data-stu-id="7928d-166">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="7928d-167">Seleccione el **icono Planner.**</span><span class="sxs-lookup"><span data-stu-id="7928d-167">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="7928d-168">En Planner, seleccione **Nuevo plan** en la navegación izquierda para crear un plan.</span><span class="sxs-lookup"><span data-stu-id="7928d-168">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="7928d-169">Debe obtener un mensaje que indica que el plan y la creación de grupos están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="7928d-169">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="7928d-170">Vuelva a intentar el mismo procedimiento con un miembro del grupo.</span><span class="sxs-lookup"><span data-stu-id="7928d-170">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="7928d-171">Si los miembros del grupo no pueden crear grupos, compruebe que no se están bloqueando a través de su directiva [de buzón de OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="7928d-171">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7928d-172">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7928d-172">Related topics</span></span>

[<span data-ttu-id="7928d-173">Planeación paso a paso de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="7928d-173">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="7928d-174">Crear el plan de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="7928d-174">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="7928d-175">Introducción a PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="7928d-175">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="7928d-176">Configurar la administración de grupos de autoservicio en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7928d-176">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="7928d-177">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="7928d-177">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="7928d-178">Cmdlets de Azure Active Directory para configurar configuraciones de grupo</span><span class="sxs-lookup"><span data-stu-id="7928d-178">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
