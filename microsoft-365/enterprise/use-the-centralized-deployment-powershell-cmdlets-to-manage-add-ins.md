---
title: Usar los cmdlets de PowerShell de Implementación centralizada para administrar complementos
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: Use los cmdlets de PowerShell de implementación centralizada para ayudarle a implementar y administrar complementos de Office para su organización de Microsoft 365.
ms.openlocfilehash: 7872deedfcfe058f0a4ac63c489bbed139699d18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924677"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a><span data-ttu-id="3bf8c-103">Usar los cmdlets de PowerShell de Implementación centralizada para administrar complementos</span><span class="sxs-lookup"><span data-stu-id="3bf8c-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>

<span data-ttu-id="3bf8c-104">Como administrador global de Microsoft 365, puede implementar complementos de Office para los usuarios a través de la característica Implementación centralizada (vea [Deploy Office Add-ins in the admin center](../admin/manage/manage-deployment-of-add-ins.md)).</span><span class="sxs-lookup"><span data-stu-id="3bf8c-104">As a Microsoft 365 global admin, you can deploy Office add-ins to users via the Centralized Deployment feature (see [Deploy Office Add-ins in the admin center](../admin/manage/manage-deployment-of-add-ins.md)).</span></span> <span data-ttu-id="3bf8c-105">Además de implementar complementos de Office a través del Centro de administración de Microsoft 365, también puede usar Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-105">In addition to deploying Office add-ins via the Microsoft 365 admin center, you can also use Microsoft PowerShell.</span></span> <span data-ttu-id="3bf8c-106">Instale el [módulo de implementación centralizada Add-In O365 para Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span><span class="sxs-lookup"><span data-stu-id="3bf8c-106">Install the [O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span></span> 

<span data-ttu-id="3bf8c-107">Después de descargar el módulo, abra una ventana Windows PowerShell normal y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3bf8c-107">After you download the module, open a regular Windows PowerShell window and run the following cmdlet:</span></span>

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a><span data-ttu-id="3bf8c-108">Conectarse con sus credenciales de administrador</span><span class="sxs-lookup"><span data-stu-id="3bf8c-108">Connect using your admin credentials</span></span>

<span data-ttu-id="3bf8c-109">Para poder usar los cmdlets de implementación centralizada, debe iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-109">Before you can use the Centralized Deployment cmdlets, you need to sign in.</span></span>
  
1. <span data-ttu-id="3bf8c-110">Inicie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-110">Start PowerShell.</span></span>
    
2. <span data-ttu-id="3bf8c-111">Conéctese a PowerShell con las credenciales de administrador de la empresa.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-111">Connect to PowerShell by using your company admin credentials.</span></span> <span data-ttu-id="3bf8c-112">Ejecute el siguiente cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-112">Run the following cmdlet.</span></span>
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. <span data-ttu-id="3bf8c-113">En la **página Escribir credenciales,** escriba sus credenciales de administrador global de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-113">In the **Enter Credentials** page, enter your Microsoft 365 global admin credentials.</span></span> <span data-ttu-id="3bf8c-114">Como alternativa, puede escribir sus credenciales directamente en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-114">Alternately, you can enter your credentials directly into the cmdlet.</span></span> 
    
    <span data-ttu-id="3bf8c-115">Ejecute el siguiente cmdlet que especifica las credenciales de administrador de la empresa como un objeto PSCredential.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-115">Run the following cmdlet specifying your company admin credentials as a PSCredential object.</span></span>
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> <span data-ttu-id="3bf8c-116">Para obtener más información acerca del uso de PowerShell, vea [Connect to Microsoft 365 with PowerShell](./connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3bf8c-116">For more information about using PowerShell, see [Connect to Microsoft 365 with PowerShell](./connect-to-microsoft-365-powershell.md).</span></span> 
  
## <a name="upload-an-add-in-manifest"></a><span data-ttu-id="3bf8c-117">Cargar un manifiesto de complemento</span><span class="sxs-lookup"><span data-stu-id="3bf8c-117">Upload an add-in manifest</span></span>

<span data-ttu-id="3bf8c-118">Ejecute el cmdlet **New-OrganizationAdd-In** para cargar un manifiesto de complemento desde una ruta de acceso, que puede ser una ubicación de archivo o una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-118">Run the **New-OrganizationAdd-In** cmdlet to upload an add-in manifest from a path, which can be either a file location or URL.</span></span> <span data-ttu-id="3bf8c-119">En el ejemplo siguiente se muestra una ubicación de archivo para el valor del _parámetro ManifestPath._</span><span class="sxs-lookup"><span data-stu-id="3bf8c-119">The following example shows a file location for the value of the  _ManifestPath_ parameter.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

<span data-ttu-id="3bf8c-120">También puede ejecutar el cmdlet **New-OrganizationAdd-In** para cargar un complemento y asignarlo a usuarios o grupos directamente mediante el parámetro  _Members,_ como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-120">You can also run the **New-OrganizationAdd-In** cmdlet to upload an add-in and assign it to users or groups directly by using the  _Members_ parameter, as shown in the following example.</span></span> <span data-ttu-id="3bf8c-121">Separe las direcciones de correo electrónico de los miembros con una coma.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-121">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a><span data-ttu-id="3bf8c-122">Cargar un complemento desde la Tienda Office</span><span class="sxs-lookup"><span data-stu-id="3bf8c-122">Upload an add-in from the Office Store</span></span>

<span data-ttu-id="3bf8c-123">Ejecute el cmdlet **New-OrganizationAddIn** para cargar un manifiesto desde la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-123">Run the **New-OrganizationAddIn** cmdlet to upload a manifest from the Office Store.</span></span>
  
<span data-ttu-id="3bf8c-124">En el ejemplo siguiente, el cmdlet **New-OrganizationAddIn** especifica el AssetId de un complemento para un mercado de contenido y ubicación de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-124">In the following example, the **New-OrganizationAddIn** cmdlet specifies the AssetId for an add-in for a United States location and content market.</span></span>
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

<span data-ttu-id="3bf8c-125">Para determinar el valor del parámetro  _AssetId,_ puede copiarlo desde la dirección URL de la página web de la Tienda Office para el complemento.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-125">To determine the value for the  _AssetId_ parameter, you can copy it from the URL of the Office Store webpage for the add-in.</span></span> <span data-ttu-id="3bf8c-126">AssetIds siempre comienza con "WA" seguido de un número.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-126">AssetIds always begin with "WA" followed by a number.</span></span> <span data-ttu-id="3bf8c-127">Por ejemplo, en el ejemplo anterior, el origen del valor AssetId de WA104099688 es la dirección URL de la página web de la Tienda Office para el complemento: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .</span><span class="sxs-lookup"><span data-stu-id="3bf8c-127">For example, in the previous example, the source for the AssetId value of WA104099688 is the Office Store webpage URL for the add-in: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span></span>
  
<span data-ttu-id="3bf8c-128">Los valores del  _parámetro Locale_ y el parámetro  _ContentMarket_ son idénticos e indican el país o región desde el que está intentando instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-128">The values for the  _Locale_ parameter and the  _ContentMarket_ parameter are identical and indicate the country/region you're trying to install the add-in from.</span></span> <span data-ttu-id="3bf8c-129">El formato es en-US, fr-FR.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-129">The format is en-US, fr-FR.</span></span> <span data-ttu-id="3bf8c-130">y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-130">and so forth.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3bf8c-131">Los complementos cargados desde la Tienda Office se actualizarán automáticamente unos días después de que la última actualización esté disponible en la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-131">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="get-details-of-an-add-in"></a><span data-ttu-id="3bf8c-132">Obtener detalles de un complemento</span><span class="sxs-lookup"><span data-stu-id="3bf8c-132">Get details of an add-in</span></span>

<span data-ttu-id="3bf8c-133">Ejecute el cmdlet **Get-OrganizationAddIn** como se muestra a continuación para obtener detalles de todos los complementos cargados en el inquilino, incluido el id. de producto de un complemento.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-133">Run the **Get-OrganizationAddIn** cmdlet as shown below to get details of all add-ins uploaded to the tenant, included an add-in's product ID.</span></span>
  
```powershell
Get-OrganizationAddIn
```

<span data-ttu-id="3bf8c-134">Ejecute el cmdlet **Get-OrganizationAddIn** con un valor para el parámetro  _ProductId_ para especificar para qué complemento desea recuperar los detalles.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-134">Run the **Get-OrganizationAddIn** cmdlet with a value for the  _ProductId_ parameter to specify which add-in you want to retrieve details for.</span></span> 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<span data-ttu-id="3bf8c-135">Para obtener todos los detalles de todos los complementos más los usuarios y grupos asignados, canalizar el resultado del cmdlet **Get-OrganizationAddIn** al cmdlet Format-List, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-135">To get full details of all the add-ins plus the assigned users and groups, pipe the output of the **Get-OrganizationAddIn** cmdlet to the Format-List cmdlet, as shown in the following example.</span></span>
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a><span data-ttu-id="3bf8c-136">Activar o desactivar un complemento</span><span class="sxs-lookup"><span data-stu-id="3bf8c-136">Turn on or turn off an add-in</span></span>

<span data-ttu-id="3bf8c-137">Para desactivar un complemento para que los usuarios y grupos que están asignados a él ya no tengan acceso, ejecute el cmdlet **Set-OrganizationAddIn** con el parámetro  _ProductId_ y el parámetro  _Enabled_ establecido en , como se muestra en el ejemplo  `$false` siguiente.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-137">To turn off an add-in so users and groups that are assigned to it will no longer have access, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_ parameter and the  _Enabled_ parameter set to  `$false`, as shown in the following example.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

<span data-ttu-id="3bf8c-138">Para volver a activar un complemento, ejecute el mismo cmdlet con el  _parámetro Enabled_ establecido en  `$true` .</span><span class="sxs-lookup"><span data-stu-id="3bf8c-138">To turn an add-in back on, run the same cmdlet with the  _Enabled_ parameter set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a><span data-ttu-id="3bf8c-139">Agregar o quitar usuarios de un complemento</span><span class="sxs-lookup"><span data-stu-id="3bf8c-139">Add or remove users from an add-in</span></span>

<span data-ttu-id="3bf8c-140">Para agregar usuarios y grupos a un complemento específico, ejecute el cmdlet **Set-OrganizationAddInAssignments** con los parámetros _ProductId,_ _Add_ y _Members._</span><span class="sxs-lookup"><span data-stu-id="3bf8c-140">To add users and groups to a specific add-in, run the **Set-OrganizationAddInAssignments** cmdlet with the  _ProductId_,  _Add_, and  _Members_ parameters.</span></span> <span data-ttu-id="3bf8c-141">Separe las direcciones de correo electrónico de los miembros con una coma.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-141">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="3bf8c-142">Para quitar usuarios y grupos, ejecute el mismo cmdlet con el _parámetro Remove._</span><span class="sxs-lookup"><span data-stu-id="3bf8c-142">To remove users and groups, run the same cmdlet using the  _Remove_ parameter.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="3bf8c-143">Para asignar un complemento a todos los usuarios del inquilino, ejecute el mismo cmdlet con el parámetro  _AssignToEveryone_ con el valor establecido en  `$true` .</span><span class="sxs-lookup"><span data-stu-id="3bf8c-143">To assign an add-in to all users on the tenant, run the same cmdlet using the  _AssignToEveryone_ parameter with the value set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

<span data-ttu-id="3bf8c-144">Para no asignar un complemento a todos los usuarios y volver a los usuarios y grupos asignados anteriormente, puede ejecutar el mismo cmdlet y desactivar el parámetro  _AssignToEveryone_ estableciendo su valor en  `$false` .</span><span class="sxs-lookup"><span data-stu-id="3bf8c-144">To not assign an add-in to everyone and revert to the previously assigned users and groups, you can run the same cmdlet and turn off the  _AssignToEveryone_ parameter by setting its value to  `$false`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a><span data-ttu-id="3bf8c-145">Actualizar un complemento</span><span class="sxs-lookup"><span data-stu-id="3bf8c-145">Update an add-in</span></span>

<span data-ttu-id="3bf8c-146">Para actualizar un complemento desde un manifiesto, ejecute el cmdlet **Set-OrganizationAddIn** con los parámetros  _ProductId,_  _ManifestPath_ y  _Locale,_ como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-146">To update an add-in from a manifest, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_,  _ManifestPath_, and  _Locale_ parameters, as shown in the following example.</span></span> 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> <span data-ttu-id="3bf8c-147">Los complementos cargados desde la Tienda Office se actualizarán automáticamente unos días después de que la última actualización esté disponible en la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-147">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="delete-an-add-in"></a><span data-ttu-id="3bf8c-148">Eliminar un complemento</span><span class="sxs-lookup"><span data-stu-id="3bf8c-148">Delete an add-in</span></span>

<span data-ttu-id="3bf8c-149">Para eliminar un complemento, ejecute el cmdlet **Remove-OrganizationAddIn** con el parámetro  _ProductId,_ como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-149">To delete an add-in, run the **Remove-OrganizationAddIn** cmdlet with the  _ProductId_ parameter, as shown in the following example.</span></span> 
  
```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature. 

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters 
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters: 
 
    - \<
    -  \>
    -  ;
    -  =   

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set –OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg" 
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg" 
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in’s icon (in admin center). </br> |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.| 
| \<AppDomains> | A list of domains that the add-in can connect with. | 
| \<SupportURL>| The URL users can use to access help and support. | 
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.| 
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>  
    <bt:Images> 
          <bt:Image id=”img16icon” DefaultValue=”https://site.com/img.jpg” 
    </bt:Images> 
</Resources> 
``` 
In this case, the element id for the image is “img16icon” and the value associated with it is “http:<i></i>//site.<i></i>com/img.jpg.”

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{“ElementID” = “New Value”; “NextElementID” = “Next New Value”} 
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.  

```powershell
Get-OrganizationAddInOverrides 
```
If ProductId is specified, then a list of overrides applied to that add-in is returned. 

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remive an add-in from cache:

1. Navigate to the “Users” folder in C:\ 
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a><span data-ttu-id="3bf8c-150">Obtener ayuda detallada para cada cmdlet</span><span class="sxs-lookup"><span data-stu-id="3bf8c-150">Get detailed help for each cmdlet</span></span>

<span data-ttu-id="3bf8c-151">Puede ver la ayuda detallada para cada cmdlet mediante el cmdlet Get-help.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-151">You can look at detailed help for each cmdlet by using the Get-help cmdlet.</span></span> <span data-ttu-id="3bf8c-152">Por ejemplo, el siguiente cmdlet proporciona información detallada sobre el cmdlet Remove-OrganizationAddIn.</span><span class="sxs-lookup"><span data-stu-id="3bf8c-152">For example, the following cmdlet provides detailed information about the Remove-OrganizationAddIn cmdlet.</span></span>
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```