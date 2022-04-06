---
title: Validar la configuración de protección de aplicaciones Windows 10 equipos
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
description: Obtén información sobre cómo comprobar que la Microsoft 365 de protección de aplicaciones empresariales ha tenido efecto en los dispositivos Windows 10 usuarios.
ms.openlocfilehash: 47c220b36050376d1eddf7d83435f175e00f88cb
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64633291"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>Validar la configuración de protección de dispositivos Windows 10 equipos

> [!NOTE]
> Microsoft Defender für Unternehmen se está implementando para Microsoft 365 Business Premium clientes, a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para dispositivos. [Obtenga más información sobre Defender para empresas](../../security/defender-business/mdb-overview.md).

## <a name="verify-that-windows-10-device-policies-are-set"></a>Comprobar que Windows 10 directivas de dispositivo están establecidas

Después de [configurar directivas de dispositivo](../../business-premium/m365bp-protection-settings-for-windows-10-pcs.md), la directiva puede tardar hasta unas horas en tener efecto en los dispositivos de los usuarios. Puede confirmar que las directivas se han hecho efectivas mirando varias Windows Configuración pantallas en los dispositivos de los usuarios. Dado que los usuarios no podrán modificar la configuración de Windows Update y Antivirus de Microsoft Defender en sus dispositivos Windows 10, muchas opciones se atenuarán.
  
1. Ve a **Configuración** \> **Actualizar seguridad &amp; Windows Update** \>  \> **Reiniciar** y confirma que todas las opciones están atenuadas. 
    
    ![Todas las opciones reiniciar están atenuadas.](../../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Ve a **Configuración** \> **Actualizar seguridad &amp; Windows Update** \>  \> **opciones avanzadas** y confirma que todas las opciones están atenuadas. 
    
    ![Windows opciones de actualizaciones avanzadas están atenuadas.](../../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Vaya a **Configuración** \> **Actualizar seguridad &amp; Windows Update** \>  \> **Opciones avanzadas** \> **Elija cómo se entregan las actualizaciones**.
    
    Confirme que puede ver el mensaje (en rojo) de que algunas opciones de configuración están ocultas o administradas por la organización y todas las opciones están atenuadas.
    
    ![Elegir cómo se entregan las actualizaciones en la página indica que la configuración está oculta o administrada por la organización.](../../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir el Centro Windows Defender seguridad, vaya a **Configuración** \> **Actualizar &amp;** \>  \> seguridad Windows Defender haga clic en Abrir Windows Defender **Protección** \> **&amp;** \> **&amp; contra virus del Centro de seguridad Protección contra amenazas de virus configuración**. 
    
5. Compruebe que todas las opciones están atenuadas. 
    
    ![La configuración de protección contra virus y amenazas está atenuada.](../../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 documentación y recursos para empresas](/admin)

[Establecer configuraciones de dispositivos para Windows 10 de PCsTop](../../business-premium/m365bp-protection-settings-for-windows-10-devices.md)
 [10 para proteger Microsoft 365 planes empresariales](../../admin/security-and-compliance/secure-your-business-data.md)
