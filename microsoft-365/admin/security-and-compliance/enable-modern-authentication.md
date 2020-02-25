---
title: Habilitar autenticación moderna para Office 2013 en dispositivos Windows
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Obtenga información sobre cómo configurar las claves del registro para habilitar la autenticación moderna para dispositivos que tienen instalado Microsoft Office 2013.
ms.openlocfilehash: f1264affa5be93b19e564a0edea00bfb78f452f1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248004"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="168ed-103">Habilitar autenticación moderna para Office 2013 en dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="168ed-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="168ed-104">Para habilitar la autenticación moderna para los dispositivos con Windows que tienen Office 2013 instalado, debe configurar claves del registro específicas.</span><span class="sxs-lookup"><span data-stu-id="168ed-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="168ed-105">Habilitar la autenticación moderna para los clientes de Office 2013</span><span class="sxs-lookup"><span data-stu-id="168ed-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="168ed-106">La autenticación moderna ya está habilitada para los clientes de Office 2016, no necesita configurar claves del registro para Office 2016.</span><span class="sxs-lookup"><span data-stu-id="168ed-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="168ed-p101">Para habilitar la autenticación moderna para cualquier dispositivo con Windows (por ejemplo, en portátiles y tabletas), que tienen Microsoft Office 2013 instalado, debe configurar las siguientes claves del registro. Las claves se tienen que establecer en cada dispositivo en el que quiera habilitar la autenticación moderna:</span><span class="sxs-lookup"><span data-stu-id="168ed-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="168ed-109">**Clave del registro**</span><span class="sxs-lookup"><span data-stu-id="168ed-109">**Registry key**</span></span>|<span data-ttu-id="168ed-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="168ed-110">**Type**</span></span>|<span data-ttu-id="168ed-111">**Valor**</span><span class="sxs-lookup"><span data-stu-id="168ed-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="168ed-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="168ed-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="168ed-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="168ed-113">REG_DWORD</span></span>  |<span data-ttu-id="168ed-114">1</span><span class="sxs-lookup"><span data-stu-id="168ed-114">1</span></span>  |
|<span data-ttu-id="168ed-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="168ed-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="168ed-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="168ed-116">REG_DWORD</span></span> |<span data-ttu-id="168ed-117">1</span><span class="sxs-lookup"><span data-stu-id="168ed-117">1</span></span> |
   
<span data-ttu-id="168ed-118">Cuando haya establecido las claves del registro, puede configurar las aplicaciones para dispositivo de Office 2013 para que usen la [autenticación multifactor (MFA)](set-up-multi-factor-authentication.md) con Office 365</span><span class="sxs-lookup"><span data-stu-id="168ed-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Office 365</span></span> 
  
<span data-ttu-id="168ed-p102">Si ha iniciado sesión actualmente con cualquiera de las aplicaciones de cliente, tendrá que cerrar sesión y volver a iniciarla para que el cambio surta efecto. En caso contrario, la configuración usada recientemente y de itinerancia no estará disponible hasta que se establezca la identidad ADAL.</span><span class="sxs-lookup"><span data-stu-id="168ed-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="168ed-121">Deshabilitar la autenticación moderna en los dispositivos</span><span class="sxs-lookup"><span data-stu-id="168ed-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="168ed-122">Para deshabilitar la autenticación moderna en un dispositivo, establezca las siguientes claves del registro en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="168ed-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="168ed-123">**Clave del registro**</span><span class="sxs-lookup"><span data-stu-id="168ed-123">**Registry key**</span></span>|<span data-ttu-id="168ed-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="168ed-124">**Type**</span></span>|<span data-ttu-id="168ed-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="168ed-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="168ed-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="168ed-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="168ed-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="168ed-127">REG_DWORD</span></span>|<span data-ttu-id="168ed-128">comprendi</span><span class="sxs-lookup"><span data-stu-id="168ed-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="168ed-129">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="168ed-129">Related articles</span></span>
[<span data-ttu-id="168ed-130">Inicie sesión en Office 2013 con un segundo método de verificación</span><span class="sxs-lookup"><span data-stu-id="168ed-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)

  

