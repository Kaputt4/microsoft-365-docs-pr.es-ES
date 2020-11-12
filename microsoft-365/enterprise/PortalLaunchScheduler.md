---
title: Iniciar el portal mediante el programador de inicio del portal
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: En este artículo se describe cómo puede iniciar el portal mediante el programador de inicio del portal
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999596"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Iniciar el portal mediante el programador de inicio del portal

Puede iniciar el portal mediante el programador de inicio del portal, validando primero la capacidad del administrador de inquilinos para configurar una onda para un nuevo portal. A continuación, el administrador puede validar una redirección de solicitudes en función de la existencia de un usuario en las ondas activas.

Para obtener más información acerca de cómo iniciar correctamente un portal, siga los principios básicos, prácticas y recomendaciones que se detallan en el [portal de creación, Inicio y mantenimiento de un buen portal](https://go.microsoft.com/fwlink/?linkid=2105838). 

## <a name="app-setup"></a>Configuración de aplicaciones
1. Desinstalar si ya hay un `Microsoft.Online.SharePoint.PowerShell` desde el equipo a través del panel de control.
2. En PowerShell Pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .

## <a name="connect-to-sharepoint-online"></a>Conexión a SharePoint Online
1. Abra el [Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en Windows.
2. Conéctese a su inquilino como administrador.
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  Proporcione su contraseña cuando se le solicite.

## <a name="command-to-get-an-existing-setup"></a>Comando para obtener una instalación existente

Para ver las configuraciones de inicio del portal existentes:

1. Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .
2. Pase el parámetro adicional `-DisplayFormat Raw` si desea ver la colección de ondas con formato de formato de entrada sin formato.

## <a name="commands-for-bi-directional-redirection"></a>Comandos para la redirección bidireccional

Para migrar usuarios del sitio antiguos al nuevo sitio de forma escalonada:

1. Crear ondas de inicio del portal.
   - Esto solo es aplicable en la fase de prueba de versiones anteriores.
   - Para probar el impacto del cambio inmediatamente, asegúrese de que la primera onda `LaunchDateUtc` esté configurada en la fecha actual. Si no proporciona esta marca, recibirá un mensaje de error. Este error se produce porque los lanzamientos en producción deben programarse al menos 7 días antes.

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Validación completa.
  - La redirección puede tardar hasta 5 minutos en completar su configuración en el servicio, por lo que debe esperar antes de continuar.
  - Si inicia sesión con el usuario especificado como `WaveOverrideUsers` , no cambiará nada. Debe permanecer en el sitio al que ha navegado.
  - Iniciar sesión con un usuario que forma parte de los *visores SG1*.
    - Navegue al sitio anterior y debe redirigirse al sitio nuevo.
    - Navegue hasta el nuevo sitio y debe permanecer en el nuevo sitio.
    - Inicie sesión con el usuario en *visores SG2* y vaya al sitio anterior y manténgase en el sitio antiguo.
    - Navegue al sitio nuevo y debe redirigirse al sitio anterior.

3. PAUSE el inicio del portal.
  - Si tiene que pausar las ondas de inicio, puede ponerlas en pausa para "x" número de días. Si se establece la `Status` marca en pausar, se evitan los próximos avances de onda. 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Esto valida que todos los usuarios se redirigen al sitio anterior.

4. Reinicie la progresión de inicio del portal. 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Valida que la redirección ya se haya restaurado.

5. Eliminar un portal iniciar configuración.
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - Validar que no se produzca ninguna redirección para todos los usuarios.

## <a name="commands-for-redirection-to-temporary-page"></a>Comandos para redirigir a página temporal

Siga estos pasos si no tiene un sitio anterior y desea omitir los usuarios que no están en el desembarque de la onda en la nueva página del portal.

Para crear una página temporal en cualquiera de los sitios:

1. Cree una onda de lanzamiento de portal.
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Validación completa.

  - Espere cinco minutos antes de continuar, ya que la acción puede tardar hasta cinco minutos en completarse.
  - Registro con el usuario que forma parte de los *visores SG1* y:
     - Navegue al nuevo sitio y debe permanecer en el nuevo sitio.
     - Navegue a la página Temp y debe permanecer en la página Temp.
  - Registro con el usuario que forma parte de los *visores SG2* y:
     - Navegue hasta el nuevo sitio y se le redirigirá a la página Temp.
     - Navegue a la página Temp y debe permanecer en la página Temp.

3. Eliminar un portal iniciar configuración.
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Validar que no se produzca ninguna redirección para todos los usuarios.

## <a name="learn-more"></a>Más información
[Planeación del lanzamiento del portal del plan de implementación en SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)