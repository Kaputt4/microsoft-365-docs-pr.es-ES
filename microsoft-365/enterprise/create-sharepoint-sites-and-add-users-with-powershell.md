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
description: 'Resumen: use PowerShell para crear nuevos sitios de SharePoint Online y, a continuación, agregar usuarios y grupos a esos sitios.'
ms.openlocfilehash: 28a51cc39fe838f6c7f9c50e9d750d28e5d830c4
ms.sourcegitcommit: 24ccb910ffac4d065c512a57c5decd9dd19ef4c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594923"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="84be3-103">Crear sitios de SharePoint Online y agregar usuarios con PowerShell</span><span class="sxs-lookup"><span data-stu-id="84be3-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="84be3-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="84be3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="84be3-105">Al usar PowerShell para Microsoft 365 para crear sitios de SharePoint Online y agregar usuarios, puede realizar tareas de forma rápida y repetida mucho más rápido que en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="84be3-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="84be3-106">También puede realizar tareas que no son posibles realizar en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="84be3-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="84be3-107">Conexión a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="84be3-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="84be3-108">Los procedimientos de este tema requieren que se conecte a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="84be3-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="84be3-109">Para obtener instrucciones, vea [Conectarse a SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="84be3-109">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="84be3-110">Paso 1: Crear nuevas colecciones de sitios con PowerShell</span><span class="sxs-lookup"><span data-stu-id="84be3-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="84be3-111">Cree varios sitios con PowerShell y un archivo .csv que cree con el código de ejemplo proporcionado y el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="84be3-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="84be3-112">Para este procedimiento, reemplazará la información de marcador de posición que se muestra entre corchetes por su propia información específica del sitio y del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="84be3-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="84be3-113">Este proceso le permite crear un único archivo y ejecutar un único comando de PowerShell que usa ese archivo.</span><span class="sxs-lookup"><span data-stu-id="84be3-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="84be3-114">Esto hace que las acciones realizadas se puedan repetir y portátiles y elimina muchos errores, si no todos, que pueden ser resultado de escribir comandos largos en el Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="84be3-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="84be3-115">Este procedimiento tiene dos partes.</span><span class="sxs-lookup"><span data-stu-id="84be3-115">There are two parts to this procedure.</span></span> <span data-ttu-id="84be3-116">Primero creará un archivo .csv y, a continuación, hará referencia a ese archivo .csv con PowerShell, que usará su contenido para crear los sitios.</span><span class="sxs-lookup"><span data-stu-id="84be3-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="84be3-117">El cmdlet de PowerShell importa el archivo .csv y lo canaliza a un bucle entre corchetes que lee la primera línea del archivo como encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="84be3-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="84be3-118">A continuación, el cmdlet de PowerShell recorre en iteración los registros restantes, crea una nueva colección de sitios para cada registro y asigna propiedades de la colección de sitios según los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="84be3-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="84be3-119">Crear un archivo .csv</span><span class="sxs-lookup"><span data-stu-id="84be3-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="84be3-120">El parámetro de cuota de recursos solo funciona en sitios clásicos.</span><span class="sxs-lookup"><span data-stu-id="84be3-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="84be3-121">Si usa este parámetro en un sitio moderno, es posible que reciba un mensaje de advertencia de que está en desuso.</span><span class="sxs-lookup"><span data-stu-id="84be3-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span> 

1. <span data-ttu-id="84be3-122">Abra el Bloc de notas y pegue el siguiente bloque de texto:</span><span class="sxs-lookup"><span data-stu-id="84be3-122">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="84be3-123">Donde *el inquilino* es el  nombre de su inquilino y el propietario es el nombre de usuario del usuario del inquilino al que desea conceder el rol de administrador de la colección de sitios principal.</span><span class="sxs-lookup"><span data-stu-id="84be3-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="84be3-124">(Puede presionar Ctrl + H cuando use el Bloc de notas para reemplazar en masa más rápido).</span><span class="sxs-lookup"><span data-stu-id="84be3-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="84be3-125">Guarde el archivo en el escritorio como **SiteCollections.csv**.</span><span class="sxs-lookup"><span data-stu-id="84be3-125">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="84be3-126">Antes de usar este o cualquier otro archivo de script .csv o Windows PowerShell, es una buena práctica asegurarse de que no haya caracteres extraneosos o no imprimibles.</span><span class="sxs-lookup"><span data-stu-id="84be3-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="84be3-127">Abra el archivo en Word y, en la cinta de opciones, haga clic en el icono de párrafo para mostrar los caracteres no imprimibles.</span><span class="sxs-lookup"><span data-stu-id="84be3-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="84be3-128">No debe haber ningún carácter extraño o no imprimible.</span><span class="sxs-lookup"><span data-stu-id="84be3-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="84be3-129">Por ejemplo, no debe haber ninguna marca de párrafo después del último carácter al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="84be3-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="84be3-130">Ejecutar el comando de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="84be3-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="84be3-131">En el Windows PowerShell, escriba o copie y pegue el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="84be3-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="84be3-132">Donde *MyAlias es* igual a su alias de usuario.</span><span class="sxs-lookup"><span data-stu-id="84be3-132">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="84be3-p107">Espere a que el símbolo del sistema de Windows PowerShell aparezca de nuevo. Esto puede tardar un par de minutos.</span><span class="sxs-lookup"><span data-stu-id="84be3-p107">Wait for the Windows PowerShell prompt to reappear. It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="84be3-135">En el símbolo del sistema de Windows PowerShell, escriba o copie y pegue el siguiente cmdlet y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="84be3-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="84be3-136">Observe que las nuevas colecciones de sitios figuran en la lista.</span><span class="sxs-lookup"><span data-stu-id="84be3-136">Note the new site collections in the list.</span></span> <span data-ttu-id="84be3-137">Con nuestro archivo CSV de ejemplo, verá las siguientes colecciones de sitios: **TeamSite01**, **Blog01**, **Project01** y **Community01**</span><span class="sxs-lookup"><span data-stu-id="84be3-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="84be3-138">Eso es todo.</span><span class="sxs-lookup"><span data-stu-id="84be3-138">That’s it.</span></span> <span data-ttu-id="84be3-139">Ha creado varias colecciones de sitios con el archivo .csv que creó y un único comando Windows PowerShell sitio.</span><span class="sxs-lookup"><span data-stu-id="84be3-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="84be3-140">Ya está listo para crear y asignar usuarios a estos sitios.</span><span class="sxs-lookup"><span data-stu-id="84be3-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="84be3-141">Paso 2: agregar usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="84be3-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="84be3-p110">Ahora vamos a crear usuarios y a agregarlos a un grupo de colecciones de sitios. Luego, usaremos un archivo .csv para cargar los nuevos usuarios y grupos de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="84be3-p110">Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="84be3-144">Los siguientes procedimientos siguen usando los sitios de ejemplo TeamSite01, Blog01, Project01 y Community01.</span><span class="sxs-lookup"><span data-stu-id="84be3-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="84be3-145">Crear los archivos .csv y .ps1</span><span class="sxs-lookup"><span data-stu-id="84be3-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="84be3-146">Abra el Bloc de notas y pegue el siguiente bloque de texto:</span><span class="sxs-lookup"><span data-stu-id="84be3-146">Open Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="84be3-147">Donde *el inquilino* es igual a su nombre de inquilino.</span><span class="sxs-lookup"><span data-stu-id="84be3-147">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="84be3-148">Guarde el archivo en el escritorio como **GroupsAndPermissions.csv**.</span><span class="sxs-lookup"><span data-stu-id="84be3-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="84be3-149">Abra otra instancia del Bloc de notas y pegue el siguiente bloque de texto:</span><span class="sxs-lookup"><span data-stu-id="84be3-149">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="84be3-150">Donde *el inquilino* es igual a su nombre de inquilino y *el* nombre de usuario es igual al nombre de usuario de un usuario existente.</span><span class="sxs-lookup"><span data-stu-id="84be3-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="84be3-151">Guarde el archivo en el escritorio como **Users.csv**.</span><span class="sxs-lookup"><span data-stu-id="84be3-151">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="84be3-152">Abra otra instancia del Bloc de notas y pegue el siguiente bloque de texto:</span><span class="sxs-lookup"><span data-stu-id="84be3-152">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="84be3-153">Donde MyAlias es igual al nombre de usuario del usuario que ha iniciado sesión actualmente.</span><span class="sxs-lookup"><span data-stu-id="84be3-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="84be3-154">Guarde el archivo en el escritorio como **UsersAndGroups.ps1**.</span><span class="sxs-lookup"><span data-stu-id="84be3-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="84be3-155">Este es un script de Windows PowerShell sencillo.</span><span class="sxs-lookup"><span data-stu-id="84be3-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="84be3-156">Ya puede ejecutar el script UsersAndGroup.ps1 para agregar usuarios y grupos a varias colecciones de sitios.</span><span class="sxs-lookup"><span data-stu-id="84be3-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="84be3-157">Ejecutar el script UsersAndGroups.ps1</span><span class="sxs-lookup"><span data-stu-id="84be3-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="84be3-158">Vuelva al Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="84be3-158">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="84be3-159">En el símbolo del sistema de Windows PowerShell, escriba o copie y pegue la siguiente línea y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="84be3-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="84be3-160">En el símbolo del sistema de confirmación, presione **Y**.</span><span class="sxs-lookup"><span data-stu-id="84be3-160">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="84be3-161">En el símbolo del sistema de Windows PowerShell, escriba o copie y pegue lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="84be3-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="84be3-162">Donde *MyAlias es* igual a su nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="84be3-162">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="84be3-p112">Antes de continuar, espere a que el símbolo del sistema vuelva. Primero verá que los grupos aparecen según se han creado y, luego, verá la lista de grupos repetida a medida que se vayan agregando usuarios.</span><span class="sxs-lookup"><span data-stu-id="84be3-p112">Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="84be3-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="84be3-166">See also</span></span>

[<span data-ttu-id="84be3-167">Conectarse a SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="84be3-167">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="84be3-168">Administrar grupos de sitio de SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="84be3-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="84be3-169">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="84be3-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="84be3-170">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="84be3-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
