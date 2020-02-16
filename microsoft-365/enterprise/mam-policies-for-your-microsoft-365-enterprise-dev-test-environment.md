---
title: Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 Enterprise
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
description: Use esta guía del laboratorio de pruebas para agregar directivas de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: b0b8bd2d76a3959bbcca749545d9a16e50491d20
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066917"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 Enterprise

*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*

Con las instrucciones de este artículo, agregará una directiva de cumplimiento de dispositivos de Intune para dispositivos Windows 10 y Office 365 ProPlus a su entorno de prueba empresarial 365 de Microsoft.

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise

Si solo quiere configurar directivas de MAM de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10

En esta fase, creará una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.
  
1. Vaya al portal de Office 365 en ([https://portal.office.com](https://portal.office.com)) e inicie sesión en su suscripción de laboratorio de pruebas de Office 365 con su cuenta de administrador global.
    
2. En una pestaña nueva del explorador, abra Azure portal en [https://portal.azure.com](https://portal.azure.com).

3. En la pestaña Azure portal del explorador, escriba **Intune** en el cuadro de búsqueda y, a continuación, haga clic en **Intune**.
    
4. Si ve un mensaje **que indica que no ha habilitado la administración de dispositivos todavía** en el panel de **Microsoft Intune** , haga clic en él. En el panel **entidad de administración de dispositivos móviles** , haga clic en **Intune MDM**y, a continuación, haga clic en **elegir**. Actualice la pestaña del explorador.
    
5. En el panel izquierdo de navegación, haga clic en **Grupos**.
    
6. En el panel **grupos todos los grupos** , haga clic en **+ nuevo grupo**.
    
7. En el panel **Grupo** , seleccione **Office 365** o **seguridad** para **tipo de grupo**, escriba **usuarios de dispositivos de Windows 10 administrados** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, a continuación, haga clic en **crear**. 
    
8. Haga clic en **Microsoft Intune**. En el panel de **Microsoft Intune** , en la lista **tareas rápidas** , haga clic en **crear una directiva de cumplimiento**.
    
9. En el panel **perfiles de directiva de cumplimiento** , haga clic en **crear Directiva**.
    
10. En el panel **crear Directiva** , en **nombre**, escriba **Windows 10**. En **plataforma**, seleccione **Windows 10 y versiones posteriores**, haga clic en **Aceptar** en el panel **Directiva de cumplimiento de Windows 10** y, a continuación, haga clic en **crear**. 
    
11. Haga clic en **perfiles de directiva de cumplimiento**y, a continuación, en el nombre de directiva de **Windows 10** .
    
12. En el panel **Windows 10** , haga clic en **tareas**y, a continuación, haga clic en **seleccionar grupos para incluir**.
    
13. En el panel **seleccionar grupos para incluir** , haga clic en el grupo **usuarios de dispositivos de Windows 10 administrados** y, a continuación, haga clic en **seleccionar**.
    
14. Haga clic en **Guardar**, haga clic en **Microsoft Intune-Overview**y, a continuación, haga clic en **aplicaciones cliente** en el panel de navegación izquierdo.
    
15. En el panel **aplicaciones cliente** , haga clic en **aplicaciones**y, a continuación, en **Agregar**. 

16. En el panel **Agregar aplicación** , seleccione **tipo de aplicación**y, después, seleccione **Windows 10** en **Office 365 Suite**.

17. En el panel **Agregar aplicación** , seleccione **información del conjunto de aplicaciones**.
 
18. En el panel de **información del conjunto de aplicaciones** , escriba **Office 365 ProPlus** en el nombre del **conjunto** de aplicaciones y la **Descripción del conjunto**.
Haga clic en Aceptar.

19. En el panel **Agregar aplicación** , seleccione **configurar conjunto de aplicaciones**y, a continuación, haga clic en **Aceptar**.

20. En el panel **Agregar aplicación** , seleccione **configuración del conjunto de aplicaciones**.

21. En **canal de actualización**, seleccione **semestral**y, a continuación, haga clic en **Aceptar**.

22. En el panel **Agregar aplicación** , haga clic en **Agregar**.

Ahora tiene una directiva de cumplimiento de dispositivos para probar las aplicaciones seleccionadas en la Directiva de cumplimiento de dispositivos de **Windows 10** y para los miembros del grupo de **usuarios de dispositivos de Windows 10 administrados** . Tenga en cuenta que, al seleccionar Office 365 como tipo de grupo, se crearán recursos adicionales. 
  
## <a name="next-step"></a>Paso siguiente

Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías del laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).
  
[Inscribir dispositivos iOS y Android en su entorno de prueba de Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
