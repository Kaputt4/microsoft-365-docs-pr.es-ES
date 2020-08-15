---
title: Inscribir dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use esta guía del laboratorio de pruebas para inscribir dispositivos en el entorno de prueba de Microsoft 365 y administrarlos de forma remota.
ms.openlocfilehash: b4a95b2c7e58239c0a8d0d3b5045e7337f43de6b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686015"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Inscribir dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

Si sigue las instrucciones que se proporcionan en este artículo, podrá inscribir y probar las funciones básicas de administración de dispositivos móviles para iOS y dispositivos Android en el entorno de prueba de Microsoft 365 para empresas.

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere inscribir dispositivos iOS y Android de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea inscribir dispositivos iOS y Android en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: inscribir los dispositivos Android y iOS

En primer lugar, siga las instrucciones de [instalar e iniciar sesión en la aplicación portal de empresa](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) para personalizar la aplicación del portal de empresa de Microsoft Intune para su entorno de prueba.

A continuación, siga las instrucciones que se [definen en configurar el acceso a los recursos de la empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) para inscribir un dispositivo iOS.

A continuación, siga las instrucciones de [inscribir el dispositivo Android en Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) para inscribir un dispositivo Android.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: administrar los dispositivos iOS y Android de forma remota

Microsoft Intune proporciona capacidades de restablecimiento de código de acceso y bloqueo remoto. Si alguien pierde su dispositivo, puede bloquearlo de forma remota. Si alguien olvida su código de acceso, puede restablecerlo de forma remota.
  
Para bloquear de forma remota un dispositivo iOS o Android:

1. Inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con las credenciales de su cuenta de administrador global.
2. En la pestaña Azure portal del explorador, escriba **Intune** en el cuadro de búsqueda y, a continuación, haga clic en **Intune**.
3. Haga clic en **dispositivos > todos los dispositivos**.
4. En la lista de dispositivos, haga clic en un dispositivo iOS o Android y, a continuación, haga clic en la acción **bloqueo remoto** .

    
Para restablecer el código de acceso de forma remota:

1. Si es necesario, inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con las credenciales de su cuenta de administrador global.
2. En la pestaña Azure portal del explorador, escriba **Intune** en el cuadro de búsqueda y, a continuación, haga clic en **Intune**.
3. Haga clic en **dispositivos > todos los dispositivos**.
4. En la lista de dispositivos que administra, haga clic en un dispositivo iOS o Android y elija **... Más**. A continuación, elija la acción quitar el dispositivo de **código** de acceso remoto.

Para experimentación adicional, consulte [available Device Actions](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Paso siguiente

Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)
  
[Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

