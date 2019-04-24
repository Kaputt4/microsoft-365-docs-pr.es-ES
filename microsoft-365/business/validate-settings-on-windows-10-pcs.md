---
title: Validar la configuración de protección de aplicaciones en PC con Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Obtenga información sobre cómo validar la configuración de protección de aplicaciones empresariales de Microsoft 365 en dispositivos Windows 10.
ms.openlocfilehash: 5ab91d65fa7bd40ebc118df217c9711b7bbfe7a4
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286778"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validar la configuración de protección de dispositivos en equipos con Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Comprobar que las directivas de dispositivos de Windows 10 están definidas

Una vez que haya [configurado las directivas de dispositivos](protection-settings-for-windows-10-pcs.md), la Directiva puede tardar hasta unas pocas horas en aplicarse a los dispositivos de los usuarios. Para confirmar que las directivas tuvieron efecto, consulte varias pantallas de configuración de Windows en los dispositivos de los usuarios. Como los usuarios no podrán modificar la configuración de Windows Update y antivirus de Windows Defender en sus dispositivos con Windows 10, se mostrarán muchas opciones en gris.
  
1. Vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **** restart y confirme que todas las opciones están atenuadas. 
    
    ![Todas las opciones de reInicio están atenuadas.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vaya a **configuración** \> **actualizar &amp; seguridad** \> **Windows Update** \> **Opciones avanzadas** y confirme que toda la configuración está atenuada. 
    
    ![Las opciones de actualizaciones avanzadas de Windows están en gris.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Ir a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **Opciones** \> avanzadas **Elija cómo se entregan las actualizaciones**.
    
    Confirme que puede ver el mensaje (en rojo) que la organización está ocultando o administrando, y que todas las opciones están atenuadas.
    
    ![Elegir cómo se entregan las actualizaciones la página indica que la configuración está oculta o administrada por la organización.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir el centro de seguridad de Windows Defender, vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Defender** \> , haga clic en abrir el tema de \> **** **antivirus &amp; del centro de seguridad de Windows Defender ** \> **configuración de &amp; protección contra amenazas de virus**de protección. 
    
5. Compruebe que todas las opciones están atenuadas. 
    
    ![La configuración de protección contra virus y amenazas está atenuada.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Temas relacionados

[Documentación y recursos de Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introducción a Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Administrar Microsoft 365 Business](manage.md)
  
[Establecer configuraciones de dispositivo para equipos PC con Windows 10](protection-settings-for-windows-10-pcs.md)
  

