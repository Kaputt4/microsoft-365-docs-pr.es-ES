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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Obtén información sobre cómo comprobar que la configuración de protección de aplicaciones de Microsoft 365 para empresas ha tenido efecto en los dispositivos Windows 10 de los usuarios.
ms.openlocfilehash: ff99b3a4fce49aebdb5c72f51e46678a7821e186
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912422"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validar la configuración de protección de dispositivos en equipos con Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Comprobar que las directivas de dispositivo de Windows 10 están establecidas

Después de [configurar directivas de dispositivos,](protection-settings-for-windows-10-pcs.md)la directiva puede tardar hasta unas horas en tener efecto en los dispositivos de los usuarios. Puedes confirmar que las directivas se han hecho efectivas si ves varias pantallas de configuración de Windows en los dispositivos de los usuarios. Dado que los usuarios no podrán modificar la configuración de Windows Update y Windows Defender Antivirus en sus dispositivos Windows 10, muchas opciones se atenuarán.
  
1. Ve a **Configuración Actualizar** seguridad Opciones de reinicio de Windows Update y confirma que todas las opciones \> **&amp;** están \>  \>  atenuadas. 
    
    ![Todas las opciones reiniciar están atenuadas.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Ve a **Configuración** Actualizar seguridad Opciones avanzadas de Windows Update y confirma que todas las opciones \> **&amp;** \>  \>  están atenuadas. 
    
    ![Las opciones de actualizaciones avanzadas de Windows están atenuadas.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Ve a **Configuración** Actualizar seguridad Opciones avanzadas de Windows \> **&amp;** \> **Update** \>  \> **Elegir cómo se entregan las actualizaciones.**
    
    Confirme que puede ver el mensaje (en rojo) de que algunas opciones de configuración están ocultas o administradas por la organización y todas las opciones están atenuadas.
    
    ![Elegir cómo se entregan las actualizaciones en la página indica que la configuración está oculta o administrada por la organización.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir el Centro Windows Defender seguridad,  vaya a Configuración Actualizar seguridad Windows Defender haga clic en Abrir Windows Defender Protección contra virus del Centro de seguridad Configuración de protección contra amenazas \> **&amp;** \>  \>  \> **&amp;** \> **&amp; de virus**. 
    
5. Compruebe que todas las opciones están atenuadas. 
    
    ![La configuración de protección contra virus y amenazas está atenuada.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Temas relacionados

[Documentación y recursos de Microsoft 365 para empresas](./index.yml)
  
[Introducción a Microsoft 365 para empresas](microsoft-365-business-overview.md)
  
[Administrar Microsoft 365 para empresas](manage.md)
  
[Establecer configuraciones de dispositivo para equipos PC con Windows 10](protection-settings-for-windows-10-pcs.md)
