---
title: Redirigir cuentas de Microsoft Defender para endpoint al Centro de seguridad de Microsoft 365
description: Cómo redirigir cuentas y sesiones desde Defender for Endpoint al Centro de seguridad de Microsoft 365.
keywords: Centro de seguridad de Microsoft 365, Introducción al centro de seguridad de Microsoft 365, redirección del centro de seguridad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: db458015d8434843ec64f3c2c00d640d4c4d8ff2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760181"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a><span data-ttu-id="e5e26-104">Redirigir cuentas de Microsoft Defender para endpoint al Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5e26-104">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e5e26-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e5e26-105">**Applies to:**</span></span>
- <span data-ttu-id="e5e26-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5e26-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="e5e26-107">Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e5e26-107">Defender for Endpoint</span></span>

<span data-ttu-id="e5e26-108">En línea con el enfoque entre dominios de Microsoft para la protección contra amenazas con SIEM y la detección y respuesta extendidas (XDR), hemos cambiado el nombre de Protección contra amenazas avanzada de Microsoft Defender como Microsoft Defender para endpoint y lo hemos unificado en un único portal integrado: el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5e26-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - the Microsoft 365 security center.</span></span>

<span data-ttu-id="e5e26-109">En esta guía se explica cómo enrutar cuentas al centro de seguridad de Microsoft 365 habilitando la redirección automática desde el antiguo portal de Microsoft Defender para endpoints (securitycenter.windows.com o securitycenter.microsoft.com), al portal del centro de seguridad de Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e5e26-109">This guide explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to the Microsoft 365 security center portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="e5e26-110">Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365 admite la concesión de acceso a proveedores de servicios de seguridad administrados [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) del mismo modo que se concede acceso en el Centro de seguridad de [Microsoft Defender.](./mssp-access.md)</span><span class="sxs-lookup"><span data-stu-id="e5e26-110">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="e5e26-111">Qué esperar</span><span class="sxs-lookup"><span data-stu-id="e5e26-111">What to expect</span></span>
<span data-ttu-id="e5e26-112">Una vez habilitada la redirección automática, las cuentas que tengan acceso al antiguo portal de Microsoft Defender para endpoints en securitycenter.windows.com o securitycenter.microsoft.com, se enruta automáticamente al portal del centro de seguridad de Microsoft 365 en security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e5e26-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to the Microsoft 365 security center portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="e5e26-113">Obtenga más información sobre los cambios: Microsoft Defender para endpoint en el Centro de [seguridad de Microsoft 365.](microsoft-365-security-center-mde.md)</span><span class="sxs-lookup"><span data-stu-id="e5e26-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in the Microsoft 365 security center](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="e5e26-114">Esto incluye el redireccionamiento para el acceso directo al antiguo portal a través del explorador, incluidos los vínculos que apuntan hacia el antiguo portal de securitycenter.windows.com, como vínculos en notificaciones de correo electrónico y vínculos devueltos por llamadas api siem.</span><span class="sxs-lookup"><span data-stu-id="e5e26-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="e5e26-115">Actualmente, los vínculos externos de las notificaciones de correo electrónico o las API SIEM contienen vínculos a ambos portales.</span><span class="sxs-lookup"><span data-stu-id="e5e26-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="e5e26-116">Una vez habilitado el redireccionamiento, ambos vínculos apuntarán al centro de seguridad de Microsoft 365 hasta que el vínculo antiguo se quite finalmente.</span><span class="sxs-lookup"><span data-stu-id="e5e26-116">Once redirection is enabled, both links will point to the Microsoft 365 security center until the old link is eventually removed.</span></span> <span data-ttu-id="e5e26-117">Le recomendamos que adopte el nuevo vínculo que apunta al centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5e26-117">We encourage you to adopt the new link pointing to the Microsoft 365 security center.</span></span>

<span data-ttu-id="e5e26-118">Consulte la tabla siguiente para obtener más información sobre los vínculos y el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="e5e26-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="e5e26-119">Enrutamiento de API siem</span><span class="sxs-lookup"><span data-stu-id="e5e26-119">SIEM API routing</span></span>

|<span data-ttu-id="e5e26-120">**Property**</span><span class="sxs-lookup"><span data-stu-id="e5e26-120">**Property**</span></span>  |<span data-ttu-id="e5e26-121">**Destino cuando el redireccionamiento está DESACTIVADO**</span><span class="sxs-lookup"><span data-stu-id="e5e26-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="e5e26-122">**Destino cuando el redireccionamiento está ON**</span><span class="sxs-lookup"><span data-stu-id="e5e26-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="e5e26-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="e5e26-123">LinkToWDATP</span></span> | <span data-ttu-id="e5e26-124">Página de alerta en securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="e5e26-125">Página de alerta en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="e5e26-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="e5e26-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="e5e26-127">Página de incidentes en securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="e5e26-128">Página de incidentes en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="e5e26-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="e5e26-129">LinkToMTP</span></span> | <span data-ttu-id="e5e26-130">Página de alerta en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="e5e26-131">Página de alerta en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="e5e26-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="e5e26-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="e5e26-133">Página de incidentes en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="e5e26-134">Página de incidentes en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="e5e26-135">Notificaciones de alertas de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="e5e26-135">Email alert notifications</span></span>

|<span data-ttu-id="e5e26-136">**Property**</span><span class="sxs-lookup"><span data-stu-id="e5e26-136">**Property**</span></span>  |<span data-ttu-id="e5e26-137">**Destino cuando el redireccionamiento está DESACTIVADO**</span><span class="sxs-lookup"><span data-stu-id="e5e26-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="e5e26-138">**Destino cuando el redireccionamiento está ON**</span><span class="sxs-lookup"><span data-stu-id="e5e26-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="e5e26-139">Página alerta</span><span class="sxs-lookup"><span data-stu-id="e5e26-139">Alert page</span></span>  | <span data-ttu-id="e5e26-140">Página de alerta en securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="e5e26-141">Página de alerta en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="e5e26-142">Página Incidentes</span><span class="sxs-lookup"><span data-stu-id="e5e26-142">Incident page</span></span>  |<span data-ttu-id="e5e26-143">Página de incidentes en securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="e5e26-144">Página de incidentes en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="e5e26-145">Página de alertas en el portal del centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="e5e26-145">Alert page in security center portal</span></span> | <span data-ttu-id="e5e26-146">Página de alerta en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="e5e26-147">Página de alerta en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="e5e26-148">Página de incidentes en el portal del centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="e5e26-148">Incident page in security center portal</span></span> | <span data-ttu-id="e5e26-149">Página de incidentes en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="e5e26-150">Página de incidentes en security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e26-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="e5e26-151">¿Cuándo tiene efecto?</span><span class="sxs-lookup"><span data-stu-id="e5e26-151">When does this take effect?</span></span> 
<span data-ttu-id="e5e26-152">Una vez habilitada, esta actualización podría tener efecto casi inmediatamente para algunas cuentas.</span><span class="sxs-lookup"><span data-stu-id="e5e26-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="e5e26-153">Pero la redirección puede tardar más tiempo en propagarse a todas las cuentas de la organización.</span><span class="sxs-lookup"><span data-stu-id="e5e26-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="e5e26-154">Las cuentas en sesiones activas mientras se aplica esta configuración no se expulsarán de su sesión y solo se enrutarán al centro de seguridad de Microsoft 365 después de finalizar la sesión actual y volver a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="e5e26-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="e5e26-155">Configurar la redirección del portal</span><span class="sxs-lookup"><span data-stu-id="e5e26-155">Set up portal redirection</span></span>
<span data-ttu-id="e5e26-156">Para iniciar el enrutamiento de cuentas al Centro de seguridad de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e5e26-156">To start routing accounts to the Microsoft 365 security center:</span></span>
1. <span data-ttu-id="e5e26-157">Asegúrese de que es un administrador global o que tiene permisos de administrador de seguridad en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e5e26-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="e5e26-158">[Inicie sesión](https://security.microsoft.com/) en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5e26-158">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>

3. <span data-ttu-id="e5e26-159">Vaya a **Configuración Redirección** del Portal general de  >    >    >  **extremos o** [haga clic aquí.](https://security.microsoft.com/preferences2/portal_redirection)</span><span class="sxs-lookup"><span data-stu-id="e5e26-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="e5e26-160">Alterna la configuración de redirección automática a **On**.</span><span class="sxs-lookup"><span data-stu-id="e5e26-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="e5e26-161">Haga **clic en** Habilitar para aplicar el redireccionamiento automático al portal del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5e26-161">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e5e26-162">Si se habilita esta configuración, no se finalizarán las sesiones de usuario activas.</span><span class="sxs-lookup"><span data-stu-id="e5e26-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="e5e26-163">Las cuentas que se encuentran en una sesión activa mientras se aplica esta configuración solo se dirigirán al centro de seguridad de Microsoft 365 después de finalizar la sesión actual y volver a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="e5e26-163">Accounts who are in an active session while this setting is applied will only be directed to the Microsoft 365 security center after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="e5e26-164">Debe ser un administrador global o tener permisos de administrador de seguridad en Azure Active Directory para habilitar o deshabilitar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="e5e26-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="e5e26-165">¿Puedo volver a usar el portal anterior?</span><span class="sxs-lookup"><span data-stu-id="e5e26-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="e5e26-166">Si algo no funciona para usted o si hay algo que no puede completar a través del portal del centro de seguridad de Microsoft 365, queremos escucharlo.</span><span class="sxs-lookup"><span data-stu-id="e5e26-166">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it.</span></span> <span data-ttu-id="e5e26-167">Si ha encontrado algún problema con el redireccionamiento, le recomendamos que nos lo haga saber mediante el formulario Enviar comentarios.</span><span class="sxs-lookup"><span data-stu-id="e5e26-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="e5e26-168">Para volver al antiguo portal de Microsoft Defender para endpoint:</span><span class="sxs-lookup"><span data-stu-id="e5e26-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="e5e26-169">[Inicie sesión](https://security.microsoft.com/) en el Centro de seguridad de Microsoft 365 como administrador global o use y tenga una cuenta con permisos de administrador de seguridad en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e5e26-169">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="e5e26-170">Vaya a **Configuración**  >  **Desdireccionamiento del** Portal general de extremos  >    >   o [abra la página aquí](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="e5e26-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="e5e26-171">Alterna la opción Redirección automática a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="e5e26-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="e5e26-172">Haga **clic en** Deshabilitar & compartir comentarios cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="e5e26-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="e5e26-173">Esta configuración se puede habilitar de nuevo en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="e5e26-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="e5e26-174">Una vez deshabilitadas, las cuentas ya no se enrutarán a security.microsoft.com y volverás a tener acceso al antiguo portal: securitycenter.windows.com o securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e5e26-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="e5e26-175">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="e5e26-175">Related information</span></span>
- [<span data-ttu-id="e5e26-176">Vista general del Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5e26-176">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="e5e26-177">Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5e26-177">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="e5e26-178">Microsoft ofrece SIEM y XDR unificados para modernizar las operaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="e5e26-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="e5e26-179">XDR frente a la infografía siem</span><span class="sxs-lookup"><span data-stu-id="e5e26-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="e5e26-180">El nuevo defensor</span><span class="sxs-lookup"><span data-stu-id="e5e26-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="e5e26-181">Acerca de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5e26-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="e5e26-182">Portales de seguridad de Microsoft y centros de administración</span><span class="sxs-lookup"><span data-stu-id="e5e26-182">Microsoft security portals and admin centers</span></span>](portals.md)