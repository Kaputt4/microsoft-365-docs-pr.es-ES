---
title: Administrar quién puede crear grupos de Office 365
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
description: Obtenga información sobre cómo controlar qué usuarios pueden crear grupos de Office 365.
ms.openlocfilehash: 9016b96821dd9d40a0fb65574ce96d7badd0c2bd
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212086"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="7d3ae-103">Administrar quién puede crear grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="7d3ae-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="7d3ae-104">Puesto que es extremadamente fácil para los usuarios crear grupos de Office 365, no va a recibir una infinidad de solicitudes para crearlos en nombre de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="7d3ae-105">Sin embargo, dependiendo de su empresa, es posible que quiera controlar quién tiene la capacidad de crear grupos.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="7d3ae-106">En este artículo se explica cómo deshabilitar la capacidad de crear grupos en todos los servicios de Office 365 que usan grupos, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="7d3ae-106">This article explains how to disable the ability to create groups in all Office 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="7d3ae-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="7d3ae-107">Outlook</span></span>
    
- <span data-ttu-id="7d3ae-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d3ae-108">SharePoint</span></span>
    
- <span data-ttu-id="7d3ae-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="7d3ae-109">Yammer</span></span>
    
- <span data-ttu-id="7d3ae-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d3ae-110">Microsoft Teams</span></span>

- <span data-ttu-id="7d3ae-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="7d3ae-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="7d3ae-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="7d3ae-112">StaffHub</span></span>
    
- <span data-ttu-id="7d3ae-113">Planner</span><span class="sxs-lookup"><span data-stu-id="7d3ae-113">Planner</span></span>
    
- <span data-ttu-id="7d3ae-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="7d3ae-114">PowerBI</span></span>

- <span data-ttu-id="7d3ae-115">Plan de desarrollo</span><span class="sxs-lookup"><span data-stu-id="7d3ae-115">Roadmap</span></span>
    
<span data-ttu-id="7d3ae-116">Puede restringir la creación de grupos de Office 365 a los miembros de un grupo de seguridad en particular.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="7d3ae-117">Para configurar esto, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="7d3ae-118">Este artículo le guiará por los pasos necesarios.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="7d3ae-119">Los pasos de este artículo no impiden que los miembros de determinados roles creen grupos.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="7d3ae-120">Office 365 los administradores globales pueden crear grupos a través de cualquier medio, como el centro de administración de Microsoft 365, Planner, Teams, Exchange y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="7d3ae-121">Otros roles pueden crear grupos a través de medios limitados, que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="7d3ae-122">Administrador de Exchange: Centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d3ae-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="7d3ae-123">Soporte técnico de nivel 1 de asociado: Centro de administración de Microsoft 365, centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d3ae-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="7d3ae-124">Soporte técnico del nivel 2 del asociado: Centro de administración de Microsoft 365, centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d3ae-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="7d3ae-125">Escritores de directorios: Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d3ae-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="7d3ae-126">Administrador de SharePoint: Centro de administración de SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d3ae-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="7d3ae-127">Team Service Administrator: Centro de administración de Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d3ae-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="7d3ae-128">Administrador de administración de usuarios: Centro de administración de Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7d3ae-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="7d3ae-129">Si es miembro de uno de estos roles, puede crear Grupos de Office 365 para usuarios restringidos y, después, asignar al usuario la propiedad del grupo.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="7d3ae-130">Los usuarios que tienen este rol pueden crear grupos conectados en Yammer, independientemente de la configuración de PowerShell que pueda impedir la creación.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7d3ae-131">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="7d3ae-131">Licensing requirements</span></span>

<span data-ttu-id="7d3ae-132">Para administrar quién crea grupos, las siguientes personas necesitan licencias de Azure AD Premium o de Azure AD Basic EDU asignadas:</span><span class="sxs-lookup"><span data-stu-id="7d3ae-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7d3ae-133">El administrador que configura la configuración de creación de grupos</span><span class="sxs-lookup"><span data-stu-id="7d3ae-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="7d3ae-134">Los miembros del grupo de seguridad que tienen permiso para crear grupos</span><span class="sxs-lookup"><span data-stu-id="7d3ae-134">The members of the security group who are allowed to create groups</span></span>

<span data-ttu-id="7d3ae-135">Los siguientes usuarios no necesitan que se les asignen licencias de Azure AD Premium o Azure AD Basic EDU:</span><span class="sxs-lookup"><span data-stu-id="7d3ae-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7d3ae-136">Personas que son miembros de los grupos de Office 365 y que no tienen la capacidad de crear otros grupos.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="7d3ae-137">Paso 1: Crear un grupo de seguridad para los usuarios que necesiten crear Grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="7d3ae-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="7d3ae-138">Solo se puede usar un grupo de seguridad de la organización para controlar quién puede crear grupos.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="7d3ae-139">Sin embargo, puede anidar otros grupos de seguridad como miembros de este grupo.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="7d3ae-140">Por ejemplo, el grupo denominado Permitir la creación de grupos es el grupo de seguridad designado, y los grupos denominados Usuarios de Microsoft Planner y Usuarios de Exchange Online son miembros de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="7d3ae-141">Los administradores de los roles enumerados anteriormente no tienen que ser miembros de este grupo: conservan la capacidad de crear grupos.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d3ae-142">Asegúrese de usar un **grupo de seguridad** para restringir quién puede crear grupos.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="7d3ae-143">Si intenta usar un grupo de Office 365, los miembros no podrán crear un grupo desde SharePoint porque busca un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-143">If you try to use an Office 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="7d3ae-144">En el centro de administración, vaya a **la** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="7d3ae-145">Haga clic en **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="7d3ae-146">Elija **seguridad** como tipo de grupo.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="7d3ae-147">Recuerde que el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-147">Remember the name of the group!</span></span> <span data-ttu-id="7d3ae-148">Lo necesitará más adelante.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="7d3ae-149">Termine de configurar el grupo de seguridad, agregando personas u otros grupos de seguridad que quiera que puedan crear grupos en su organización.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-149">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="7d3ae-150">Para obtener instrucciones detalladas, vea [crear, editar o eliminar un grupo de seguridad en el centro de administración de Microsoft 365](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="7d3ae-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="7d3ae-151">Paso 2: Ejecutar los comandos de PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d3ae-151">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="7d3ae-152">Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado en el nivel de Grupo:</span><span class="sxs-lookup"><span data-stu-id="7d3ae-152">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="7d3ae-153">Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) y siga las instrucciones para instalar la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-153">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="7d3ae-154">Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-154">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="7d3ae-155">Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-155">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="7d3ae-156">Copie el script siguiente en un editor de texto, como el Bloc de notas o [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="7d3ae-156">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="7d3ae-157">Reemplace \* \<SecurityGroupName\> \* por el nombre del grupo de seguridad que ha creado.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-157">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="7d3ae-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d3ae-158">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="7d3ae-159">Guarde el archivo como GroupCreators. ps1.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-159">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="7d3ae-160">En la ventana de PowerShell, navegue hasta la ubicación donde guardó el archivo (escriba "CD <FileLocation>").</span><span class="sxs-lookup"><span data-stu-id="7d3ae-160">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="7d3ae-161">Para ejecutar el script, escriba:</span><span class="sxs-lookup"><span data-stu-id="7d3ae-161">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="7d3ae-162">e [inicie sesión con su cuenta de administrador](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-162">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="7d3ae-163">La última línea del script mostrará la configuración actualizada:</span><span class="sxs-lookup"><span data-stu-id="7d3ae-163">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="7d3ae-165">Si en el futuro desea cambiar el grupo de seguridad que se va a usar, puede volver a ejecutar el script con el nombre del nuevo grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-165">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="7d3ae-166">Si desea desactivar la restricción de creación de grupos y volver a permitir que todos los usuarios creen grupos, establezca $GroupName en "" y $AllowGroupCreation en "true" y vuelva a ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-166">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="7d3ae-167">Paso 4: comprobar que funciona</span><span class="sxs-lookup"><span data-stu-id="7d3ae-167">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="7d3ae-168">Inicie sesión en Office 365 con la cuenta de usuario de alguien que NO debe tener la capacidad de crear grupos.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-168">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="7d3ae-169">Es decir, no son miembros del grupo de seguridad que ha creado o administrador.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-169">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="7d3ae-170">Seleccione el mosaico de **Planner** .</span><span class="sxs-lookup"><span data-stu-id="7d3ae-170">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="7d3ae-171">En Planner, seleccione **nuevo plan** en el panel de navegación izquierdo para crear un plan.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-171">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="7d3ae-172">Debe obtener un mensaje que indica que la creación de grupos y el plan está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-172">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="7d3ae-173">Vuelva a probar el mismo procedimiento con un miembro del grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7d3ae-173">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="7d3ae-174">Si los miembros del grupo de seguridad no pueden crear grupos, compruebe que no se bloquean a través de la [Directiva de buzón de OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="7d3ae-174">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="7d3ae-175">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="7d3ae-175">Related articles</span></span>

[<span data-ttu-id="7d3ae-176">Introducción a PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="7d3ae-176">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="7d3ae-177">Configurar la administración de grupos de autoservicio en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7d3ae-177">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="7d3ae-178">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="7d3ae-178">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="7d3ae-179">Cmdlets de Azure Active Directory para configurar configuraciones de grupo</span><span class="sxs-lookup"><span data-stu-id="7d3ae-179">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
