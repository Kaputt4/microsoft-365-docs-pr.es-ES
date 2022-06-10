---
title: Microsoft Defender para punto de conexión en Android
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para punto de conexión en Android
keywords: microsoft, defender, Microsoft Defender para punto de conexión, android, installation, deploy, uninstallation, intune
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8de6af6f04243a8481d116fe9a67f5420b536f6c
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66016534"
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
   - Acceda [a Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431) a:
     - Implemente la aplicación en grupos de usuarios inscritos en su organización.
     - Configure Microsoft Defender para punto de conexión señales de riesgo en la directiva de protección de aplicaciones.
  
    > [!NOTE]
    >
    > - Microsoft Defender para punto de conexión ahora amplía la protección a los datos de una organización dentro de una aplicación administrada (MAM) para los dispositivos que no están inscritos mediante la administración de dispositivos móviles (MDM), pero que usan Intune para administrar aplicaciones móviles. También amplía esta compatibilidad a los clientes que usan otras soluciones de administración de movilidad empresarial, mientras siguen usando Intune para [la administración de aplicaciones móviles (MAM).](/mem/intune/apps/mam-faq)
    > - Además, Microsoft Defender para punto de conexión ya admite dispositivos inscritos mediante Intune administración de dispositivos móviles (MDM).

### <a name="network-requirements"></a>Requisitos de red

- Para que Microsoft Defender para punto de conexión en Android funcione cuando se conecte a una red, el firewall o proxy deberá configurarse para [habilitar el acceso a las direcciones URL de servicio de Microsoft Defender para punto de conexión](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).

### <a name="system-requirements"></a>Requisitos del sistema

- Teléfonos móviles que ejecutan Android 6.0 y versiones posteriores. **Actualmente no se admiten los teléfonos móviles que ejecutan Android go, tabletas y otros dispositivos móviles que ejecutan Android.**
- Portal de empresa de Intune aplicación se descarga de [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) y se instala. La inscripción de dispositivos es necesaria para que se apliquen Intune directivas de cumplimiento de dispositivos.

### <a name="installation-instructions"></a>Instrucciones de instalación

Microsoft Defender para punto de conexión en Android admite la instalación en ambos modos de dispositivos inscritos: el administrador de dispositivos heredado y los modos de Android Enterprise. **Actualmente, los dispositivos de propiedad personal con perfil de trabajo y las inscripciones de dispositivos de usuario totalmente administrados de propiedad corporativa se admiten en Android Enterprise. La compatibilidad con otros modos de Android Enterprise se anunciará cuando esté listo.**

- La implementación de Microsoft Defender para punto de conexión en Android se realiza a través de Microsoft Intune (MDM). Para obtener más información, consulte [Implementación de Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md).
- Instalación de Microsoft Defender para punto de conexión en dispositivos que no están inscritos mediante Intune administración de dispositivos móviles (MDM), consulte [Configuración de señales de riesgo de Microsoft Defender para punto de conexión en la directiva de protección de aplicaciones (MAM).](android-configure-mam.md)

> [!NOTE]
> **Microsoft Defender para punto de conexión en Android ya está disponible en [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx).**
>
> Puede conectarse a Google Play desde Intune para implementar Microsoft Defender para punto de conexión aplicación, a través del administrador de dispositivos y Android Enterprise modos de inscripción.

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Configuración de Microsoft Defender para punto de conexión en Android

Las instrucciones sobre cómo configurar Microsoft Defender para punto de conexión en las características de Android están disponibles en [Configurar Microsoft Defender para punto de conexión en Android características](android-configure.md).

## <a name="related-topics"></a>Temas relacionados

- [Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md)
- [Configurar Microsoft Defender para punto de conexión en funciones de Android](android-configure.md)
- [Aspectos básicos de la administración de aplicaciones móviles (MAM)](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
