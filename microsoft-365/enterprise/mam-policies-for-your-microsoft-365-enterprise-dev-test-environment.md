---
title: Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del laboratorio de pruebas para agregar directivas de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487417"
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

En esta fase, cree una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.
  
1. Vaya al [centro de administración de microsoft 365](https://admin.microsoft.com) e inicie sesión en su suscripción de laboratorio de pruebas de Microsoft 365 con su cuenta de administrador global.
1. En una pestaña nueva del explorador, abra Azure portal en [https://portal.azure.com](https://portal.azure.com) .
1. En el cuadro de búsqueda de Azure portal, escriba **Intune**y, a continuación, seleccione **Intune**.
1. Si ve un mensaje **que indica que no ha habilitado la administración de dispositivos todavía** en el panel de **Microsoft Intune** , selecciónelo. En el panel **entidad de administración de dispositivos móviles** , seleccione **Intune MDM Authority**y, a continuación, seleccione **elegir**.
1. Actualice la pestaña del explorador.
1. En el panel de navegación izquierdo, seleccione **grupos**.
1. En el panel **grupos todos los grupos** , seleccione **+ nuevo grupo**.
1. En el panel de **Grupo** , **seleccione Microsoft 365** o **seguridad** para **tipo de grupo**, escriba usuarios de dispositivos de **Windows 10 administrados** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, después, seleccione **crear**.
1. Seleccione **Microsoft Intune**.
1. En el panel de **Microsoft Intune** , en la lista **tareas rápidas** , seleccione **crear una directiva de cumplimiento**.
1. En el panel **perfiles de directiva de cumplimiento** , seleccione **crear Directiva**.
1. En el panel **crear Directiva** , en **nombre**, escriba **Windows 10**. En **plataforma**, seleccione **Windows 10 y versiones posteriores**, seleccione **Aceptar** en el panel **Directiva de cumplimiento de Windows 10** y, a continuación, seleccione **crear**.
1. Selecciona **perfiles de directiva de cumplimiento**y, a continuación, selecciona el nombre de la Directiva de **Windows 10** .
1. En el panel de **Windows 10** , seleccione **tareas**y, a continuación, seleccione **seleccionar grupos para incluirlos**.
1. En el panel **seleccionar grupos para incluir** , seleccione el grupo de **usuarios de dispositivos de Windows 10 administrados** y, a continuación, seleccione **seleccionar**.
1. Seleccione **Guardar**, seleccione **Microsoft Intune-Overview**y, a continuación, seleccione **aplicaciones cliente** en el panel de navegación izquierdo.
1. En el panel **aplicaciones cliente** , seleccione **aplicaciones**y, después, seleccione **Agregar**.
1. En el panel **Agregar aplicación** , seleccione **tipo de aplicación**y, después, seleccione **Windows 10** en **Microsoft 365 Suite**.
1. En el panel **Agregar aplicación** , seleccione **información del conjunto de aplicaciones**.
1. En el panel de **información del conjunto de aplicaciones** , escriba **Microsoft 365 apps for Enterprise** en el **nombre del conjunto** de aplicaciones y la **Descripción del conjunto**y, después, seleccione **Aceptar**.
1. En el panel **Agregar aplicación** , seleccione **configurar conjunto de aplicaciones**y, después, haga clic en **Aceptar**.
1. En el panel **Agregar aplicación** , seleccione **configuración del conjunto de aplicaciones**.
1. En **canal de actualización**, seleccione **empresa semianual**y, a continuación, seleccione **Aceptar**.
1. En el panel **Agregar aplicación** , seleccione **Agregar**.

Ahora tiene una directiva de cumplimiento de dispositivos para probar las aplicaciones seleccionadas en la Directiva de cumplimiento de dispositivos de **Windows 10** y para los miembros del grupo de **usuarios de dispositivos de Windows 10 administrados** . Tenga en cuenta que seleccionar **Microsoft 365** como el tipo de grupo crea recursos adicionales.
  
## <a name="next-step"></a>Paso siguiente

Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Microsoft 365 para las guías del laboratorio de pruebas de la empresa](m365-enterprise-test-lab-guides.md).
  
[Inscribir dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
