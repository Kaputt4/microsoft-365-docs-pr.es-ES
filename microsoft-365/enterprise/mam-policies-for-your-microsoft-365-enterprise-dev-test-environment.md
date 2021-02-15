---
title: Directivas de cumplimiento de dispositivos para su entorno de prueba de Microsoft 365 para empresas
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
description: Use esta Guía del entorno de pruebas para agregar directivas de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367100"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Directivas de cumplimiento de dispositivos para su entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo se puede usar para Entornos de prueba de Microsoft 365 para empresas.*

En este artículo se describe cómo agregar una directiva de cumplimiento de dispositivos intune para dispositivos Con Windows 10 y Aplicaciones de Microsoft 365 para empresas a su entorno de prueba de Microsoft 365 para empresas.

La adición de una directiva de cumplimiento de dispositivos de Intune consta de dos fases:
- [Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Crear una directiva de cumplimiento de dispositivos para dispositivos Windows 10](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vaya a La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas

Si desea configurar directivas MAM solo de forma ligera con los requisitos mínimos, siga las instrucciones de [la configuración básica ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Si desea configurar directivas MAM en una empresa simulada, siga las instrucciones de autenticación [de paso a través.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Las pruebas de licencias automatizadas y pertenencia a grupos no requieren el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Crear una directiva de cumplimiento de dispositivos para dispositivos Windows 10

En esta fase, crearás una directiva de cumplimiento de dispositivos para dispositivos Con Windows 10. Esta fase usa Microsoft Intune y el Centro de administración [de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) para agregar un grupo y crear una directiva de cumplimiento.

1. Vaya al Centro [de administración de Microsoft 365](https://admin.microsoft.com)e inicie sesión en su suscripción al laboratorio de pruebas de Microsoft 365 con su cuenta de administrador global. Selecciona el Centro **de administración de Endpoint Manager.** Se [abre el Centro de administración de Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)

    Si se muestra un mensaje similar **al que** aún no has habilitado la administración de dispositivos, selecciona Intune como entidad de administración de MDM. Para obtener los pasos específicos, consulte [Establecer la autoridad de administración de dispositivos móviles.](/mem/intune/fundamentals/mdm-authority-set)

    El Centro de administración de Endpoint Manager se centra en la administración de dispositivos y la administración de aplicaciones. Para ver un recorrido por este centro de administración, consulta [Tutorial: Tutorial de Intune en Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)

2. En **Grupos,** agregue un nuevo grupo  de Seguridad o **Microsoft 365** denominado Usuarios de **dispositivos Administrados de Windows 10,** con un **tipo de** pertenencia asignada. En los pasos siguientes, asignará la directiva de cumplimiento a este grupo. 

    Para obtener los pasos específicos y para  obtener información sobre **Microsoft 365** o grupos de seguridad, vea Agregar grupos [para organizar usuarios y dispositivos.](/mem/intune/fundamentals/groups-add)

3. En **Dispositivos,** crea una directiva de cumplimiento de Windows 10. Asigna esta directiva al grupo **de usuarios de dispositivos administrados de Windows 10** que creaste.

    En la directiva, puede bloquear contraseñas sencillas, requerir un firewall, requerir que se ejecute el servicio antimalware de Microsoft Defender y mucho más. Por lo general, una directiva de cumplimiento incluye la configuración básica o el mínimo mínimo que debe tener cada dispositivo.

    Para obtener los pasos específicos y para obtener información sobre las opciones de cumplimiento disponibles que puede configurar, vea Usar directivas de cumplimiento para establecer reglas para los dispositivos [que administra.](/mem/intune/protect/device-compliance-get-started)

Cuando haya terminado, tendrá una directiva de cumplimiento de dispositivos para probar los miembros del grupo de usuarios de dispositivos **administrados de Windows 10.**
  
## <a name="next-step"></a>Paso siguiente

Explore características y [funcionalidades adicionales](m365-enterprise-test-lab-guides.md#mobile-device-management) de administración de dispositivos móviles en su entorno de prueba.

## <a name="see-also"></a>Vea también

Guías del laboratorio de pruebas de [Microsoft 365 para empresas.](m365-enterprise-test-lab-guides.md)
  
[Inscribir dispositivos iOS y Android en su entorno de prueba de Microsoft 365 para empresas](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
