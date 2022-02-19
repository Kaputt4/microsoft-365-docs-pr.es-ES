---
title: Novedades de Microsoft Defender para endpoint en iOS
description: Obtenga información sobre los cambios principales de versiones anteriores de Microsoft Defender para endpoint en iOS.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, installation, macos, whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: sunasing
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 503ae29fd371948f68b0c25aafe34f02f7bb8f1d
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2022
ms.locfileid: "62903701"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-ios"></a>Novedades de Microsoft Defender para endpoint en iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="improved-experience-on-supervised-ios-devices"></a>Experiencia mejorada en dispositivos iOS supervisados

Microsoft Defender para endpoint en iOS ahora tiene capacidad especializada en dispositivos iOS/iPadOS supervisados, dadas las capacidades de administración mejoradas que proporciona la plataforma en estos tipos de dispositivos. También puede proporcionar Protección web **sin configurar una VPN local en el dispositivo**. Esto proporciona a los usuarios finales una experiencia perfecta mientras siguen estando protegidos contra la suplantación de identidad (phishing) y otros ataques basados en web. Para obtener más información, visite [esta documentación](ios-install.md#complete-deployment-for-supervised-devices)

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-app-store"></a>Microsoft Defender para endpoint ahora es Microsoft Defender en la Tienda de aplicaciones

Microsoft Defender para endpoint ya está disponible como **Microsoft Defender** en la tienda de aplicaciones. Con esta actualización, la aplicación estará disponible como versión preliminar para **los consumidores de la región de Estados Unidos**. En función de cómo inicie sesión en la aplicación con su cuenta personal o laboral, tendrá acceso a las características de Microsoft Defender para Endpoint o a las características de Microsoft Defender para individuos. Para obtener más información, consulta [este blog](https://www.microsoft.com/en-us/microsoft-365/microsoft-defender-for-individuals).

## <a name="threat-and-vulnerability-management"></a>Administración de amenazas y vulnerabilidades

El 25 de enero de 2022, anunciamos la disponibilidad general de la administración de amenazas y vulnerabilidades en Android e iOS. Para obtener más información, [consulta la publicación techcommunity aquí](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663).

## <a name="1124210103"></a>1.1.24210103

- Se han resuelto problemas de conectividad a Internet en dispositivos supervisados. Para obtener más información, consulte [Deploy Defender for Endpoint on enrolled iOS devices](ios-install.md).
- Correcciones de errores.

## <a name="1123250104"></a>1.1.23250104

- Optimizaciones de rendimiento: pruebe el rendimiento de la batería con esta versión y háganos saber sus comentarios.
- **Incorporación sin** contacto para dispositivos iOS inscritos: con esta versión, se ha agregado la versión preliminar de Zero-touch onboard para dispositivos inscritos a través de Microsoft Endpoint Manager (Intune). Para obtener más información, consulte esta [documentación para](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint-preview) obtener más información sobre la configuración y la configuración.
- **Controles de privacidad** : configure los controles de privacidad para el informe de alertas de suplantación de identidad. Para obtener más información, consulta [Configurar características de iOS](ios-configure-features.md).

## <a name="1123010101"></a>1.1.23010101

- Correcciones de errores y mejoras de rendimiento 
  - En esta versión se han realizado optimizaciones de rendimiento. Pruebe el rendimiento de la batería con esta versión y háganos saber sus comentarios.

## <a name="1120240103"></a>1.1.20240103
- Tarjeta de estado del dispositivo: la tarjeta de mantenimiento del dispositivo notifica a los usuarios finales sobre las actualizaciones de software pendientes.
- Mejoras de facilidad de uso: los usuarios finales ahora pueden deshabilitar defender la VPN de extremo desde la propia aplicación MSDefender. Antes de esta actualización, los usuarios finales tenían que deshabilitar VPN solo desde la Configuración aplicación.
- Correcciones de errores.

## <a name="1120020101"></a>1.1.20020101
- Mejoras de la experiencia de usuario: Microsoft Defender para endpoint tiene un aspecto nuevo.
- Correcciones de errores.

## <a name="1117240101"></a>1.1.17240101
- La compatibilidad con la administración de aplicaciones móviles (MAM) a través de Intune suele estar disponible con esta versión. Para obtener más información, consulta [Microsoft Defender para las señales de riesgo de punto de conexión disponibles para las directivas de protección de aplicaciones](https://techcommunity.microsoft.com/t5/intune-customer-success/microsoft-defender-for-endpoint-risk-signals-available-for-your/ba-p/2186322)
- **Jailbreak Detection** suele estar disponible. Para obtener más información, consulta [Configurar la directiva de acceso condicional en función de las señales de riesgo del dispositivo](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios).
- **La configuración automática del perfil VPN para** dispositivos inscritos a través de Microsoft Endpoint Manager (Intune) suele estar disponible. Para obtener más información, [consulte Auto-Setup VPN profile for enrolled iOS devices](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding).
- Correcciones de errores.

## <a name="1115140101"></a>1.1.15140101

- **Jailbreak Detection** está en versión preliminar. Para obtener más información, consulta [Configurar la directiva de acceso condicional en función de las señales de riesgo del dispositivo](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios).
- **La configuración automática del perfil vpn** está en versión preliminar para dispositivos inscritos a través de Microsoft Endpoint Manager (Intune). Para obtener más información, [consulte Auto-Setup VPN profile for enrolled iOS devices](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding).
- El nombre del producto atp de Microsoft Defender ahora se ha actualizado a Microsoft Defender para Endpoint en la tienda de aplicaciones.
- Experiencia de inicio de sesión mejorada.
- Correcciones de errores.

## <a name="1115010101"></a>1.1.15010101

- Con esta versión, anunciamos compatibilidad con dispositivos iPadOS/iPad.
- Correcciones de errores.
