---
title: Proteger dispositivos con Windows 10
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 'Obtenga información sobre predeterminada y otras opciones de configuración para proteger los dispositivos de Windows 10. '
ms.openlocfilehash: 0bdf6a56d880cb84f4a4f50550539d97c006ba49
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871717"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="4d9ab-103">Proteger dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="4d9ab-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="4d9ab-p101">Las opciones que configure aquí forman parte de la directiva de dispositivo predeterminada para Windows 10. Todos los usuarios que se conecten a un dispositivo con Windows 10, incluidos dispositivos móviles y equipos PC, recibirán automáticamente esta configuración al iniciar sesión con su cuenta profesional. Recomendamos que acepte la directiva predeterminada durante la configuración y que, posteriormente, agregue directivas para grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="4d9ab-107">Configuración para proteger dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="4d9ab-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="4d9ab-p102">De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles:</span><span class="sxs-lookup"><span data-stu-id="4d9ab-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4d9ab-110">Configuración</span><span class="sxs-lookup"><span data-stu-id="4d9ab-110">Setting</span></span>  <br/> |<span data-ttu-id="4d9ab-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d9ab-111">Description</span></span>  <br/> |
|<span data-ttu-id="4d9ab-112">Ayudar a proteger los equipos PC de los virus y otras amenazas con Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="4d9ab-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="4d9ab-113">Requiere que Antivirus de Windows Defender esté activado para proteger los equipos de los riesgos de estar conectado a Internet.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="4d9ab-114">Ayudar a proteger los equipos PC de amenazas basadas en web en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4d9ab-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="4d9ab-115">Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="4d9ab-116">Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo</span><span class="sxs-lookup"><span data-stu-id="4d9ab-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="4d9ab-p103">Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="4d9ab-120">Permitir a los usuarios descargar aplicaciones desde la Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="4d9ab-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="4d9ab-p104">Permite a los usuarios descargar e instalar aplicaciones desde la Microsoft Store. Las aplicaciones pueden ser de cualquier tipo, desde juegos hasta herramientas de productividad, por lo que dejamos esta configuración **activada**, pero puede desactivarla para obtener una capa de seguridad adicional.  </span><span class="sxs-lookup"><span data-stu-id="4d9ab-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="4d9ab-123">Permitir a los usuarios acceder a Cortana</span><span class="sxs-lookup"><span data-stu-id="4d9ab-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="4d9ab-p105">Cortana puede ser muy útil. Permite activar o desactivar opciones automáticamente, ofrece indicaciones y se asegura de que llegue a tiempo a las citas, por lo que mantenemos **activada** esta opción de forma predeterminada.  </span><span class="sxs-lookup"><span data-stu-id="4d9ab-p105">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="4d9ab-126">Permitir a los usuarios recibir sugerencias de Windows y anuncios de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4d9ab-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="4d9ab-127">Las sugerencias de Windows pueden ser útiles y orientar a los usuarios cuando se publiquen nuevas características.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="4d9ab-128">Mantener actualizados automáticamente los dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="4d9ab-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="4d9ab-129">Garantiza que los dispositivos con Windows 10 reciban automáticamente las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

