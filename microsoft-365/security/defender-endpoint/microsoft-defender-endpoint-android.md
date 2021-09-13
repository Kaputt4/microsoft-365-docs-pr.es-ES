---
title: Microsoft Defender para punto de conexión en Android
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para Endpoint en Android
keywords: microsoft, defender, Microsoft Defender para Endpoint, android, instalación, implementación, desinstalación, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 242d0983913a646e34caf4766bcaec90c652fbd3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213587"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender para punto de conexión en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se describe cómo instalar, configurar, actualizar y usar Defender para Endpoint en Android.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Defender para Endpoint en Android cause problemas de rendimiento y errores impredecibles del sistema.

## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Cómo instalar Microsoft Defender para Endpoint en Android

### <a name="prerequisites"></a>Requisitos previos

- **Para los usuarios finales:**
  - Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación. Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)
  - Portal de empresa de Intune aplicación se puede descargar desde [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) y está disponible en el dispositivo Android.
  - Además, los dispositivos se [](/mem/intune/user-help/enroll-device-android-company-portal) pueden inscribir mediante la aplicación Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune. Esto requiere que al usuario final se le asigne una Microsoft Intune licencia.
  - Para obtener más información sobre cómo asignar licencias, vea [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).

- **Para administradores**
   - Acceso al portal Microsoft 365 Defender web.

    > [!NOTE]
    > - Microsoft Defender para endpoint ahora amplía la protección a los datos de una organización dentro de una aplicación administrada para aquellos que no usan la administración de dispositivos móviles (MDM), pero que usan Intune para administrar aplicaciones móviles. También amplía esta compatibilidad a los clientes que usan otras soluciones de administración de movilidad empresarial, mientras que sigue usando Intune para la administración de aplicaciones móviles [(MAM).](/mem/intune/apps/mam-faq)
    > - Además, Microsoft Defender para Endpoint ya admite dispositivos inscritos mediante la administración de dispositivos móviles (MDM) de Intune.

    - Accede [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431), para implementar la aplicación en grupos de usuarios inscritos en tu organización.

### <a name="network-requirements"></a>Requisitos de red

- Para que Microsoft Defender para endpoint en Android funcione cuando se conecte a una red, el firewall/proxy tendrá que configurarse para habilitar el acceso a las direcciones URL del servicio De extremo [de Microsoft Defender.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

### <a name="system-requirements"></a>Requisitos del sistema

- Teléfonos móviles que ejecutan Android 6.0 y versiones posteriores. **Las tabletas y otros dispositivos móviles que ejecutan Android no son compatibles actualmente.**
- Portal de empresa de Intune aplicación se descarga desde [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e se instala. La inscripción de dispositivos es necesaria para que se cumplan las directivas de cumplimiento de dispositivos de Intune.

### <a name="installation-instructions"></a>Instrucciones de instalación

Microsoft Defender para Endpoint en Android admite la instalación en ambos modos de dispositivos inscritos: el administrador de dispositivos heredado y los modos Enterprise Android. **Actualmente, los dispositivos de propiedad personal con perfil de trabajo y las inscripciones de dispositivos de usuario totalmente administrados de propiedad corporativa se admiten en Android Enterprise. La compatibilidad con otros Enterprise Android se anunciará cuando esté listo.**

La implementación de Microsoft Defender para Endpoint en Android es a través Microsoft Intune (MDM). Para obtener más información, vea [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).

> [!NOTE]
> **Microsoft Defender para Endpoint en Android ya está disponible [en Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**
>
> Puedes conectarte a Google Play desde Intune para implementar la aplicación Microsoft Defender para endpoint, entre los modos de inscripción de Administrador de dispositivos y Android Enterprise inscripción.

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Cómo configurar Microsoft Defender para endpoint en Android

Encontrará instrucciones sobre cómo configurar las características de Microsoft Defender para Endpoint en Android en [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).

## <a name="related-topics"></a>Temas relacionados

- [Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md)
- [Configurar Microsoft Defender para punto de conexión en funciones de Android](android-configure.md)
- [Conceptos básicos de administración de aplicaciones móviles (MAM)](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
