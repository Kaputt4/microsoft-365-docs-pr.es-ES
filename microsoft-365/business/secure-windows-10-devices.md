---
title: Proteger dispositivos con Windows 10
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
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
description: Obtén información sobre cómo configurar la configuración de la directiva de dispositivo predeterminada que cualquier dispositivo Windows 10 recibirá al iniciar sesión en su cuenta laboral o educativa.
ms.openlocfilehash: 3f85549e722c9aa4196cf50fc02bee2e89506017
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925247"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="34ffe-103">Proteger dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="34ffe-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="34ffe-104">Este artículo se aplica a Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="34ffe-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="34ffe-105">Las opciones que configure aquí forman parte de la directiva de dispositivo predeterminada para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="34ffe-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="34ffe-106">Todos los usuarios que conecten un Windows 10, incluidos los dispositivos móviles y los equipos, al iniciar sesión con su cuenta de trabajo recibirán automáticamente esta configuración.</span><span class="sxs-lookup"><span data-stu-id="34ffe-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="34ffe-107">Recomendamos que acepte la directiva predeterminada durante la configuración y que, posteriormente, agregue directivas para grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="34ffe-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="34ffe-108">Configuración para proteger dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="34ffe-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="34ffe-p102">De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles:</span><span class="sxs-lookup"><span data-stu-id="34ffe-p102">By default all settings are **On**. The following settings are available:</span></span>
  


|<span data-ttu-id="34ffe-111">Configuración</span><span class="sxs-lookup"><span data-stu-id="34ffe-111">Setting</span></span>  <br/> |<span data-ttu-id="34ffe-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="34ffe-112">Description</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="34ffe-113">Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender</span><span class="sxs-lookup"><span data-stu-id="34ffe-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="34ffe-114">Es necesario que el antivirus Windows Defender esté activado para proteger los equipos PC de los peligros de estar conectados a Internet.</span><span class="sxs-lookup"><span data-stu-id="34ffe-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="34ffe-115">Proteger los equipos PC de amenazas basadas en web en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="34ffe-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="34ffe-116">Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.</span><span class="sxs-lookup"><span data-stu-id="34ffe-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="34ffe-117">Ayudar a proteger archivos y carpetas en equipos PC ante el acceso no autorizado con BitLocker</span><span class="sxs-lookup"><span data-stu-id="34ffe-117">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="34ffe-118">BitLocker protege los datos al cifrar los discos duros del equipo y proteger ante la exposición de datos en caso del robo o pérdida de un equipo.</span><span class="sxs-lookup"><span data-stu-id="34ffe-118">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="34ffe-119">Para obtener más información, consulta [Preguntas más frecuentes de Bitlocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="34ffe-119">For more information, see [Bitlocker FAQ](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).</span></span>  <br/> |
|<span data-ttu-id="34ffe-120">Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo</span><span class="sxs-lookup"><span data-stu-id="34ffe-120">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="34ffe-p104">Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.</span><span class="sxs-lookup"><span data-stu-id="34ffe-p104">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|