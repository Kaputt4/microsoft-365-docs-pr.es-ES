---
title: Solucionar problemas en ATP de Microsoft Defender para Android
description: Solucionar problemas de ATP de Microsoft Defender para Android
keywords: microsoft, defender, atp, android, cloud, connectivity, communication
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 444541c85f8f4416288dcebf4bbee2c65a33d3d2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164874"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="7b3c4-104">Solución de problemas en Microsoft Defender para Endpoint para Android</span><span class="sxs-lookup"><span data-stu-id="7b3c4-104">Troubleshooting issues on Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7b3c4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7b3c4-105">**Applies to:**</span></span>
- [<span data-ttu-id="7b3c4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7b3c4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7b3c4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b3c4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7b3c4-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="7b3c4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7b3c4-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="7b3c4-110">Al incorporar un dispositivo, es posible que veas problemas de inicio de sesión después de instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="7b3c4-111">Durante la incorporación, es posible que encuentres problemas de inicio de sesión después de instalar la aplicación en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="7b3c4-112">En este artículo se proporcionan soluciones para ayudar a solucionar los problemas de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="7b3c4-113">Error de inicio de sesión: error inesperado</span><span class="sxs-lookup"><span data-stu-id="7b3c4-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="7b3c4-114">**Error de inicio de sesión:** *error inesperado, inténtelo más tarde*</span><span class="sxs-lookup"><span data-stu-id="7b3c4-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Imagen del error de inicio de sesión Error inesperado](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="7b3c4-116">**Mensaje:**</span><span class="sxs-lookup"><span data-stu-id="7b3c4-116">**Message:**</span></span>

<span data-ttu-id="7b3c4-117">Error inesperado, inténtelo más tarde</span><span class="sxs-lookup"><span data-stu-id="7b3c4-117">Unexpected error, try later</span></span>

<span data-ttu-id="7b3c4-118">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="7b3c4-118">**Cause:**</span></span>

<span data-ttu-id="7b3c4-119">Tienes instalada una versión anterior de la aplicación "Microsoft Authenticator" en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="7b3c4-120">**Solución:**</span><span class="sxs-lookup"><span data-stu-id="7b3c4-120">**Solution:**</span></span>

<span data-ttu-id="7b3c4-121">Instalar la versión más reciente y [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) de Google Play Store e intentarlo de nuevo</span><span class="sxs-lookup"><span data-stu-id="7b3c4-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="7b3c4-122">Error al iniciar sesión: licencia no válida</span><span class="sxs-lookup"><span data-stu-id="7b3c4-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="7b3c4-123">**Error al iniciar sesión: licencia** *no válida, póngase en contacto con el administrador*</span><span class="sxs-lookup"><span data-stu-id="7b3c4-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Imagen del error de inicio de sesión póngase en contacto con el administrador](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="7b3c4-125">**Mensaje: Licencia** *no válida, póngase en contacto con el administrador*</span><span class="sxs-lookup"><span data-stu-id="7b3c4-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="7b3c4-126">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="7b3c4-126">**Cause:**</span></span>

<span data-ttu-id="7b3c4-127">No tiene asignada la licencia de Microsoft 365 o su organización no tiene una licencia para la suscripción a Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="7b3c4-128">**Solución:**</span><span class="sxs-lookup"><span data-stu-id="7b3c4-128">**Solution:**</span></span>

<span data-ttu-id="7b3c4-129">Póngase en contacto con el administrador para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-129">Contact your administrator for help.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="7b3c4-130">Las páginas de suplantación de identidad no están bloqueadas en algunos dispositivos OEM</span><span class="sxs-lookup"><span data-stu-id="7b3c4-130">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="7b3c4-131">**Se aplica a:** Oem específicos solo</span><span class="sxs-lookup"><span data-stu-id="7b3c4-131">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="7b3c4-132">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="7b3c4-132">**Xiaomi**</span></span>

<span data-ttu-id="7b3c4-133">El phishing y las amenazas web nocivas detectadas por Defender para Endpoint para Android no se bloquean en algunos dispositivos Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-133">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="7b3c4-134">La siguiente funcionalidad no funciona en estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-134">The following functionality doesn't work on these devices.</span></span>

![Imagen del sitio notificado no seguro](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="7b3c4-136">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="7b3c4-136">**Cause:**</span></span>

<span data-ttu-id="7b3c4-137">Los dispositivos Xiaomi incluyen un nuevo modelo de permisos.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-137">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="7b3c4-138">Esto impide que Defender para Endpoint para Android muestre ventanas emergentes mientras se ejecuta en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-138">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="7b3c4-139">Permiso de dispositivos Xiaomi: "Mostrar ventanas emergentes mientras se ejecuta en segundo plano".</span><span class="sxs-lookup"><span data-stu-id="7b3c4-139">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Imagen de configuración emergente](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="7b3c4-141">**Solución:**</span><span class="sxs-lookup"><span data-stu-id="7b3c4-141">**Solution:**</span></span>

<span data-ttu-id="7b3c4-142">Habilite el permiso necesario en dispositivos Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-142">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="7b3c4-143">Mostrar ventanas emergentes mientras se ejecuta en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="7b3c4-143">Display pop-up windows while running in the background.</span></span>
