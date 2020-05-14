---
title: Administrar quién puede crear grupos
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Obtenga información sobre cómo controlar qué usuarios pueden crear grupos de Microsoft 365.
ms.openlocfilehash: 7a699a01687aec47fd39ce108c5a8c7a888afe65
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222388"
---
# <a name="manage-who-can-create-groups"></a><span data-ttu-id="51122-103">Administrar quién puede crear grupos</span><span class="sxs-lookup"><span data-stu-id="51122-103">Manage who can create Groups</span></span>

  
<span data-ttu-id="51122-104">Como es tan fácil para los usuarios crear grupos de 365 de Microsoft, no se ven inundados con solicitudes para crearlas en nombre de otras personas.</span><span class="sxs-lookup"><span data-stu-id="51122-104">Because it's so easy for users to create Microsoft 365 groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="51122-105">Sin embargo, dependiendo de su empresa, es posible que quiera controlar quién tiene la capacidad de crear grupos.</span><span class="sxs-lookup"><span data-stu-id="51122-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="51122-106">En este artículo se explica cómo deshabilitar la capacidad de crear grupos en todos los servicios de Microsoft 365 que usan grupos, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="51122-106">This article explains how to disable the ability to create groups in all Microsoft 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="51122-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="51122-107">Outlook</span></span>
    
- <span data-ttu-id="51122-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="51122-108">SharePoint</span></span>
    
- <span data-ttu-id="51122-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="51122-109">Yammer</span></span>
    
- <span data-ttu-id="51122-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51122-110">Microsoft Teams</span></span>

- <span data-ttu-id="51122-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="51122-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="51122-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="51122-112">StaffHub</span></span>
    
- <span data-ttu-id="51122-113">Planner</span><span class="sxs-lookup"><span data-stu-id="51122-113">Planner</span></span>
    
- <span data-ttu-id="51122-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="51122-114">PowerBI</span></span>

- <span data-ttu-id="51122-115">Hoja de ruta</span><span class="sxs-lookup"><span data-stu-id="51122-115">Roadmap</span></span>
    
<span data-ttu-id="51122-116">Puede restringir la creación de grupos de Microsoft 365 a los miembros de un grupo de seguridad en particular.</span><span class="sxs-lookup"><span data-stu-id="51122-116">You can restrict Microsoft 365 group creation to the members of a particular security group.</span></span> <span data-ttu-id="51122-117">Para configurar esto, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51122-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="51122-118">Este artículo le guiará por los pasos necesarios.</span><span class="sxs-lookup"><span data-stu-id="51122-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="51122-119">Los pasos de este artículo no impiden que los miembros de determinados roles creen grupos.</span><span class="sxs-lookup"><span data-stu-id="51122-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="51122-120">Los administradores globales pueden crear grupos a través de cualquier medio, como el centro de administración de Microsoft 365, Planner, Teams, Exchange y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="51122-120">Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="51122-121">Otros roles pueden crear grupos a través de medios limitados, que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="51122-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="51122-122">Administrador de Exchange: Centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="51122-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="51122-123">Soporte técnico de nivel 1 de asociado: Centro de administración de Microsoft 365, centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="51122-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="51122-124">Soporte técnico del nivel 2 del asociado: Centro de administración de Microsoft 365, centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="51122-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="51122-125">Escritores de directorios: Azure AD</span><span class="sxs-lookup"><span data-stu-id="51122-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="51122-126">Administrador de SharePoint: Centro de administración de SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="51122-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="51122-127">Team Service Administrator: Centro de administración de Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="51122-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="51122-128">Administrador de administración de usuarios: Centro de administración de Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="51122-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="51122-129">Si es miembro de uno de estos roles, puede crear grupos de Microsoft 365 para usuarios restringidos y, a continuación, asignar al usuario como propietario del grupo.</span><span class="sxs-lookup"><span data-stu-id="51122-129">If you're a member of one of these roles, you can create Microsoft 365 groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="51122-130">Los usuarios que tienen este rol pueden crear grupos conectados en Yammer, independientemente de la configuración de PowerShell que pueda impedir la creación.</span><span class="sxs-lookup"><span data-stu-id="51122-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="51122-131">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="51122-131">Licensing requirements</span></span>

<span data-ttu-id="51122-132">Para administrar quién crea grupos, las siguientes personas necesitan licencias de Azure AD Premium o de Azure AD Basic EDU asignadas:</span><span class="sxs-lookup"><span data-stu-id="51122-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="51122-133">El administrador que configura la configuración de creación de grupos</span><span class="sxs-lookup"><span data-stu-id="51122-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="51122-134">Los miembros del grupo de seguridad que tienen permiso para crear grupos</span><span class="sxs-lookup"><span data-stu-id="51122-134">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="51122-135">Consulte [asignar o quitar licencias en el portal de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) para obtener más información sobre cómo asignar licencias de Azure.</span><span class="sxs-lookup"><span data-stu-id="51122-135">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="51122-136">Los siguientes usuarios no necesitan que se les asignen licencias de Azure AD Premium o Azure AD Basic EDU:</span><span class="sxs-lookup"><span data-stu-id="51122-136">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="51122-137">Personas que son miembros de grupos de 365 de Microsoft y que no tienen la capacidad de crear otros grupos.</span><span class="sxs-lookup"><span data-stu-id="51122-137">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="51122-138">Paso 1: crear un grupo de seguridad para los usuarios que necesiten crear grupos de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="51122-138">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="51122-139">Solo se puede usar un grupo de seguridad de la organización para controlar quién puede crear grupos.</span><span class="sxs-lookup"><span data-stu-id="51122-139">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="51122-140">Sin embargo, puede anidar otros grupos de seguridad como miembros de este grupo.</span><span class="sxs-lookup"><span data-stu-id="51122-140">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="51122-141">Por ejemplo, el grupo denominado Permitir la creación de grupos es el grupo de seguridad designado, y los grupos denominados Usuarios de Microsoft Planner y Usuarios de Exchange Online son miembros de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="51122-141">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="51122-142">Los administradores de los roles enumerados anteriormente no tienen que ser miembros de este grupo: conservan la capacidad de crear grupos.</span><span class="sxs-lookup"><span data-stu-id="51122-142">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51122-143">Asegúrese de usar un **grupo de seguridad** para restringir quién puede crear grupos.</span><span class="sxs-lookup"><span data-stu-id="51122-143">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="51122-144">Si intenta usar un grupo de 365 de Microsoft, los miembros no podrán crear un grupo desde SharePoint porque busca un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="51122-144">If you try to use a Microsoft 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="51122-145">En el centro de administración, vaya a **la** página grupos de grupos \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="51122-145">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="51122-146">Haga clic en **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="51122-146">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="51122-147">Elija **seguridad** como tipo de grupo.</span><span class="sxs-lookup"><span data-stu-id="51122-147">Choose **Security** as the group type.</span></span> <span data-ttu-id="51122-148">Recuerde que el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="51122-148">Remember the name of the group!</span></span> <span data-ttu-id="51122-149">Lo necesitará más adelante.</span><span class="sxs-lookup"><span data-stu-id="51122-149">You'll need it later.</span></span>
  
4. <span data-ttu-id="51122-150">Termine de configurar el grupo de seguridad, agregando personas u otros grupos de seguridad que quiera que puedan crear grupos en su organización.</span><span class="sxs-lookup"><span data-stu-id="51122-150">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="51122-151">Para obtener instrucciones detalladas, vea [crear, editar o eliminar un grupo de seguridad en el centro de administración de Microsoft 365](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="51122-151">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="51122-152">Paso 2: Ejecutar los comandos de PowerShell</span><span class="sxs-lookup"><span data-stu-id="51122-152">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="51122-153">Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado en el nivel de Grupo:</span><span class="sxs-lookup"><span data-stu-id="51122-153">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="51122-154">Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) y siga las instrucciones para instalar la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="51122-154">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="51122-155">Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="51122-155">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="51122-156">Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.</span><span class="sxs-lookup"><span data-stu-id="51122-156">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="51122-157">Copie el script siguiente en un editor de texto, como el Bloc de notas o [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="51122-157">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="51122-158">Reemplace \* \< SecurityGroupName \> \* por el nombre del grupo de seguridad que ha creado.</span><span class="sxs-lookup"><span data-stu-id="51122-158">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="51122-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51122-159">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="51122-160">Guarde el archivo como GroupCreators. ps1.</span><span class="sxs-lookup"><span data-stu-id="51122-160">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="51122-161">En la ventana de PowerShell, navegue hasta la ubicación donde guardó el archivo (escriba "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="51122-161">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="51122-162">Para ejecutar el script, escriba:</span><span class="sxs-lookup"><span data-stu-id="51122-162">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="51122-163">e [inicie sesión con su cuenta de administrador](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="51122-163">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="51122-164">La última línea del script mostrará la configuración actualizada:</span><span class="sxs-lookup"><span data-stu-id="51122-164">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="51122-166">Si en el futuro desea cambiar el grupo de seguridad que se va a usar, puede volver a ejecutar el script con el nombre del nuevo grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="51122-166">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="51122-167">Si desea desactivar la restricción de creación de grupos y volver a permitir que todos los usuarios creen grupos, establezca $GroupName en "" y $AllowGroupCreation en "true" y vuelva a ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="51122-167">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="51122-168">Paso 4: comprobar que funciona</span><span class="sxs-lookup"><span data-stu-id="51122-168">Step 4: Verify that it works</span></span>

<span data-ttu-id="51122-169">Los cambios pueden tardar treinta minutos o más en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="51122-169">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="51122-170">Puede comprobar la nueva configuración haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="51122-170">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="51122-171">Inicie sesión con una cuenta de usuario que no debe tener la capacidad de crear grupos.</span><span class="sxs-lookup"><span data-stu-id="51122-171">Sign in with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="51122-172">Es decir, no son miembros del grupo de seguridad que ha creado o administrador.</span><span class="sxs-lookup"><span data-stu-id="51122-172">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="51122-173">Seleccione el mosaico de **Planner** .</span><span class="sxs-lookup"><span data-stu-id="51122-173">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="51122-174">En Planner, seleccione **nuevo plan** en el panel de navegación izquierdo para crear un plan.</span><span class="sxs-lookup"><span data-stu-id="51122-174">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="51122-175">Debe obtener un mensaje que indica que la creación de grupos y el plan está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="51122-175">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="51122-176">Vuelva a probar el mismo procedimiento con un miembro del grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="51122-176">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="51122-177">Si los miembros del grupo de seguridad no pueden crear grupos, compruebe que no se bloquean a través de la [Directiva de buzón de OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="51122-177">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="51122-178">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="51122-178">Related articles</span></span>

[<span data-ttu-id="51122-179">Introducción a PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="51122-179">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="51122-180">Configurar la administración de grupos de autoservicio en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="51122-180">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="51122-181">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="51122-181">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="51122-182">Cmdlets de Azure Active Directory para configurar configuraciones de grupo</span><span class="sxs-lookup"><span data-stu-id="51122-182">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
