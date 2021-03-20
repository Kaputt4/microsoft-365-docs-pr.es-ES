---
title: Administrar grupos de sitio de SharePoint Online con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
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
description: En este artículo, busque procedimientos para usar PowerShell para Microsoft 365 para administrar grupos de sitios de SharePoint Online.
ms.openlocfilehash: bcc7a00a6114a6fa2ba8aa02520267bd03a0abf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909543"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="e7f52-103">Administrar grupos de sitio de SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7f52-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="e7f52-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e7f52-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e7f52-105">Aunque puede usar el Centro de administración de Microsoft 365, también puede usar PowerShell para Microsoft 365 para administrar los grupos de sitios de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e7f52-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e7f52-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="e7f52-106">Before you begin</span></span>

<span data-ttu-id="e7f52-107">Los procedimientos de este artículo requieren que se conecte a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e7f52-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="e7f52-108">Para obtener instrucciones, consulte [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="e7f52-108">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="e7f52-109">Ver SharePoint Online con PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7f52-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="e7f52-110">El Centro de administración de SharePoint Online tiene algunos métodos fáciles de usar para administrar grupos de sitios.</span><span class="sxs-lookup"><span data-stu-id="e7f52-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="e7f52-111">Por ejemplo, supongamos que desea ver los grupos y los miembros del grupo para el `https://litwareinc.sharepoint.com/sites/finance` sitio.</span><span class="sxs-lookup"><span data-stu-id="e7f52-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="e7f52-112">Esto es lo que tiene que hacer para:</span><span class="sxs-lookup"><span data-stu-id="e7f52-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="e7f52-113">En el Centro de administración de SharePoint, haga clic **en Sitios activos** y, a continuación, haga clic en la dirección URL del sitio.</span><span class="sxs-lookup"><span data-stu-id="e7f52-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="e7f52-114">En la página del  sitio, haga clic en el icono Configuración (ubicado en la esquina superior derecha de la página) y, a continuación, haga clic en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="e7f52-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="e7f52-115">Y, así, repita el proceso con el siguiente sitio que quiera ver.</span><span class="sxs-lookup"><span data-stu-id="e7f52-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="e7f52-116">Para obtener una lista de los grupos con PowerShell para Microsoft 365, puede usar los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="e7f52-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

<span data-ttu-id="e7f52-117">Hay dos formas de ejecutar este conjunto de comandos en el símbolo del sistema del Shell de administración de SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="e7f52-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="e7f52-118">Copie los comandos en el Bloc de notas (u otro editor de texto), modifique el valor de la variable **$siteURL,** seleccione los comandos y, a continuación, péguelos en el símbolo del sistema del Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e7f52-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="e7f52-119">Cuando lo haga, PowerShell se detendrá en un **>>** mensaje.</span><span class="sxs-lookup"><span data-stu-id="e7f52-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="e7f52-120">Presione Entrar para ejecutar el `foreach` comando.</span><span class="sxs-lookup"><span data-stu-id="e7f52-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="e7f52-121">Copie los comandos en el Bloc de notas (u otro editor de texto), modifique el valor de la variable **$siteURL** y después guarde este archivo de texto con un nombre y la extensión. ps1 en la carpeta adecuada.</span><span class="sxs-lookup"><span data-stu-id="e7f52-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="e7f52-122">A continuación, ejecute el script desde el símbolo del sistema del Shell de administración de SharePoint Online especificando su ruta de acceso y nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="e7f52-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="e7f52-123">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7f52-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="e7f52-124">En ambos casos, el resultado será parecido a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7f52-124">In both cases, you should see something similar to this:</span></span>

![Grupos de sitios de SharePoint Online](../media/SPO-site-groups.png)

<span data-ttu-id="e7f52-126">Estos son todos los grupos que se han creado para el sitio `https://litwareinc.sharepoint.com/sites/finance` y todos los usuarios asignados a esos grupos.</span><span class="sxs-lookup"><span data-stu-id="e7f52-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="e7f52-127">Los nombres de grupo están en amarillo para ayudarle a separar los nombres de grupo de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="e7f52-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="e7f52-128">Como otro ejemplo, este es un conjunto de comandos que enumera los grupos y todas las pertenencias a grupos para todos los sitios de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e7f52-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a><span data-ttu-id="e7f52-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7f52-129">See also</span></span>

[<span data-ttu-id="e7f52-130">Conectarse a SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7f52-130">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="e7f52-131">Crear sitios de SharePoint Online y agregar usuarios con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7f52-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="e7f52-132">Administrar usuarios y grupos de SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7f52-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="e7f52-133">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7f52-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e7f52-134">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7f52-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)