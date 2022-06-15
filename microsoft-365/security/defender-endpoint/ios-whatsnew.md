---
title: Novedades de Microsoft Defender para punto de conexión en iOS
description: Obtenga información sobre los cambios principales de las versiones anteriores de Microsoft Defender para punto de conexión en iOS.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, macos, whatsnew
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
ms.openlocfilehash: 3f05c819e5390504bca9c1f5aaa7f85d1e7edc2a
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66090487"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-ios"></a>Novedades de Microsoft Defender para punto de conexión en iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="network-protection"></a>Protección de red
La protección de red en Microsoft Defender para punto de conexión está ahora en versión preliminar pública. La protección de red proporciona protección contra amenazas no autorizadas Wi-Fi relacionadas, hardware no autorizado como dispositivos de piña y notifica al usuario si se detecta una amenaza relacionada. Los usuarios también verán una experiencia guiada para conectarse a redes seguras y cambiar las redes cuando estén conectadas a una conexión no segura.

Incluye varios controles de administración para ofrecer flexibilidad, como la capacidad de configurar la característica desde el centro de Microsoft Endpoint Manager Administración. Los administradores también pueden habilitar los controles de privacidad para configurar los datos enviados por Defender para punto de conexión desde iOS dispositivos. Para obtener más información, consulte [Configurar protección de red]().

La protección de red para iOS ya está habilitada para el inquilino. Los usuarios finales que prueban la característica protección de red pueden instalar la versión preliminar de la aplicación a través de TestFlight. Vaya a https://aka.ms/mdeiospp en el dispositivo iOS. Esto le pedirá que instale la aplicación de TestFlight en el dispositivo o abra TestFlight en caso de que ya esté instalada. En la aplicación TestFlight, siga las instrucciones en pantalla para instalar el punto de conexión de Microsoft Defender. Compruebe que el número de versión de MDE es 1.1.29270104.

## <a name="integration-with-tunnel"></a>Integración con Tunnel
Microsoft Defender para punto de conexión en iOS ahora se puede integrar con Microsoft Tunnel, una solución de puerta de enlace de VPN para habilitar la seguridad y la conectividad en una sola aplicación.  La integración con Tunnel proporciona una experiencia VPN más sencilla y segura en iOS con una sola aplicación. Esta característica solo estaba disponible anteriormente en Android. Para obtener más información, [consulte la publicación techcommunity aquí](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/what-s-new-in-microsoft-endpoint-manager-2204-april-edition/ba-p/3297995).

## <a name="improved-experience-on-supervised-ios-devices"></a>Experiencia mejorada en dispositivos de iOS supervisados

Microsoft Defender para punto de conexión en iOS ahora tiene una capacidad especializada en dispositivos iOS/iPadOS supervisados, dadas las mayores capacidades de administración proporcionadas por la plataforma en estos tipos de dispositivos. También puede proporcionar protección web **sin configurar una VPN local en el dispositivo**. Esto proporciona a los usuarios finales una experiencia sin problemas mientras siguen protegidos contra suplantación de identidad (phishing) y otros ataques basados en web. Para obtener más información, visite [esta documentación](ios-install.md#complete-deployment-for-supervised-devices).

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-app-store"></a>Microsoft Defender para punto de conexión ahora es Microsoft Defender en app store

Microsoft Defender para punto de conexión ahora está disponible como **Microsoft Defender** en la tienda de aplicaciones. Con esta actualización, la aplicación estará disponible como versión preliminar para **consumidores en la región de EE. UU**. En función de cómo inicie sesión en la aplicación con su cuenta profesional o personal, tendrá acceso a las características de Microsoft Defender para punto de conexión o a las características de Microsoft Defender para usuarios individuales. Para obtener más información, consulte [este blog](https://www.microsoft.com/en-us/microsoft-365/microsoft-defender-for-individuals).

## <a name="threat-and-vulnerability-management"></a>Administración de amenazas y vulnerabilidades

El 25 de enero de 2022, anunciamos la disponibilidad general de la administración de amenazas y vulnerabilidades en Android y iOS. Para obtener más información, consulte [la publicación techcommunity aquí](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663).

## <a name="1128250101"></a>1.1.28250101
- **Integración con Tunnel**: Microsoft Defender para punto de conexión en iOS ahora se puede integrar con Microsoft Tunnel, una solución de VPN Gateway para habilitar la seguridad y la conectividad en una sola aplicación. Para obtener más información, consulte [introducción a Microsoft Tunnel](/mem/intune/protect/microsoft-tunnel-overview).
- **La incorporación sin contacto para los dispositivos iOS inscritos** inscritos a través de Microsoft Endpoint Manager (Intune) está disponible con carácter general. Para obtener más información, consulte [Incorporación táctil cero de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/ios-install#zero-touch-onboarding-of-microsoft-defender-for-endpoint).
- Correcciones de errores.


## <a name="1124210103"></a>1.1.24210103

- Se han resuelto problemas de conectividad a Internet en dispositivos supervisados. Para obtener más información, consulte [Implementación de Defender para punto de conexión en dispositivos iOS inscritos](ios-install.md).
- Correcciones de errores.

## <a name="1123250104"></a>1.1.23250104

- Optimizaciones de rendimiento: pruebe el rendimiento de la batería con esta versión y háganos saber sus comentarios.
- **Incorporación sin interacción para dispositivos iOS inscritos**: con esta versión, se ha agregado la versión preliminar de Zero-touch onboard para los dispositivos inscritos a través de Microsoft Endpoint Manager (Intune). Para obtener más información, consulte esta [documentación](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint) para obtener más información sobre la configuración y la configuración.
- **Controles de privacidad** : configure los controles de privacidad para el informe de alertas de phish. Para obtener más información, vea [Configurar características de iOS](ios-configure-features.md).

## <a name="1123010101"></a>1.1.23010101

- Correcciones de errores y mejoras de rendimiento 
  - En esta versión se realizaron optimizaciones de rendimiento. Pruebe el rendimiento de la batería con esta versión y háganos saber sus comentarios.

## <a name="1120240103"></a>1.1.20240103
- Tarjeta de estado del dispositivo: la tarjeta device health notifica a los usuarios finales sobre las actualizaciones de software pendientes.
- Mejoras de facilidad de uso: los usuarios finales ahora pueden deshabilitar la VPN de Defender para punto de conexión desde la propia aplicación de Microsoft Defender. Antes de esta actualización, los usuarios finales tenían que deshabilitar la VPN solo desde la aplicación Configuración.
- Correcciones de errores.

## <a name="1120020101"></a>1.1.20020101
- Mejoras de experiencia de usuario: Microsoft Defender para punto de conexión tiene un nuevo aspecto.
- Correcciones de errores.

## <a name="1117240101"></a>1.1.17240101
- La compatibilidad con la administración de aplicaciones móviles (MAM) a través de Intune está disponible con carácter general con esta versión. Para obtener más información, consulte [Microsoft Defender para punto de conexión señales de riesgo disponibles para las directivas de Protección de aplicaciones](https://techcommunity.microsoft.com/t5/intune-customer-success/microsoft-defender-for-endpoint-risk-signals-available-for-your/ba-p/2186322)
- **La detección de jailbreak** está disponible con carácter general. Para obtener más información, consulte [Configuración de la directiva de acceso condicional en función de las señales de riesgo del dispositivo](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios).
- **La configuración automática del perfil de VPN** para dispositivos inscritos a través de Microsoft Endpoint Manager (Intune) está disponible con carácter general. Para obtener más información, consulte [Configuración automática del perfil de VPN para dispositivos iOS inscritos](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding).
- Correcciones de errores.

## <a name="1115140101"></a>1.1.15140101

- **La detección de jailbreak** está en versión preliminar. Para obtener más información, consulte [Configuración de la directiva de acceso condicional en función de las señales de riesgo del dispositivo](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios).
- **La configuración automática del perfil de VPN** está en versión preliminar para los dispositivos inscritos a través de Microsoft Endpoint Manager (Intune). Para obtener más información, consulte [Configuración automática del perfil de VPN para dispositivos iOS inscritos](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding).
- El nombre del producto atp de Microsoft Defender se ha actualizado para Microsoft Defender para punto de conexión en la tienda de aplicaciones.
- Experiencia de inicio de sesión mejorada.
- Correcciones de errores.

## <a name="1115010101"></a>1.1.15010101

- Con esta versión, anunciamos compatibilidad con dispositivos iPadOS/iPad.
- Correcciones de errores.
