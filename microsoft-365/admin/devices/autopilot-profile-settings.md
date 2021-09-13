---
title: Información sobre la configuración de los perfiles de AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Los perfiles de AutoPilot te ayudan a controlar Windows se instala en dispositivos de usuario. Los perfiles contienen configuraciones predeterminadas y opcionales, como omitir Cortana instalación.
ms.openlocfilehash: 9d425e73a5cedf51ce8267afa9505cbde8b97038
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184910"
---
# <a name="about-autopilot-profile-settings"></a>Información sobre la configuración de los perfiles de AutoPilot

## <a name="autopilot-profile-settings"></a>Configuración del perfil de AutoPilot

Puedes usar perfiles de AutoPilot para controlar cómo se Windows en dispositivos de usuario. Los perfiles contienen la siguiente configuración.
  
 **Características predeterminadas de AutoPilot (necesarias) que se establecen automáticamente:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir Cortana, OneDrive y registro OEM  <br/> |Omite la instalación de aplicaciones de consumidor como Cortana y personal OneDrive. El usuario del dispositivo puede instalar estos más adelante siempre que el usuario sea un administrador local en el dispositivo. El registro del fabricante original se omite porque el dispositivo se administrará Microsoft 365 Empresa Premium.  <br/> |
|Experiencia de inicio de sesión con la marca de su empresa  <br/> |Si tu empresa tiene una página Agregar la marca de tu empresa [Microsoft 365](../setup/customize-sign-in-page.md)inicio de sesión, el usuario del dispositivo tendrá esa experiencia al iniciar sesión.  <br/> |
|Inscripción automática de MDM con cuentas de AAD configuradas.  <br/> |La identidad de usuario la administrará Azure Active Directory y los usuarios iniciarán sesión en Windows y Microsoft 365 con sus Microsoft 365 Empresa Premium credenciales.  <br/> |
   
 **Configuración opcional:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir la configuración de privacidad (desactivado de forma predeterminada)  <br/> |Si esta opción está establecida en **On**, el usuario del dispositivo no verá el contrato de licencia para el dispositivo y se Windows la primera vez que inicia sesión.  <br/> |
|No permitir que el usuario se convierta en el administrador local  <br/> |Si esta opción está establecida en **On**, el usuario del dispositivo no podrá instalar ninguna aplicación personal, como Cortana.<br/> |
