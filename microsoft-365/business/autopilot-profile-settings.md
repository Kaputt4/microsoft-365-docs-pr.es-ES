---
title: Información sobre la configuración de los perfiles de AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
description: Los perfiles de autoPilot le ayudan a controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen opciones de configuración predeterminadas y opcionales, como omitir la instalación de Cortana.
ms.openlocfilehash: d43a15e5f3dc83596b5c23dd0ceb416b24810298
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276949"
---
# <a name="about-autopilot-profile-settings"></a>Información sobre la configuración de los perfiles de AutoPilot

## <a name="autopilot-profile-settings"></a>Configuración del perfil de autoPilot

Puede controlar cómo se instala Windows en los dispositivos de usuario mediante el uso de los perfiles de piloto automático. Los perfiles contienen la siguiente configuración.
  
 **Las características predeterminadas de autoPilot (necesarias) que se establecen automáticamente:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir Cortana, registro de OneDrive y OEM  <br/> |Omite la instalación de aplicaciones para consumidores, como Cortana y OneDrive personal. El usuario del dispositivo puede instalarlos más adelante, siempre que sea administrador local en el dispositivo. Se omite el registro original del fabricante porque el dispositivo se administrará con Microsoft 365 Business.  <br/> |
|Experiencia de inicio de sesión con la marca de la compañía  <br/> |Si su compañía tiene una [página Agregar la personalización de marca de la compañía a Office 365](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), el usuario del dispositivo obtendrá esa experiencia al iniciar sesión.  <br/> |
|Inscripción automática MDM con cuentas de AAD configuradas.  <br/> |Azure Active Directory administrará la identidad del usuario y los usuarios iniciarán sesión en Windows y Office 365 con sus credenciales de empresa de Microsoft 365.  <br/> |
   
 **Configuración opcional:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir la configuración de privacidad (desHabilitada de forma predeterminada)  <br/> |Si esta opción se establece **en activado**, el usuario del dispositivo no verá el contrato de licencia para el dispositivo y Windows cuando inicie sesión por primera vez.  <br/> |
|No permitir que el usuario se convierta en el administrador local  <br/> |Si esta opción se establece **en activado**, el usuario del dispositivo no podrá instalar ninguna aplicación personal, como Cortana.  <br/> |
   
