---
title: ATP de Microsoft Defender para Android
ms.reviewer: ''
description: Describe cómo instalar y usar ATP de Microsoft Defender para Android
keywords: microsoft, defender, atp, android, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 6518b86861fd5d03533bb787d4ee005d7ace1a0c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076867"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a>Microsoft Defender para endpoint para Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se describe cómo instalar, configurar, actualizar y usar Defender para Endpoint para Android.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Defender para Endpoint para Android cause problemas de rendimiento y errores impredecibles del sistema.


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a>Cómo instalar Microsoft Defender para Endpoint para Android

### <a name="prerequisites"></a>Requisitos previos

-   **Para usuarios finales**

    -   Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación. Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   La aplicación Portal de empresa de Intune se puede descargar desde [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) y está disponible en el dispositivo Android.

        -   Además, los dispositivos se pueden inscribir [a](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) través de la aplicación Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune. Esto requiere que al usuario final se le asigne una licencia de Microsoft Intune.

    -   Para obtener más información sobre cómo asignar licencias, vea [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).
        

-   **Para administradores**

    -   Acceso al portal del Centro de seguridad de Microsoft Defender.

        > [!NOTE]
        > Microsoft Intune es la única solución de administración de dispositivos móviles (MDM) compatible para implementar Microsoft Defender para Endpoint para Android. Actualmente, solo se admiten dispositivos inscritos para aplicar las directivas de cumplimiento de dispositivos relacionados con Defender for Endpoint para Android en Intune. 

    -   Accede [al Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)para implementar la aplicación en grupos de usuarios inscritos en tu organización.

### <a name="system-requirements"></a>Requisitos del sistema

-   Dispositivos Android que ejecutan Android 6.0 y versiones posteriores.
-   La aplicación Portal de empresa de Intune se descarga [de Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e se instala. La inscripción de dispositivos es necesaria para que se cumplan las directivas de cumplimiento de dispositivos de Intune.

### <a name="installation-instructions"></a>Instrucciones de instalación

Microsoft Defender para Endpoint para Android admite la instalación en ambos modos de dispositivos inscritos: los modos heredados administrador de dispositivos y Android Enterprise.
**Actualmente, los dispositivos de propiedad personal con perfil de trabajo y las inscripciones de dispositivos de usuario totalmente administrados de propiedad corporativa se admiten en Android Enterprise. La compatibilidad con otros modos de Android Enterprise se anunciará cuando esté listo.**

La implementación de Microsoft Defender para Endpoint para Android se realiza a través de Microsoft Intune (MDM).
Para obtener más información, vea [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).


> [!NOTE]
> **Microsoft Defender para Endpoint para Android ya está disponible en [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)** <br> Puedes conectarte a Google Play desde Intune para implementar la aplicación Microsoft Defender para endpoint, en los modos de inscripción administrador de dispositivos y Android Enterprise. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a>Cómo configurar Microsoft Defender para endpoint para Android

Encontrará instrucciones sobre cómo configurar las características de Microsoft Defender para Endpoint para Android en [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).



## <a name="related-topics"></a>Temas relacionados
- [Implementar Microsoft Defender para endpoint para con Microsoft Intune](android-intune.md)
- [Configurar Microsoft Defender para las características de Punto de conexión para Android](android-configure.md)

