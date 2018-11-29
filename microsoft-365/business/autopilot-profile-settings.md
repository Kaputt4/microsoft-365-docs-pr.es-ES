---
title: Información sobre la configuración de los perfiles de AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Perfiles de piloto automático le ayudarán a controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen predeterminada y valores de configuración opcionales como omitir la instalación de Cortana.
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871185"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="8d67e-104">Información sobre la configuración de los perfiles de AutoPilot</span><span class="sxs-lookup"><span data-stu-id="8d67e-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="8d67e-105">Configuración del perfil de piloto automático</span><span class="sxs-lookup"><span data-stu-id="8d67e-105">AutoPilot profile settings</span></span>

<span data-ttu-id="8d67e-p102">Puede controlar cómo se instala Windows en los dispositivos de usuario mediante el uso de los perfiles de piloto automático. Los perfiles contienen los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="8d67e-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="8d67e-108">**Piloto automático características predeterminadas de (obligatorio) que se establecen automáticamente:**</span><span class="sxs-lookup"><span data-stu-id="8d67e-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="8d67e-109">**Valor**</span><span class="sxs-lookup"><span data-stu-id="8d67e-109">**Setting**</span></span>|<span data-ttu-id="8d67e-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8d67e-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8d67e-111">Omitir el registro OEM, OneDrive y Cortana</span><span class="sxs-lookup"><span data-stu-id="8d67e-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="8d67e-p103">Omite la instalación de aplicaciones de consumidor como Cortana y OneDrive personal. El usuario del dispositivo puede instalar más adelante, siempre y cuando éste sea un administrador local en el dispositivo. Debido a que el dispositivo estará administrado por Microsoft 365 empresarial, se omite el registro del fabricante original.</span><span class="sxs-lookup"><span data-stu-id="8d67e-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="8d67e-115">Inicie sesión en la experiencia con la marca de su empresa</span><span class="sxs-lookup"><span data-stu-id="8d67e-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="8d67e-116">Si su compañía tiene una [personalización de marca de agregar su compañía a Office 365 inicio de sesión en la página](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), el usuario del dispositivo obtendrá esa experiencia al iniciar la sesión.</span><span class="sxs-lookup"><span data-stu-id="8d67e-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="8d67e-117">MDM la inscripción automática con cuentas AAD configuradas.</span><span class="sxs-lookup"><span data-stu-id="8d67e-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="8d67e-118">La identidad del usuario estará administrada por Azure Active directory y los usuarios va a iniciar sesión en Windows y Office 365 con sus credenciales de Microsoft 365 empresarial.</span><span class="sxs-lookup"><span data-stu-id="8d67e-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="8d67e-119">**Configuración opcional:**</span><span class="sxs-lookup"><span data-stu-id="8d67e-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="8d67e-120">**Valor**</span><span class="sxs-lookup"><span data-stu-id="8d67e-120">**Setting**</span></span>|<span data-ttu-id="8d67e-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8d67e-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8d67e-122">Omitir la configuración de privacidad (desactivada de forma predeterminada)</span><span class="sxs-lookup"><span data-stu-id="8d67e-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="8d67e-123">Si esta opción está establecida en **On**, el usuario del dispositivo no verá el contrato de licencia para el dispositivo y Windows cuando navegará primero inicia sesión en.</span><span class="sxs-lookup"><span data-stu-id="8d67e-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="8d67e-124">No permitir que el usuario se convierta en el administrador local</span><span class="sxs-lookup"><span data-stu-id="8d67e-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="8d67e-125">Si esta opción está establecida en **On**, el usuario del dispositivo no podrá instalar aplicaciones de personal, por ejemplo, Cortana.</span><span class="sxs-lookup"><span data-stu-id="8d67e-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
