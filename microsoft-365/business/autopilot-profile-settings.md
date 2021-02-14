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
# <a name="about-autopilot-profile-settings"></a>Información sobre la configuración de los perfiles de AutoPilot

## <a name="autopilot-profile-settings"></a>Configuración de perfil de AutoPilot

Puedes usar perfiles de AutoPilot para controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen la siguiente configuración.
  
 **Características predeterminadas de AutoPilot (necesarias) que se establecen automáticamente:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir el registro de Cortana, OneDrive y OEM  <br/> |Omite la instalación de aplicaciones de consumidor como Cortana y OneDrive personal. El usuario del dispositivo puede instalar estos más adelante siempre que el usuario sea un administrador local en el dispositivo. Se omite el registro original del fabricante porque Microsoft 365 Empresa Premium administrará el dispositivo.  <br/> |
|Experiencia de inicio de sesión con la marca de su empresa  <br/> |Si su empresa tiene una página Agregar la marca de su empresa a la página de inicio de sesión de [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page)el usuario del dispositivo recibirá esa experiencia al iniciar sesión.  <br/> |
|Inscripción automática de MDM con cuentas de AAD configuradas.  <br/> |Azure Active Directory administrará la identidad del usuario y los usuarios iniciarán sesión en Windows y Microsoft 365 con sus credenciales de Microsoft 365 Empresa Premium.  <br/> |
   
 **Configuración opcional:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir la configuración de privacidad (desactivada de forma predeterminada)  <br/> |Si esta opción está establecida en **On,** el usuario del dispositivo no verá el contrato de licencia para el dispositivo y Windows cuando inicia sesión por primera vez.  <br/> |
|No permitir que el usuario se convierta en el administrador local  <br/> |Si esta opción está establecida en **On,** el usuario del dispositivo no podrá instalar ninguna aplicación personal, como Cortana.<br/> |
   
