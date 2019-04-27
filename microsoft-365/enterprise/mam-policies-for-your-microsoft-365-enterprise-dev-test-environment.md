---
title: Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del laboratorio de pruebas para agregar directivas de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: d20b050bfc56776656bf1d485b2e107a9debe2f7
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353192"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 Enterprise

Con las instrucciones de este artículo, agregará una directiva de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 Enterprise.

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise

Si solo quiere configurar directivas de MAM de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10

En esta fase, creará una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.
  
1. Vaya al portal de Office 365 en ([https://portal.office.com](https://portal.office.com)) e inicie sesión en su suscripción de laboratorio de pruebas de Office 365 con su cuenta de administrador global.
    
2. En una pestaña nueva del explorador, abra Azure portal en [https://portal.azure.com](https://portal.azure.com).

3. En la pestaña Azure portal del explorador, en el panel de navegación, haga clic en **todos los servicios**, escriba Intune y, a continuación, haga clic en **** Intune. ****
    
4. Si ve un mensaje **que indica que no ha habilitado la administración de dispositivos todavía** en la hoja de **Microsoft Intune** , haga clic en él. En la hoja **entidad de administración de dispositivos móviles** , haga clic en Intune **MDM**y, a continuación, haga clic en **elegir**. Actualice la pestaña del explorador.
    
5. En el panel izquierdo de navegación, haga clic en **Grupos**.
    
6. En la hoja **grupos-todos los grupos** , haga clic en **+ nuevo grupo**.
    
7. En la hoja **Grupo** , seleccione **Office 365** para **tipo de grupo**, escriba **usuarios de dispositivos Windows 10 administrados** en **nombre**, seleccione **asignado** en **tipo**de pertenencia y, a continuación, haga clic en **crear**. 
    
8. Cierre la hoja **Grupo**.
    
11. Cierre la hoja **grupos-todos los grupos** .
    
12. En la hoja de **Microsoft Intune** , en la lista **tareas rápidas** , haga clic en **crear una directiva de cumplimiento**.
    
13. En la hoja **Perfiles de directiva de cumplimiento**, haga clic en **Crear directiva**.
    
14. En la hoja **crear Directiva** , en **nombre**, escriba **Windows 10**. En **plataforma**, seleccione **Windows 10 y versiones posteriores**, haga clic en **Aceptar** en la hoja **Directiva de cumplimiento de Windows 10** y, a continuación, haga clic en **crear**. Cierra la hoja de **Windows 10** .
    
15. En la hoja **perfiles de directiva de cumplimiento** , haga clic en el nombre de directiva de **Windows 10** .
    
16. En la hoja de **Windows 10** , haga clic en **tareas**y, a continuación, haga clic en **seleccionar grupos para incluir**.
    
17. En la hoja **seleccionar grupos para incluir** , haga clic en el grupo **usuarios de dispositivos de Windows 10 administrados** y, a continuación, haga clic en **seleccionar**.
    
18. Haga clic en **Guardar**y, a continuación, cierre la hoja **Windows 10-asignaciones** .
    
19. Cierre la hoja **Perfiles de directiva de cumplimiento**.
    
20. En la hoja de **Microsoft Intune** , haga clic en **aplicaciones cliente** en el panel de navegación izquierdo.
    
21. En la hoja **aplicaciones cliente** , haga clic en **aplicaciones**y, a continuación, en **Agregar**. 

22. En la hoja **Agregar aplicación** , seleccione **tipo de aplicación**y, a continuación, seleccione **Windows 10** en **Office 365 Suite**.

23. Haga clic en **configurar conjunto de aplicaciones**y, a continuación, en **Aceptar**.

24. Haga clic en **información del conjunto de aplicaciones**, escriba **Office apps para Windows 10** en **nombre del conjunto**, **aplicaciones de Office para Windows 10** en la **Descripción del paquete**y, a continuación, haga clic en **Aceptar**.

25. Haga clic en **configuración del conjunto de aplicaciones**, seleccione **semestral** en **Actualizar canal**y, a continuación, haga clic en **Aceptar**.

26. En la hoja **Agregar aplicación** , haga clic en **Agregar**.

Ahora tiene una directiva de cumplimiento de dispositivos para probar las aplicaciones seleccionadas en la Directiva de cumplimiento de dispositivos de **Windows 10** y para los miembros del grupo de **usuarios de dispositivos de Windows 10 administrados** . 
  
## <a name="next-step"></a>Paso siguiente

Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías del laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).
  
[Inscribir dispositivos iOS y Android en su entorno de prueba de Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
