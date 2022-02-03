---
title: Microsoft Defender para endpoint- Mobile Threat Defense
ms.reviewer: ''
description: Información general sobre mobile threat defense en Microsoft Defender para endpoint
keywords: móvil, defender, Microsoft Defender para endpoint, ios, mtd, android, seguridad
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0754886d70759b4869151ad2c915a878a5ca111c
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "62355049"
---
# <a name="microsoft-defender-for-endpoint---mobile-threat-defense"></a>Microsoft Defender para endpoint- Mobile Threat Defense

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender para Endpoint en Android e iOS es nuestra **solución de defensa contra amenazas móviles (MTD).**. Normalmente, las empresas toman la iniciativa de proteger sus PC frente a vulnerabilidades y ataques, pero a menudo no supervisan sus dispositivos móviles y quedan desprotegidos. Cuando las plataformas móviles tienen protección integrada, como el aislamiento de aplicaciones y almacenes de aplicaciones de consumidores, estas plataformas siguen siendo vulnerables a ataques basados en web u otros ataques sofisticados. A medida que más empleados usan dispositivos para trabajar y obtener acceso a información confidencial, es imperativo que las empresas implemente una solución MTD para proteger los dispositivos y sus recursos de ataques cada vez más sofisticados en dispositivos móviles.

## <a name="key-capabilities"></a>Principales funcionalidades

Microsoft Defender para Endpoint en Android e iOS proporciona las siguientes funcionalidades clave, Para obtener información sobre las características y ventajas más recientes, lea nuestros [anuncios](https://aka.ms/mdeblog).

<br>

|Funcionalidad|Descripción|
|---|---|
|Protección web|Anti-phishing, bloqueo de conexiones de red no seguras y compatibilidad con indicadores personalizados.|
|Protección contra malware (solo Android)|Buscar aplicaciones malintencionadas.|
|Detección de jailbreak (solo iOS)|Detección de dispositivos con jailbreak.|
|Administración de amenazas y vulnerabilidades (TVM) |Evaluación de vulnerabilidad de dispositivos móviles incorporados. Visita esta [página para](next-gen-threat-and-vuln-mgt.md) obtener más información sobre Administración de amenazas y vulnerabilidades en Microsoft Defender para endpoint. *Ten en cuenta que en iOS solo se admiten vulnerabilidades del sistema operativo en esta versión preliminar.*|
|Alertas unificadas|Alertas de todas las plataformas en la consola de seguridad unificada de M365|
|Acceso condicional, inicio condicional|Bloquear el acceso de los dispositivos de riesgo a los recursos corporativos. Las señales de riesgo de Defender for Endpoint también se pueden agregar a las directivas de protección de aplicaciones (MAM)|
|Controles de privacidad. En vista previa (vea la nota siguiente)|Configure la privacidad en los informes de amenazas mediante el control de los datos enviados por Microsoft Defender para Endpoint. *Ten en cuenta que actualmente los controles de privacidad solo están disponibles para los dispositivos inscritos. Los controles para dispositivos no inscritos se agregarán más adelante*|
|Integración con Microsoft Tunnel|Se puede integrar con Microsoft Tunnel, una solución de puerta de enlace VPN para habilitar la seguridad y la conectividad en una sola aplicación. Disponible solo en Android actualmente|

Todas estas funcionalidades están disponibles para microsoft defender para los titulares de licencias de extremo. Para obtener más información, vea [Requisitos de licencias](minimum-requirements.md#licensing-requirements).


## <a name="overview-and-deploy"></a>Introducción e implementación

La implementación de Microsoft Defender para endpoint en dispositivos móviles se puede realizar mediante Microsoft Endpoint Manager (MEM). Vea este vídeo para obtener una introducción rápida a las funciones e implementación de MTD:

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMpiC]

### <a name="deploy"></a>Implementar

En la tabla siguiente se resume cómo implementar Microsoft Defender para endpoint en Android e iOS. Para obtener documentación detallada, vea 
- [Información general sobre Microsoft Defender para endpoint en Android](microsoft-defender-endpoint-android.md) y
- [Introducción a Microsoft Defender para punto de conexión en iOS](microsoft-defender-endpoint-ios.md)

**Android**

|Tipo de inscripción     |Detalles      |
|--------------------|-------------|
|Android Enterprise con Intune Unified Endpoint Manager (Microsoft Endpoint Manager)|[Implementar en dispositivos Enterprise android inscritos](android-intune.md#deploy-on-android-enterprise-enrolled-devices)|
|Administrador de dispositivos con intune unified Endpoint Manager (Microsoft Endpoint Manager)|[Implementar en dispositivos inscritos por el administrador de dispositivos](android-intune.md#deploy-on-device-administrator-enrolled-devices)|
|Dispositivos BYOD O no administrados por otros administradores de extremos unificados / Directiva de protección de aplicaciones de configuración (MAM)|[Configurar señales de riesgo de Defender en la directiva de protección de aplicaciones (MAM)](android-configure-mam.md)|

**iOS**

|Tipo de inscripción     |Detalles      |
|--------------------|-------------|
|Dispositivos supervisados con Intune Unified Endpoint Manager (Microsoft Endpoint Manager)|1. [Implementar como aplicación de la tienda iOS](ios-install.md)<br/>2. [Configurar Web Protection sin VPN para dispositivos iOS supervisados](ios-install.md#complete-deployment-for-supervised-devices)|
|Dispositivos no supervisados (BYOD) inscritos con Intune UEM (Microsoft Endpoint Manager)|[Implementar como aplicación de la tienda iOS](ios-install.md)|
|Dispositivos BYOD O no administrados por otros UEMs / Directiva de protección de aplicaciones de instalación (MAM)|[Configurar señales de riesgo de Defender en la directiva de protección de aplicaciones (MAM)](ios-install-unmanaged.md)|

### <a name="end-user-onboarding"></a>Incorporación de usuarios finales

- [Configurar la](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint-preview) incorporación sin intervención táctil para dispositivos inscritos en iOS: los administradores pueden configurar la instalación sin intervención táctil para incorporar de forma silenciosa Microsoft Defender para Endpoint en dispositivos iOS inscritos sin necesidad de que el usuario abra la aplicación. 

- [Configurar el acceso condicional para exigir la incorporación](android-configure.md#conditional-access-with-defender-for-endpoint-on-android) de usuarios: esto se puede aplicar para garantizar que los usuarios finales se incorpore a la aplicación Microsoft Defender para endpoint después de la implementación. Vea este vídeo para obtener una demostración rápida sobre cómo configurar el acceso condicional con las señales de riesgo de Defender para endpoint. 

  <br/>

  > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMwR1]

### <a name="simplify-onboarding"></a>Simplificar la incorporación

- [iOS: Zero-Touch incorporado](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint-preview)
- [Android Enterprise: configurar VPN siempre en marcha](android-intune.md#auto-setup-of-always-on-vpn).
- [iOS: configuración automática del perfil de VPN](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)

## <a name="pilot-evaluation"></a>Evaluación piloto

Al evaluar la defensa contra amenazas móviles con Microsoft Defender para endpoint, puede comprobar que se cumplen ciertos criterios antes de continuar con la implementación del servicio en un conjunto de dispositivos más grande. Puede definir los criterios de salida y asegurarse de que se cumplen antes de implementarse ampliamente.

Esto ayuda a reducir los posibles problemas que podrían surgir al implementar el servicio. Estos son algunos criterios de prueba y salida que pueden ayudar:

- Los dispositivos aparecen en la lista de inventario de dispositivos: después de la incorporación correcta de Defender for Endpoint en el dispositivo móvil, compruebe que el dispositivo aparece en el Inventario de dispositivos en la [consola de seguridad](https://security.microsoft.com).

- Ejecuta una prueba de detección de malware en un dispositivo Android: instala cualquier aplicación de virus de prueba desde la Tienda Google Play y comprueba que Microsoft Defender la detecte para Endpoint. Esta es una aplicación de ejemplo que se puede usar para esta prueba: [Probar virus](https://play.google.com/store/apps/details?id=com.androidantivirus.testvirus). Tenga en cuenta que Enterprise Android con un perfil de trabajo, solo se admite el perfil de trabajo.

- Ejecutar una prueba de suplantación de identidad: busque https://smartscreentestratings2.net y compruebe que Microsoft Defender lo bloquea para endpoint. Tenga en cuenta que Enterprise Android con un perfil de trabajo, solo se admite el perfil de trabajo.

- Las alertas aparecen en el panel: compruebe que las alertas de pruebas de detección anteriores aparecen en la [consola de seguridad](https://security.microsoft.com).

## <a name="configure"></a>Configurar

- [Configurar características de Android](android-configure.md)
- [Configurar características de iOS](ios-configure-features.md)
- [Configurar Web Protection sin VPN para dispositivos iOS supervisados](ios-install.md#complete-deployment-for-supervised-devices)

## <a name="resources"></a>Resources

- [Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Microsoft Defender para punto de conexión en iOS](microsoft-defender-endpoint-ios.md)
- Manténgase informado sobre las próximas versiones mediante la lectura de [nuestros anuncios](https://aka.ms/mdeblog).

