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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Los perfiles de AutoPilot te ayudan a controlar cómo se instala Windows en los dispositivos del usuario. Los perfiles contienen la configuración predeterminada y opcional, como omitir la instalación de Cortana.
ms.openlocfilehash: 100de5e9548f901008d3ae154ac5a237ef265ffb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401042"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="a28c2-104">Información sobre la configuración de los perfiles de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="a28c2-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="a28c2-105">Configuración de perfil de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="a28c2-105">AutoPilot profile settings</span></span>

<span data-ttu-id="a28c2-106">Puedes usar perfiles de AutoPilot para controlar cómo se instala Windows en los dispositivos de usuario.</span><span class="sxs-lookup"><span data-stu-id="a28c2-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="a28c2-107">Los perfiles contienen la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="a28c2-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="a28c2-108">**Características predeterminadas de AutoPilot (necesarias) que se establecen automáticamente:**</span><span class="sxs-lookup"><span data-stu-id="a28c2-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="a28c2-109">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a28c2-109">**Setting**</span></span>|<span data-ttu-id="a28c2-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a28c2-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a28c2-111">Omitir el registro de Cortana, OneDrive y OEM</span><span class="sxs-lookup"><span data-stu-id="a28c2-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="a28c2-112">Omite la instalación de aplicaciones de consumidor como Cortana y OneDrive personal.</span><span class="sxs-lookup"><span data-stu-id="a28c2-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="a28c2-113">El usuario del dispositivo puede instalar estos más adelante siempre que el usuario sea un administrador local en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a28c2-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="a28c2-114">Se omite el registro original del fabricante porque Microsoft 365 Empresa Premium administrará el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a28c2-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="a28c2-115">Experiencia de inicio de sesión con la marca de su empresa</span><span class="sxs-lookup"><span data-stu-id="a28c2-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="a28c2-116">Si su empresa tiene una página Agregar la marca de su empresa a la página de inicio de sesión de [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page)el usuario del dispositivo recibirá esa experiencia al iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="a28c2-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="a28c2-117">Inscripción automática de MDM con cuentas de AAD configuradas.</span><span class="sxs-lookup"><span data-stu-id="a28c2-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="a28c2-118">Azure Active Directory administrará la identidad del usuario y los usuarios iniciarán sesión en Windows y Microsoft 365 con sus credenciales de Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="a28c2-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="a28c2-119">**Configuración opcional:**</span><span class="sxs-lookup"><span data-stu-id="a28c2-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="a28c2-120">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a28c2-120">**Setting**</span></span>|<span data-ttu-id="a28c2-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a28c2-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a28c2-122">Omitir la configuración de privacidad (desactivada de forma predeterminada)</span><span class="sxs-lookup"><span data-stu-id="a28c2-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="a28c2-123">Si esta opción está establecida en **On,** el usuario del dispositivo no verá el contrato de licencia para el dispositivo y Windows cuando inicia sesión por primera vez.</span><span class="sxs-lookup"><span data-stu-id="a28c2-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="a28c2-124">No permitir que el usuario se convierta en el administrador local</span><span class="sxs-lookup"><span data-stu-id="a28c2-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="a28c2-125">Si esta opción está establecida en **On,** el usuario del dispositivo no podrá instalar ninguna aplicación personal, como Cortana.</span><span class="sxs-lookup"><span data-stu-id="a28c2-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
