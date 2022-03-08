---
title: Validar la configuración de protección de aplicaciones para equipos con Windows 10
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
description: Obtén información sobre cómo comprobar que la configuración de protección de aplicaciones de Microsoft 365 para empresas ha tenido efecto en los dispositivos Windows 10 de los usuarios.
ms.openlocfilehash: be25acb8414705c48a8763a0530ec2a70565de83
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313599"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>Validar la configuración de protección de dispositivos para equipos con Windows 10

> [!NOTE]
> Microsoft Defender para empresas se está implementando para los clientes de Microsoft 365 Empresa Premium, a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para dispositivos. [Obtenga más información sobre Defender para empresas](../../security/defender-business/mdb-overview.md).

## <a name="verify-that-windows-10-device-policies-are-set"></a>Comprobar que las directivas de dispositivo de Windows 10 están establecidas

Después de [configurar directivas de dispositivo](protection-settings-for-windows-10-pcs.md), la directiva puede tardar hasta unas horas en tener efecto en los dispositivos de los usuarios. Puedes confirmar que las directivas se han hecho efectivas si ves varias pantallas de configuración de Windows en los dispositivos de los usuarios. Dado que los usuarios no podrán modificar la configuración de Windows Update y Antivirus de Microsoft Defender en sus dispositivos Windows 10, muchas opciones se atenuarán.
  
1. Ve a **Configuración Actualizar** \> **seguridad Opciones &amp;** \> de **reinicio de Windows Update** \> y confirma que todas las opciones están atenuadas. 
    
    ![Todas las opciones reiniciar están atenuadas.](../../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Ve a **Configuración** \> **Actualizar seguridad Opciones &amp;** \> **avanzadas de Windows Update** \> y confirma que todas las opciones están atenuadas. 
    
    ![Las opciones de actualizaciones avanzadas de Windows están atenuadas.](../../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Ve a **Configuración Actualizar** \> **seguridad Opciones &amp;** \> **avanzadas de Windows Update** \>  \> **Elige cómo se entregan las actualizaciones**.
    
    Confirme que puede ver el mensaje (en rojo) de que algunas opciones de configuración están ocultas o administradas por la organización y todas las opciones están atenuadas.
    
    ![Elegir cómo se entregan las actualizaciones en la página indica que la configuración está oculta o administrada por la organización.](../../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir el Centro Windows Defender seguridad,  \> **&amp;** \>  \> vaya a Configuración Actualizar seguridad Windows Defender haga clic en Abrir **Windows Defender Protección** \> **&amp;** \> **&amp;** contra virus del Centro de seguridad Configuración de protección contra amenazas de virus. 
    
5. Compruebe que todas las opciones están atenuadas. 
    
    ![La configuración de protección contra virus y amenazas está atenuada.](../../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-content"></a>Contenido relacionado

[Documentación y recursos de Microsoft 365 para empresas](/admin)\
[Establecer configuraciones de dispositivos para equipos con](protection-settings-for-windows-10-pcs.md)
 Windows 10 [Principales 10 formas de proteger los planes de Microsoft 365 para empresas](../security-and-compliance/secure-your-business-data.md)