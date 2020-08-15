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
ms.openlocfilehash: 3c77a7ea8ddc5120a2ce53fa0834dab213502657
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686759"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

Con las instrucciones de este artículo, agregará una directiva de cumplimiento de dispositivos de Intune para dispositivos Windows 10 y Microsoft 365 apps for Enterprise a su Microsoft 365 para el entorno de prueba Enterprise.

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere configurar directivas de MAM de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10

En esta fase, creará una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.
  
1. Vaya al [centro de administración de microsoft 365](https://admin.microsoft.com) e inicie sesión en su suscripción de laboratorio de pruebas de Microsoft 365 con su cuenta de administrador global.
    
2. En una pestaña nueva del explorador, abra Azure portal en [https://portal.azure.com](https://portal.azure.com) .

3. En la pestaña Azure portal del explorador, escriba **Intune** en el cuadro de búsqueda y, a continuación, haga clic en **Intune**.
    
4. Si ve un mensaje **que indica que no ha habilitado la administración de dispositivos todavía** en el panel de **Microsoft Intune** , haga clic en él. En el panel **entidad de administración de dispositivos móviles** , haga clic en **Intune MDM**y, a continuación, haga clic en **elegir**. Actualice la pestaña del explorador.
    
5. En el panel izquierdo de navegación, haga clic en **Grupos**.
    
6. En el panel **grupos todos los grupos** , haga clic en **+ nuevo grupo**.
    
7. En el panel de **Grupo** , seleccione **Microsoft 365** o **seguridad** para **tipo de grupo?**, escriba **usuarios de dispositivos de Windows 10 administrados** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, a continuación, haga clic en **crear**. 
    
8. Haga clic en **Microsoft Intune**. En el panel de **Microsoft Intune** , en la lista **tareas rápidas** , haga clic en **crear una directiva de cumplimiento**.
    
9. En el panel **perfiles de directiva de cumplimiento** , haga clic en **crear Directiva**.
    
10. En el panel **crear Directiva** , en **nombre**, escriba **Windows 10**. En **plataforma**, seleccione **Windows 10 y versiones posteriores**, haga clic en **Aceptar** en el panel **Directiva de cumplimiento de Windows 10** y, a continuación, haga clic en **crear**. 
    
11. Haga clic en **perfiles de directiva de cumplimiento**y, a continuación, en el nombre de directiva de **Windows 10** .
    
12. En el panel **Windows 10** , haga clic en **tareas**y, a continuación, haga clic en **seleccionar grupos para incluir**.
    
13. En el panel **seleccionar grupos para incluir** , haga clic en el grupo **usuarios de dispositivos de Windows 10 administrados** y, a continuación, haga clic en **seleccionar**.
    
14. Haga clic en **Guardar**, haga clic en **Microsoft Intune-Overview**y, a continuación, haga clic en **aplicaciones cliente** en el panel de navegación izquierdo.
    
15. En el panel **aplicaciones cliente** , haga clic en **aplicaciones**y, a continuación, en **Agregar**. 

16. En el panel **Agregar aplicación** , seleccione **tipo de aplicación**y, después, seleccione **Windows 10** en **Microsoft 365 Suite**.

17. En el panel **Agregar aplicación** , seleccione **información del conjunto de aplicaciones**.
 
18. En el panel de **información del conjunto de aplicaciones** , escriba **Microsoft 365 apps for Enterprise** en **el nombre del conjunto** y la descripción del **conjunto**.
Haga clic en Aceptar.

19. En el panel **Agregar aplicación** , seleccione **configurar conjunto de aplicaciones**y, a continuación, haga clic en **Aceptar**.

20. En el panel **Agregar aplicación** , seleccione **configuración del conjunto de aplicaciones**.

21. En **canal de actualización**, seleccione **empresa semianual**y, a continuación, haga clic en **Aceptar**.

22. En el panel **Agregar aplicación** , haga clic en **Agregar**.

Ahora tiene una directiva de cumplimiento de dispositivos para probar las aplicaciones seleccionadas en la Directiva de cumplimiento de dispositivos de **Windows 10** y para los miembros del grupo de **usuarios de dispositivos de Windows 10 administrados** . Tenga en cuenta que, al seleccionar Microsoft 365 como tipo de grupo, se crearán recursos adicionales. 
  
## <a name="next-step"></a>Paso siguiente

Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.

## <a name="see-also"></a>Recursos adicionales

[Microsoft 365 para las guías del laboratorio de pruebas de la empresa](m365-enterprise-test-lab-guides.md).
  
[Inscribir dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
