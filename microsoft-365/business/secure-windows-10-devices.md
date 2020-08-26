---
title: Proteger dispositivos con Windows 10
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Obtenga información sobre cómo configurar las opciones de la Directiva de dispositivo predeterminada que recibirá cualquier dispositivo Windows 10 al iniciar sesión en su cuenta profesional o educativa.
ms.openlocfilehash: b586e687d6b61873b77fac8586396ab51fd90b9b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898076"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="36fec-103">Proteger dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="36fec-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="36fec-104">Este artículo se aplica a Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="36fec-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="36fec-105">Las opciones que configure aquí forman parte de la directiva de dispositivo predeterminada para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="36fec-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="36fec-106">Todos los usuarios que se conecten a un dispositivo de Windows 10, incluidos los dispositivos móviles y los equipos, al iniciar sesión con su cuenta profesional recibirán esta configuración automáticamente.</span><span class="sxs-lookup"><span data-stu-id="36fec-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="36fec-107">Recomendamos que acepte la directiva predeterminada durante la configuración y que, posteriormente, agregue directivas para grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="36fec-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="36fec-108">Configuración para proteger dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="36fec-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="36fec-p102">De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles:</span><span class="sxs-lookup"><span data-stu-id="36fec-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="36fec-111">Configuración</span><span class="sxs-lookup"><span data-stu-id="36fec-111">Setting</span></span>  <br/> |<span data-ttu-id="36fec-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="36fec-112">Description</span></span>  <br/> |
|<span data-ttu-id="36fec-113">Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender</span><span class="sxs-lookup"><span data-stu-id="36fec-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="36fec-114">Es necesario que el antivirus Windows Defender esté activado para proteger los equipos PC de los peligros de estar conectados a Internet.</span><span class="sxs-lookup"><span data-stu-id="36fec-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="36fec-115">Proteger los equipos PC de amenazas basadas en web en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36fec-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="36fec-116">Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.</span><span class="sxs-lookup"><span data-stu-id="36fec-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="36fec-117">Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo</span><span class="sxs-lookup"><span data-stu-id="36fec-117">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="36fec-p103">Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.</span><span class="sxs-lookup"><span data-stu-id="36fec-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="36fec-121">Permitir a los usuarios descargar aplicaciones desde la Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="36fec-121">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="36fec-p104">Permite a los usuarios descargar e instalar aplicaciones desde la Microsoft Store. Las aplicaciones pueden ser de cualquier tipo, desde juegos hasta herramientas de productividad, por lo que dejamos esta configuración **activada**, pero puede desactivarla para obtener una capa de seguridad adicional.  </span><span class="sxs-lookup"><span data-stu-id="36fec-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|