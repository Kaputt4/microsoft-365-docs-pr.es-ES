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
ms.openlocfilehash: 3a0ac5ef48eabfd06e0df3f509c7d8e4be3cff10
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602024"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="29455-103">Administrar quién puede crear grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29455-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="29455-104">De forma predeterminada, todos los usuarios pueden crear grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="29455-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="29455-105">Este es el método recomendado, ya que permite a los usuarios empezar a colaborar sin necesidad de ayuda.</span><span class="sxs-lookup"><span data-stu-id="29455-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="29455-106">Si su empresa requiere que restrinja quién puede crear grupos, siga los procedimientos que se indican en este artículo.</span><span class="sxs-lookup"><span data-stu-id="29455-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="29455-107">Al limitar quién puede crear un grupo, afecta a todos los servicios que se basan en grupos para Access, incluidos:</span><span class="sxs-lookup"><span data-stu-id="29455-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="29455-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="29455-108">Outlook</span></span>
- <span data-ttu-id="29455-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="29455-109">SharePoint</span></span>
- <span data-ttu-id="29455-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="29455-110">Yammer</span></span>
- <span data-ttu-id="29455-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29455-111">Microsoft Teams</span></span>
- <span data-ttu-id="29455-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="29455-112">Microsoft Stream</span></span>
- <span data-ttu-id="29455-113">Planner</span><span class="sxs-lookup"><span data-stu-id="29455-113">Planner</span></span>
- <span data-ttu-id="29455-114">PowerBI (Classic)</span><span class="sxs-lookup"><span data-stu-id="29455-114">PowerBI (classic)</span></span>
- <span data-ttu-id="29455-115">Proyecto para la web o plan de desarrollo</span><span class="sxs-lookup"><span data-stu-id="29455-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="29455-116">Puede restringir la creación de grupos de Microsoft 365 a los miembros de un grupo de seguridad en particular.</span><span class="sxs-lookup"><span data-stu-id="29455-116">You can restrict Microsoft 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="29455-117">Para configurar esto, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29455-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="29455-118">Este artículo le guiará por los pasos necesarios.</span><span class="sxs-lookup"><span data-stu-id="29455-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="29455-119">Los pasos de este artículo no impiden que los miembros de determinados roles creen grupos.</span><span class="sxs-lookup"><span data-stu-id="29455-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="29455-120">Office 365 los administradores globales pueden crear grupos a través de cualquier medio, como el centro de administración de Microsoft 365, Planner, Teams, Exchange y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="29455-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="29455-121">Otros roles pueden crear grupos a través de medios limitados, que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="29455-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="29455-122">Administrador de Exchange: Centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="29455-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="29455-123">Soporte técnico de nivel 1 de asociado: Centro de administración de Microsoft 365, centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="29455-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="29455-124">Soporte técnico del nivel 2 del asociado: Centro de administración de Microsoft 365, centro de administración de Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="29455-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="29455-125">Escritores de directorios: Azure AD</span><span class="sxs-lookup"><span data-stu-id="29455-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="29455-126">Administrador de SharePoint: Centro de administración de SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="29455-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="29455-127">Team Service Administrator: Centro de administración de Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="29455-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="29455-128">Administrador de administración de usuarios: Centro de administración de Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="29455-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>

<span data-ttu-id="29455-129">Si es miembro de uno de estos roles, puede crear grupos de Microsoft 365 para usuarios restringidos y, a continuación, asignar al usuario como propietario del grupo.</span><span class="sxs-lookup"><span data-stu-id="29455-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="29455-130">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="29455-130">Licensing requirements</span></span>

<span data-ttu-id="29455-131">Para administrar quién crea grupos, las siguientes personas necesitan licencias de Azure AD Premium o de Azure AD Basic EDU asignadas:</span><span class="sxs-lookup"><span data-stu-id="29455-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="29455-132">El administrador que configura la configuración de creación de grupos</span><span class="sxs-lookup"><span data-stu-id="29455-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="29455-133">Los miembros del grupo de seguridad que tienen permiso para crear grupos</span><span class="sxs-lookup"><span data-stu-id="29455-133">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="29455-134">Consulte [asignar o quitar licencias en el portal de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) para obtener más información sobre cómo asignar licencias de Azure.</span><span class="sxs-lookup"><span data-stu-id="29455-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="29455-135">Los siguientes usuarios no necesitan que se les asignen licencias de Azure AD Premium o Azure AD Basic EDU:</span><span class="sxs-lookup"><span data-stu-id="29455-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="29455-136">Personas que son miembros de grupos de 365 de Microsoft y que no tienen la capacidad de crear otros grupos.</span><span class="sxs-lookup"><span data-stu-id="29455-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="29455-137">Paso 1: crear un grupo de seguridad para los usuarios que necesiten crear grupos de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="29455-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="29455-138">Solo se puede usar un grupo de seguridad de la organización para controlar quién puede crear grupos.</span><span class="sxs-lookup"><span data-stu-id="29455-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="29455-139">Sin embargo, puede anidar otros grupos de seguridad como miembros de este grupo.</span><span class="sxs-lookup"><span data-stu-id="29455-139">But, you can nest other security groups as members of this group.</span></span>

<span data-ttu-id="29455-140">Los administradores de los roles enumerados anteriormente no tienen que ser miembros de este grupo: conservan la capacidad de crear grupos.</span><span class="sxs-lookup"><span data-stu-id="29455-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29455-141">Asegúrese de usar un **grupo de seguridad** para restringir quién puede crear grupos.</span><span class="sxs-lookup"><span data-stu-id="29455-141">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="29455-142">No se admite el uso de un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="29455-142">Using a Microsoft 365 group is not supported.</span></span>

1. <span data-ttu-id="29455-143">En el centro de administración, vaya a la [Página grupos](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="29455-143">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="29455-144">Haga clic en **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="29455-144">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="29455-145">Elija **seguridad** como tipo de grupo.</span><span class="sxs-lookup"><span data-stu-id="29455-145">Choose **Security** as the group type.</span></span> <span data-ttu-id="29455-146">Recuerde que el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="29455-146">Remember the name of the group!</span></span> <span data-ttu-id="29455-147">Lo necesitará más adelante.</span><span class="sxs-lookup"><span data-stu-id="29455-147">You'll need it later.</span></span>

4. <span data-ttu-id="29455-148">Termine de configurar el grupo de seguridad, agregando personas u otros grupos de seguridad que quiera que puedan crear grupos en su organización.</span><span class="sxs-lookup"><span data-stu-id="29455-148">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="29455-149">Para obtener instrucciones detalladas, vea [crear, editar o eliminar un grupo de seguridad en el centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="29455-149">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="29455-150">Paso 2: Ejecutar los comandos de PowerShell</span><span class="sxs-lookup"><span data-stu-id="29455-150">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="29455-151">Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado en el nivel de Grupo:</span><span class="sxs-lookup"><span data-stu-id="29455-151">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="29455-152">Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) y siga las instrucciones para instalar la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="29455-152">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="29455-153">Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="29455-153">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="29455-154">Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.</span><span class="sxs-lookup"><span data-stu-id="29455-154">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="29455-155">Copie el script siguiente en un editor de texto, como el Bloc de notas o [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="29455-155">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="29455-156">Reemplace *\<SecurityGroupName\>* por el nombre del grupo de seguridad que ha creado.</span><span class="sxs-lookup"><span data-stu-id="29455-156">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="29455-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="29455-157">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="29455-158">Guarde el archivo como GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="29455-158">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="29455-159">En la ventana de PowerShell, navegue hasta la ubicación donde guardó el archivo (escriba "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="29455-159">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="29455-160">Para ejecutar el script, escriba:</span><span class="sxs-lookup"><span data-stu-id="29455-160">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="29455-161">e [inicie sesión con su cuenta de administrador](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="29455-161">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
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

<span data-ttu-id="29455-162">La última línea del script mostrará la configuración actualizada:</span><span class="sxs-lookup"><span data-stu-id="29455-162">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="29455-164">Si en el futuro desea cambiar el grupo de seguridad que se va a usar, puede volver a ejecutar el script con el nombre del nuevo grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="29455-164">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="29455-165">Si desea desactivar la restricción de creación de grupos y volver a permitir que todos los usuarios creen grupos, establezca $GroupName en "" y $AllowGroupCreation en "true" y vuelva a ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="29455-165">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="29455-166">Paso 3: Comprobar que funciona correctamente</span><span class="sxs-lookup"><span data-stu-id="29455-166">Step 3: Verify that it works</span></span>

<span data-ttu-id="29455-167">Los cambios pueden tardar treinta minutos o más en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="29455-167">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="29455-168">Puede comprobar la nueva configuración haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="29455-168">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="29455-169">Inicie sesión en Microsoft 365 con una cuenta de usuario que no debe tener la capacidad de crear grupos.</span><span class="sxs-lookup"><span data-stu-id="29455-169">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="29455-170">Es decir, no son miembros del grupo de seguridad que ha creado o administrador.</span><span class="sxs-lookup"><span data-stu-id="29455-170">That is, they are not a member of the security group you created or an administrator.</span></span>

2. <span data-ttu-id="29455-171">Seleccione el mosaico de **Planner** .</span><span class="sxs-lookup"><span data-stu-id="29455-171">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="29455-172">En Planner, seleccione **nuevo plan** en el panel de navegación izquierdo para crear un plan.</span><span class="sxs-lookup"><span data-stu-id="29455-172">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="29455-173">Debe obtener un mensaje que indica que la creación de grupos y el plan está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="29455-173">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="29455-174">Vuelva a probar el mismo procedimiento con un miembro del grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="29455-174">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="29455-175">Si los miembros del grupo de seguridad no pueden crear grupos, compruebe que no se bloquean a través de la [Directiva de buzón de OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="29455-175">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-articles"></a><span data-ttu-id="29455-176">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="29455-176">Related articles</span></span>

[<span data-ttu-id="29455-177">Introducción a PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="29455-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="29455-178">Configurar la administración de grupos de autoservicio en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="29455-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="29455-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="29455-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="29455-180">Cmdlets de Azure Active Directory para configurar configuraciones de grupo</span><span class="sxs-lookup"><span data-stu-id="29455-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
