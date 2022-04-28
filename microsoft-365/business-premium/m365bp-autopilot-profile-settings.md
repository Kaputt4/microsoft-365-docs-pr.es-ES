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
ms.localizationpriority: high
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
description: Los perfiles de AutoPilot le ayudan a controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen opciones predeterminadas y opcionales, como omitir la instalación de Cortana.
ms.openlocfilehash: 9cfacb4ca69f8a674a50cfd5946e6a095433aed9
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090650"
---
# <a name="about-autopilot-profile-settings"></a>Información sobre la configuración de los perfiles de AutoPilot

## <a name="autopilot-profile-settings"></a>Configuración de perfiles de Autopilot

> [!NOTE]
> Microsoft Defender para empresas se está implementando para los clientes de Microsoft 365 Empresa Premium a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para los dispositivos. [Más información sobre Defender para empresas](../security/defender-business/mdb-overview.md).

Puede usar perfiles de AutoPilot para controlar cómo se instala Windows en los dispositivos de usuario. Los perfiles contienen la siguiente configuración.
  
## <a name="autopilot-default-features-required-that-are-set-automatically"></a>Características predeterminadas de AutoPilot (necesarias) que se establecen automáticamente
  
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

[Las 10 mejores formas de proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)