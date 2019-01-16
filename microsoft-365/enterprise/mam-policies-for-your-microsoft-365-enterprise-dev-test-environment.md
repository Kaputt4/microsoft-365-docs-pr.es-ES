---
title: Entorno de prueba de las directivas de cumplimiento de normas de dispositivo para su empresa de 365 de Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía de laboratorio de prueba para agregar el entorno de prueba de directivas de cumplimiento de dispositivo Intune a la empresa de 365 de Microsoft.
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871788"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Entorno de prueba de las directivas de cumplimiento de normas de dispositivo para su empresa de 365 de Microsoft

Con las instrucciones de este artículo, se agrega una directiva de cumplimiento de normas de dispositivo Intune al entorno de prueba de Microsoft 365 Enterprise.

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise

Si desea configurar directivas de MAM en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Las pruebas automatizadas de licencias y pertenencia a grupos no requiere el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Crear una directiva de cumplimiento de normas de dispositivo para los dispositivos de Windows 10

En esta fase, se crea una directiva de cumplimiento de normas de dispositivo para dispositivos Windows 10.
  
1. Vaya al portal de Office en ([https://office.com](https://office.com)) e inicie sesión en su suscripción de prueba de Office 365 con su cuenta de administrador global.
    
2. En una nueva ficha del explorador, abra el portal de Azure en [https://portal.azure.com](https://portal.azure.com).

3. En la ficha portal Azure en el explorador, en el panel de navegación, haga clic en **todos los servicios**, escriba **Intune**y, a continuación, haga clic en **Intune**.
    
4. Si ve un mensaje **no ha habilitado la administración de dispositivos todavía** en el servidor blade de **Intune de Microsoft** , haga clic en él. En el servidor blade de **autoridad de administración de dispositivos móviles** , haga clic en **Intune MDM entidad**y, a continuación, haga clic en **Elegir**. Actualización de la ficha del explorador.
    
5. En el panel de navegación izquierdo, haga clic en **Grupos**.
    
6. En el servidor blade de **grupos a todos los grupos** , haga clic en **+ nuevo grupo**.
    
7. En el servidor blade de **grupo** , seleccione **Office 365** para **tipo de grupo?**, escriba **los usuarios de dispositivos administrados 10 de Windows** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, a continuación, haga clic en **crear**. 
    
8. Cierre la hoja **Grupo**.
    
11. Cierre el servidor blade de **grupos a todos los grupos** .
    
12. En el servidor blade **Intune de Microsoft** , en la lista de **tareas rápidas** , haga clic en **crear una directiva de cumplimiento**.
    
13. En la hoja **Perfiles de directiva de cumplimiento**, haga clic en **Crear directiva**.
    
14. En el módulo de **Directiva de crear** , en **nombre**, escriba **10 de Windows**. En la **plataforma**, seleccione **10 y versiones posteriores de Windows**, haga clic en **Aceptar** en el servidor blade de la **Directiva de cumplimiento del 10 de Windows** y, a continuación, haga clic en **crear**. Cierre el blade **10 de Windows** .
    
15. En el servidor blade de **Perfiles de directivas de cumplimiento** , haga clic en el nombre de la directiva de **Windows 10** .
    
16. En el módulo **10 de Windows** , haga clic en **asignaciones**y, a continuación, haga clic en **Seleccionar grupos que se incluirán**.
    
17. En el servidor blade **seleccione grupos para incluir** , haga clic en el grupo de **usuarios de dispositivos administrados 10 de Windows** y, a continuación, haga clic en **Seleccionar**.
    
18. Haga clic en **Guardar**y, a continuación, cierre el módulo **Windows 10 - las asignaciones** .
    
19. Cierre la hoja **Perfiles de directiva de cumplimiento**.
    
20. En el servidor blade **Intune de Microsoft** , haga clic en **aplicaciones de cliente** en el panel de navegación izquierdo.
    
21. En el módulo de **Aplicaciones de cliente** , haga clic en **aplicaciones**y, a continuación, haga clic en **Agregar**. 

22. En el módulo de **aplicación de agregar** , seleccione el **tipo de aplicación**y, a continuación, seleccione **Windows 10** en **El conjunto de aplicaciones de Office 365**.

23. Haga clic en **Configurar el conjunto de aplicaciones**y, a continuación, haga clic en **Aceptar**.

24. Haga clic en **Información de conjunto de aplicaciones de una aplicación**, escriba **aplicaciones de Office para Windows 10** en **Nombre del conjunto de aplicaciones**, **aplicaciones de Office para Windows 10** en la **Descripción del conjunto de aplicaciones**y, a continuación, haga clic en **Aceptar**.

25. Haga clic en **Configuración del conjunto de programas de aplicación**, seleccione **anual punto y** en el **canal de actualización de**y, a continuación, haga clic en **Aceptar**.

26. En el módulo de **aplicación de agregar** , haga clic en **Agregar**.

Ahora dispone de una directiva de cumplimiento de normas de dispositivo para probar las aplicaciones seleccionadas en la directiva de cumplimiento de normas de dispositivo de **Windows 10** y para los miembros del grupo de **usuarios de dispositivos administrados 10 de Windows** . 
  
## <a name="next-step"></a>Paso siguiente

Explorar las características adicionales de [administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).
  
[Inscriba sus dispositivos iOS y Android en su entorno de desarrollo y prueba de Microsoft Enterprise 365](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Movilidad de la empresa + seguridad (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
