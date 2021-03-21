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
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Usar los cmdlets de PowerShell de Implementación centralizada para administrar complementos

Como administrador global de Microsoft 365, puede implementar complementos de Office para los usuarios a través de la característica Implementación centralizada (vea [Deploy Office Add-ins in the admin center](../admin/manage/manage-deployment-of-add-ins.md)). Además de implementar complementos de Office a través del Centro de administración de Microsoft 365, también puede usar Microsoft PowerShell. Instale el [módulo de implementación centralizada Add-In O365 para Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment). 

Después de descargar el módulo, abra una ventana Windows PowerShell normal y ejecute el siguiente cmdlet:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Conectarse con sus credenciales de administrador

Para poder usar los cmdlets de implementación centralizada, debe iniciar sesión.
  
1. Inicie PowerShell.
    
2. Conéctese a PowerShell con las credenciales de administrador de la empresa. Ejecute el siguiente cmdlet.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. En la **página Escribir credenciales,** escriba sus credenciales de administrador global de Microsoft 365. Como alternativa, puede escribir sus credenciales directamente en el cmdlet. 
    
    Ejecute el siguiente cmdlet que especifica las credenciales de administrador de la empresa como un objeto PSCredential.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Para obtener más información acerca del uso de PowerShell, vea [Connect to Microsoft 365 with PowerShell](./connect-to-microsoft-365-powershell.md). 
  
## <a name="upload-an-add-in-manifest"></a>Cargar un manifiesto de complemento

Ejecute el cmdlet **New-OrganizationAdd-In** para cargar un manifiesto de complemento desde una ruta de acceso, que puede ser una ubicación de archivo o una dirección URL. En el ejemplo siguiente se muestra una ubicación de archivo para el valor del _parámetro ManifestPath._ 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

También puede ejecutar el cmdlet **New-OrganizationAdd-In** para cargar un complemento y asignarlo a usuarios o grupos directamente mediante el parámetro  _Members,_ como se muestra en el ejemplo siguiente. Separe las direcciones de correo electrónico de los miembros con una coma. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Cargar un complemento desde la Tienda Office

Ejecute el cmdlet **New-OrganizationAddIn** para cargar un manifiesto desde la Tienda Office.
  
En el ejemplo siguiente, el cmdlet **New-OrganizationAddIn** especifica el AssetId de un complemento para un mercado de contenido y ubicación de Estados Unidos.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Para determinar el valor del parámetro  _AssetId,_ puede copiarlo desde la dirección URL de la página web de la Tienda Office para el complemento. AssetIds siempre comienza con "WA" seguido de un número. Por ejemplo, en el ejemplo anterior, el origen del valor AssetId de WA104099688 es la dirección URL de la página web de la Tienda Office para el complemento: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
Los valores del  _parámetro Locale_ y el parámetro  _ContentMarket_ son idénticos e indican el país o región desde el que está intentando instalar el complemento. El formato es en-US, fr-FR. y así sucesivamente. 
  
> [!NOTE]
> Los complementos cargados desde la Tienda Office se actualizarán automáticamente unos días después de que la última actualización esté disponible en la Tienda Office. 
  
## <a name="get-details-of-an-add-in"></a>Obtener detalles de un complemento

Ejecute el cmdlet **Get-OrganizationAddIn** como se muestra a continuación para obtener detalles de todos los complementos cargados en el inquilino, incluido el id. de producto de un complemento.
  
```powershell
Get-OrganizationAddIn
```

Ejecute el cmdlet **Get-OrganizationAddIn** con un valor para el parámetro  _ProductId_ para especificar para qué complemento desea recuperar los detalles. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

Para obtener todos los detalles de todos los complementos más los usuarios y grupos asignados, canalizar el resultado del cmdlet **Get-OrganizationAddIn** al cmdlet Format-List, como se muestra en el ejemplo siguiente.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Activar o desactivar un complemento

Para desactivar un complemento para que los usuarios y grupos que están asignados a él ya no tengan acceso, ejecute el cmdlet **Set-OrganizationAddIn** con el parámetro  _ProductId_ y el parámetro  _Enabled_ establecido en , como se muestra en el ejemplo  `$false` siguiente.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Para volver a activar un complemento, ejecute el mismo cmdlet con el  _parámetro Enabled_ establecido en  `$true` .
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Agregar o quitar usuarios de un complemento

Para agregar usuarios y grupos a un complemento específico, ejecute el cmdlet **Set-OrganizationAddInAssignments** con los parámetros _ProductId,_ _Add_ y _Members._ Separe las direcciones de correo electrónico de los miembros con una coma. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Para quitar usuarios y grupos, ejecute el mismo cmdlet con el _parámetro Remove._ 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Para asignar un complemento a todos los usuarios del inquilino, ejecute el mismo cmdlet con el parámetro  _AssignToEveryone_ con el valor establecido en  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Para no asignar un complemento a todos los usuarios y volver a los usuarios y grupos asignados anteriormente, puede ejecutar el mismo cmdlet y desactivar el parámetro  _AssignToEveryone_ estableciendo su valor en  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Actualizar un complemento

Para actualizar un complemento desde un manifiesto, ejecute el cmdlet **Set-OrganizationAddIn** con los parámetros  _ProductId,_  _ManifestPath_ y  _Locale,_ como se muestra en el ejemplo siguiente. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Los complementos cargados desde la Tienda Office se actualizarán automáticamente unos días después de que la última actualización esté disponible en la Tienda Office. 
  
## <a name="delete-an-add-in"></a>Eliminar un complemento

Para eliminar un complemento, ejecute el cmdlet **Remove-OrganizationAddIn** con el parámetro  _ProductId,_ como se muestra en el ejemplo siguiente. 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a>Obtener ayuda detallada para cada cmdlet

Puede ver la ayuda detallada para cada cmdlet mediante el cmdlet Get-help. Por ejemplo, el siguiente cmdlet proporciona información detallada sobre el cmdlet Remove-OrganizationAddIn.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```