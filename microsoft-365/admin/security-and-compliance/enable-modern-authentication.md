---
title: Habilitar autenticación moderna para Office 2013 en dispositivos Windows
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Aprenda a establecer claves del Registro para habilitar la autenticación moderna para dispositivos que Microsoft Office 2013 instalados.
ms.openlocfilehash: f803cf9a30be63e71ef3c4293d0d1ba5b2355e75
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580839"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="942fd-103">Habilitar autenticación moderna para Office 2013 en dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="942fd-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="942fd-104">Para habilitar la autenticación moderna para los dispositivos con Windows que tienen Office 2013 instalado, debe configurar claves del registro específicas.</span><span class="sxs-lookup"><span data-stu-id="942fd-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="942fd-105">Habilitar la autenticación moderna para los clientes de Office 2013</span><span class="sxs-lookup"><span data-stu-id="942fd-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="942fd-106">La autenticación moderna ya está habilitada para los clientes de Office 2016, no necesita configurar claves del registro para Office 2016.</span><span class="sxs-lookup"><span data-stu-id="942fd-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="942fd-p101">Para habilitar la autenticación moderna para cualquier dispositivo con Windows (por ejemplo, en portátiles y tabletas), que tienen Microsoft Office 2013 instalado, debe configurar las siguientes claves del registro. Las claves se tienen que establecer en cada dispositivo en el que quiera habilitar la autenticación moderna:</span><span class="sxs-lookup"><span data-stu-id="942fd-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="942fd-109">**Clave del registro**</span><span class="sxs-lookup"><span data-stu-id="942fd-109">**Registry key**</span></span>|<span data-ttu-id="942fd-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="942fd-110">**Type**</span></span>|<span data-ttu-id="942fd-111">**Valor**</span><span class="sxs-lookup"><span data-stu-id="942fd-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="942fd-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="942fd-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="942fd-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="942fd-113">REG_DWORD</span></span>  |<span data-ttu-id="942fd-114">1</span><span class="sxs-lookup"><span data-stu-id="942fd-114">1</span></span>  |
|<span data-ttu-id="942fd-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="942fd-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="942fd-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="942fd-116">REG_DWORD</span></span> |<span data-ttu-id="942fd-117">1</span><span class="sxs-lookup"><span data-stu-id="942fd-117">1</span></span> |
   
<span data-ttu-id="942fd-118">Una vez establecidas las claves del Registro, puede establecer aplicaciones de dispositivos de Office 2013 para que usen la autenticación [multifactor (MFA)](set-up-multi-factor-authentication.md) con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="942fd-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="942fd-p102">Si ha iniciado sesión actualmente con cualquiera de las aplicaciones de cliente, tendrá que cerrar sesión y volver a iniciarla para que el cambio surta efecto. En caso contrario, la configuración usada recientemente y de itinerancia no estará disponible hasta que se establezca la identidad ADAL.</span><span class="sxs-lookup"><span data-stu-id="942fd-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="942fd-121">Deshabilitar la autenticación moderna en los dispositivos</span><span class="sxs-lookup"><span data-stu-id="942fd-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="942fd-122">Para deshabilitar la autenticación moderna en un dispositivo, establezca las siguientes claves del registro en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="942fd-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="942fd-123">**Clave del registro**</span><span class="sxs-lookup"><span data-stu-id="942fd-123">**Registry key**</span></span>|<span data-ttu-id="942fd-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="942fd-124">**Type**</span></span>|<span data-ttu-id="942fd-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="942fd-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="942fd-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="942fd-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="942fd-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="942fd-127">REG_DWORD</span></span>|<span data-ttu-id="942fd-128">0</span><span class="sxs-lookup"><span data-stu-id="942fd-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="942fd-129">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="942fd-129">Related articles</span></span>
[<span data-ttu-id="942fd-130">Inicie sesión en Office 2013 con un segundo método de verificación</span><span class="sxs-lookup"><span data-stu-id="942fd-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[<span data-ttu-id="942fd-131">Outlook solicita contraseña y no usa la autenticación moderna para conectarse a Office 365</span><span class="sxs-lookup"><span data-stu-id="942fd-131">Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365</span></span>](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)

