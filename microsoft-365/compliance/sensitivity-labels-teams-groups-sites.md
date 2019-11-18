---
title: Usar etiquetas de confidencialidad con Microsoft Teams, Office 365 grupos y sitios de SharePoint (versión preliminar pública)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/13/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Puede aplicar etiquetas a Microsoft Teams, a los grupos de Office 365 y a los sitios de SharePoint.
ms.openlocfilehash: 5fc7fec199482449baf9174d6e854d0a5564faa6
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "38687813"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="51f41-103">Usar etiquetas de confidencialidad con Microsoft Teams, Office 365 grupos y sitios de SharePoint (versión preliminar pública)</span><span class="sxs-lookup"><span data-stu-id="51f41-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="51f41-104">Al crear etiquetas de confidencialidad en el [centro de cumplimiento de microsoft 365](https://protection.office.com/), ahora puede aplicarlas a Microsoft Teams, a los grupos de Office 365 y a los sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="51f41-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="51f41-105">Puede asociar directivas con las etiquetas para controlar:</span><span class="sxs-lookup"><span data-stu-id="51f41-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="51f41-106">Configuración pública o privada</span><span class="sxs-lookup"><span data-stu-id="51f41-106">Public/private settings</span></span>
- <span data-ttu-id="51f41-107">Acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="51f41-107">Guest access</span></span>
- <span data-ttu-id="51f41-108">Acceso desde dispositivos no administrados</span><span class="sxs-lookup"><span data-stu-id="51f41-108">Access from unmanaged devices</span></span>

<span data-ttu-id="51f41-109">Cuando se aplica una etiqueta a un equipo o grupo, la etiqueta se aplica automáticamente al sitio de grupo de SharePoint conectado y al contrario.</span><span class="sxs-lookup"><span data-stu-id="51f41-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="51f41-110">Ahora, también puede habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="51f41-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="51f41-111">[Obtenga más información](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="51f41-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="51f41-112">Información sobre la versión preliminar pública para Microsoft Teams, Office 365 grupos y sitios de SharePoint</span><span class="sxs-lookup"><span data-stu-id="51f41-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="51f41-113">Las etiquetas de confidencialidad para Microsoft Teams, Office 365 grupos y sitios de SharePoint se implementan gradualmente para los inquilinos y podrían cambiar antes de la versión final.</span><span class="sxs-lookup"><span data-stu-id="51f41-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

## <a name="overview"></a><span data-ttu-id="51f41-114">Información general</span><span class="sxs-lookup"><span data-stu-id="51f41-114">Overview</span></span>

<span data-ttu-id="51f41-115">Al publicar etiquetas de confidencialidad, los usuarios de Office 365 tienen acceso a la misma lista de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="51f41-115">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="51f41-116">Estas imágenes muestran:</span><span class="sxs-lookup"><span data-stu-id="51f41-116">These images show:</span></span>

- <span data-ttu-id="51f41-117">Cómo aparece la lista cuando se crea un nuevo sitio de grupo desde SharePoint</span><span class="sxs-lookup"><span data-stu-id="51f41-117">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="51f41-118">Cuando ve la lista en Word</span><span class="sxs-lookup"><span data-stu-id="51f41-118">When you view the list in Word</span></span>

![Una etiqueta de confidencialidad al crear un sitio de grupo desde SharePoint](media/sensitivity-label-new-team-site.png)

![Etiqueta de confidencialidad mostrada en la aplicación de escritorio de Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="51f41-121">Habilitación de esta vista previa mediante Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="51f41-121">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="51f41-122">Inicie sesión en Azure como administrador global mediante Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51f41-122">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="51f41-123">Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="51f41-123">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="51f41-124">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="51f41-124">Run the following command:</span></span>

```powershell
  Connect-AzureAD
  $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
  if ($setting -eq $null)
  {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
  }
  else
  {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
  }
```

<span data-ttu-id="51f41-125">Office 365 ya no usa las clasificaciones antiguas para nuevos grupos y sitios de SharePoint cuando habilita esta vista previa.</span><span class="sxs-lookup"><span data-stu-id="51f41-125">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="51f41-126">Si usó la [clasificación de sitios de Azure ad](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($Setting ["ClassificationList"]), los grupos y sitios existentes seguirán mostrando las clasificaciones antiguas.</span><span class="sxs-lookup"><span data-stu-id="51f41-126">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="51f41-127">Para mostrar las clasificaciones nuevas, conviértalos.</span><span class="sxs-lookup"><span data-stu-id="51f41-127">To display the new classifications, convert them.</span></span> <span data-ttu-id="51f41-128">Para obtener información sobre cómo convertirlos, vea [si usó la clasificación clásica de sitios de Azure ad](#if-you-used-classic-azure-ad-site-classification).</span><span class="sxs-lookup"><span data-stu-id="51f41-128">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span>

## <a name="set-site-and-group-settings-when-you-create-sensitivity-labels"></a><span data-ttu-id="51f41-129">Establecer la configuración de sitios y grupos al crear etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="51f41-129">Set site and group settings when you create sensitivity labels</span></span>

<span data-ttu-id="51f41-130">Después de habilitar la vista previa, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51f41-130">After you enable the preview, follow these steps:</span></span>

1. <span data-ttu-id="51f41-131">En el centro de cumplimiento de Microsoft 365, seleccione**etiquetas de sensibilidad**de **clasificación** > .</span><span class="sxs-lookup"><span data-stu-id="51f41-131">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="51f41-132">Seleccione **crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="51f41-132">Select **Create a label**.</span></span>

3. <span data-ttu-id="51f41-133">Seleccione las opciones que desee y, a continuación, en la pestaña **configuración de sitio y grupo** , elija:</span><span class="sxs-lookup"><span data-stu-id="51f41-133">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="51f41-134">Privacidad (pública o privada): privada significa que solo los miembros aprobados en la organización pueden ver el contenido del grupo.</span><span class="sxs-lookup"><span data-stu-id="51f41-134">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="51f41-135">Cualquier otra persona de la organización no puede ver el contenido del grupo.</span><span class="sxs-lookup"><span data-stu-id="51f41-135">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="51f41-136">Más información</span><span class="sxs-lookup"><span data-stu-id="51f41-136">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="51f41-137">Acceso de invitado: puede controlar si los invitados se pueden agregar a un grupo.</span><span class="sxs-lookup"><span data-stu-id="51f41-137">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="51f41-138">Información acerca de la administración del acceso de invitado en Office 365 grupos</span><span class="sxs-lookup"><span data-stu-id="51f41-138">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="51f41-139">Dispositivos no administrados: esta opción permite bloquear o limitar el acceso al contenido de SharePoint desde dispositivos que no son compatibles con AD híbrido o que no son compatibles con Intune.</span><span class="sxs-lookup"><span data-stu-id="51f41-139">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="51f41-140">Si selecciona dispositivos no administrados, tendrá que ir a Azure AD para finalizar la configuración de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="51f41-140">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="51f41-141">Para obtener información, vea [controlar el acceso desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="51f41-141">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

![Ficha Configuración de sitio y grupo](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="51f41-143">Solo la configuración de sitio y grupo surte efecto cuando se aplica una etiqueta a un equipo, grupo o sitio.</span><span class="sxs-lookup"><span data-stu-id="51f41-143">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="51f41-144">Otras opciones, como el cifrado y la marcación de contenido, no se aplican a todo el contenido dentro del equipo, grupo o sitio.</span><span class="sxs-lookup"><span data-stu-id="51f41-144">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="51f41-145">De forma similar, si crea una etiqueta y no activa la configuración de sitio y grupo, la etiqueta seguirá estando disponible cuando los usuarios creen equipos, grupos y sitios, pero no hará nada cuando los usuarios lo apliquen.</span><span class="sxs-lookup"><span data-stu-id="51f41-145">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="51f41-146">Obtener información sobre cómo publicar una etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="51f41-146">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="51f41-147">Aplicar una etiqueta de confidencialidad a un nuevo equipo</span><span class="sxs-lookup"><span data-stu-id="51f41-147">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="51f41-148">Los usuarios pueden seleccionar las etiquetas de confidencialidad cuando crean nuevos equipos en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="51f41-148">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="51f41-149">Cuando seleccionan el nivel de confidencialidad, la configuración de privacidad cambia cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="51f41-149">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="51f41-150">En función de la configuración de acceso de invitado que haya seleccionado para la etiqueta, los usuarios podrán o no agregar personas fuera de la organización al equipo.</span><span class="sxs-lookup"><span data-stu-id="51f41-150">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![La configuración de privacidad cuando se crea un nuevo equipo](media/privacy-setting-new-team.png)

<span data-ttu-id="51f41-152">Después de crear el equipo, la etiqueta de confidencialidad aparece en la esquina superior derecha de todos los canales.</span><span class="sxs-lookup"><span data-stu-id="51f41-152">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![La etiqueta de confidencialidad aparece en el equipo](media/privacy-setting-teams.png)

<span data-ttu-id="51f41-154">El servicio aplica automáticamente la misma etiqueta de confidencialidad al grupo de Office 365 y al sitio de grupo de SharePoint conectado.</span><span class="sxs-lookup"><span data-stu-id="51f41-154">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="51f41-155">Aplicar una etiqueta de confidencialidad a un nuevo grupo</span><span class="sxs-lookup"><span data-stu-id="51f41-155">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="51f41-156">En Outlook en la web, el nuevo cuadro de **confidencialidad** contiene las etiquetas publicadas.</span><span class="sxs-lookup"><span data-stu-id="51f41-156">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="51f41-157">Si los usuarios desean más información, pueden hacer clic en el icono ayuda para leer los detalles sobre las etiquetas disponibles y las directivas asociadas.</span><span class="sxs-lookup"><span data-stu-id="51f41-157">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![Creación de un grupo y selección de una opción en confidencialidad](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="51f41-159">Aplicar una etiqueta de confidencialidad a un sitio nuevo</span><span class="sxs-lookup"><span data-stu-id="51f41-159">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="51f41-160">Los administradores y los usuarios finales pueden seleccionar las etiquetas de confidencialidad cuando crean sitios de grupo y de comunicación modernos.</span><span class="sxs-lookup"><span data-stu-id="51f41-160">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="51f41-161">Obtenga información sobre cómo crear un sitio en el nuevo centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="51f41-161">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="51f41-162">Cuando los usuarios crean sitios de comunicación y de equipo modernos, la etiqueta de confidencialidad ya está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="51f41-162">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="51f41-163">Los usuarios pueden seleccionar el icono de ayuda para obtener más información sobre las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="51f41-163">Users can select the help icon to learn more about the labels.</span></span>

![Creación de un sitio y selección de una opción en confidencialidad](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="51f41-165">Cuando los usuarios visitan el sitio, pueden ver el nombre de la etiqueta y las directivas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="51f41-165">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Un sitio con una etiqueta de confidencialidad aplicada](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="51f41-167">Administrar las etiquetas de confidencialidad en el centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="51f41-167">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="51f41-168">Para ver y editar las etiquetas, use la página sitios activos en el nuevo centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="51f41-168">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![Columna confidencial de la página sitios activos](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="51f41-170">[Obtenga más información sobre cómo administrar sitios en el nuevo centro de administración de SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="51f41-170">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="51f41-171">Cambiar la configuración de sitio y grupo de una etiqueta</span><span class="sxs-lookup"><span data-stu-id="51f41-171">Change site and group settings for a label</span></span>

<span data-ttu-id="51f41-172">Como práctica recomendada, no cambie la configuración después de aplicar una etiqueta a varios equipos, grupos o sitios.</span><span class="sxs-lookup"><span data-stu-id="51f41-172">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="51f41-173">Si debe realizar algún cambio, deberá usar un script de PowerShell de Azure AD para aplicar manualmente las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="51f41-173">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="51f41-174">Este método garantiza que todos los equipos, sitios y grupos existentes apliquen la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="51f41-174">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="51f41-175">Compatibilidad con las nuevas etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="51f41-175">Support for the new sensitivity labels</span></span>

<span data-ttu-id="51f41-176">Las siguientes aplicaciones y servicios admiten las etiquetas de confidencialidad en esta vista previa:</span><span class="sxs-lookup"><span data-stu-id="51f41-176">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="51f41-177">Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51f41-177">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="51f41-178">SharePoint</span><span class="sxs-lookup"><span data-stu-id="51f41-178">SharePoint</span></span>
- <span data-ttu-id="51f41-179">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="51f41-179">Outlook on the web</span></span>
- <span data-ttu-id="51f41-180">Teams</span><span class="sxs-lookup"><span data-stu-id="51f41-180">Teams</span></span>
- <span data-ttu-id="51f41-181">Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="51f41-181">SharePoint admin center</span></span>
- <span data-ttu-id="51f41-182">Centro de administración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="51f41-182">Azure AD admin center</span></span>

<span data-ttu-id="51f41-183">No puede usar las siguientes aplicaciones y servicios para crear grupos de Office 365 con las nuevas etiquetas de confidencialidad:</span><span class="sxs-lookup"><span data-stu-id="51f41-183">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="51f41-184">Outlook para Mac</span><span class="sxs-lookup"><span data-stu-id="51f41-184">Outlook for the Mac</span></span>
- <span data-ttu-id="51f41-185">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="51f41-185">Outlook mobile</span></span>  
- <span data-ttu-id="51f41-186">Escritorio de Outlook para Windows</span><span class="sxs-lookup"><span data-stu-id="51f41-186">Outlook desktop for Windows</span></span>
- <span data-ttu-id="51f41-187">Formularios</span><span class="sxs-lookup"><span data-stu-id="51f41-187">Forms</span></span>  
- <span data-ttu-id="51f41-188">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="51f41-188">Dynamics 365</span></span>  
- <span data-ttu-id="51f41-189">Yammer</span><span class="sxs-lookup"><span data-stu-id="51f41-189">Yammer</span></span>  
- <span data-ttu-id="51f41-190">Stream</span><span class="sxs-lookup"><span data-stu-id="51f41-190">Stream</span></span>  
- <span data-ttu-id="51f41-191">Planner</span><span class="sxs-lookup"><span data-stu-id="51f41-191">Planner</span></span>  
- <span data-ttu-id="51f41-192">Project</span><span class="sxs-lookup"><span data-stu-id="51f41-192">Project</span></span>  
- <span data-ttu-id="51f41-193">PowerBI</span><span class="sxs-lookup"><span data-stu-id="51f41-193">PowerBI</span></span>  
- <span data-ttu-id="51f41-194">Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="51f41-194">Teams admin center</span></span>  
- <span data-ttu-id="51f41-195">Centro de administración de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="51f41-195">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="51f41-196">Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="51f41-196">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="51f41-197">Si usó la clasificación clásica del sitio de Azure AD</span><span class="sxs-lookup"><span data-stu-id="51f41-197">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="51f41-198">Office 365 ya no es compatible con las clasificaciones antiguas para nuevos grupos y sitios de SharePoint cuando habilita esta vista previa.</span><span class="sxs-lookup"><span data-stu-id="51f41-198">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="51f41-199">Sin embargo, los grupos y sitios existentes todavía muestran las clasificaciones antiguas a menos que las convierta.</span><span class="sxs-lookup"><span data-stu-id="51f41-199">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="51f41-200">Las clasificaciones antiguas incluyen la clasificación de los sitios "modernos" que configuró, posiblemente a través de Azure AD PowerShell o la biblioteca principal de PnP `ClassificationList` , que definía los valores de la configuración.</span><span class="sxs-lookup"><span data-stu-id="51f41-200">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="51f41-201">Por ejemplo, en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="51f41-201">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="51f41-202">Para obtener más información sobre el método de clasificación anterior, consulte [clasificación de sitios "modernos" de SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="51f41-202">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="51f41-203">En función de la implementación actual, tiene dos opciones para convertir las clasificaciones antiguas en las nuevas clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="51f41-203">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="51f41-204">Si nunca ha usado etiquetas de confidencialidad (etiquetas unificadas de protección de la información de Microsoft) para los archivos y el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="51f41-204">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="51f41-205">Le recomendamos que haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="51f41-205">We recommend that you:</span></span>

1. <span data-ttu-id="51f41-206">Cree nuevas etiquetas de confidencialidad en el centro de cumplimiento de Microsoft 365 que tengan los mismos nombres que las clasificaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="51f41-206">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="51f41-207">Use PowerShell para aplicar las nuevas etiquetas a los grupos de Office 365 y los sitios de SharePoint existentes mediante la asignación de nombres.</span><span class="sxs-lookup"><span data-stu-id="51f41-207">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="51f41-208">Elimine las clasificaciones antiguas.</span><span class="sxs-lookup"><span data-stu-id="51f41-208">Delete the old classifications.</span></span>

<span data-ttu-id="51f41-209">Las aplicaciones y los servicios que admitan las nuevas etiquetas de confidencialidad las mostrarán.</span><span class="sxs-lookup"><span data-stu-id="51f41-209">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="51f41-210">Cree nuevos equipos, grupos y sitios con las nuevas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="51f41-210">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="51f41-211">Los usuarios pueden seguir creando grupos a partir de aplicaciones y servicios que no admiten las nuevas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="51f41-211">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="51f41-212">Sin embargo, los usuarios no pueden aplicar una etiqueta a estos grupos.</span><span class="sxs-lookup"><span data-stu-id="51f41-212">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="51f41-213">Use PowerShell para aplicar las nuevas etiquetas de confidencialidad a estos grupos.</span><span class="sxs-lookup"><span data-stu-id="51f41-213">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="51f41-214">Puede mantener sus clasificaciones antiguas; sin embargo, se recomienda encarecidamente usar PowerShell para aplicar las nuevas etiquetas de confidencialidad a estos grupos.</span><span class="sxs-lookup"><span data-stu-id="51f41-214">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="51f41-215">Las aplicaciones y los servicios que admiten las nuevas etiquetas de confidencialidad se crearán con las nuevas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="51f41-215">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="51f41-216">Cuando los usuarios crean grupos a partir de aplicaciones y servicios que no admiten las nuevas etiquetas, pueden seleccionar una clasificación.</span><span class="sxs-lookup"><span data-stu-id="51f41-216">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="51f41-217">Si usa etiquetas de confidencialidad (etiquetas unificadas de protección de la información de Microsoft) para los archivos y el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="51f41-217">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="51f41-218">En cuanto habilite esta vista previa, vaya a cada etiqueta del centro de cumplimiento de Microsoft 365 y aplique las directivas que desee para los sitios y grupos.</span><span class="sxs-lookup"><span data-stu-id="51f41-218">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="51f41-219">Los usuarios empezarán a ver las etiquetas existentes disponibles para los sitios y grupos.</span><span class="sxs-lookup"><span data-stu-id="51f41-219">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="51f41-220">Preparar el shell de administración de SharePoint Online antes de reetiquetar los grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="51f41-220">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="51f41-221">Antes de aplicar nuevas etiquetas, asegúrese de que está ejecutando el shell de administración de SharePoint Online más reciente.</span><span class="sxs-lookup"><span data-stu-id="51f41-221">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="51f41-222">Si ya tiene la última versión, puede volver a [etiquetar los grupos de Office 365 con nuevas etiquetas de confidencialidad](#relabel-office-365-groups-with-new-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="51f41-222">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="51f41-223">Para preparar el shell de administración de SharePoint Online para la vista previa:</span><span class="sxs-lookup"><span data-stu-id="51f41-223">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="51f41-224">Si instaló una versión anterior del shell de administración de SharePoint Online, vaya a **Agregar o quitar programas** y desinstale "Shell de administración de SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="51f41-224">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="51f41-225">En un explorador Web, vaya a la página del centro de descarga y [Descargue el shell de administración de SharePoint Online más reciente](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="51f41-225">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="51f41-226">Seleccione su idioma y, a continuación, haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="51f41-226">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="51f41-227">Elija entre el archivo x64 y x86. msi.</span><span class="sxs-lookup"><span data-stu-id="51f41-227">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="51f41-228">Descargue el archivo x64 si ejecuta la versión de 64 bits de Windows o el archivo x86 si está ejecutando la versión de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="51f41-228">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="51f41-229">Si no lo sabe, consulte ¿ [qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="51f41-229">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="51f41-230">Una vez descargado el archivo, ejecute el archivo y siga los pasos del Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="51f41-230">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="51f41-231">Reetiquetar grupos de Office 365 con nuevas etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="51f41-231">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="51f41-232">Asegúrese de que está usando la versión más reciente del shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="51f41-232">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="51f41-233">Para obtener instrucciones, vea [preparar el shell de administración de SharePoint Online antes de reetiquetar grupos de Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="51f41-233">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="51f41-234">Con una cuenta profesional o educativa que tenga privilegios de administrador global o de administrador de SharePoint en Office 365, conéctese a la consola de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="51f41-234">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="51f41-235">Para saber cómo hacerlo, vea [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="51f41-235">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="51f41-236">Ejecute el siguiente comando para obtener una lista de las etiquetas de confidencialidad y sus GUID.</span><span class="sxs-lookup"><span data-stu-id="51f41-236">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="51f41-237">Anote el GUID de la etiqueta que desea sobrescribir.</span><span class="sxs-lookup"><span data-stu-id="51f41-237">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="51f41-238">Por ejemplo, la etiqueta "general".</span><span class="sxs-lookup"><span data-stu-id="51f41-238">For example, the "General" label.</span></span>

5. <span data-ttu-id="51f41-239">Use el siguiente comando para obtener la lista de grupos que tienen la clasificación "general".</span><span class="sxs-lookup"><span data-stu-id="51f41-239">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="51f41-240">Al ejecutar este comando, se conectará a Exchange Online PowerShell y ejecutará el cmdlet Get-UnifiedGroup.</span><span class="sxs-lookup"><span data-stu-id="51f41-240">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="51f41-241">Para cada grupo, agregue el nuevo GUID de la etiqueta de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="51f41-241">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
