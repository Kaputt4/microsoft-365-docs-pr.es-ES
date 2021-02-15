---
title: Iniciar el portal mediante el Programador de inicio del portal
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
description: En este artículo se describe cómo iniciar el portal mediante el Programador de inicio del portal
ms.openlocfilehash: 66912f5730c580bd75282a64124fefcdf262d738
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864881"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="06ecd-103">Iniciar el portal mediante el Programador de inicio del portal</span><span class="sxs-lookup"><span data-stu-id="06ecd-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="06ecd-104">Un portal es un sitio de SharePoint en la intranet que tiene un gran número de visores de sitio que emplean el contenido en el sitio.</span><span class="sxs-lookup"><span data-stu-id="06ecd-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="06ecd-105">Iniciar el portal en oleadas es una parte importante de garantizar que los usuarios tengan una experiencia fluida y con un rendimiento que acceda a un nuevo portal de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="06ecd-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="06ecd-106">Iniciar en oleadas es una forma clave de lanzar el portal, como se detalla en la planeación del plan de lanzamiento de lanzamiento del [portal en SharePoint Online.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="06ecd-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="06ecd-107">El Programador de inicio del portal está diseñado para ayudarle a seguir un enfoque de implementación por fases o oleadas mediante la administración de redireccionamientos para el nuevo portal.</span><span class="sxs-lookup"><span data-stu-id="06ecd-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="06ecd-108">Durante cada una de las oleadas, puedes recopilar comentarios de los usuarios y supervisar el rendimiento durante cada oleada de implementación.</span><span class="sxs-lookup"><span data-stu-id="06ecd-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="06ecd-109">Esto tiene la ventaja de introducir lentamente el portal, lo que te da la opción de pausar y resolver problemas antes de continuar con la siguiente oleada y, en última instancia, garantizar una experiencia positiva para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="06ecd-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="06ecd-110">Hay dos tipos de redirección:</span><span class="sxs-lookup"><span data-stu-id="06ecd-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="06ecd-111">bidireccional: inicie un nuevo portal de SharePoint Online moderno para reemplazar un portal moderno o clásico de SharePoint existente</span><span class="sxs-lookup"><span data-stu-id="06ecd-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="06ecd-112">redirección de página temporal: inicie un nuevo portal de SharePoint Online moderno sin ningún portal de SharePoint existente</span><span class="sxs-lookup"><span data-stu-id="06ecd-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="06ecd-113">El programador de inicio del portal solo está disponible para iniciar portales modernos de SharePoint Online (es decir, sitios de comunicación).</span><span class="sxs-lookup"><span data-stu-id="06ecd-113">The portal launch scheduler is only available to launch modern SharePoint Online portals (i.e. communication sites).</span></span> <span data-ttu-id="06ecd-114">Los inicios deben programarse con al menos 7 días de antelación.</span><span class="sxs-lookup"><span data-stu-id="06ecd-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="06ecd-115">El número de oleadas requerido está determinado por el número esperado de usuarios.</span><span class="sxs-lookup"><span data-stu-id="06ecd-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="06ecd-116">Antes de programar el inicio de un portal, debe ejecutarse la herramienta Diagnóstico de páginas para [SharePoint](https://aka.ms/perftool) para comprobar que la página principal del portal está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="06ecd-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="06ecd-117">Al final del inicio del portal, todos los usuarios con permisos para el sitio podrán acceder al nuevo sitio.</span><span class="sxs-lookup"><span data-stu-id="06ecd-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="06ecd-118">Para obtener más información sobre cómo iniciar un portal correcto, siga los principios, prácticas y recomendaciones básicos detallados en Crear, iniciar y mantener [un portal en buen estado.](https://docs.microsoft.com/sharepoint/portal-health)</span><span class="sxs-lookup"><span data-stu-id="06ecd-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="06ecd-119">Esta característica no está disponible para los planes de Office 365 Germany, Office 365 operado por 21Vianet (China) o Microsoft 365 Us Government.</span><span class="sxs-lookup"><span data-stu-id="06ecd-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="06ecd-120">Configuración de la aplicación y conexión a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="06ecd-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="06ecd-121">[Descargue el Shell de administración de SharePoint Online más reciente](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="06ecd-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="06ecd-p104">Si instaló una versión anterior del Shell de administración de SharePoint Online, vaya a Agregar o quitar programas y desinstale "Shell de administración de SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="06ecd-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="06ecd-123">En la página Centro de descarga, seleccione su idioma y haga clic en el botón Descargar.</span><span class="sxs-lookup"><span data-stu-id="06ecd-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="06ecd-124">Se le pedirá que elija entre descargar un archivo .msi x64 y x86.</span><span class="sxs-lookup"><span data-stu-id="06ecd-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="06ecd-125">Descargue el archivo x64 si está ejecutando la versión de 64 bits de Windows o el archivo x86 si está ejecutando la versión de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="06ecd-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="06ecd-126">Si no lo sabe, consulte [¿Qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="06ecd-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="06ecd-127">Después de descargar el archivo, ejecútelo y siga los pasos del Asistente de configuración.</span><span class="sxs-lookup"><span data-stu-id="06ecd-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="06ecd-128">Conéctese a SharePoint como un [administrador global o como un administrador de SharePoint](/sharepoint/sharepoint-admin-role) en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06ecd-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="06ecd-129">Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="06ecd-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="06ecd-130">Ver las configuraciones de inicio del portal existentes</span><span class="sxs-lookup"><span data-stu-id="06ecd-130">View any existing portal launch setups</span></span>

<span data-ttu-id="06ecd-131">Para ver si hay configuraciones de inicio de portal existentes:</span><span class="sxs-lookup"><span data-stu-id="06ecd-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="06ecd-132">Programar el inicio de un portal en el sitio</span><span class="sxs-lookup"><span data-stu-id="06ecd-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="06ecd-133">El número de oleadas necesarias depende del tamaño de inicio esperado.</span><span class="sxs-lookup"><span data-stu-id="06ecd-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="06ecd-134">Menos de 10.000 usuarios: 1 oleada</span><span class="sxs-lookup"><span data-stu-id="06ecd-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="06ecd-135">De 10.000 a 30.000 usuarios: 3 oleadas</span><span class="sxs-lookup"><span data-stu-id="06ecd-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="06ecd-136">De 30.000 a 100.000 usuarios: 5 oleadas</span><span class="sxs-lookup"><span data-stu-id="06ecd-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="06ecd-137">Más de 100.000 usuarios: 5 oleadas y póngase en contacto con su equipo de cuentas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="06ecd-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="06ecd-138">Pasos para la redirección bidireccional</span><span class="sxs-lookup"><span data-stu-id="06ecd-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="06ecd-139">La redirección bidireccional implica el inicio de un nuevo portal de SharePoint Online moderno para reemplazar un portal moderno o clásico de SharePoint existente.</span><span class="sxs-lookup"><span data-stu-id="06ecd-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="06ecd-140">Los usuarios de las oleadas activas serán redirigidos al nuevo sitio independientemente de si navegan al sitio antiguo o nuevo.</span><span class="sxs-lookup"><span data-stu-id="06ecd-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="06ecd-141">Los usuarios de una oleada no iniciada que intenten obtener acceso al nuevo sitio serán redirigidos de nuevo al sitio antiguo hasta que se inicia su oleada.</span><span class="sxs-lookup"><span data-stu-id="06ecd-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="06ecd-142">Solo se admite el redireccionamiento entre la página principal predeterminada del sitio antiguo y la página principal predeterminada en el nuevo sitio.</span><span class="sxs-lookup"><span data-stu-id="06ecd-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="06ecd-143">Si tiene administradores o propietarios que necesitan tener acceso a los sitios antiguos y nuevos sin ser redirigidos, asegúrese de que aparecen con el `WaveOverrideUsers` parámetro.</span><span class="sxs-lookup"><span data-stu-id="06ecd-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="06ecd-144">Para migrar usuarios de un sitio de SharePoint existente a un nuevo sitio de SharePoint de forma por fases:</span><span class="sxs-lookup"><span data-stu-id="06ecd-144">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="06ecd-145">Ejecute el siguiente comando para designar las oleadas de inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="06ecd-145">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="06ecd-146">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="06ecd-146">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="06ecd-147">Validación completa.</span><span class="sxs-lookup"><span data-stu-id="06ecd-147">Complete validation.</span></span> <span data-ttu-id="06ecd-148">El redireccionamiento puede tardar entre 5 y 10 minutos en completar su configuración en todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="06ecd-148">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="06ecd-149">Pasos para la redirección a la página temporal</span><span class="sxs-lookup"><span data-stu-id="06ecd-149">Steps for redirection to temporary page</span></span>

<span data-ttu-id="06ecd-150">El redireccionamiento temporal de páginas debe usarse cuando no exista ningún portal de SharePoint existente.</span><span class="sxs-lookup"><span data-stu-id="06ecd-150">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="06ecd-151">Los usuarios se dirigen a un nuevo portal de SharePoint Online moderno de forma por fases.</span><span class="sxs-lookup"><span data-stu-id="06ecd-151">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="06ecd-152">Si un usuario está en una oleada que no se ha iniciado, se le redirigirá a una página temporal (cualquier dirección URL).</span><span class="sxs-lookup"><span data-stu-id="06ecd-152">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="06ecd-153">Ejecute el siguiente comando para designar las oleadas de inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="06ecd-153">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="06ecd-154">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="06ecd-154">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="06ecd-155">Validación completa.</span><span class="sxs-lookup"><span data-stu-id="06ecd-155">Complete validation.</span></span> <span data-ttu-id="06ecd-156">El redireccionamiento puede tardar entre 5 y 10 minutos en completar su configuración en todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="06ecd-156">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="06ecd-157">Pausar o reiniciar el inicio de un portal en el sitio</span><span class="sxs-lookup"><span data-stu-id="06ecd-157">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="06ecd-158">Para pausar el inicio de un portal en curso y evitar temporalmente que se produzcan las próximas progresión de oleadas, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="06ecd-158">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="06ecd-159">Valide que todos los usuarios sean redirigidos al sitio antiguo.</span><span class="sxs-lookup"><span data-stu-id="06ecd-159">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="06ecd-160">Para reiniciar un inicio de portal que se ha pausado, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="06ecd-160">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="06ecd-161">Valide que el redireccionamiento ya está restaurado.</span><span class="sxs-lookup"><span data-stu-id="06ecd-161">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="06ecd-162">Eliminar un inicio de portal en el sitio</span><span class="sxs-lookup"><span data-stu-id="06ecd-162">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="06ecd-163">Ejecute el siguiente comando para eliminar un inicio del portal programado o en curso para un sitio.</span><span class="sxs-lookup"><span data-stu-id="06ecd-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="06ecd-164">Valide que no se produce ningún redireccionamiento para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="06ecd-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="06ecd-165">Más información</span><span class="sxs-lookup"><span data-stu-id="06ecd-165">Learn more</span></span>
[<span data-ttu-id="06ecd-166">Planeación del plan de lanzamiento de lanzamiento del portal en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="06ecd-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
