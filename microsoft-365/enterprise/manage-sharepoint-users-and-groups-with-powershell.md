---
title: Administrar usuarios y grupos de SharePoint Online con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: En este artículo, obtenga información sobre cómo usar PowerShell para Microsoft 365 administrar SharePoint, grupos y sitios en línea.
ms.openlocfilehash: 823c5fdc9af178a2e8ea8f0ca4c63fbfa4673dd8
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289060"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Administrar usuarios y grupos de SharePoint Online con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Si es un administrador de SharePoint Online que trabaja con listas grandes de cuentas de usuario o grupos y quiere una forma más sencilla de administrarlas, puede usar PowerShell para Microsoft 365.

Antes de comenzar, los procedimientos de este tema requieren que se conecte a SharePoint Online. Para obtener instrucciones, [vea Conectar to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="get-a-list-of-sites-groups-and-users"></a>Obtener una lista de sitios, grupos y usuarios

Antes de empezar a administrar usuarios y grupos, hay que conseguir las listas de los sitios, grupos y usuarios. Después puede usar esta información para trabajar con el ejemplo de este artículo.

Obtenga la lista de los sitios de su inquilino con este comando:

```powershell
Get-SPOSite
```

Obtenga la lista de los grupos de su inquilino con este comando:

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

Obtenga la lista de los usuarios de su inquilino con este comando:

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>Agregar un usuario al grupo Administradores de la colección de sitios

Use el cmdlet para agregar un usuario a la lista de administradores de colecciones de `Set-SPOUser` sitios de una colección de sitios.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Para usar estos comandos, reemplace todo dentro de las comillas, incluidos los < y >, por los nombres correctos.

Por ejemplo, este conjunto de comandos agrega Opal Castillo (nombre de usuario opalc) a la lista de administradores de colecciones de sitios de la colección de sitios ContosoTest en el arrendamiento contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

Puede copiar y pegar estos comandos en Bloc de notas, cambiar los valores de variable de $tenant, $site y $user a valores reales del entorno y, a continuación, pegarlo en la ventana del Shell de administración en línea de SharePoint para ejecutarlos.

## <a name="add-a-user-to-other-site-collection-groups"></a>Agregar un usuario a otros grupos de colecciones de sitios

En esta tarea, usaremos el cmdlet para agregar un usuario a un `Add-SPOUser` grupo SharePoint una colección de sitios.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Por ejemplo, vamos a agregar a Glen Rife (nombre de usuario de glenr) al grupo Auditors de la colección de sitios ContosoTest en el arrendamiento de contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Crear un grupo de colecciones de sitios

Use el `New-SPOSiteGroup` cmdlet para crear un nuevo grupo SharePoint y agregarlo a una colección de sitios.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

Las propiedades de grupo, como los niveles de permisos, se pueden actualizar más adelante mediante el `Set-SPOSiteGroup` cmdlet.

Por ejemplo, vamos a agregar el grupo Auditores con permisos de solo vista a la colección de sitios contosotest en el arrendamiento de contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Quitar usuarios de un grupo

A veces, es necesario quitar un usuario de un sitio o incluso de todos los sitios. Tal vez el empleado se mueva de una división a otra o abandone la compañía. Puede hacer esto fácilmente para un empleado en la interfaz de usuario, pero no es tan fácil cuando hay que mover una división completa de un sitio a otro.

Sin embargo, al usar SharePoint Shell de administración en línea y archivos CSV, esto es rápido y fácil. En esta tarea, vamos a usar Windows PowerShell para quitar un usuario de un grupo de seguridad de la colección de sitios. A continuación, puede usar un archivo CSV y quitar muchos usuarios de distintos sitios.

Usaremos el cmdlet "Remove-SPOUser" para quitar un único usuario de Microsoft 365 de un grupo de colecciones de sitios para que podamos ver la sintaxis de comandos. Este es el aspecto de la sintaxis:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Por ejemplo, vamos a quitar a Bobby Overby del grupo auditores de la colección de sitios de la colección de sitios contosotest del arrendamiento contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Supongamos que quisiéramos quitar a Bobby de todos los grupos a los que pertenece. Este es el método que usaríamos para hacerlo:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Este es solo un ejemplo. No debe ejecutar este comando a menos que realmente tenga que quitar un usuario de cada grupo, por ejemplo, si el usuario deja la empresa.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Automatizar la administración de grandes listas de usuarios y grupos

Para agregar un gran número de cuentas a SharePoint sitios y concederles permisos, puede usar el Centro de administración de Microsoft 365, comandos de PowerShell individuales o PowerShell un archivo CSV. De estas opciones, el uso del archivo CSV es la forma más rápida de automatizar esta tarea.

El proceso básico consiste en crear un archivo CSV que tiene encabezados (columnas) que se corresponden con los parámetros que el script de Windows PowerShell necesita. Puede crear fácilmente dicha lista en Excel luego exportarla como un archivo CSV. A continuación, puede usar un script de Windows PowerShell para iterar a través de registros (filas) en el archivo CSV, agregar los usuarios a los grupos y los grupos a los sitios.

Por ejemplo, vamos a crear un archivo CSV para definir un grupo de colecciones de sitios, grupos y permisos. A continuación, vamos a crear un archivo CSV para rellenar los grupos con usuarios. Por último, vamos a crear y ejecutar un script de Windows PowerShell que cree y rellene los grupos.

El primer archivo CSV agregará uno o más grupos a una o más colecciones de sitios y tendrá esta estructura:

Encabezado:

```powershell
Site,Group,PermissionLevels
```

Elemento:

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

Este es un archivo de ejemplo:

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

El segundo archivo CSV agregará uno o varios usuarios a uno o varios grupos y tendrá esta estructura:

Encabezado:

```powershell
Group,LoginName,Site
```

Elemento:

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

Este es un archivo de ejemplo:

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

En el paso siguiente, debe tener los dos archivos CSV guardados en la unidad. Estos son comandos de ejemplo que usan archivos CSV y para agregar permisos y pertenencia a grupos:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

El script importa el contenido del archivo CSV y usa los valores de las columnas para rellenar los parámetros de los comandos **New-SPOSiteGroup** y **Add-SPOUser.** En nuestro ejemplo, lo guardamos en la carpetaO365Admin de la unidad C, pero puede guardarlo donde quiera.

Ahora, vamos a quitar un grupo de personas para varios grupos en diferentes sitios con el mismo archivo CSV. A continuación se muestra un ejemplo:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Generar informes de usuario

Tal vez desee obtener un informe sencillo para unos cuantos sitios y mostrar los usuarios de dichos sitios, su nivel de permisos y otras propiedades. Este es el aspecto de la sintaxis:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

Esto tomará los datos de estos tres sitios y los escribirá en un archivo de texto de la unidad local. Tenga en cuenta que el parámetro –Append agregará nuevo contenido a un archivo existente.

Por ejemplo, vamos a ejecutar un informe en los sitios ContosoTest, TeamSite01 y Project01 para el inquilino Contoso1:

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Tenga en cuenta que solo tuvimos que cambiar la **$site** variable. La **variable $tenant** mantiene su valor a través de las tres ejecuciones del comando.

Sin embargo, ¿qué pasa si quisiera hacer esto para cada sitio? Puede hacerlo sin tener que escribir todos los sitios web con este comando:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Este informe es bastante sencillo y podemos agregar más código para crear informes más específicos o que incluyan información más detallada. Pero esto debería darle una idea de cómo usar el Shell de administración en línea de SharePoint para administrar usuarios en el entorno SharePoint Online.

## <a name="see-also"></a>Vea también

[Conectarse a SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[Administrar SharePoint Online con PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
