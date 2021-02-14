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
description: Aprende a comprobar que la configuración de protección de aplicaciones de Microsoft 365 para empresas ha tenido efecto en los dispositivos Windows 10 de los usuarios.
ms.openlocfilehash: 39aee3bc811cb0090d58f9a282de7a8162c097b3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403598"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validar la configuración de protección de dispositivos en equipos con Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Comprobar que las directivas de dispositivo de Windows 10 están establecidas

Después de [configurar las directivas de dispositivos,](protection-settings-for-windows-10-pcs.md)la directiva puede tardar hasta unas horas en tener efecto en los dispositivos de los usuarios. Para confirmar que las directivas se han hecho efectivas, mira varias pantallas de configuración de Windows en los dispositivos de los usuarios. Dado que los usuarios no podrán modificar la configuración de Windows Update y antivirus de Windows Defender en sus dispositivos Windows 10, muchas opciones aparecerán atenuadas.
  
1. Ve a Opciones **de** seguridad de Actualización de configuración de Reinicio de Windows \> **&amp;** \> **Update** y confirma que \>  todas las opciones están atenuadas. 
    
    ![Todas las opciones de reinicio están atenuadas.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Ve a Opciones **avanzadas de** Windows Update de seguridad de La actualización de configuración y confirma que todas las opciones \> **&amp;** están \>  \>  atenuadas. 
    
    ![Todas las opciones de actualizaciones avanzadas de Windows están atenuadas.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Ve a Opciones **avanzadas** de Windows Update \> **&amp; de** seguridad de La actualización \>  \> **de configuración** \> **Elige cómo se entregan las actualizaciones.**
    
    Confirme que puede ver el mensaje (en rojo) en el que se indica que algunas opciones de configuración están ocultas o administradas por su organización y que todas las opciones están atenuadas.
    
    ![Elegir cómo se entregan las actualizaciones en la página indica que la configuración está oculta o administrada por la organización.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir el Centro de seguridad  Windows Defender, vaya a Configuración de actualización de seguridad Windows Defender haga clic en Abrir \> **&amp;** \>  \> **Windows Defender** \> **Protección &amp;** \> **&amp;** antivirus del Centro de seguridad. 
    
5. Compruebe que todas las opciones están atenuadas. 
    
    ![La configuración de protección contra virus y amenazas está atenuada.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Temas relacionados

[Documentación y recursos de Microsoft 365 para empresas](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introducción a Microsoft 365 para empresas](microsoft-365-business-overview.md)
  
[Administrar Microsoft 365 para empresas](manage.md)
  
[Establecer configuraciones de dispositivo para equipos PC con Windows 10](protection-settings-for-windows-10-pcs.md)
  

