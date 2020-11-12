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
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="0aa57-103">Iniciar el portal mediante el programador de inicio del portal</span><span class="sxs-lookup"><span data-stu-id="0aa57-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="0aa57-104">Puede iniciar el portal mediante el programador de inicio del portal, validando primero la capacidad del administrador de inquilinos para configurar una onda para un nuevo portal.</span><span class="sxs-lookup"><span data-stu-id="0aa57-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="0aa57-105">A continuación, el administrador puede validar una redirección de solicitudes en función de la existencia de un usuario en las ondas activas.</span><span class="sxs-lookup"><span data-stu-id="0aa57-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="0aa57-106">Para obtener más información acerca de cómo iniciar correctamente un portal, siga los principios básicos, prácticas y recomendaciones que se detallan en el [portal de creación, Inicio y mantenimiento de un buen portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span><span class="sxs-lookup"><span data-stu-id="0aa57-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="0aa57-107">Configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0aa57-107">App setup</span></span>
1. <span data-ttu-id="0aa57-108">Desinstalar si ya hay un `Microsoft.Online.SharePoint.PowerShell` desde el equipo a través del panel de control.</span><span class="sxs-lookup"><span data-stu-id="0aa57-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="0aa57-109">En PowerShell Pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="0aa57-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="0aa57-110">Conexión a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0aa57-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="0aa57-111">Abra el [Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en Windows.</span><span class="sxs-lookup"><span data-stu-id="0aa57-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="0aa57-112">Conéctese a su inquilino como administrador.</span><span class="sxs-lookup"><span data-stu-id="0aa57-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="0aa57-113">Proporcione su contraseña cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="0aa57-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="0aa57-114">Comando para obtener una instalación existente</span><span class="sxs-lookup"><span data-stu-id="0aa57-114">Command to get an existing setup</span></span>

<span data-ttu-id="0aa57-115">Para ver las configuraciones de inicio del portal existentes:</span><span class="sxs-lookup"><span data-stu-id="0aa57-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="0aa57-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .</span><span class="sxs-lookup"><span data-stu-id="0aa57-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="0aa57-117">Pase el parámetro adicional `-DisplayFormat Raw` si desea ver la colección de ondas con formato de formato de entrada sin formato.</span><span class="sxs-lookup"><span data-stu-id="0aa57-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="0aa57-118">Comandos para la redirección bidireccional</span><span class="sxs-lookup"><span data-stu-id="0aa57-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="0aa57-119">Para migrar usuarios del sitio antiguos al nuevo sitio de forma escalonada:</span><span class="sxs-lookup"><span data-stu-id="0aa57-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="0aa57-120">Crear ondas de inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="0aa57-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="0aa57-121">Esto solo es aplicable en la fase de prueba de versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="0aa57-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="0aa57-122">Para probar el impacto del cambio inmediatamente, asegúrese de que la primera onda `LaunchDateUtc` esté configurada en la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="0aa57-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="0aa57-123">Si no proporciona esta marca, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="0aa57-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="0aa57-124">Este error se produce porque los lanzamientos en producción deben programarse al menos 7 días antes.</span><span class="sxs-lookup"><span data-stu-id="0aa57-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="0aa57-125">Validación completa.</span><span class="sxs-lookup"><span data-stu-id="0aa57-125">Complete validation.</span></span>
  - <span data-ttu-id="0aa57-126">La redirección puede tardar hasta 5 minutos en completar su configuración en el servicio, por lo que debe esperar antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="0aa57-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="0aa57-127">Si inicia sesión con el usuario especificado como `WaveOverrideUsers` , no cambiará nada.</span><span class="sxs-lookup"><span data-stu-id="0aa57-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="0aa57-128">Debe permanecer en el sitio al que ha navegado.</span><span class="sxs-lookup"><span data-stu-id="0aa57-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="0aa57-129">Iniciar sesión con un usuario que forma parte de los *visores SG1*.</span><span class="sxs-lookup"><span data-stu-id="0aa57-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="0aa57-130">Navegue al sitio anterior y debe redirigirse al sitio nuevo.</span><span class="sxs-lookup"><span data-stu-id="0aa57-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="0aa57-131">Navegue hasta el nuevo sitio y debe permanecer en el nuevo sitio.</span><span class="sxs-lookup"><span data-stu-id="0aa57-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="0aa57-132">Inicie sesión con el usuario en *visores SG2* y vaya al sitio anterior y manténgase en el sitio antiguo.</span><span class="sxs-lookup"><span data-stu-id="0aa57-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="0aa57-133">Navegue al sitio nuevo y debe redirigirse al sitio anterior.</span><span class="sxs-lookup"><span data-stu-id="0aa57-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="0aa57-134">PAUSE el inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="0aa57-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="0aa57-135">Si tiene que pausar las ondas de inicio, puede ponerlas en pausa para "x" número de días.</span><span class="sxs-lookup"><span data-stu-id="0aa57-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="0aa57-136">Si se establece la `Status` marca en pausar, se evitan los próximos avances de onda.</span><span class="sxs-lookup"><span data-stu-id="0aa57-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="0aa57-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="0aa57-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="0aa57-138">Esto valida que todos los usuarios se redirigen al sitio anterior.</span><span class="sxs-lookup"><span data-stu-id="0aa57-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="0aa57-139">Reinicie la progresión de inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="0aa57-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="0aa57-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="0aa57-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="0aa57-141">Valida que la redirección ya se haya restaurado.</span><span class="sxs-lookup"><span data-stu-id="0aa57-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="0aa57-142">Eliminar un portal iniciar configuración.</span><span class="sxs-lookup"><span data-stu-id="0aa57-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="0aa57-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="0aa57-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="0aa57-144">Validar que no se produzca ninguna redirección para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0aa57-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="0aa57-145">Comandos para redirigir a página temporal</span><span class="sxs-lookup"><span data-stu-id="0aa57-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="0aa57-146">Siga estos pasos si no tiene un sitio anterior y desea omitir los usuarios que no están en el desembarque de la onda en la nueva página del portal.</span><span class="sxs-lookup"><span data-stu-id="0aa57-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="0aa57-147">Para crear una página temporal en cualquiera de los sitios:</span><span class="sxs-lookup"><span data-stu-id="0aa57-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="0aa57-148">Cree una onda de lanzamiento de portal.</span><span class="sxs-lookup"><span data-stu-id="0aa57-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="0aa57-149">Validación completa.</span><span class="sxs-lookup"><span data-stu-id="0aa57-149">Complete validation.</span></span>

  - <span data-ttu-id="0aa57-150">Espere cinco minutos antes de continuar, ya que la acción puede tardar hasta cinco minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="0aa57-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="0aa57-151">Registro con el usuario que forma parte de los *visores SG1* y:</span><span class="sxs-lookup"><span data-stu-id="0aa57-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="0aa57-152">Navegue al nuevo sitio y debe permanecer en el nuevo sitio.</span><span class="sxs-lookup"><span data-stu-id="0aa57-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="0aa57-153">Navegue a la página Temp y debe permanecer en la página Temp.</span><span class="sxs-lookup"><span data-stu-id="0aa57-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="0aa57-154">Registro con el usuario que forma parte de los *visores SG2* y:</span><span class="sxs-lookup"><span data-stu-id="0aa57-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="0aa57-155">Navegue hasta el nuevo sitio y se le redirigirá a la página Temp.</span><span class="sxs-lookup"><span data-stu-id="0aa57-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="0aa57-156">Navegue a la página Temp y debe permanecer en la página Temp.</span><span class="sxs-lookup"><span data-stu-id="0aa57-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="0aa57-157">Eliminar un portal iniciar configuración.</span><span class="sxs-lookup"><span data-stu-id="0aa57-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="0aa57-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="0aa57-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="0aa57-159">Validar que no se produzca ninguna redirección para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0aa57-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="0aa57-160">Más información</span><span class="sxs-lookup"><span data-stu-id="0aa57-160">Learn more</span></span>
[<span data-ttu-id="0aa57-161">Planeación del lanzamiento del portal del plan de implementación en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0aa57-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)