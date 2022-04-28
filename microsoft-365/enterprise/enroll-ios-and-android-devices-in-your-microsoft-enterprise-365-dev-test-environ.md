---
title: Inscripción de dispositivos iOS/iPadOS y Android en el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use esta guía de laboratorio de pruebas para inscribir dispositivos en el entorno de prueba de Microsoft 365 y administrarlos de forma remota.
ms.openlocfilehash: 5cefabf6b995754f6febe117776ad2de97443df0
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092941"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Inscripción de dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas

*Esta Guía de laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*

En este artículo se describe cómo inscribir y probar funcionalidades básicas de administración de dispositivos móviles para dispositivos iOS/iPadOS y Android en el entorno de prueba de Microsoft 365 para empresas.

La inscripción de dispositivos iOS/iPadOS y Android en el entorno de prueba implica tres fases:
- [Fase 1: Compilación de la Microsoft 365 para el entorno de prueba empresarial](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Inscripción de dispositivos iOS/iPadOS y Android](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: Administración remota de dispositivos iOS/iPadOS y Android](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guías de laboratorio de prueba para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila Microsoft 365 para la pila guía del laboratorio de pruebas empresarial, vaya a [Microsoft 365 para la pila de la guía del laboratorio de pruebas empresarial](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Compilación de la Microsoft 365 para el entorno de prueba empresarial

Si desea inscribir dispositivos iOS/iPadOS y Android de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea inscribir dispositivos iOS/iPadOS y Android en una empresa simulada, siga las instrucciones de [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de licencias automatizadas y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos, y puede experimentar con ella en un entorno que representa una organización típica.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: Inscripción de dispositivos iOS y Android

Si está pensando en una solución de administración de dispositivos móviles (MDM) para administrar los dispositivos, puede usar Microsoft Intune. Cuando se trabaja con cualquier proveedor de MDM, incluidos los Intune, los dispositivos se "inscriben". Cuando se inscriben, reciben las características y la configuración que se configuran. 

En Intune, hay varias maneras de inscribir los dispositivos iOS/iPadOS y Android. Puede elegir la opción de inscripción que mejor funcione para su organización. Para obtener más información e instrucciones, consulte los artículos siguientes:

- [Guía de implementación: inscripción de dispositivos iOS y iPadOS en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Guía de implementación: Inscripción de dispositivos Android en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Si está listo para usar Intune para la administración de dispositivos y quiere alguna guía, puede que la siguiente información le ayude:

- [Información sobre la administración de dispositivos](/mem/intune/fundamentals/what-is-device-management)
- [Tutorial: Paso a paso de Intune en Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Guía de implementación: Cómo configurar o pasar a Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: Administración remota de dispositivos iOS y Android

Microsoft Intune proporciona la característica de restablecimiento de código de acceso y bloqueo remoto. Si alguien pierde su dispositivo, puede bloquearlo de forma remota. Si alguien olvida su código de acceso, puede restablecerlo de forma remota.

- Para bloquear de forma remota un dispositivo iOS/iPadOS o Android, consulte [Bloqueo remoto de dispositivos con Intune](/mem/intune/remote-actions/device-remote-lock).
- Para restablecer de forma remota el código de acceso, consulte [Restablecer o quitar un código de acceso de dispositivo en Intune](/mem/intune/remote-actions/device-passcode-reset).

Para ver tareas adicionales que puede ejecutar de forma remota, consulte [acciones de dispositivo disponibles](/mem/intune/remote-actions/device-management#available-device-actions).
    
## <a name="next-step"></a>Paso siguiente

Explore características y funcionalidades adicionales de [administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en el entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)
  
[Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
