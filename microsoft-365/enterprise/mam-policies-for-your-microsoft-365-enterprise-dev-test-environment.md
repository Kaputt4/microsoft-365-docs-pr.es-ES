---
title: Directivas MAM para sus entornos de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía de laboratorio de prueba para agregar el entorno de prueba de directivas de administración (MAM) de Intune aplicaciones móviles para la empresa de 365 de Microsoft.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871788"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a>Directivas MAM para sus entornos de prueba de Microsoft 365 Enterprise

Con las instrucciones de este artículo, se agrega el entorno de prueba de directivas de administración (MAM) de Intune aplicaciones móviles para la empresa de 365 de Microsoft.

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise

Si desea configurar directivas de MAM en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Las pruebas automatizadas de licencias y pertenencia a grupos no requiere el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica. 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a>Fase 2: Crear e implementar directivas de MAM para dispositivos iOS y Android

En esta fase, creará e implementará dos directivas de MAM diferentes: una para dispositivos iOS y otra para dispositivos Android.
  
1. Vaya al portal de Office 365 en ([https://portal.office.com](https://portal.office.com)) e inicie sesión en su suscripción de prueba de Office 365 con su cuenta de administrador global.
    
2. En una nueva ficha del explorador, abra el portal de Azure en [https://portal.azure.com](https://portal.azure.com).

3. En la ficha portal Azure en Internet Explorer, en el panel de navegación, haga clic en **todos los servicios**, escriba **Intune**y, a continuación, haga clic en **Intune**.
    
4. Si ve un mensaje **no ha habilitado la administración de dispositivos todavía** en el servidor blade de **Intune de Microsoft** , haga clic en él. En el servidor blade de **autoridad de administración de dispositivos móviles** , haga clic en **Intune MDM entidad**y, a continuación, haga clic en **Elegir**. Actualización de la ficha del explorador.
    
5. En el panel de navegación izquierdo, haga clic en **Grupos**.
    
6. En el servidor blade de **grupos a todos los grupos** , haga clic en **+ nuevo grupo**.
    
7. En el servidor blade de **grupo** , seleccione **Office 365** para **tipo de grupo?**, escriba **administrado a los usuarios de dispositivos iOS** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, a continuación, haga clic en **crear**. 
    
8. Cierre la hoja **Grupo**.
    
9. En el servidor blade de **grupos a todos los grupos** , haga clic en **Agregar**.
    
10. En el servidor blade de **grupo** , seleccione **Office 365** para **tipo de grupo?**, escriba **usuario de dispositivos Android administrado** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, a continuación, haga clic en **crear**.
    
11. Cierre el servidor blade de **grupos a todos los grupos** .
    
12. En la hoja **Intune**, en la lista **Tareas rápidas**, haga clic en **Crear una directiva de cumplimiento**.
    
13. En la hoja **Perfiles de directiva de cumplimiento**, haga clic en **Crear directiva**.
    
14. En la hoja **Crear directiva**, en **Nombre**, escriba **iOS**. En **Plataforma**, seleccione **iOS**, haga clic en **Aceptar** en la hoja **Directiva de cumplimiento de iOS** y, a continuación, haga clic en **Crear**.
    
15. En la hoja **Perfiles de directiva de cumplimiento**, haga clic en **Crear directiva**.
    
16. En la hoja **Crear directiva**, en **Nombre**, escriba **Android**. En **Plataforma**, seleccione **Android**, haga clic en **Aceptar** en la hoja **Directiva de cumplimiento de Android** y, a continuación, haga clic en **Crear**.
    
17. En la hoja **Perfiles de directiva de cumplimiento**, haga clic en el nombre de directiva **Android**.
    
18. En el panel de navegación izquierdo de la hoja **Android - Propiedades**, haga clic en **Tareas** y, a continuación, en **Seleccionar grupos**.
    
19. En la hoja **Seleccionar grupos**, haga clic en **Usuarios de dispositivos Android administrados** y después haga clic en **Seleccionar**.
    
20. Haga clic en **Guardar**y, a continuación, cierre el blade **Android - las asignaciones** .
    
21. En la hoja **Perfiles de directiva de cumplimiento**, haga clic en el nombre de directiva **iOS**.
    
22. En el panel de navegación izquierdo de la hoja **iOS - Propiedades**, haga clic en **Tareas** y, a continuación, en **Seleccionar grupos**.
    
23. En la hoja **Seleccionar grupos**, haga clic en el grupo **Usuarios de dispositivos iOS administrados** y después haga clic en **Seleccionar**.
    
24. Haga clic en **Guardar**y, a continuación, cierre el blade **iOS - las asignaciones** .
    
25. Cierre la hoja **Perfiles de directiva de cumplimiento**.
    
26. En la hoja **Intune**, haga clic en **Administrar aplicaciones** en el panel de navegación izquierdo.
    
27. En la hoja **Aplicaciones móviles**, haga clic en **Aplicaciones**.
    
28. En la lista de aplicaciones, haga clic en **PowerPoint**,  
    
29. En la hoja **Información general sobre PowerPoint**, haga clic en **Tareas > Seleccionar grupos > Dispositivos iOS administrados > Seleccionar**. En **Tipo**, seleccione **Disponible** y, a continuación, haga clic en **Guardar**.
    
30. Repita el paso 29 para las aplicaciones siguientes:
    
    - Outlook para Android
    
    - Word para iOS
    
    - Excel para iOS
    
    - Outlook para iOS
    
    - Microsoft Dynamics CRM en iPad para iOS
    
    - Microsoft Dynamics CRM en iPhone para iOS
    
    - Dynamics CRM para teléfonos Android
    
    - Dynamics CRM para tabletas Android
    
    - Excel para Android
    
    - Word para Android
    
    - OneNote para iOS
    
31. Cierre la hoja **Aplicaciones móviles - Aplicaciones**.
    
32. En la hoja **Aplicaciones móviles**, haga clic en **Directivas de protección de aplicaciones**.
    
33. En la hoja **Directivas de protección de aplicaciones**, haga clic en **Agregar directiva**.
    
34. En la hoja **Agregar directiva**, escriba **iOS** y, a continuación, haga clic en **Elegir aplicaciones obligatorias**.
    
35. En la hoja **Aplicaciones**, haga clic en **PowerPoint**, **Microsoft Dynamics CRM en iPhone**, **Excel**, **Microsoft Dynamics CRM en iPhone**, **Word**, **OneNote** y **Outlook**, y, a continuación, en **Seleccionar**.
    
36. En la hoja **Agregar una directiva**, haga clic en **Crear**.
    
37. En la hoja **Directivas de protección de aplicaciones**, haga clic en **Agregar directiva**.
    
38. En la hoja **Agregar una directiva**, escriba **Android**, seleccione **Android** en **Plataforma** y, a continuación, haga clic en **Elegir aplicaciones obligatorias**.
    
39. En la hoja **Aplicaciones**, haga clic en **PowerPoint**, **Dynamics CRM para tabletas**, **Excel**, **Word**, **Outlook** y **Dynamics CRM para teléfonos** y, a continuación, en **Seleccionar**.
    
40. En la hoja **Agregar una directiva**, haga clic en **Crear**.
    
Ahora tiene dos directivas de MAM, una para dispositivos iOS y otra para dispositivos Android, y está preparado para experimentar con la configuración de prueba para las aplicaciones seleccionadas. 
  
## <a name="next-step"></a>Paso siguiente

Explorar las características adicionales de [administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).
  
[Inscriba sus dispositivos iOS y Android en su entorno de desarrollo y prueba de Microsoft Enterprise 365](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Movilidad de la empresa + seguridad (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
