---
title: Validar la configuración de protección de aplicaciones en PC con Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Obtenga información sobre cómo comprobar que la configuración de la protección de aplicaciones de Microsoft 365 para empresas surta efecto en los dispositivos Windows 10 de los usuarios.
ms.openlocfilehash: b63681f040b0fe49127693e9cb7aac7ba6c41af6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635712"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validar la configuración de protección de dispositivos en equipos con Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Comprobar que las directivas de dispositivos de Windows 10 están definidas

Una vez que haya [configurado las directivas de dispositivos](protection-settings-for-windows-10-pcs.md), la Directiva puede tardar hasta unas pocas horas en aplicarse a los dispositivos de los usuarios. Para confirmar que las directivas tuvieron efecto, consulte varias pantallas de configuración de Windows en los dispositivos de los usuarios. Como los usuarios no podrán modificar la configuración de Windows Update y antivirus de Windows Defender en sus dispositivos con Windows 10, muchas opciones estarán atenuadas.
  
1. Vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **restart** y confirme que todas las opciones están atenuadas. 
    
    ![Todas las opciones de reinicio están atenuadas.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vaya a **configuración** \> **actualizar &amp; seguridad** \> **Windows Update** \> **Opciones avanzadas** y confirme que toda la configuración está atenuada. 
    
    ![Las opciones de actualizaciones avanzadas de Windows están atenuadas.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Ir a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **Opciones** \> avanzadas **Elija cómo se entregan las actualizaciones**.
    
    Confirme que puede ver el mensaje (en rojo) que la organización está ocultando o administrando, y que todas las opciones están atenuadas.
    
    ![Elegir cómo se entregan las actualizaciones la página indica que la configuración está oculta o administrada por la organización.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir el centro de seguridad de Windows Defender, vaya a **configuración** \> ** &amp; actualización seguridad** \> **Windows Defender** \> haga clic en **abrir el centro** \> de seguridad de Windows Defender configuración de protección frente a **virus &amp; **de protección de ** &amp; subprocesos.** \> 
    
5. Compruebe que todas las opciones están atenuadas. 
    
    ![La configuración de protección contra virus y amenazas está atenuada.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Temas relacionados

[Documentación y recursos de Microsoft 365 para la empresa](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introducción a Microsoft 365 para empresas](microsoft-365-business-overview.md)
  
[Administración de Microsoft 365 para empresas](manage.md)
  
[Establecer configuraciones de dispositivo para equipos PC con Windows 10](protection-settings-for-windows-10-pcs.md)
  

