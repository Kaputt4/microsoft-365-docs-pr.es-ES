---
title: 'Microsoft Defender para punto de conexión: Mobile Threat Defense'
ms.reviewer: ''
description: Introducción a Mobile Threat Defense en Microsoft Defender para punto de conexión
keywords: mobile, defender, Microsoft Defender para punto de conexión, ios, mtd, android, security
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
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 83da2034a04da85849383700204174110ceffa57
ms.sourcegitcommit: 7e0094ddff54bcbe5d691dba58d4c4fb86f8b1a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "65188534"
---
# <a name="microsoft-defender-for-endpoint---mobile-threat-defense"></a>Microsoft Defender para punto de conexión: Mobile Threat Defense

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender para punto de conexión en Android e iOS es nuestra **solución de defensa contra amenazas móviles (MTD).** Normalmente, las empresas toman la iniciativa de proteger sus PC frente a vulnerabilidades y ataques, pero a menudo no supervisan sus dispositivos móviles y quedan desprotegidos. Cuando las plataformas móviles tienen protección integrada, como el aislamiento de aplicaciones y las tiendas de aplicaciones de consumidor supervisadas, estas plataformas siguen siendo vulnerables a ataques sofisticados o basados en web. A medida que más empleados usan dispositivos para el trabajo y para acceder a información confidencial, es imperativo que las empresas implementen una solución MTD para proteger los dispositivos y los recursos frente a ataques cada vez más sofisticados en los dispositivos móviles.

## <a name="key-capabilities"></a>Principales funcionalidades

Microsoft Defender para punto de conexión en Android e iOS proporciona las siguientes funcionalidades clave, para obtener información sobre las características y [ventajas](https://aka.ms/mdeblog) más recientes, lea nuestros anuncios.

<br>

|Funcionalidad|Descripción|
|---|---|
|Protección web|Protección contra phishing, bloqueo de conexiones de red no seguras y compatibilidad con indicadores personalizados.|
|Protección contra malware (solo Android)|Examen de aplicaciones malintencionadas.|
|Detección de jailbreak (solo iOS)|Detección de dispositivos jailbreak.|
|Administración de amenazas y vulnerabilidades (TVM) |Evaluación de vulnerabilidades de dispositivos móviles incorporados. Visite esta [página](next-gen-threat-and-vuln-mgt.md) para obtener más información sobre Administración de amenazas y vulnerabilidades en Microsoft Defender para punto de conexión. *Tenga en cuenta que en iOS solo se admiten vulnerabilidades del sistema operativo en esta versión preliminar.*|
|Alertas unificadas|Alertas de todas las plataformas en la consola de seguridad unificada de M365|
|Acceso condicional, inicio condicional|Impedir que los dispositivos de riesgo accedan a los recursos corporativos. Las señales de riesgo de Defender para punto de conexión también se pueden agregar a las directivas de protección de aplicaciones (MAM)|
|Controles de privacidad. En versión preliminar (vea la nota siguiente)|Configure la privacidad en los informes de amenazas mediante el control de los datos enviados por Microsoft Defender para punto de conexión. *Tenga en cuenta que los controles de privacidad solo están disponibles actualmente para dispositivos inscritos. Los controles para dispositivos no inscritos se agregarán más adelante.*|
|Integración con Microsoft Tunnel|Se puede integrar con Microsoft Tunnel, una solución de puerta de enlace de VPN para habilitar la seguridad y la conectividad en una sola aplicación. Disponible en Android y ahora también está disponible con carácter general en iOS.|

Todas estas funcionalidades están disponibles para Microsoft Defender para punto de conexión titulares de licencias. Para obtener más información, consulte [Requisitos de licencias](minimum-requirements.md#licensing-requirements).


## <a name="overview-and-deploy"></a>Información general e implementación

La implementación de Microsoft Defender para punto de conexión en dispositivos móviles se puede realizar a través de Microsoft Endpoint Manager (MEM). Vea este vídeo para obtener información general rápida sobre las funcionalidades y la implementación de MTD:

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMpiC]

### <a name="deploy"></a>Implementar

En la tabla siguiente se resume cómo implementar Microsoft Defender para punto de conexión en Android e iOS. Para obtener documentación detallada, consulte 
- [Introducción a Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md) y
- [Introducción a Microsoft Defender para punto de conexión en iOS](microsoft-defender-endpoint-ios.md)

**Android**

|Tipo de inscripción     |Detalles      |
|--------------------|-------------|
|Android Enterprise con Intune unified Endpoint Manager (Microsoft Endpoint Manager)|[Implementación en dispositivos android Enterprise inscritos](android-intune.md#deploy-on-android-enterprise-enrolled-devices)|
|Administrador de dispositivos con Intune Endpoint Manager unificado (Microsoft Endpoint Manager)|[Implementación en dispositivos inscritos por el administrador de dispositivos](android-intune.md#deploy-on-device-administrator-enrolled-devices)|
|Dispositivos BYOD O no administrados administrados por otros administradores de puntos de conexión unificados o directiva de protección de aplicaciones de configuración (MAM)|[Configuración de señales de riesgo de Defender en la directiva de protección de aplicaciones (MAM)](android-configure-mam.md)|

**iOS**

|Tipo de inscripción     |Detalles      |
|--------------------|-------------|
|Dispositivos supervisados con Intune Endpoint Manager unificado (Microsoft Endpoint Manager)|1. [Implementación como aplicación de la tienda iOS](ios-install.md)<br/>2. [Configurar la protección web sin VPN para dispositivos iOS supervisados](ios-install.md#complete-deployment-for-supervised-devices)|
|Dispositivos no supervisados (BYOD) inscritos con Intune UEM (Microsoft Endpoint Manager)|[Implementación como aplicación de la Tienda iOS](ios-install.md)|
|Dispositivos BYOD O no administrados administrados por otros UEM o directiva de protección de aplicaciones de configuración (MAM)|[Configuración de señales de riesgo de Defender en la directiva de protección de aplicaciones (MAM)](ios-install-unmanaged.md)|

### <a name="end-user-onboarding"></a>Incorporación del usuario final

- [Configurar la incorporación zero-touch para dispositivos inscritos en iOS](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint): los administradores pueden configurar la instalación sin intervención táctil para incorporar de forma silenciosa Microsoft Defender para punto de conexión en dispositivos iOS inscritos sin necesidad de que el usuario abra la aplicación. 

- [Configurar el acceso condicional para aplicar la incorporación de usuarios](android-configure.md#conditional-access-with-defender-for-endpoint-on-android): esto se puede aplicar para garantizar que los usuarios finales se incorporen a la aplicación Microsoft Defender para punto de conexión después de la implementación. Vea este vídeo para ver una demostración rápida sobre la configuración del acceso condicional con señales de riesgo de Defender para punto de conexión. 

  <br/>

  > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMwR1]

### <a name="simplify-onboarding"></a>Simplificación de la incorporación

- [iOS: incorporación de Zero-Touch](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint)
- [Android Enterprise: configuración de VPN always-on](android-intune.md#auto-setup-of-always-on-vpn).
- [iOS: configuración automática del perfil de VPN](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)

## <a name="pilot-evaluation"></a>Evaluación piloto

Al evaluar la defensa contra amenazas móviles con Microsoft Defender para punto de conexión, puede comprobar que se cumplen determinados criterios antes de continuar con la implementación del servicio en un conjunto mayor de dispositivos. Puede definir los criterios de salida y asegurarse de que están satisfechos antes de implementarlo ampliamente.

Esto ayuda a reducir los posibles problemas que podrían surgir al implementar el servicio. Estas son algunas pruebas y criterios de salida que podrían ayudar a:

- Los dispositivos se muestran en la lista de inventario de dispositivos: después de incorporar correctamente Defender para punto de conexión en el dispositivo móvil, compruebe que el dispositivo aparece en inventario de dispositivos en la [consola de seguridad](https://security.microsoft.com).

- Ejecutar una prueba de detección de malware en un dispositivo Android: instale cualquier aplicación de virus de prueba desde Google Play Store y compruebe que se detecta mediante Microsoft Defender para punto de conexión. Esta es una aplicación de ejemplo que se puede usar para esta prueba: [Virus de prueba](https://play.google.com/store/apps/details?id=com.androidantivirus.testvirus). Tenga en cuenta que en Android Enterprise con un perfil de trabajo, solo se admite el perfil de trabajo.

- Ejecutar una prueba de suplantación de identidad (phishing): vaya a https://smartscreentestratings2.net y compruebe que Microsoft Defender para punto de conexión la bloquea. Tenga en cuenta que en Android Enterprise con un perfil de trabajo, solo se admite el perfil de trabajo.

- Las alertas aparecen en el panel: compruebe que las alertas de las pruebas de detección anteriores aparecen en la [consola de seguridad](https://security.microsoft.com).

## <a name="configure"></a>Configuración

- [Configuración de características de Android](android-configure.md)
- [Configurar características de iOS](ios-configure-features.md)
- [Configuración de Web Protection sin VPN para dispositivos iOS supervisados](ios-install.md#complete-deployment-for-supervised-devices)

## <a name="resources"></a>Recursos

- [Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Microsoft Defender para punto de conexión en iOS](microsoft-defender-endpoint-ios.md)
- Manténgase informado sobre las próximas versiones leyendo nuestros [anuncios](https://aka.ms/mdeblog).

