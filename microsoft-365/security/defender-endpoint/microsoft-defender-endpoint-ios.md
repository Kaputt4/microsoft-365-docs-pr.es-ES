---
title: Introducción a ATP para iOS de Microsoft Defender
ms.reviewer: ''
description: Describe cómo instalar y usar ATP de Microsoft Defender para iOS
keywords: microsoft, defender, atp, ios, overview, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 72c3cfd51e472bbbda61f0084e131c4298633193
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186994"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a>Microsoft Defender para endpoint para iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender para Endpoint para iOS** ofrecerá protección contra la suplantación de identidad (phishing) y las conexiones de red no seguras de sitios web, correos electrónicos y aplicaciones. Todas las alertas estarán disponibles a través de un único panel de cristal en el Centro de seguridad de Microsoft Defender. El portal ofrece a los equipos de seguridad una vista centralizada de las amenazas en dispositivos iOS junto con otras plataformas.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Defender para Endpoint para iOS cause problemas de rendimiento y errores impredecibles del sistema.

## <a name="pre-requisites"></a>Requisitos previos

**Para usuarios finales**

- Licencia de Microsoft Defender para endpoint asignada a los usuarios finales de la aplicación. Consulta [Requisitos de licencias de Microsoft Defender para puntos de conexión.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

- Los dispositivos se [inscriben a través de](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) la aplicación Portal de empresa de Intune para aplicar directivas de cumplimiento de dispositivos de Intune. Esto requiere que al usuario final se le asigne una licencia de Microsoft Intune.
    - La aplicación Portal de empresa de Intune se puede descargar desde [la Tienda de aplicaciones de Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Ten en cuenta que Apple no permite que los usuarios redireccionamientos descarguen otras aplicaciones de la tienda de aplicaciones y, por lo tanto, este paso debe realizarlo el usuario antes de incorporarse a la aplicación Microsoft Defender para endpoint.

- Para obtener más información sobre cómo asignar licencias, vea [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).

**Para administradores**

- Acceso al portal del Centro de seguridad de Microsoft Defender.

    > [!NOTE]
    > Microsoft Intune es la única solución de administración de dispositivos móviles (MDM) compatible para implementar Microsoft Defender para endpoint para iOS. Actualmente, solo se admiten dispositivos inscritos para aplicar las directivas de cumplimiento de dispositivos relacionados con iOS de Defender for Endpoint en Intune.

- Acceso al [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), para implementar la aplicación en grupos de usuarios inscritos en su organización.

**Requisitos del sistema**

- Dispositivos iOS que ejecutan iOS 11.0 y posteriores. Los dispositivos iPad se admiten oficialmente a partir de la versión 1.1.15010101.

- El dispositivo está inscrito en la [aplicación Portal de empresa de Intune.](https://apps.apple.com/us/app/intune-company-portal/id719171358)

> [!NOTE]
> **Atp de Microsoft Defender (Microsoft Defender para endpoint) para iOS ya está disponible en [Apple App Store](https://aka.ms/mdatpiosappstore).**

## <a name="installation-instructions"></a>Instrucciones de instalación

La implementación de Microsoft Defender para endpoint para iOS se realiza a través de Microsoft Intune (MDM) y se admiten dispositivos supervisados y no supervisados.
Para obtener más información, vea [Deploy Microsoft Defender for Endpoint for iOS](ios-install.md).

## <a name="resources"></a>Recursos

- Manténgase informado acerca de las próximas versiones visitando nuestro [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).

- Proporcionar comentarios a través del sistema de comentarios desde la aplicación o a través del [portal de SecOps](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Siguientes pasos

- [Implementar Microsoft Defender para endpoint para iOS](ios-install.md)
- [Configurar Microsoft Defender para endpoint para características de iOS](ios-configure-features.md)
