---
title: Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del laboratorio de pruebas para agregar directivas de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367100"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

En este artículo se describe cómo agregar una directiva de cumplimiento de dispositivos de Intune para dispositivos Windows 10 y Microsoft 365 apps for Enterprise a su Microsoft 365 para el entorno de prueba Enterprise.

La adición de una directiva de cumplimiento de dispositivos de Intune implica dos fases:
- [Fase 1: crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si desea configurar directivas de MAM solo de una manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10

En esta fase, creará una directiva de cumplimiento de dispositivos para dispositivos con Windows 10. En esta fase se usa Microsoft Intune y el [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) para agregar un grupo y crear una directiva de cumplimiento.

1. Vaya al [centro de administración de microsoft 365](https://admin.microsoft.com)y inicie sesión en su suscripción de laboratorio de pruebas de Microsoft 365 con su cuenta de administrador global. Seleccione el centro de administración de **Endpoint Manager** . Se abre el [centro de administración de Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) .

    Si un mensaje es similar a **no ha habilitado la administración de dispositivos, pero** se muestra el mensaje, seleccione Intune como la entidad de MDM. Para conocer los pasos específicos, consulte [establecer la entidad de administración de dispositivos móviles](/mem/intune/fundamentals/mdm-authority-set).

    El centro de administración de Endpoint Manager se centra en la administración de dispositivos y la administración de aplicaciones. Para obtener un paseo por este centro de administración, vea [Tutorial: tutorial Intune en Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. En **grupos**, agregue un nuevo grupo de **seguridad** de **Microsoft 365** o con el nombre **usuarios de dispositivos de Windows 10 administrados**, con un tipo de pertenencia **asignado** . En los pasos siguientes, asignará la Directiva de cumplimiento a este grupo. 

    Para conocer los pasos específicos y para obtener información sobre los grupos de **seguridad** de **Microsoft 365** o, consulte [Add groups to organizte Users and Devices](/mem/intune/fundamentals/groups-add).

3. En **dispositivos**, cree una directiva de cumplimiento de Windows 10. Asigne esta directiva al grupo de **usuarios de dispositivos de Windows 10 administrado** que ha creado.

    En la Directiva, puede bloquear contraseñas sencillas, requerir un firewall, requerir que el servicio antimalware de Microsoft defender se esté ejecutando y mucho más. Una directiva de cumplimiento normalmente incluye la configuración base o el mínimo que debe tener cada dispositivo.

    Para conocer los pasos específicos y obtener información sobre la configuración de cumplimiento disponible que puede configurar, consulte [usar directivas de cumplimiento para establecer las reglas para los dispositivos que administra](/mem/intune/protect/device-compliance-get-started).

Al finalizar, tiene una directiva de cumplimiento de dispositivos para probar los miembros del grupo **administrado de usuarios de dispositivos de Windows 10** .
  
## <a name="next-step"></a>Paso siguiente

Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.

## <a name="see-also"></a>Consulte también

[Microsoft 365 para las guías del laboratorio de pruebas de la empresa](m365-enterprise-test-lab-guides.md).
  
[Inscribir dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
