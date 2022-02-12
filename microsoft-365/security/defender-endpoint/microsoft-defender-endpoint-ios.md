---
title: Microsoft Defender para punto de conexión en iOS
ms.reviewer: ''
description: Describe cómo instalar y usar Microsoft Defender para endpoint en iOS
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, overview, installation, deploy, uninstallation, intune
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 3e0246160424e76d0ddce42b3dacf74c6b56e43c
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765089"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender para punto de conexión en iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender para Endpoint en iOS** ofrece protección contra la suplantación de identidad (phishing) y las conexiones de red no seguras de sitios web, correos electrónicos y aplicaciones. Todas las alertas estarán disponibles a través de un único panel de cristal en Microsoft 365 Defender portal. El portal ofrece a los equipos de seguridad una vista centralizada de las amenazas en dispositivos iOS junto con otras plataformas.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de extremos de terceros junto con Defender for Endpoint en iOS cause problemas de rendimiento y errores impredecibles del sistema.

## <a name="pre-requisites"></a>Requisitos previos

**Para usuarios finales**

- Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación. Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).

- **Para dispositivos inscritos**:
    - Los dispositivos se [inscriben a](/mem/intune/user-help/enroll-your-device-in-intune-ios) través de la Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune. Esto requiere que al usuario final se le asigne una Microsoft Intune licencia.
    - Portal de empresa de Intune aplicación se puede descargar desde la [Tienda de aplicaciones de Apple](https://apps.apple.com/us/app/intune-company-portal/id719171358).
    
    >[!NOTE]
    >Apple no permite que los usuarios de redireccionamiento descarguen otras aplicaciones de la tienda de aplicaciones, por lo que este paso debe realizarlo el usuario antes de incorporarse a la aplicación De endpoint de Microsoft Defender.
    
    - Los dispositivos están registrados con Azure Active Directory. Esto requiere que el usuario final haya iniciado sesión [a través Microsoft Authenticator aplicación](https://apps.apple.com/app/microsoft-authenticator/id983156458).

- **Para dispositivos no inscritos**: los dispositivos están registrados con Azure Active Directory. Esto requiere que el usuario final haya iniciado sesión [a través Microsoft Authenticator aplicación](https://apps.apple.com/app/microsoft-authenticator/id983156458).

- Para obtener más información sobre cómo asignar licencias, vea [Asignar licencias a los usuarios](/azure/active-directory/users-groups-roles/licensing-groups-assign).

**Para administradores**

- Acceso al portal Microsoft 365 Defender web.

- Acceso a [Microsoft Endpoint Manager de administración](https://go.microsoft.com/fwlink/?linkid=2109431), para:
   - Implemente la aplicación en grupos de usuarios inscritos en su organización.
   - Configurar Microsoft Defender para señales de riesgo de extremo en la directiva de protección de aplicaciones (MAM)


    > [!NOTE]
    > - Microsoft Defender para endpoint ahora amplía la protección a los datos de una organización dentro de una aplicación administrada para aquellos que no usan la administración de dispositivos móviles (MDM), pero que usan Intune para administrar aplicaciones móviles. También amplía esta compatibilidad a los clientes que usan otras soluciones de administración de movilidad empresarial, mientras que sigue usando Intune para la administración de aplicaciones móviles [(MAM).](/mem/intune/apps/mam-faq)
    > - Además, Microsoft Defender para Endpoint ya admite dispositivos inscritos mediante la administración de dispositivos móviles (MDM) de Intune.  

**Requisitos del sistema**

- Dispositivo iOS que ejecuta iOS 12.0 y posteriores. También se admiten iPads.

- El dispositivo está inscrito con la aplicación [Portal de empresa de Intune o](https://apps.apple.com/us/app/intune-company-portal/id719171358) está registrado con Azure Active Directory a través [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458) con la misma cuenta.

## <a name="installation-instructions"></a>Instrucciones de instalación

La implementación de Microsoft Defender para endpoint en iOS se puede realizar a través de Microsoft Endpoint Manager (MEM) y se admiten dispositivos supervisados y no supervisados. Los usuarios finales también pueden instalar directamente la aplicación desde la [Tienda de aplicaciones de Apple](https://aka.ms/mdatpiosappstore).

- Para obtener información sobre la implementación en dispositivos inscritos mediante Microsoft Endpoint Manager o Intune, consulte [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).
- Para obtener información sobre cómo usar Defender para endpoint en la directiva de protección de aplicaciones (MAM), consulta Configurar la directiva de protección de aplicaciones para incluir [las señales de riesgo de Defender for Endpoint (MAM)](ios-install-unmanaged.md)

## <a name="resources"></a>Recursos

- Manténgase informado sobre las próximas versiones visitando Novedades de [Microsoft Defender para endpoint en iOS](ios-whatsnew.md) o nuestro [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).

- Proporcionar comentarios a través del sistema de comentarios desde la aplicación o a través de la [consola de seguridad unificada](https://security.microsoft.com)

## <a name="next-steps"></a>Siguientes pasos

- [Implementar Microsoft Defender para endpoint en iOS a través de Intune para dispositivos inscritos](ios-install.md)
- [Configurar la directiva de protección de aplicaciones para incluir las señales de riesgo de Defender for Endpoint (MAM)](ios-install-unmanaged.md)
- [Configurar Microsoft Defender para endpoint en características de iOS](ios-configure-features.md)
- [Configurar la directiva de acceso condicional en función de la puntuación de riesgo del dispositivo de Microsoft Defender para el extremo](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)
- [Aspectos básicos de la administración de aplicaciones móviles (MAM)](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
