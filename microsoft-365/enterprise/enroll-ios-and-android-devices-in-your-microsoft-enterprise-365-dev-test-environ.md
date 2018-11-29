---
title: Inscriba sus dispositivos iOS y Android en su entorno de desarrollo y prueba de Microsoft Enterprise 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use esta guía de laboratorio de prueba para inscribirse dispositivos en su entorno de prueba de Microsoft 365 y administrar de forma remota.
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871296"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Inscriba sus dispositivos iOS y Android en su entorno de desarrollo y prueba de Microsoft Enterprise 365

Siguiendo las instrucciones proporcionadas en este artículo, podrá inscribirse y probar las capacidades de administración básica de dispositivo móvil para iOS y Android dispositivos en su entorno de prueba de Microsoft 365 Enterprise.

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise

Si desea inscribirse iOS y Android dispositivos en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea inscribirse iOS y Android dispositivos en una empresa simulado, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Las pruebas automatizadas de licencias y pertenencia a grupos no requiere el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: Inscribirse los dispositivos Android y iOS

En primer lugar, use las instrucciones de [instalar e inicie sesión en la aplicación de Portal de empresa](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) para personalizar la aplicación de Portal de empresa de Microsoft Intune para su entorno de prueba.

A continuación, siga las instrucciones de [Configurar el acceso a los recursos de empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) para inscribirse en un dispositivo de iOS.

A continuación, siga las instrucciones de [inscripción su dispositivo Android en Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) para inscribirse en un dispositivo Android.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: Administrar su iOS y Android dispositivos de forma remota

Microsoft Intune proporciona capacidades de restablecimiento de bloqueo remoto y código de acceso. Si alguien pierde su dispositivo, puede bloquear el dispositivo de forma remota. Si alguien olvida su código de acceso, puede restablecer de forma remota.
  
Para bloquear una iOS o Android dispositivo de forma remota:

1. Inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con las credenciales de su cuenta de administrador global.
2. Haga clic en **todos los servicios**, escriba **Intune**y, a continuación, haga clic en **Intune**.
3. Haga clic en **dispositivos > todos los dispositivos**.
4. En la lista de dispositivos, haga clic en un dispositivo Android o iOS y, a continuación, haga clic en la acción de **bloqueo remoto** .

    
Para restablecer el código de acceso de forma remota:

1. Si es necesario, inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con las credenciales de su cuenta de administrador global.
2. Haga clic en **todos los servicios**, escriba **Intune**y, a continuación, haga clic en **Intune**.
3. Haga clic en **dispositivos > todos los dispositivos**.
4. En la lista de los dispositivos de administrar, haga clic en un dispositivo Android o iOS y elija **... Más**. A continuación, elija la acción **quitar el código de acceso de** dispositivo remota.

Para realizar otras pruebas, consulte [acciones de dispositivo disponible](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Paso siguiente

Explorar las características adicionales de [administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Consulte también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[Directivas MAM para sus entornos de prueba de Microsoft 365 Enterprise](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Movilidad de la empresa + seguridad (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
