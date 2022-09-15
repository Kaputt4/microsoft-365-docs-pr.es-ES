---
title: Microsoft Defender para punto de conexión en iOS
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para punto de conexión en iOS
keywords: microsoft, defender, Microsoft Defender para punto de conexión, ios, overview, installation, deploy, uninstallation, intune
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 641addf07516fd09ebc3ca167374c9b1ee25282c
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67700144"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender para punto de conexión en iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender para punto de conexión en iOS** ofrece protección contra suplantación de identidad (phishing) y conexiones de red no seguras desde sitios web, correos electrónicos y aplicaciones. Todas las alertas estarán disponibles a través de un único panel de cristal en el portal de Microsoft 365 Defender. El portal proporciona a los equipos de seguridad una vista centralizada de las amenazas en dispositivos iOS junto con otras plataformas.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Defender para punto de conexión en iOS provoque problemas de rendimiento y errores imprevisibles del sistema.

## <a name="prerequisites"></a>Requisitos previos

**Para los usuarios finales**

- Microsoft Defender para punto de conexión licencia asignada a los usuarios finales de la aplicación. Consulte [Microsoft Defender para punto de conexión requisitos de licencia](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).

- **Para dispositivos inscritos**:
    - Los dispositivos se [inscriben](/mem/intune/user-help/enroll-your-device-in-intune-ios) a través de la aplicación Portal de empresa de Intune para aplicar Intune directivas de cumplimiento de dispositivos. Esto requiere que al usuario final se le asigne una licencia de Microsoft Intune.
    - Portal de empresa de Intune aplicación se puede descargar desde el [App Store de Apple](https://apps.apple.com/us/app/intune-company-portal/id719171358).
    
    >[!NOTE]
    >Apple no permite redirigir a los usuarios para que descarguen otras aplicaciones de la tienda de aplicaciones, por lo que el usuario debe realizar este paso antes de incorporarse a Microsoft Defender para punto de conexión aplicación).


    - Los dispositivos están registrados en Azure Active Directory. Esto requiere que el usuario final inicie sesión a través de la [aplicación Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).

- **Para dispositivos no inscritos**: los dispositivos se registran con Azure Active Directory. Esto requiere que el usuario final inicie sesión a través de la [aplicación Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).

- Para obtener más información sobre cómo asignar licencias, consulte [Asignación de licencias a usuarios](/azure/active-directory/users-groups-roles/licensing-groups-assign).

**Para administradores**

- Acceso al portal de Microsoft 365 Defender.

- Acceso al [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) para:
   - Implemente la aplicación en grupos de usuarios inscritos en su organización.
   - Configuración de señales de riesgo Microsoft Defender para punto de conexión en la directiva de protección de aplicaciones (MAM)


    > [!NOTE]
    > - Microsoft Defender para punto de conexión ahora amplía la protección a los datos de una organización dentro de una aplicación administrada para aquellos que no usan la administración de dispositivos móviles (MDM), pero usan Intune para administrar aplicaciones móviles. También amplía esta compatibilidad a los clientes que usan otras soluciones de administración de movilidad empresarial, mientras siguen usando Intune para [la administración de aplicaciones móviles (MAM).](/mem/intune/apps/mam-faq)
    > - Además, Microsoft Defender para punto de conexión ya admite dispositivos inscritos mediante Intune administración de dispositivos móviles (MDM).  

**Requisitos del sistema**

- Dispositivo iOS que ejecuta iOS 12.0 y versiones posteriores. También se admiten iPads. *Tenga en cuenta que a partir del 31 de marzo de 2022, la versión mínima admitida de iOS por Microsoft Defender para punto de conexión será iOS 13.0.*

- El dispositivo está inscrito con la [aplicación Portal de empresa de Intune](https://apps.apple.com/us/app/intune-company-portal/id719171358) o está registrado en Azure Active Directory a través de [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458) con la misma cuenta.

 > [!NOTE]
 > Microsoft Defender para punto de conexión en iOS no se admite actualmente mientras se usa la inscripción de usuarios de iOS.

## <a name="installation-instructions"></a>Instrucciones de instalación

La implementación de Microsoft Defender para punto de conexión en iOS se puede realizar a través de Microsoft Endpoint Manager (MEM) y se admiten dispositivos supervisados y no supervisados. Los usuarios finales también pueden instalar directamente la aplicación desde la [tienda de aplicaciones de Apple](https://aka.ms/mdatpiosappstore).

- Para obtener información sobre la implementación en dispositivos inscritos a través de Microsoft Endpoint Manager o Intune, consulte [Implementación de Microsoft Defender para punto de conexión en iOS](ios-install.md).
- Para obtener información sobre el uso de Defender para punto de conexión en la directiva de protección de aplicaciones (MAM), consulte Configuración de la [directiva de protección de aplicaciones para incluir señales de riesgo de Defender para punto de conexión (MAM)](ios-install-unmanaged.md)

## <a name="resources"></a>Recursos

- Manténgase informado sobre las próximas versiones visitando [Novedades de Microsoft Defender para punto de conexión en iOS](ios-whatsnew.md) o en nuestro [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).

- Proporcionar comentarios a través del sistema de comentarios desde la aplicación o a través de la [consola de seguridad unificada](https://security.microsoft.com)

## <a name="next-steps"></a>Pasos siguientes

- [Implementación de Microsoft Defender para punto de conexión en iOS mediante Intune para dispositivos inscritos](ios-install.md)
- [Configuración de la directiva de protección de aplicaciones para incluir señales de riesgo de Defender para punto de conexión (MAM)](ios-install-unmanaged.md)
- [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
- [Configuración de la directiva de acceso condicional en función de la puntuación de riesgo del dispositivo de Microsoft Defender para punto de conexión](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)
- [Aspectos básicos de la administración de aplicaciones móviles (MAM)](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
