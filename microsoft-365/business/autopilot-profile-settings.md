---
title: Información sobre la configuración de los perfiles de AutoPilot
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Los perfiles de AutoPilot le ayudan a controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen opciones de configuración predeterminadas y opcionales, como omitir la instalación de Cortana.
ms.openlocfilehash: adc8112861b67fd96a91ff24dc155aeb0c394532
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071868"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="5d618-104">Información sobre la configuración de los perfiles de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="5d618-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="5d618-105">Configuración del perfil de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="5d618-105">AutoPilot profile settings</span></span>

<span data-ttu-id="5d618-106">Puede controlar cómo se instala Windows en los dispositivos de usuario mediante el uso de los perfiles de piloto automático.</span><span class="sxs-lookup"><span data-stu-id="5d618-106">You can control how Windows gets installed on user devices by using the AutoPilot profiles.</span></span> <span data-ttu-id="5d618-107">Los perfiles contienen la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="5d618-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="5d618-108">**Las características predeterminadas de AutoPilot (necesarias) que se establecen automáticamente:**</span><span class="sxs-lookup"><span data-stu-id="5d618-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="5d618-109">**Valor**</span><span class="sxs-lookup"><span data-stu-id="5d618-109">**Setting**</span></span>|<span data-ttu-id="5d618-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5d618-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5d618-111">Omitir Cortana, registro de OneDrive y OEM</span><span class="sxs-lookup"><span data-stu-id="5d618-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="5d618-112">Omite la instalación de aplicaciones para consumidores, como Cortana y OneDrive personal.</span><span class="sxs-lookup"><span data-stu-id="5d618-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="5d618-113">El usuario del dispositivo puede instalarlos más adelante, siempre que sea administrador local en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d618-113">The device user can install these later as long as he or she is a local admin on the device.</span></span> <span data-ttu-id="5d618-114">Se omite el registro original del fabricante porque el dispositivo se administrará con Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="5d618-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="5d618-115">Experiencia de inicio de sesión con la marca de la compañía</span><span class="sxs-lookup"><span data-stu-id="5d618-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="5d618-116">Si su compañía tiene una [página Agregar la personalización de marca de la compañía a Office 365](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), el usuario del dispositivo obtendrá esa experiencia al iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="5d618-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="5d618-117">Inscripción automática MDM con cuentas de AAD configuradas.</span><span class="sxs-lookup"><span data-stu-id="5d618-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="5d618-118">Azure Active Directory administrará la identidad del usuario y los usuarios iniciarán sesión en Windows y Office 365 con sus credenciales de empresa de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5d618-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="5d618-119">**Configuración opcional:**</span><span class="sxs-lookup"><span data-stu-id="5d618-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="5d618-120">**Valor**</span><span class="sxs-lookup"><span data-stu-id="5d618-120">**Setting**</span></span>|<span data-ttu-id="5d618-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5d618-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5d618-122">Omitir la configuración de privacidad (deshabilitada de forma predeterminada)</span><span class="sxs-lookup"><span data-stu-id="5d618-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="5d618-123">Si esta opción se establece **en activado**, el usuario del dispositivo no verá el contrato de licencia para el dispositivo y Windows cuando inicie sesión por primera vez.</span><span class="sxs-lookup"><span data-stu-id="5d618-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="5d618-124">No permitir que el usuario se convierta en el administrador local</span><span class="sxs-lookup"><span data-stu-id="5d618-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="5d618-125">Si esta opción se establece **en activado**, el usuario del dispositivo no podrá instalar ninguna aplicación personal, como Cortana.</span><span class="sxs-lookup"><span data-stu-id="5d618-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
