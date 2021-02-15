---
title: Inscribir dispositivos iOS/iPadOS y Android en el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use esta Guía del entorno de pruebas para inscribir dispositivos en su entorno de prueba de Microsoft 365 y administrarlos de forma remota.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367088"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Inscribir dispositivos iOS y Android en su entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo se puede usar para Entornos de prueba de Microsoft 365 para empresas.*

En este artículo se describe cómo inscribir y probar las capacidades básicas de administración de dispositivos móviles para dispositivos iOS/iPadOS y Android en su entorno de prueba de Microsoft 365 para empresas.

La inscripción de dispositivos iOS/iPadOS y Android en el entorno de prueba consta de tres fases:
- [Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Inscribir los dispositivos iOS/iPadOS y Android](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: Administrar los dispositivos iOS/iPadOS y Android de forma remota](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vaya a La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas

Si desea inscribir dispositivos iOS/iPadOS y Android de forma ligera con los requisitos mínimos, siga las instrucciones de [configuración básica ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Si desea inscribir dispositivos iOS/iPadOS y Android en una empresa simulada, siga las instrucciones de autenticación [de paso a través.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Las pruebas de licencias automatizadas y pertenencia a grupos no requieren el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos, y puede experimentar con ella en un entorno que representa una organización típica.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: Inscribir los dispositivos iOS y Android

Si estás considerando una solución de administración de dispositivos móviles (MDM) para administrar los dispositivos, puedes usar Microsoft Intune. Al trabajar con cualquier proveedor de MDM, incluido Intune, los dispositivos se "inscriben". Cuando se inscriba, recibirán las características y opciones de configuración que configure. 

En Intune, hay varias formas de inscribir los dispositivos iOS/iPadOS y Android. Puedes elegir la opción de inscripción que mejor se adapte a tu organización. Para obtener más información e instrucciones, vea los artículos siguientes:

- [Guía de implementación: Inscribir dispositivos iOS y iPadOS en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Guía de implementación: Inscribir dispositivos Android en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Si estás listo para usar Intune para la administración de dispositivos y quieres obtener algunas instrucciones, la siguiente información puede ayudarte:

- [Introducción a la administración de dispositivos](/mem/intune/fundamentals/what-is-device-management)
- [Tutorial: Tutorial de Intune en Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Guía de implementación: Configurar o pasar a Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: Administrar los dispositivos iOS y Android de forma remota

Microsoft Intune proporciona la característica de restablecimiento de código de acceso y bloqueo remoto. Si alguien pierde su dispositivo, puedes bloquearlo de forma remota. Si alguien olvida su código de acceso, puedes restablecerlo de forma remota.

- Para bloquear de forma remota un dispositivo iOS/iPadOS o Android, vea Bloqueo remoto de [dispositivos con Intune.](/mem/intune/remote-actions/device-remote-lock)
- Para restablecer el código de acceso de forma remota, consulta Restablecer o quitar un código de acceso de [dispositivo en Intune.](/mem/intune/remote-actions/device-passcode-reset)

Para otras tareas que puedes ejecutar de forma remota, consulta [las acciones de dispositivo disponibles.](/mem/intune/remote-actions/device-management#available-device-actions)
    
## <a name="next-step"></a>Paso siguiente

Explore características y [funcionalidades adicionales](m365-enterprise-test-lab-guides.md#mobile-device-management) de administración de dispositivos móviles en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)
  
[Directivas de cumplimiento de dispositivos para su entorno de prueba de Microsoft 365 para empresas](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
