---
title: Información sobre la configuración de los perfiles de AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Los perfiles de AutoPilot le ayudan a controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen opciones de configuración predeterminadas y opcionales, como omitir la instalación de Cortana.
ms.openlocfilehash: 0c706d12ba262856ff40ea3bee57c64234fd77f7
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165849"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="bc1d2-104">Información sobre la configuración de los perfiles de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="bc1d2-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="bc1d2-105">Configuración del perfil de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="bc1d2-105">AutoPilot profile settings</span></span>

<span data-ttu-id="bc1d2-106">Puede usar los perfiles de AutoPilot para controlar cómo se instala Windows en los dispositivos de usuario.</span><span class="sxs-lookup"><span data-stu-id="bc1d2-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="bc1d2-107">Los perfiles contienen la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="bc1d2-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="bc1d2-108">**Las características predeterminadas de AutoPilot (necesarias) que se establecen automáticamente:**</span><span class="sxs-lookup"><span data-stu-id="bc1d2-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="bc1d2-109">**Valor**</span><span class="sxs-lookup"><span data-stu-id="bc1d2-109">**Setting**</span></span>|<span data-ttu-id="bc1d2-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bc1d2-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bc1d2-111">Omitir Cortana, OneDrive y registro de OEM</span><span class="sxs-lookup"><span data-stu-id="bc1d2-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="bc1d2-112">Omite la instalación de aplicaciones para consumidores, como Cortana y OneDrive personal.</span><span class="sxs-lookup"><span data-stu-id="bc1d2-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="bc1d2-113">El usuario del dispositivo puede instalarlos más adelante, siempre que el usuario sea un administrador local en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bc1d2-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="bc1d2-114">Se omite el registro original del fabricante porque el dispositivo se administrará con Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="bc1d2-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="bc1d2-115">Experiencia de inicio de sesión con la marca de la compañía</span><span class="sxs-lookup"><span data-stu-id="bc1d2-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="bc1d2-116">Si su compañía tiene una [Página de inicio de sesión agregar la personalización de marca de la compañía a Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), el usuario del dispositivo obtendrá esa experiencia al iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="bc1d2-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="bc1d2-117">Inscripción automática MDM con cuentas de AAD configuradas.</span><span class="sxs-lookup"><span data-stu-id="bc1d2-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="bc1d2-118">La identidad de usuario será administrada por Azure Active Directory y los usuarios iniciarán sesión en Windows y Microsoft 365 con sus credenciales de Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="bc1d2-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="bc1d2-119">**Configuración opcional:**</span><span class="sxs-lookup"><span data-stu-id="bc1d2-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="bc1d2-120">**Valor**</span><span class="sxs-lookup"><span data-stu-id="bc1d2-120">**Setting**</span></span>|<span data-ttu-id="bc1d2-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bc1d2-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bc1d2-122">Omitir la configuración de privacidad (deshabilitada de forma predeterminada)</span><span class="sxs-lookup"><span data-stu-id="bc1d2-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="bc1d2-123">Si esta opción se establece **en activado**, el usuario del dispositivo no verá el contrato de licencia para el dispositivo y Windows cuando inicie sesión por primera vez.</span><span class="sxs-lookup"><span data-stu-id="bc1d2-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="bc1d2-124">No permitir que el usuario se convierta en el administrador local</span><span class="sxs-lookup"><span data-stu-id="bc1d2-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="bc1d2-125">Si esta opción se establece **en activado**, el usuario del dispositivo no podrá instalar ninguna aplicación personal, como Cortana.</span><span class="sxs-lookup"><span data-stu-id="bc1d2-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
