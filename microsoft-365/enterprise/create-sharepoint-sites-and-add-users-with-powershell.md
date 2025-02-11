---
title: Crear sitios de SharePoint Online y agregar usuarios con PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: landing-page
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: 'Resumen: use PowerShell para crear nuevos sitios de SharePoint Online y, a continuación, agregar usuarios y grupos a esos sitios.'
ms.openlocfilehash: f640b7abcba9f05460e77fb11b8578c15b0a76fc
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68167547"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Crear sitios de SharePoint Online y agregar usuarios con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Cuando se usa PowerShell para Microsoft 365 para crear sitios de SharePoint Online y agregar usuarios, puede realizar tareas de forma rápida y repetida mucho más rápido de lo que puede en el Centro de administración de Microsoft 365. También puede realizar tareas que no son posibles realizar en el Centro de administración de Microsoft 365.

## <a name="connect-to-sharepoint-online"></a>Conexión a SharePoint Online

Los procedimientos de este tema requieren que se conecte a SharePoint Online. Para obtener instrucciones, consulte [Conexión a PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

## <a name="step-1-create-new-site-collections-using-powershell"></a>Paso 1: Creación de nuevas colecciones de sitios mediante PowerShell

Cree varios sitios mediante PowerShell y un archivo .csv que cree con el código de ejemplo proporcionado y el Bloc de notas. Para este procedimiento, reemplazará la información de marcador de posición que se muestra entre corchetes por su propia información específica del sitio y del inquilino. Este proceso le permite crear un único archivo y ejecutar un único comando de PowerShell que use ese archivo. Esto hace que las acciones realizadas sean repetibles y portátiles y elimina muchos errores, si no todos, que pueden provenir de escribir comandos largos en el Shell de administración de SharePoint Online. Hay dos partes de este procedimiento. En primer lugar, creará un archivo .csv y, a continuación, hará referencia a ese archivo .csv mediante PowerShell, que usará su contenido para crear los sitios.

El cmdlet de PowerShell importa el archivo .csv y lo canaliza a un bucle dentro de los corchetes que lee la primera línea del archivo como encabezados de columna. A continuación, el cmdlet de PowerShell recorre en iteración los registros restantes, crea una nueva colección de sitios para cada registro y asigna propiedades de la colección de sitios según los encabezados de columna.

### <a name="create-a-csv-file"></a>Crear un archivo .csv

> [!NOTE]
> El parámetro de cuota de recursos solo funciona en sitios clásicos. Si usa este parámetro en un sitio moderno, puede recibir un mensaje de advertencia que indica que está en desuso.

1. Abra el Bloc de notas y pegue el siguiente bloque de texto:

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   Donde *inquilino* es el nombre del inquilino y *propietario* es el nombre de usuario del usuario del inquilino al que desea conceder el rol de administrador de la colección de sitios principal.

   (Puede presionar Ctrl+H cuando use el Bloc de notas para reemplazar de forma masiva más rápido).

2. Guarde el archivo en el escritorio como **SiteCollections.csv**.

> [!TIP]
> Antes de usar este o cualquier otro archivo de script .csv o Windows PowerShell, se recomienda asegurarse de que no haya caracteres extraños o no imprimibles. Abra el archivo en Word y, en la cinta de opciones, haga clic en el icono de párrafo para mostrar los caracteres no imprimibles. No debe haber ningún carácter extraño o no imprimible. Por ejemplo, no debe haber ninguna marca de párrafo después del último carácter al final del archivo.

### <a name="run-the-windows-powershell-command"></a>Ejecutar el comando de Windows PowerShell

1. En el símbolo del sistema Windows PowerShell, escriba o copie y pegue el siguiente comando y presione Entrar:

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   Donde *MyAlias* es igual al alias de usuario.

2. Espere a que el símbolo del sistema de Windows PowerShell aparezca de nuevo. Esto puede tardar un par de minutos.

3. En el símbolo del sistema de Windows PowerShell, escriba o copie y pegue el siguiente cmdlet y presione ENTRAR:

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. Observe que las nuevas colecciones de sitios figuran en la lista. Con nuestro archivo CSV de ejemplo, verá las siguientes colecciones de sitios: **TeamSite01**, **Blog01**, **Project01** y **Community01**.

Eso es todo. Ha creado varias colecciones de sitios mediante el archivo .csv que creó y un único comando Windows PowerShell. Ya está listo para crear y asignar usuarios a estos sitios.

## <a name="step-2-add-users-and-groups"></a>Paso 2: agregar usuarios y grupos

Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.

Los procedimientos siguientes siguen usando los sitios de ejemplo TeamSite01, Blog01, Project01 y Community01.

### <a name="create-csv-and-ps1-files"></a>Crear los archivos .csv y .ps1

1. Abra el Bloc de notas y pegue el siguiente bloque de texto:

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

   Donde *el inquilino* es igual al nombre del inquilino.

2. Guarde el archivo en el escritorio como **GroupsAndPermissions.csv**.

3. Abra otra instancia del Bloc de notas y pegue el siguiente bloque de texto:

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

   Donde *el inquilino* es igual al nombre del inquilino y el *nombre de usuario* es igual al nombre de usuario de un usuario existente.

4. Guarde el archivo en el escritorio como **Users.csv**.

5. Abra otra instancia del Bloc de notas y pegue el siguiente bloque de texto:

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   Donde MyAlias es igual al nombre de usuario del usuario que ha iniciado sesión actualmente.

6. Guarde el archivo en el escritorio como **UsersAndGroups.ps1**. Este es un script de Windows PowerShell sencillo.

Ya puede ejecutar el script UsersAndGroup.ps1 para agregar usuarios y grupos a varias colecciones de sitios.

### <a name="run-usersandgroupsps1-script"></a>Ejecutar el script UsersAndGroups.ps1

1. Vuelva al Shell de administración de SharePoint Online.

2. En el símbolo del sistema de Windows PowerShell, escriba o copie y pegue la siguiente línea y presione ENTRAR:

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. En el símbolo del sistema de confirmación, presione **Y**.

4. En el símbolo del sistema de Windows PowerShell, escriba o copie y pegue lo siguiente y presione ENTRAR:

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   Donde *MyAlias* es igual a su nombre de usuario.

5. Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.

## <a name="see-also"></a>Vea también

[Conectarse a SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[Administrar grupos de sitio de SharePoint Online con PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
