---
title: Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta Guía del laboratorio de pruebas para agregar directivas de cumplimiento de dispositivos Intune a su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 6d75721bd8b4fa6e707111ffd383c20770da0cda
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68178787"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas

*Esta guía de laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*

En este artículo se describe cómo agregar una directiva de cumplimiento de dispositivos de Intune para dispositivos Windows 10 y Aplicaciones Microsoft 365 para empresas al entorno de prueba de Microsoft 365 para empresas.

Agregar una directiva de cumplimiento de dispositivos Intune implica dos fases:
- [Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Creación de una directiva de cumplimiento de dispositivos para dispositivos Windows 10](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guías de laboratorio de prueba para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para enterprise Test Lab Guide Stack (Pila de guía del laboratorio de pruebas empresariales).](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas

Si desea configurar directivas MAM solo de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar directivas MAM en una empresa simulada, siga las instrucciones de [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de licencias automatizadas y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Creación de una directiva de cumplimiento de dispositivos para dispositivos Windows 10

En esta fase, creará una directiva de cumplimiento de dispositivos para Windows 10 dispositivos. Esta fase usa Microsoft Intune y el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) para agregar un grupo y crear una directiva de cumplimiento.

1. Vaya a la [Centro de administración de Microsoft 365](https://admin.microsoft.com), inicie sesión en su suscripción al laboratorio de pruebas de Microsoft 365 con su cuenta de administrador global y seleccione el <a href="https://go.microsoft.com/fwlink/?linkid=2109431" target="_blank">centro de administración de Endpoint Manager</a>.

    Si se muestra un mensaje similar a **No ha habilitado la administración de dispositivos,** seleccione Intune como entidad de MDM. Para conocer los pasos específicos, consulte [Establecer la entidad de administración de dispositivos móviles](/mem/intune/fundamentals/mdm-authority-set).

    El centro de administración de Endpoint Manager se centra en la administración de dispositivos y la administración de aplicaciones. Para ver un recorrido por este centro de administración, consulte [Tutorial: Tutorial: Tutorial Intune en Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. En **Grupos**, agregue un nuevo grupo **de Microsoft 365** o **Seguridad** denominado **Usuarios de dispositivos Windows 10 administrados**, con un tipo **de pertenencia asignado**. En los pasos siguientes, asignará la directiva de cumplimiento a este grupo. 

    Para conocer los pasos específicos y obtener información sobre **Microsoft 365** o grupos **de seguridad** , consulte [Agregar grupos para organizar usuarios y dispositivos](/mem/intune/fundamentals/groups-add).

3. En **Dispositivos**, cree una directiva de cumplimiento de Windows 10. Asigne esta directiva al grupo **de usuarios de dispositivos Windows 10 administrados** que ha creado.

    En la directiva, puede bloquear contraseñas sencillas, requerir un firewall, requerir que se ejecute el servicio Antimalware Microsoft Defender, etc. Normalmente, una directiva de cumplimiento incluye la configuración base o el mínimo que debe tener cada dispositivo.

    Para conocer los pasos específicos y obtener información sobre la configuración de cumplimiento disponible que puede configurar, consulte [Uso de directivas de cumplimiento para establecer reglas para los dispositivos que administra](/mem/intune/protect/device-compliance-get-started).

Cuando haya terminado, tendrá una directiva de cumplimiento de dispositivos para probar miembros en el grupo **Usuarios de dispositivos Windows 10 administrados**.
  
## <a name="next-step"></a>Paso siguiente

Explore características y funcionalidades adicionales de [administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en el entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md).
  
[Inscripción de dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
