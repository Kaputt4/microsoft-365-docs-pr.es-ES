---
title: Directivas de cumplimiento de dispositivos para Microsoft 365 entorno de prueba empresarial
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
description: Use esta Guía del laboratorio de pruebas para agregar directivas de cumplimiento de dispositivos de Intune a Microsoft 365 entorno de prueba empresarial.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367100"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Directivas de cumplimiento de dispositivos para Microsoft 365 entorno de prueba empresarial

*Esta Guía del laboratorio de pruebas solo se puede usar Microsoft 365 entornos de prueba empresariales.*

En este artículo se describe cómo agregar una directiva de cumplimiento de dispositivos de Intune para Windows 10 dispositivos y Aplicaciones Microsoft 365 para empresas a su entorno Microsoft 365 de prueba empresarial.

Agregar una directiva de cumplimiento de dispositivos de Intune implica dos fases:
- [Fase 1: Crear su Microsoft 365 entorno de prueba empresarial](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Crear una directiva de cumplimiento de dispositivos para Windows 10 dispositivos](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear su Microsoft 365 entorno de prueba empresarial

Si desea configurar directivas MAM solo de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar directivas MAM en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Las pruebas de licencias automatizadas y pertenencia a grupos no requieren el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Crear una directiva de cumplimiento de dispositivos para Windows 10 dispositivos

En esta fase, creas una directiva de cumplimiento de dispositivos para Windows 10 dispositivos. Esta fase usa Microsoft Intune y el [centro Microsoft Endpoint Manager administración](https://go.microsoft.com/fwlink/?linkid=2109431) para agregar un grupo y crear una directiva de cumplimiento.

1. Vaya al Centro [Microsoft 365 administración](https://admin.microsoft.com)e inicie sesión en su Microsoft 365 de laboratorio de pruebas con su cuenta de administrador global. Seleccione el **centro Endpoint Manager** administración. Se [abre Endpoint Manager centro de administración.](https://go.microsoft.com/fwlink/?linkid=2109431)

    Si se muestra un mensaje similar a **You haven't enabled device management yet** message, seleccione Intune como entidad de mdma. Para obtener los pasos específicos, consulte [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).

    El Endpoint Manager de administración se centra en la administración de dispositivos y la administración de aplicaciones. Para obtener un recorrido por este centro de administración, [vea Tutorial: Tutorial de Intune en Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. En **Grupos,** agregue un nuevo **Microsoft 365** **o** grupo de seguridad denominado Managed Windows 10 **device users**, con un **tipo de** pertenencia asignado. En los pasos siguientes, asignará la directiva de cumplimiento a este grupo. 

    Para obtener los pasos específicos y  para obtener información sobre **Microsoft 365** o grupos de seguridad, vea [Agregar grupos para organizar usuarios y dispositivos.](/mem/intune/fundamentals/groups-add)

3. En **Dispositivos,** cree una Windows 10 de cumplimiento. Asigna esta directiva al **grupo de usuarios Windows 10 dispositivos administrados** que creaste.

    En la directiva, puede bloquear contraseñas sencillas, requerir un firewall, requerir que se ejecute el servicio antimalware de Microsoft Defender y mucho más. Normalmente, una directiva de cumplimiento incluye la configuración base o el mínimo mínimo que debe tener cada dispositivo.

    Para ver los pasos específicos y para obtener información sobre las opciones de cumplimiento disponibles que puede configurar, vea Usar directivas de cumplimiento para establecer reglas para los dispositivos [que administra.](/mem/intune/protect/device-compliance-get-started)

Cuando termines, tienes una directiva de cumplimiento de dispositivos para probar miembros en el **grupo Usuarios Windows 10 dispositivo** administrado.
  
## <a name="next-step"></a>Paso siguiente

Explore características [y capacidades adicionales](m365-enterprise-test-lab-guides.md#mobile-device-management) de administración de dispositivos móviles en el entorno de prueba.

## <a name="see-also"></a>Consulte también

[Microsoft 365 guías del laboratorio de pruebas empresariales](m365-enterprise-test-lab-guides.md).
  
[Inscribir dispositivos iOS y Android en su Microsoft 365 entorno de prueba empresarial](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
