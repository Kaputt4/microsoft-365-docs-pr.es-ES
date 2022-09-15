---
title: Capacidades multigeográficas de OneDrive y SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: admindeeplinkSPO
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
ms.localizationpriority: medium
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Expanda la presencia de Microsoft 365 a varias regiones geográficas con las capacidades multigeográficas de OneDrive Online.
ms.openlocfilehash: b25d74c76673c8fcaf2de0e8bbbd1c73ba371856
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694367"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Capacidades multigeográficas de OneDrive y SharePoint Online

Las funcionalidades multigeográficas de OneDrive y SharePoint Online permiten el control de recursos compartidos, como sitios de grupo de SharePoint y buzones de Microsoft 365 Group almacenados en reposo en una ubicación geográfica especificada.

Cada usuario, buzón de grupo y sitio de SharePoint tienen una ubicación de datos preferida (PDL) que indica la ubicación geográfica donde se van a almacenar los datos relacionados. Los datos personales de los usuarios (buzón de Exchange y OneDrive), junto con los Grupos de Microsoft 365 o los sitios de SharePoint que creen, pueden almacenarse en la ubicación geográfica especificada para cumplir los requisitos de residencia de datos. También puede [especificar administradores diferentes para cada ubicación geográfica](add-a-sharepoint-geo-admin.md).

Los usuarios obtienen una experiencia fluida al usar los servicios de Microsoft 365, incluidas las aplicaciones de Office, OneDrive y Search. Vea [Experiencia de usuario en un entorno multi-geográfico](multi-geo-user-experience.md) para obtener más información.

## <a name="onedrive"></a>OneDrive

El OneDrive de cada usuario lo puede aprovisionar o [mover un administrador](move-onedrive-between-geo-locations.md) a una ubicación de satélite conforme con la PDL del usuario. Los archivos personales se conservan en esa ubicación geográfica, aunque se pueden compartir con usuarios en otra ubicación geográfica.

## <a name="sharepoint-sites-and-groups"></a>Sitios y grupos de SharePoint

La administración de la característica multigeográfica está disponible a través del <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">Centro de administración de SharePoint</a>. Encontrará información detallada en la [correspondiente entrada de blog](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).

Cuando un usuario crea un sitio conectado a un grupo de SharePoint en un entorno multigeográfico, su PDL se usa para determinar la ubicación geográfica donde se crean el sitio y su buzón de grupo asociado. (Si el valor de la PDL del usuario no se ha configurado o se ha establecido en una ubicación geográfica que no se ha configurado como una ubicación de satélite, el sitio y el buzón se crean en la ubicación central).

Los servicios de Microsoft 365 distintos de Exchange, OneDrive, SharePoint y Teams no son multigeográficas. Sin embargo, Grupos de Microsoft 365 que crean estos servicios se configurarán con la PDL del creador y su buzón de correo del grupo de Exchange, el sitio de SharePoint se aprovisiona en la ubicación geográfica correspondiente. 

## <a name="managing-the-multi-geo-environment"></a>Administrar el entorno multigeográfico

La configuración y administración del entorno multigeográfico se realiza a través del <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">Centro de administración de SharePoint</a>. 

![Captura de pantalla de la página de ubicaciones geográficas en el Centro de administración de SharePoint.](../media/sharepoint-multi-geo-admin-center.png)

(Algunas acciones, como cambiar un sitio de SharePoint o un sitio de OneDrive, requieren Microsoft PowerShell).

## <a name="see-also"></a>Consulte también

[Capacidades multigeográficas en grupos de SharePoint y Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Administración de un entorno multigeográfico](administering-a-multi-geo-environment.md)

[Cuotas de almacenamiento de SharePoint en entornos multigeográficos](sharepoint-multi-geo-storage-quota.md)

[Administración de buzones de correo de Exchange Online en un entorno multigeográfico](administering-exchange-online-multi-geo.md)
