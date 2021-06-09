---
title: Crear sitios de SharePoint Online y agregar usuarios con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: 'Summary: Use PowerShell to create new SharePoint Online sites and then add users and groups to those sites.'
ms.openlocfilehash: eb6c2817c8760ca222da8a7c2b14cbfcda4eb4b8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907623"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Crear sitios de SharePoint Online y agregar usuarios con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Cuando usa PowerShell para Microsoft 365 para crear sitios de SharePoint Online y agregar usuarios, puede realizar tareas de forma rápida y repetida mucho más rápido de lo que puede en el Centro de administración de Microsoft 365. También puede realizar tareas que no son posibles realizar en el centro Microsoft 365 administración. 

## <a name="connect-to-sharepoint-online"></a>Conexión a SharePoint Online

Los procedimientos de este tema requieren que se conecte a SharePoint Online. Para obtener instrucciones, [vea Conectar to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="step-1-create-new-site-collections-using-powershell"></a>Paso 1: Crear nuevas colecciones de sitios con PowerShell

Cree varios sitios con PowerShell y un archivo .csv que cree con el código de ejemplo proporcionado y Bloc de notas. Para este procedimiento, reemplazará la información de marcador de posición que se muestra entre corchetes por su propia información específica del sitio y del espacio empresarial. Este proceso le permite crear un solo archivo y ejecutar un único comando de PowerShell que usa ese archivo. Esto hace que las acciones realizadas se puedan repetir y portátiles y elimina muchos errores, si no todos, que pueden venir de escribir comandos largos en el Shell de administración en línea de SharePoint. Este procedimiento tiene dos partes. Primero creará un archivo .csv y, a continuación, hará referencia a ese archivo .csv mediante PowerShell, que usará su contenido para crear los sitios.

El cmdlet de PowerShell importa el archivo .csv y lo canaliza a un bucle dentro de los corchetes que lee la primera línea del archivo como encabezados de columna. A continuación, el cmdlet de PowerShell recorre en iteración los registros restantes, crea una nueva colección de sitios para cada registro y asigna propiedades de la colección de sitios según los encabezados de columna.

### <a name="create-a-csv-file"></a>Crear un archivo .csv

> [!NOTE]
> El parámetro de cuota de recursos solo funciona en sitios clásicos. Si usa este parámetro en un sitio moderno, puede recibir un mensaje de advertencia de que ha quedado en desuso. 

1. Abra el Bloc de notas y pegue el siguiente bloque de texto:<br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/>Donde *tenant* es el nombre de su inquilino y *owner* es el nombre de usuario del usuario del inquilino al que desea conceder el rol de administrador de la colección de sitios principal.<br/>(Puede presionar Ctrl+H cuando use Bloc de notas reemplazar masivamente más rápido).<br/>

2. Guarde el archivo en el escritorio como **SiteCollections.csv**.<br/>

> [!TIP]
> Antes de usar este o cualquier otro archivo de script .csv o Windows PowerShell, es una buena práctica asegurarse de que no hay caracteres extraneosos o no imprimibles. Abra el archivo en Word y, en la cinta de opciones, haga clic en el icono de párrafo para mostrar los caracteres no imprimibles. No debe haber ningún carácter extraño o no imprimible. Por ejemplo, no debe haber ninguna marca de párrafo después del último carácter al final del archivo.

### <a name="run-the-windows-powershell-command"></a>Ejecutar el comando de Windows PowerShell

1. En el Windows PowerShell, escriba o copie y pegue el siguiente comando y presione ENTRAR:<br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/>Donde *MyAlias* es igual al alias de usuario.<br/>

2. Espere a que el símbolo del sistema de Windows PowerShell aparezca de nuevo. Esto puede tardar un par de minutos.<br/>

3. En el símbolo del sistema de Windows PowerShell, escriba o copie y pegue el siguiente cmdlet y presione ENTRAR:<br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. Observe que las nuevas colecciones de sitios figuran en la lista. Con nuestro archivo CSV de ejemplo, vería las siguientes colecciones de sitios: **TeamSite01**, **Blog01**, **Project01** y **Community01**

Eso es todo. Ha creado varias colecciones de sitios mediante el archivo .csv que creó y un único Windows PowerShell sitio. Ya está listo para crear y asignar usuarios a estos sitios.

## <a name="step-2-add-users-and-groups"></a>Paso 2: agregar usuarios y grupos

Ahora vamos a crear usuarios y a agregarlos a un grupo de colecciones de sitios. Luego, usaremos un archivo .csv para cargar los nuevos usuarios y grupos de forma masiva.

Los siguientes procedimientos siguen usando los sitios de ejemplo TeamSite01, Blog01, Project01 y Community01.

### <a name="create-csv-and-ps1-files"></a>Crear los archivos .csv y .ps1

1. Abra el Bloc de notas y pegue el siguiente bloque de texto:<br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/>Donde *tenant* es igual al nombre del inquilino.<br/>

2. Guarde el archivo en el escritorio como **GroupsAndPermissions.csv**.<br/>

3. Abra otra instancia del Bloc de notas y pegue el siguiente bloque de texto:<br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/>Donde *tenant* es igual al nombre del inquilino y *username* es igual al nombre de usuario de un usuario existente.<br/>

4. Guarde el archivo en el escritorio como **Users.csv**.<br/>

5. Abra otra instancia del Bloc de notas y pegue el siguiente bloque de texto:<br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/>Donde MyAlias es igual al nombre de usuario del usuario que ha iniciado sesión actualmente.<br/>

6. Guarde el archivo en el escritorio como **UsersAndGroups.ps1**. Este es un script de Windows PowerShell sencillo.

Ya puede ejecutar el script UsersAndGroup.ps1 para agregar usuarios y grupos a varias colecciones de sitios.

### <a name="run-usersandgroupsps1-script"></a>Ejecutar el script UsersAndGroups.ps1

1. Vuelva al Shell de administración de SharePoint Online.<br/>
2. En el símbolo del sistema de Windows PowerShell, escriba o copie y pegue la siguiente línea y presione ENTRAR:<br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. En el símbolo del sistema de confirmación, presione **Y**.<br/>

4. En el símbolo del sistema de Windows PowerShell, escriba o copie y pegue lo siguiente y presione ENTRAR:<br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/>Donde *MyAlias* es igual al nombre de usuario.<br/>

5. Antes de continuar, espere a que el símbolo del sistema vuelva. Primero verá que los grupos aparecen según se han creado y, luego, verá la lista de grupos repetida a medida que se vayan agregando usuarios.

## <a name="see-also"></a>Consulte también

[Conectarse a SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Administrar grupos de sitio de SharePoint Online con PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)