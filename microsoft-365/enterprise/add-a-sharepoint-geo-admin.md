---
title: Agregar o quitar un administrador geográfico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection: SPO_Content
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: ¿Necesita configurar administradores independientes para cada ubicación geográfica? Obtenga más información sobre cómo agregar o quitar un administrador geográfico de Microsoft 365 Multi-Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 511dcc104eb8898c974c811b87704b3f22d4a2c2
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804672"
---
# <a name="add-or-remove-a-_geography_-administrator-in-microsoft-365-multi-geo"></a>Agregar o quitar un administrador _de Geography_ en Microsoft 365 Multi-Geo

Puede configurar administradores independientes para cada ubicación _geográfica_ que tenga en el _inquilino_. Estos administradores tendrán acceso a la configuración de SharePoint Online y OneDrive que son específicas de su ubicación _geográfica_ .

Algunos servicios, como el almacén de términos, se administran desde la ubicación _geografía aprovisionada principal_ y se replican en ubicaciones _de geografía satélite_ . El administrador _de geografía_ de la ubicación _geografía aprovisionada principal_ tiene acceso a ellos, mientras que los administradores de _geografía_ para las ubicaciones _de geografía satélite_ no.

Los administradores globales y los administradores de SharePoint Online siguen teniendo acceso a la configuración de la ubicación _geografía aprovisionada principal_ y a todas las ubicaciones _de geografía satélite_ .

## <a name="configuring-_geography_-administrators"></a>Configuración de administradores _de geografía_

La configuración de administradores _de Geography_ requiere el módulo de PowerShell de SharePoint Online.

Use [Connect-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) para conectarse al centro de administración de la ubicación _geography_ donde desea agregar el administrador _de Geography_ . (Por ejemplo, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)

Para ver los administradores de _Geography_ existentes de una ubicación, ejecute `Get-SPOGeoAdministrator`

## <a name="adding-a-user-as-a-_geography_-admin"></a>Adición de un usuario como administrador de _Geography_

Para agregar un usuario como administrador _de Geography_ , ejecute `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`

Para quitar un usuario como un Administración _geography_ de una ubicación, ejecute`Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`

## <a name="adding-a-group-as-a-_geography_-admin"></a>Adición de un grupo como administrador de _Geography_

Puede agregar un grupo de seguridad o un grupo de seguridad habilitado para correo como administrador _de Geography_. (No se admiten los grupos de distribución ni Grupos de Microsoft 365).

Para agregar un grupo como administrador _de Geography_ , ejecute `Add-SPOGeoAdministrator -GroupAlias <alias>`

Para quitar un grupo como administrador _de Geography_ , ejecute `Remove-SPOGeoAdministrator -GroupAlias <alias>`

Tenga en cuenta que no todos los grupos de seguridad tienen un alias de grupo. Si quiere agregar un grupo de seguridad que no tiene un alias, ejecute [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) para recuperar una lista de grupos, busque el ObjectID del grupo seguridad y ejecute lo siguiente:

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

Para quitar un grupo mediante ObjectID, ejecute `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`

## <a name="related-topics"></a>Temas relacionados

[Add-SPOGeoAdministrator](/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[Establecer un alias (MailNickName) de un grupo de seguridad](/powershell/module/azuread/set-azureadgroup)
