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
description: Los perfiles de AutoPilot le ayudan a controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen opciones de configuración predeterminadas y opcionales, como omitir la instalación de Cortana.
ms.openlocfilehash: 100de5e9548f901008d3ae154ac5a237ef265ffb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401042"
---
# <a name="about-autopilot-profile-settings"></a>Información sobre la configuración de los perfiles de AutoPilot

## <a name="autopilot-profile-settings"></a>Configuración del perfil de AutoPilot

Puede usar los perfiles de AutoPilot para controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen la siguiente configuración.
  
 **Las características predeterminadas de AutoPilot (necesarias) que se establecen automáticamente:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir Cortana, OneDrive y registro de OEM  <br/> |Omite la instalación de aplicaciones para consumidores, como Cortana y OneDrive personal. El usuario del dispositivo puede instalarlos más adelante, siempre que el usuario sea un administrador local en el dispositivo. Se omite el registro original del fabricante porque el dispositivo se administrará con Microsoft 365 Business Premium.  <br/> |
|Experiencia de inicio de sesión con la marca de la compañía  <br/> |Si su compañía tiene una [Página de inicio de sesión agregar la personalización de marca de la compañía a Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), el usuario del dispositivo obtendrá esa experiencia al iniciar sesión.  <br/> |
|Inscripción automática MDM con cuentas de AAD configuradas.  <br/> |La identidad de usuario será administrada por Azure Active Directory y los usuarios iniciarán sesión en Windows y Microsoft 365 con sus credenciales de Microsoft 365 Business Premium.  <br/> |
   
 **Configuración opcional:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir la configuración de privacidad (deshabilitada de forma predeterminada)  <br/> |Si esta opción se establece **en activado**, el usuario del dispositivo no verá el contrato de licencia para el dispositivo y Windows cuando inicie sesión por primera vez.  <br/> |
|No permitir que el usuario se convierta en el administrador local  <br/> |Si esta opción se establece **en activado**, el usuario del dispositivo no podrá instalar ninguna aplicación personal, como Cortana.<br/> |
   
