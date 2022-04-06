---
title: Información sobre la configuración de los perfiles de AutoPilot
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1.keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
ms.openlocfilehash: 16675317136af9dc03c3bddf88fca954ff72bce1
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635478"
---
# <a name="about-autopilot-profile-settings"></a>Información sobre la configuración de los perfiles de AutoPilot

## <a name="autopilot-profile-settings"></a>Configuración del perfil de AutoPilot

> [!NOTE]
> Microsoft Defender für Unternehmen se está implementando para Microsoft 365 Business Premium clientes, a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para dispositivos. [Obtenga más información sobre Defender para empresas](../security/defender-business/mdb-overview.md).

Puedes usar los perfiles de AutoPilot para controlar cómo Windows se instala en dispositivos de usuario. Los perfiles contienen la siguiente configuración.
  
## <a name="autopilot-default-features-required-that-are-set-automatically"></a>Características predeterminadas de AutoPilot (necesarias) que se establecen automáticamente
  
| Valor | Descripción |
|:-----|:-----|
|Omitir Cortana, OneDrive y registro OEM  |Omite la instalación de aplicaciones de consumidor como Cortana y personal OneDrive. El usuario del dispositivo puede instalar estos más adelante siempre que el usuario sea un administrador local en el dispositivo. El registro del fabricante original se omite porque el dispositivo se administrará Microsoft 365 Business Premium.  |
|Experiencia de inicio de sesión con la marca de su empresa  |Si tu empresa tiene una [página](../admin/setup/customize-sign-in-page.md) Agregar la personal de marca de tu empresa Microsoft 365 inicio de sesión, el usuario del dispositivo tendrá esa experiencia al iniciar sesión.  |
|Inscripción automática mdm con cuentas AAD configuradas.  |La identidad de usuario la administrará Azure Active Directory y los usuarios iniciarán sesión en Windows y Microsoft 365 con sus Microsoft 365 Business Premium credenciales.  |

## <a name="optional-settings"></a>Configuración opcional
  
| Valor | Descripción |
|:-----|:-----|
|Omitir la configuración de privacidad (desactivado de forma predeterminada)  |Si esta opción está establecida en **On**, el usuario del dispositivo no verá el contrato de licencia para el dispositivo y Windows cuando inicia sesión por primera vez.  |
|No permitir que el usuario se convierta en el administrador local  |Si esta opción está establecida en **On**, el usuario del dispositivo no podrá instalar ninguna aplicación personal, como Cortana.|

## <a name="see-also"></a>Vea también

[Principales 10 formas de proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)