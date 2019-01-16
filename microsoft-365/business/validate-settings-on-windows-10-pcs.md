---
title: Validar la configuración de protección de aplicaciones en PC con Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Obtenga información sobre cómo validar la configuración de protección de aplicación de Microsoft 365 Business en los dispositivos de Windows 10.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871326"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validar la configuración de la protección de dispositivo en equipos con Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Comprobar que se establecen las directivas de dispositivo de Windows 10

Después de [configurar las directivas de dispositivos](protection-settings-for-windows-10-pcs.md), pueden tardar hasta unas cuantas horas para la directiva surta efecto en los dispositivos de los usuarios. Puede confirmar que las directivas entraron en vigor observando varias pantallas de configuración de Windows en los dispositivos de los usuarios. Debido a que los usuarios no podrán modificar la configuración de actualización de Windows y Windows Defender Antivirus en sus dispositivos de Windows 10, una gran cantidad de esas opciones estará desactivada.
  
1. Vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **Opciones de reinicio** y confirme que no todas las opciones están habilitadas. 
    
    ![Todas las opciones de reinicio no están habilitadas.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **Opciones avanzadas** y confirme que no todas las opciones están habilitadas. 
    
    ![Opciones avanzadas de Windows para las actualizaciones son todos atenuadas.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Vaya a **configuración** \> **actualización &amp; seguridad** \> **Windows Update** \> **Opciones avanzadas** \> **Elegir cómo se entregan las actualizaciones**.
    
    Confirme que puede ver el mensaje (en rojo) que algunas opciones de configuración están ocultos o administrados por la organización, y todas las opciones no están habilitadas.
    
    ![Elegir cómo se entregan las actualizaciones de página indica configuración está oculta o administrada por la organización.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir el centro de seguridad de Windows Defender, vaya a **configuración de** \> **actualización &amp; seguridad** \> **Windows Defender** \> haga clic en **Centro de seguridad de abrir Windows Defender** \> **Virus &amp; subproceso protección** \> **Virus &amp; configuración de la protección de amenazas**. 
    
5. Compruebe que todas las opciones no están habilitadas. 
    
    ![La configuración de la protección contra Virus y amenazas no está habilitada.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Temas relacionados

[Documentación y recursos de Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introducción a Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Administrar Microsoft 365 Business](manage.md)
  
[Establecer configuraciones de dispositivo para equipos PC con Windows 10](protection-settings-for-windows-10-pcs.md)
  

