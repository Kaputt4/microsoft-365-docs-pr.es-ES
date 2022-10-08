---
title: Microsoft Defender para punto de conexión en Android
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para punto de conexión en Android
keywords: microsoft, defender, Microsoft Defender para punto de conexión, android, installation, deploy, uninstallation, intune
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: a69004f41b461353ce51999c1b640081e3ebf702
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68226589"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender para punto de conexión en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se describe cómo instalar, configurar, actualizar y usar Defender para punto de conexión en Android.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Defender para punto de conexión en Android provoque problemas de rendimiento y errores imprevisibles del sistema.

## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Instalación de Microsoft Defender para punto de conexión en Android

### <a name="prerequisites"></a>Requisitos previos

- **Para los usuarios finales**:
  - Al usuario final se le debe asignar una licencia de Microsoft Intune. Para obtener más información sobre cómo asignar licencias, consulte [Asignación de licencias a usuarios](/azure/active-directory/users-groups-roles/licensing-groups-assign).
  - A los usuarios de la aplicación se les debe asignar una licencia de Microsoft Defender para punto de conexión. Para obtener más información sobre cómo asignar licencias, consulte [Microsoft Defender para punto de conexión requisitos de licencia](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).
  - Portal de empresa de Intune aplicación se puede descargar desde [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) y está disponible en el dispositivo Android.
  - Además, los dispositivos se pueden [inscribir](/mem/intune/user-help/enroll-device-android-company-portal) a través de la aplicación Portal de empresa de Intune para aplicar Intune directivas de cumplimiento de dispositivos. 

- **Para administradores**:
   - Acceso al portal de Microsoft 365 Defender.
   - Acceda al [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) para:
     - Implemente la aplicación en grupos de usuarios inscritos en su organización.
     - Configure Microsoft Defender para punto de conexión señales de riesgo en la directiva de protección de aplicaciones.
  
    > [!NOTE]
    >
    > - Microsoft Defender para punto de conexión ahora amplía la protección a los datos de una organización dentro de una aplicación administrada (MAM) para los dispositivos que no están inscritos mediante la administración de dispositivos móviles (MDM), pero que usan Intune para administrar aplicaciones móviles. También amplía esta compatibilidad a los clientes que usan otras soluciones de administración de movilidad empresarial, mientras siguen usando Intune para [la administración de aplicaciones móviles (MAM).](/mem/intune/apps/mam-faq)
    > - Además, Microsoft Defender para punto de conexión ya admite dispositivos inscritos mediante Intune administración de dispositivos móviles (MDM).

### <a name="network-requirements"></a>Requisitos de red

- Para que Microsoft Defender para punto de conexión en Android funcione cuando se conecte a una red, el firewall o proxy tendrá que configurarse para habilitar el [acceso a las direcciones URL de servicio de Microsoft Defender para punto de conexión](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).

### <a name="system-requirements"></a>Requisitos del sistema

- Teléfonos móviles con Android 6.0 y versiones posteriores. **Actualmente no se admiten teléfonos móviles que ejecutan Android go, tabletas y otros dispositivos móviles que ejecutan Android.**
- Portal de empresa de Intune aplicación se descarga de [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) y se instala. La inscripción de dispositivos es necesaria para que se apliquen Intune directivas de cumplimiento de dispositivos.

### <a name="installation-instructions"></a>Instrucciones de instalación

Microsoft Defender para punto de conexión en Android admite la instalación en ambos modos de dispositivos inscritos: los modos heredados Administrador de dispositivos y Android Enterprise. **Actualmente, los dispositivos de propiedad personal con perfil de trabajo y las inscripciones de dispositivos de usuario totalmente administrados de propiedad corporativa son compatibles con Android Enterprise. La compatibilidad con otros modos de Android Enterprise se anunciará cuando esté listo.**

- La implementación de Microsoft Defender para punto de conexión en Android se realiza a través de Microsoft Intune (MDM). Para obtener más información, consulte [Implementación de Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md).
- Instalación de Microsoft Defender para punto de conexión en dispositivos que no están inscritos mediante Intune administración de dispositivos móviles (MDM), consulte [Configuración de señales de riesgo de Microsoft Defender para punto de conexión en la directiva de protección de aplicaciones (MAM).](android-configure-mam.md)

> [!NOTE]
> **Microsoft Defender para punto de conexión en Android ya está disponible en [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx).**
>
> Puede conectarse a Google Play desde Intune para implementar Microsoft Defender para punto de conexión aplicación en los modos de inscripción Administrador de dispositivos y Android Enterprise.

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Configuración de Microsoft Defender para punto de conexión en Android

Las instrucciones sobre cómo configurar Microsoft Defender para punto de conexión en las características de Android están disponibles en [Configurar características de Microsoft Defender para punto de conexión en Android](android-configure.md).

## <a name="related-topics"></a>Temas relacionados

- [Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md)
- [Configurar Microsoft Defender para punto de conexión en funciones de Android](android-configure.md)
- [Aspectos básicos de la administración de aplicaciones móviles (MAM)](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
