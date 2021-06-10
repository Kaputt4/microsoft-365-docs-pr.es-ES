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
description: En este artículo, busque procedimientos para usar PowerShell para Microsoft 365 administrar SharePoint grupos de sitios en línea.
ms.openlocfilehash: bcc7a00a6114a6fa2ba8aa02520267bd03a0abf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909543"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Administrar grupos de sitio de SharePoint Online con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Aunque puede usar el centro Microsoft 365 administración, también puede usar PowerShell para Microsoft 365 administrar los grupos de sitios SharePoint Online.

## <a name="before-you-begin"></a>Antes de empezar

Los procedimientos de este artículo requieren que se conecte a SharePoint Online. Para obtener instrucciones, consulte [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Ver SharePoint Online con PowerShell para Microsoft 365

El SharePoint de administración en línea tiene algunos métodos fáciles de usar para administrar grupos de sitios. Por ejemplo, supongamos que desea ver los grupos y los miembros del grupo para el `https://litwareinc.sharepoint.com/sites/finance` sitio. Esto es lo que tiene que hacer para:

1. En el centro SharePoint administración, haga clic en **Sitios activos** y, a continuación, haga clic en la dirección URL del sitio.
2. En la página del sitio, haga clic **en el icono Configuración** (ubicado en la esquina superior derecha de la página) y, a continuación, haga clic en Permisos del **sitio**.

Y, así, repita el proceso con el siguiente sitio que quiera ver.

Para obtener una lista de los grupos con PowerShell para Microsoft 365, puede usar los siguientes comandos:

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

Hay dos maneras de ejecutar este conjunto de comandos en el símbolo del sistema del Shell SharePoint administración en línea:

- Copie los comandos en Bloc de notas (u otro editor de texto), modifique el valor de la variable **$siteURL,** seleccione los comandos y, a continuación, péguelos en el símbolo del sistema del Shell de administración en línea de SharePoint. Cuando lo haga, PowerShell se detendrá en un **>>** mensaje. Presione Entrar para ejecutar el `foreach` comando.<br/>
- Copie los comandos en el Bloc de notas (u otro editor de texto), modifique el valor de la variable **$siteURL** y después guarde este archivo de texto con un nombre y la extensión. ps1 en la carpeta adecuada. A continuación, ejecute el script desde el símbolo del SharePoint del Shell de administración en línea especificando su ruta de acceso y nombre de archivo. A continuación se muestra un ejemplo:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

En ambos casos, el resultado será parecido a lo siguiente:

![SharePoint Grupos de sitios en línea](../media/SPO-site-groups.png)

Estos son todos los grupos que se han creado para el sitio `https://litwareinc.sharepoint.com/sites/finance` y todos los usuarios asignados a esos grupos. Los nombres de grupo están en amarillo para ayudarle a separar los nombres de grupo de sus miembros.

Como otro ejemplo, este es un conjunto de comandos que enumera los grupos y todas las pertenencias a grupos para todos los sitios SharePoint Online.

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
    
## <a name="see-also"></a>Consulte también

[Conectarse a SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Crear sitios de SharePoint Online y agregar usuarios con PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Administrar usuarios y grupos de SharePoint Online con PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)