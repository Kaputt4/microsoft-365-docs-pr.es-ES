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
ms.openlocfilehash: 83871a547aa2f644d70ada5cb121d3b32a6d9bdb
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560365"
---
# <a name="microsoft-defender-for-endpoint---mobile-threat-defense"></a>Microsoft Defender para endpoint- Mobile Threat Defense

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender para endpoint en Android e iOS es nuestra solución de defensa contra amenazas **móviles (MTD).** Normalmente, las empresas toman la iniciativa de proteger sus PC frente a vulnerabilidades y ataques, pero a menudo no supervisan sus dispositivos móviles y quedan desprotegidos. Cuando las plataformas móviles tienen protección integrada, como el aislamiento de aplicaciones y almacenes de aplicaciones de consumidores, estas plataformas siguen siendo vulnerables a ataques basados en web u otros ataques sofisticados. A medida que más empleados usan dispositivos para trabajar y obtener acceso a información confidencial, es imperativo que las empresas implemente una solución MTD para proteger los dispositivos y sus recursos de ataques cada vez más sofisticados en dispositivos móviles.

## <a name="key-capabilities"></a>Principales funcionalidades

Microsoft Defender para Endpoint en Android e iOS proporciona las siguientes funcionalidades clave, Para obtener información sobre las características y ventajas más recientes, lea nuestros [anuncios](https://aka.ms/mdeblog).

<br>

|Funcionalidad|Descripción|
|---|---|
|Protección web|Anti-phishing, bloqueo de conexiones de red no seguras y compatibilidad con indicadores personalizados.|
|Protección contra malware (solo Android)|Buscar aplicaciones malintencionadas.|
|Detección de jailbreak (solo iOS)|Detección de dispositivos con jailbreak.|
|Administración de amenazas y vulnerabilidades (TVM). En la versión preliminar. Vea la nota a continuación*|Evaluación de vulnerabilidad de dispositivos móviles incorporados. Visita esta [página para](next-gen-threat-and-vuln-mgt.md) obtener más información sobre Administración de amenazas y vulnerabilidades en Microsoft Defender para endpoint. *Ten en cuenta que en iOS solo se admiten vulnerabilidades del sistema operativo en esta versión preliminar.*|
|Alertas unificadas|Alertas de todas las plataformas en la consola de seguridad unificada de M365|
|Acceso condicional, inicio condicional|Bloquear el acceso de los dispositivos de riesgo a los recursos corporativos. Las señales de riesgo de Defender for Endpoint también se pueden agregar a las directivas de protección de aplicaciones (MAM)|
|Integración con Microsoft Tunnel|Se puede integrar con Microsoft Tunnel, una solución de puerta de enlace VPN para habilitar la seguridad y la conectividad en una sola aplicación. Disponible solo en Android actualmente|

Todas estas funcionalidades están disponibles para microsoft defender para los titulares de licencias de extremo. Para obtener más información, vea [Requisitos de licencias](minimum-requirements.md#licensing-requirements).

> [!NOTE]
> La evaluación de vulnerabilidades en Android e iOS está actualmente en versión preliminar y puede modificarse considerablemente antes de su lanzamiento comercial. Si has habilitado las características de vista previa pública, puedes consultar la funcionalidad de TVM en Android e iOS hoy mismo. Si no es así, te recomendamos que [actives](preview.md) las características de vista previa de Microsoft Defender para endpoint para obtener acceso a las funcionalidades más nuevas.

## <a name="overview-and-deploy"></a>Introducción e implementación

La implementación de Microsoft Defender para endpoint en dispositivos móviles se puede realizar mediante Microsoft Endpoint Manager (MEM). Vea este vídeo para obtener una introducción rápida a las funciones e implementación de MTD:

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMpiC]

Para obtener más información, consulte los vínculos siguientes.

**Android:** [Microsoft Defender para endpoint en Android](microsoft-defender-endpoint-android.md)

**iOS:** [Microsoft Defender para endpoint en iOS](microsoft-defender-endpoint-ios.md)

### <a name="pilot-evaluation"></a>Evaluación piloto

Durante la evaluación de la defensa contra amenazas móviles con Microsoft Defender para endpoint, puede comprobar que se cumplen ciertos criterios antes de continuar con la implementación del servicio en un conjunto de dispositivos más grande. Puede definir los criterios de salida y asegurarse de que se cumplen antes de implementarse ampliamente.

Esto ayuda a reducir los posibles problemas que podrían surgir al implementar el servicio. A continuación se muestran algunas pruebas y criterios de salida que pueden ayudar:

- Los dispositivos aparecen en la lista de inventario de dispositivos: después de la incorporación correcta de Defender for Endpoint en el dispositivo móvil, compruebe que el dispositivo aparece en el Inventario de dispositivos en la consola [de seguridad](https://security.microsoft.com).

- Ejecuta una prueba de detección de malware en un dispositivo Android: instala cualquier aplicación de virus de prueba desde la Tienda Google Play y comprueba que Microsoft Defender la detecte para Endpoint. Esta es una aplicación de ejemplo que se puede usar para esta prueba: [Probar virus](https://play.google.com/store/apps/details?id=com.androidantivirus.testvirus). Tenga en cuenta que Enterprise Android con un perfil de trabajo, solo se admite el perfil de trabajo.

- Ejecutar una prueba de suplantación de identidad: busque https://smartscreentestratings2.net y compruebe que Microsoft Defender lo bloquea para endpoint. Tenga en cuenta que Enterprise Android con un perfil de trabajo, solo se admite el perfil de trabajo.

- Las alertas aparecen en el panel: compruebe que las alertas de pruebas de detección anteriores aparecen en la [consola de seguridad.](https://security.microsoft.com)

## <a name="deployment-best-practices"></a>Procedimientos recomendados de implementación

### <a name="end-user-onboarding"></a>Incorporación de usuarios finales

- [Configurar el acceso condicional para aplicar](android-configure.md#conditional-access-with-defender-for-endpoint-on-android)la incorporación de usuarios: esto se puede aplicar para garantizar que los usuarios finales se incorpore a la aplicación Microsoft Defender para endpoint después de la implementación. Vea este vídeo para obtener una demostración rápida sobre cómo configurar el acceso condicional con las señales de riesgo de Defender para endpoint. 

  <br/>

  > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMwR1]

### <a name="simplify-onboarding"></a>Simplificar la incorporación

- [Android Enterprise: configurar LA VPN siempre en marcha.](android-intune.md#auto-setup-of-always-on-vpn)
- [iOS: configuración automática del perfil de VPN](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)

## <a name="configure"></a>Configurar

- [Configurar características de Android](android-configure.md)
- [Configurar características de iOS](ios-configure-features.md)
- [Configurar el modo supervisado para dispositivos iOS supervisados](ios-install.md#configure-microsoft-defender-for-endpoint-for-supervised-mode)

## <a name="resources"></a>Recursos

- [Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Microsoft Defender para punto de conexión en iOS](microsoft-defender-endpoint-ios.md)
- Manténgase informado acerca de las próximas versiones mediante la lectura de [nuestros anuncios](https://aka.ms/mdeblog).

