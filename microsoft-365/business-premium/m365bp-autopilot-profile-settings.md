---
title: Información sobre la configuración de los perfiles de Autopilot
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
f1.keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: microsoft-365-business
ms.subservice: business-premium
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection: ''
ms.custom:
- MiniMaven
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Los perfiles de Autopilot le ayudan a controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen opciones predeterminadas y opcionales, como omitir la instalación de Cortana.
ms.openlocfilehash: 52f69c5de63c5c35bb07df27269aa567b5eba442
ms.sourcegitcommit: 651610ca73bfd1d008d97311b59782790df664fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "67612931"
---
# <a name="about-autopilot-profile-settings"></a>Información sobre la configuración de los perfiles de Autopilot

## <a name="autopilot-profile-settings"></a>Configuración de perfiles de Autopilot

Puede usar los perfiles de Autopilot para controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen la siguiente configuración.
  
## <a name="autopilot-default-features-required-that-are-set-automatically"></a>Características predeterminadas de Autopilot (necesarias) que se establecen automáticamente
  
| Configuración | Descripción |
|:-----|:-----|
|Omitir el registro de Cortana, OneDrive y OEM  |Omite la instalación de aplicaciones de consumidor como Cortana y OneDrive personal. El usuario del dispositivo puede instalarlos más adelante siempre y cuando el usuario sea un administrador local en el dispositivo. Se omite el registro del fabricante original porque el dispositivo se administrará mediante Microsoft 365 Empresa Premium.  |
|Experiencia de inicio de sesión con su marca de empresa  |Si su empresa tiene un [Agregue la marca de su empresa a la página de inicio de sesión de Microsoft 365](../admin/setup/customize-sign-in-page.md), el usuario del dispositivo obtendrá esa experiencia al iniciar sesión.  |
|Inscripción automática de MDM con cuentas de AAD configuradas.  |La identidad de usuario se administrará mediante Azure Active Directory y los usuarios iniciarán sesión en Windows y Microsoft 365 con sus credenciales de Microsoft 365 Empresa Premium.  |

## <a name="optional-settings"></a>Configuración opcional
  
| Configuración | Descripción |
|:-----|:-----|
|Omitir la configuración de privacidad (desactivado de forma predeterminada)  |Si esta opción está establecida en **Activado**, el usuario no verá el contrato de licencia del dispositivo y Windows cuando inicie sesión por primera vez.  |
|No permitir que el usuario se convierta en el administrador local  |Si esta opción está establecida en **Activado**, el usuario del dispositivo no podrá instalar ninguna aplicación personal, como Cortana.|

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)