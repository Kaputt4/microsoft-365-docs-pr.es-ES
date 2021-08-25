---
title: Microsoft Defender para punto de conexión en iOS
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para endpoint en iOS
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, overview, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4dc2d9e0d4ea06b7b51a29be11af4e6316c83bcc
ms.sourcegitcommit: ea4bc3b005d86b029700e56015a47b8cc6dca2a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2021
ms.locfileid: "58509574"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender para punto de conexión en iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender para Endpoint en iOS** ofrece protección contra la suplantación de identidad (phishing) y las conexiones de red no seguras de sitios web, correos electrónicos y aplicaciones. Todas las alertas estarán disponibles a través de un único panel de cristal en el Centro de seguridad de Microsoft Defender. El portal ofrece a los equipos de seguridad una vista centralizada de las amenazas en dispositivos iOS junto con otras plataformas.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de extremos de terceros junto con Defender for Endpoint en iOS cause problemas de rendimiento y errores impredecibles del sistema.

## <a name="pre-requisites"></a>Requisitos previos

**Para usuarios finales**

- Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación. Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

- **Para dispositivos inscritos:** los [](/mem/intune/user-help/enroll-your-device-in-intune-ios) dispositivos se inscriben a través de la aplicación Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune. Esto requiere que al usuario final se le asigne una Microsoft Intune licencia.
    - Portal de empresa de Intune la aplicación se puede descargar desde la [Tienda de aplicaciones de Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Ten en cuenta que Apple no permite que los usuarios redireccionamientos descarguen otras aplicaciones de la tienda de aplicaciones y, por lo tanto, este paso debe realizarlo el usuario antes de incorporarse a la aplicación Microsoft Defender para endpoint.

- **Para dispositivos no** inscritos: los dispositivos están registrados con Azure Active Directory. Esto requiere que el usuario final haya iniciado sesión [a través Microsoft Authenticator aplicación](https://apps.apple.com/app/microsoft-authenticator/id983156458).

- Para obtener más información sobre cómo asignar licencias, vea [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).

**Para administradores**

- Acceso al portal Centro de seguridad de Microsoft Defender web.

- Acceso a [Microsoft Endpoint Manager de administración](https://go.microsoft.com/fwlink/?linkid=2109431), para implementar la aplicación en grupos de usuarios inscritos en su organización.

    > [!NOTE]
    > - Microsoft Defender para endpoint ahora amplía la protección a los datos de una organización dentro de una aplicación administrada para aquellos que no usan la administración de dispositivos móviles (MDM), pero que usan Intune para administrar aplicaciones móviles. También amplía esta compatibilidad a los clientes que usan otras soluciones de administración de movilidad empresarial, mientras que sigue usando Intune para la administración de aplicaciones móviles [(MAM).](/mem/intune/apps/mam-faq)
    > - Además, Microsoft Defender para Endpoint ya admite dispositivos inscritos mediante la administración de dispositivos móviles (MDM) de Intune.  

**Requisitos del sistema**

- Dispositivo iOS que ejecuta iOS 11.0 y posteriores. iPad dispositivos se admiten oficialmente a partir de la versión 1.1.15010101.

- El dispositivo se inscribe con la [aplicación Portal de empresa de Intune o](https://apps.apple.com/us/app/intune-company-portal/id719171358) se registra con Azure Active Directory a través de [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).

## <a name="installation-instructions"></a>Instrucciones de instalación

La implementación de Microsoft Defender para endpoint en iOS se puede realizar a través de Microsoft Endpoint Manager (MEM) y se admiten dispositivos supervisados y no supervisados. Los usuarios finales también pueden instalar directamente la aplicación desde la [Tienda de aplicaciones de Apple](https://aka.ms/mdatpiosappstore).
Para obtener más información, vea [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).

## <a name="resources"></a>Recursos

- Manténgase informado sobre las próximas versiones visitando Novedades de Microsoft Defender para endpoint [en iOS](ios-whatsnew.md) o nuestro [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).

- Proporcionar comentarios a través del sistema de comentarios desde la aplicación o a través del [portal de SecOps](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Siguientes pasos

- [Implementar Microsoft Defender para endpoint en iOS](ios-install.md)
- [Configurar Microsoft Defender para endpoint en características de iOS](ios-configure-features.md)
- [Configurar la directiva de protección de aplicaciones para incluir las señales de riesgo de Defender for Endpoint (MAM)](ios-install-unmanaged.md)
- [Configurar la directiva de acceso condicional en función de la puntuación de riesgo del dispositivo de Microsoft Defender para el extremo](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)
- [Conceptos básicos de administración de aplicaciones móviles (MAM)](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
