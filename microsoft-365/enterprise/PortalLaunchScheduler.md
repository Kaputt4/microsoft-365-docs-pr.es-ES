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
ms.openlocfilehash: 7e488caba5e4df47bb3f51f195e093891565d95c
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367206"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="026a9-103">Iniciar el portal mediante el programador de inicio del portal</span><span class="sxs-lookup"><span data-stu-id="026a9-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="026a9-104">Un portal es un sitio de SharePoint en la intranet que tiene un gran número de visores de sitio que emplean el contenido en el sitio.</span><span class="sxs-lookup"><span data-stu-id="026a9-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="026a9-105">El inicio del portal en ondas es una parte importante de la garantía de que los usuarios tienen una experiencia sin problemas y de forma eficaz para obtener acceso a un nuevo portal de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="026a9-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="026a9-106">El lanzamiento en ondas es una forma clave de implementar el portal, como se detalla en [planear el plan de implementación de lanzamiento de portal en SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="026a9-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="026a9-107">El programador de inicio del portal está diseñado para ayudarle a seguir un enfoque de lanzamiento en fases o oleada administrando las redirecciones para el nuevo portal.</span><span class="sxs-lookup"><span data-stu-id="026a9-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="026a9-108">Durante cada una de las ondas, puede recopilar los comentarios de los usuarios y supervisar el rendimiento durante cada una de las ondas de implementación.</span><span class="sxs-lookup"><span data-stu-id="026a9-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="026a9-109">Esto tiene la ventaja de presentar lentamente el portal, lo que le ofrece la posibilidad de pausar y resolver problemas antes de continuar con la siguiente ola y, en última instancia, garantizar una experiencia positiva para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="026a9-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="026a9-110">Hay dos tipos de redirección:</span><span class="sxs-lookup"><span data-stu-id="026a9-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="026a9-111">bidireccional: iniciar un nuevo portal moderno de SharePoint Online para reemplazar un portal clásico o moderno de SharePoint existente</span><span class="sxs-lookup"><span data-stu-id="026a9-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="026a9-112">redirección de página temporal: iniciar un nuevo portal moderno de SharePoint Online sin SharePoint Portal existente</span><span class="sxs-lookup"><span data-stu-id="026a9-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="026a9-113">El programador de inicio del portal solo está disponible para iniciar los portales modernos de SharePoint Online, es decir, los sitios de comunicación y los sitios de grupo modernos.</span><span class="sxs-lookup"><span data-stu-id="026a9-113">The portal launch scheduler is only available to launch modern SharePoint Online portals, i.e. communication sites and modern team sites.</span></span> <span data-ttu-id="026a9-114">Los lanzamientos deben programarse al menos 7 días antes.</span><span class="sxs-lookup"><span data-stu-id="026a9-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="026a9-115">El número de ondas necesario se determina según el número de usuarios previsto.</span><span class="sxs-lookup"><span data-stu-id="026a9-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="026a9-116">Antes de programar un inicio del portal, debe ejecutarse la [herramienta diagnósticos de página para SharePoint](https://aka.ms/perftool) para comprobar que la Página principal del portal está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="026a9-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="026a9-117">Al final del inicio del portal, todos los usuarios con permisos para el sitio podrán tener acceso al nuevo sitio.</span><span class="sxs-lookup"><span data-stu-id="026a9-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="026a9-118">Para obtener más información acerca de cómo iniciar correctamente un portal, siga los principios básicos, prácticas y recomendaciones detalladas para [crear, iniciar y mantener un portal saludable](https://docs.microsoft.com/sharepoint/portal-health).</span><span class="sxs-lookup"><span data-stu-id="026a9-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="026a9-119">Esta característica no está disponible para los planes de Office 365 Germany, Office 365 operado por 21Vianet (China) o Microsoft 365 US Government.</span><span class="sxs-lookup"><span data-stu-id="026a9-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="026a9-120">Configuración de aplicaciones y conexión a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="026a9-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="026a9-121">[Descargue el Shell de administración de SharePoint Online más reciente](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="026a9-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="026a9-p104">Si instaló una versión anterior del Shell de administración de SharePoint Online, vaya a Agregar o quitar programas y desinstale "Shell de administración de SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="026a9-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="026a9-123">En la página Centro de descarga, seleccione su idioma y haga clic en el botón Descargar.</span><span class="sxs-lookup"><span data-stu-id="026a9-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="026a9-124">Se le pedirá que elija entre descargar un archivo .msi x64 y x86.</span><span class="sxs-lookup"><span data-stu-id="026a9-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="026a9-125">Descargue el archivo x64 si está ejecutando la versión de 64 bits de Windows o el archivo x86 si está ejecutando la versión de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="026a9-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="026a9-126">Si no lo sabe, consulte [¿Qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="026a9-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="026a9-127">Después de descargar el archivo, ejecútelo y siga los pasos del Asistente de configuración.</span><span class="sxs-lookup"><span data-stu-id="026a9-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="026a9-128">Conéctese a SharePoint como un [administrador global o como un administrador de SharePoint](/sharepoint/sharepoint-admin-role) en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="026a9-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="026a9-129">Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="026a9-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="026a9-130">Ver las configuraciones de inicio del portal existentes</span><span class="sxs-lookup"><span data-stu-id="026a9-130">View any existing portal launch setups</span></span>

<span data-ttu-id="026a9-131">Para ver si hay configuraciones de inicio del portal existentes:</span><span class="sxs-lookup"><span data-stu-id="026a9-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="026a9-132">Programar un inicio del portal en el sitio</span><span class="sxs-lookup"><span data-stu-id="026a9-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="026a9-133">El número de ondas necesarias depende del tamaño de inicio previsto.</span><span class="sxs-lookup"><span data-stu-id="026a9-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="026a9-134">Menos de 10.000 usuarios: 1 ola</span><span class="sxs-lookup"><span data-stu-id="026a9-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="026a9-135">de 10 k a 30K: 3 ondas</span><span class="sxs-lookup"><span data-stu-id="026a9-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="026a9-136">30K + a 100 a 100 usuarios: 5 ondas</span><span class="sxs-lookup"><span data-stu-id="026a9-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="026a9-137">Más de 100 k usuarios: 5 ondas y póngase en contacto con el equipo de la cuenta de Microsoft</span><span class="sxs-lookup"><span data-stu-id="026a9-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="026a9-138">Pasos para la redirección bidireccional</span><span class="sxs-lookup"><span data-stu-id="026a9-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="026a9-139">La redirección bidireccional consiste en iniciar un nuevo portal moderno de SharePoint Online para reemplazar un portal clásico o moderno de SharePoint existente.</span><span class="sxs-lookup"><span data-stu-id="026a9-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="026a9-140">Los usuarios de ondas activas se redirigirán al nuevo sitio independientemente de si navegan hasta el sitio antiguo o el nuevo.</span><span class="sxs-lookup"><span data-stu-id="026a9-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="026a9-141">Los usuarios de una onda no iniciada que intenten obtener acceso al nuevo sitio se redirigirán de vuelta al sitio antiguo hasta que se inicie la onda.</span><span class="sxs-lookup"><span data-stu-id="026a9-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="026a9-142">Solo se admite la redirección entre la Página principal predeterminada del sitio antiguo y la Página principal predeterminada en el nuevo sitio.</span><span class="sxs-lookup"><span data-stu-id="026a9-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="026a9-143">Si tiene administradores o propietarios que necesitan tener acceso a los sitios antiguos y nuevos sin redirigirse, asegúrese de que aparecen en la lista mediante el `WaveOverrideUsers` parámetro.</span><span class="sxs-lookup"><span data-stu-id="026a9-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="026a9-144">Si tiene administradores o propietarios que necesitan tener acceso a los sitios antiguos y nuevos sin redirigirse, asegúrese de que aparecen en la lista mediante el `WaveOverrideUsers` parámetro.</span><span class="sxs-lookup"><span data-stu-id="026a9-144">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="026a9-145">Solo se admite la redirección entre la Página principal predeterminada del sitio antiguo y la Página principal predeterminada en el nuevo sitio.</span><span class="sxs-lookup"><span data-stu-id="026a9-145">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span>

<span data-ttu-id="026a9-146">Para migrar los usuarios de un sitio de SharePoint existente a un nuevo sitio de SharePoint de forma escalonada:</span><span class="sxs-lookup"><span data-stu-id="026a9-146">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="026a9-147">Ejecute el siguiente comando para designar las ondas de lanzamiento del portal.</span><span class="sxs-lookup"><span data-stu-id="026a9-147">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="026a9-148">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="026a9-148">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="026a9-149">Validación completa.</span><span class="sxs-lookup"><span data-stu-id="026a9-149">Complete validation.</span></span> <span data-ttu-id="026a9-150">El redireccionamiento puede tardar 5-10 minutos en completarse para completar su configuración en el servicio.</span><span class="sxs-lookup"><span data-stu-id="026a9-150">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="026a9-151">Pasos para redirigir a la página temporal</span><span class="sxs-lookup"><span data-stu-id="026a9-151">Steps for redirection to temporary page</span></span>

<span data-ttu-id="026a9-152">La redirección de página temporal debe usarse cuando no exista portal de SharePoint existente.</span><span class="sxs-lookup"><span data-stu-id="026a9-152">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="026a9-153">Los usuarios se dirigen a un nuevo portal moderno de SharePoint Online de forma escalonada.</span><span class="sxs-lookup"><span data-stu-id="026a9-153">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="026a9-154">Si un usuario está en una onda que no se ha iniciado, se le redirigirá a una página temporal (cualquier dirección URL).</span><span class="sxs-lookup"><span data-stu-id="026a9-154">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="026a9-155">Ejecute el siguiente comando para designar las ondas de lanzamiento del portal.</span><span class="sxs-lookup"><span data-stu-id="026a9-155">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="026a9-156">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="026a9-156">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="026a9-157">Validación completa.</span><span class="sxs-lookup"><span data-stu-id="026a9-157">Complete validation.</span></span> <span data-ttu-id="026a9-158">El redireccionamiento puede tardar 5-10 minutos en completarse para completar su configuración en el servicio.</span><span class="sxs-lookup"><span data-stu-id="026a9-158">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="026a9-159">Pausar o reiniciar el inicio de un portal en el sitio</span><span class="sxs-lookup"><span data-stu-id="026a9-159">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="026a9-160">Para pausar un inicio del portal en curso y evitar temporalmente los próximos progresos de onda, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="026a9-160">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="026a9-161">Compruebe que todos los usuarios se redirigen al sitio anterior.</span><span class="sxs-lookup"><span data-stu-id="026a9-161">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="026a9-162">Para reiniciar un inicio del portal que se ha pausado, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="026a9-162">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="026a9-163">Valida que la redirección ya se haya restaurado.</span><span class="sxs-lookup"><span data-stu-id="026a9-163">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="026a9-164">Eliminar un inicio del portal en el sitio</span><span class="sxs-lookup"><span data-stu-id="026a9-164">Delete a portal launch on the site</span></span>
1. <span data-ttu-id="026a9-165">Cree una onda de lanzamiento de portal.</span><span class="sxs-lookup"><span data-stu-id="026a9-165">Create a Portal launch Wave.</span></span>
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="026a9-166">Ejecute el siguiente comando para eliminar un inicio del portal programado o en curso para un sitio.</span><span class="sxs-lookup"><span data-stu-id="026a9-166">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. <span data-ttu-id="026a9-167">Validar que no se produzca ninguna redirección para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="026a9-167">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="026a9-168">Más información</span><span class="sxs-lookup"><span data-stu-id="026a9-168">Learn more</span></span>
[<span data-ttu-id="026a9-169">Planeación del lanzamiento del portal del plan de implementación en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="026a9-169">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
