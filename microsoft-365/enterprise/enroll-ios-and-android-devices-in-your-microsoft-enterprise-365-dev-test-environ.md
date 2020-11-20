---
title: Inscriba iOS/iPados y dispositivos Android en el entorno de prueba de Microsoft 365 para empresas
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
description: Use esta guía del laboratorio de pruebas para inscribir dispositivos en el entorno de prueba de Microsoft 365 y administrarlos de forma remota.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367088"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Inscribir dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

En este artículo se describe cómo inscribir y probar capacidades básicas de administración de dispositivos móviles para iOS/iPados y dispositivos Android en el entorno de prueba de Microsoft 365 para empresas.

La inscripción en iOS/iPados y dispositivos Android en el entorno de prueba implica tres fases:
- [Fase 1: crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: inscribir a iOS/iPados y dispositivos Android](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: administrar de forma remota sus dispositivos Android/iPad y iOS](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si desea inscribir iOS/iPados y dispositivos Android de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea inscribir iOS/iPados y dispositivos Android en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y puede experimentar con ella en un entorno que represente una organización típica.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: inscribir los dispositivos Android y iOS

Si está pensando en una solución de administración de dispositivos móviles (MDM) para administrar los dispositivos, puede usar Microsoft Intune. Cuando se trabaja con un proveedor de MDM, que incluye Intune, los dispositivos se "inscriben". Cuando se inscriben, reciben las características y la configuración que configure. 

En Intune, hay varias formas de inscribir sus dispositivos iOS/iPad y Android. Puede elegir la opción de inscripción que mejor se adapte a su organización. Para obtener más información y orientación, vea los siguientes artículos:

- [Guía de implementación: inscribir dispositivos iOS y iPados en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Guía de implementación: inscribir dispositivos Android en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Si está listo para usar Intune para la administración de dispositivos y desea tener alguna orientación, la siguiente información puede serle útil:

- [Introducción a la administración de dispositivos](/mem/intune/fundamentals/what-is-device-management)
- [Tutorial: Guía de Intune en Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Guía de implementación: configuración o traslado a Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: administrar los dispositivos iOS y Android de forma remota

Microsoft Intune proporciona características de bloqueo remoto y restablecimiento de código de acceso. Si alguien pierde el dispositivo, puedes bloquear el dispositivo de forma remota. Si alguien olvida su código de acceso, puede restablecerlo de forma remota.

- Para bloquear de forma remota un dispositivo iOS/iPado o Android, vea [bloquear dispositivos de forma remota con Intune](/mem/intune/remote-actions/device-remote-lock).
- Para restablecer el código de acceso de forma remota, vea [restablecer o quitar el código de acceso del dispositivo en Intune](/mem/intune/remote-actions/device-passcode-reset).

Para las tareas adicionales que puede ejecutar de forma remota, consulte [available Device Actions](/mem/intune/remote-actions/device-management#available-device-actions).
    
## <a name="next-step"></a>Paso siguiente

Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)
  
[Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
