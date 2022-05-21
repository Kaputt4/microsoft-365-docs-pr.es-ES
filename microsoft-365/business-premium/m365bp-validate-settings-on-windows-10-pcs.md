---
title: Validación de la configuración de protección de aplicaciones para equipos Windows 10
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
description: Obtenga información sobre cómo comprobar que la configuración de protección de aplicaciones de Microsoft 365 para empresas surtió efecto en los dispositivos Windows 10 de los usuarios.
ms.openlocfilehash: daaf9f03b9b4abdac25076ca6e6fcd42d0982bb6
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65623901"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>Validación de la configuración de protección de dispositivos para equipos Windows 10

> [!NOTE]
> Microsoft Defender para Empresas se está implementando para los clientes de Microsoft 365 Empresa Premium desde el 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para los dispositivos. [Más información sobre Defender para Empresas](../security/defender-business/mdb-overview.md).

## <a name="verify-that-windows-10-device-policies-are-set"></a>Compruebe que Windows 10 directivas de dispositivo están establecidas

Después de [configurar las directivas de dispositivo](../business-premium/m365bp-protection-settings-for-windows-10-devices.md), la directiva puede tardar hasta unas horas en surtir efecto en los dispositivos de los usuarios. Puede confirmar que las directivas surtieron efecto examinando varias pantallas de Windows Configuración en los dispositivos de los usuarios. Dado que los usuarios no podrán modificar la configuración de Windows Update y Antivirus de Microsoft Defender en sus dispositivos Windows 10, muchas opciones se atenuarán.
  
1. Vaya a **Configuración** \> **Actualizar &amp; seguridad** \> **Windows Update** \> **Opciones de reinicio** y confirme que toda la configuración está atenuada.

    ![Todas las opciones de reinicio están atenuadas.](../business-premium/media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vaya a **Configuración** \> **Actualizar &amp; seguridad** \> **Windows Update** \> **Opciones avanzadas** y confirme que toda la configuración está atenuada.

    ![Windows las opciones de actualizaciones avanzadas están atenuadas.](../business-premium/media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Vaya a **Configuración** \> **Actualizar &amp; seguridad** \> **Windows Update** \> Opciones \> **avanzadas** **Elija cómo se entregan las actualizaciones**.

    Confirme que puede ver el mensaje (en rojo) de que algunas configuraciones están ocultas o administradas por su organización y que todas las opciones están atenuadas.

    ![Elegir cómo se entregan las actualizaciones en la página indica que la organización oculta o administra la configuración.](../business-premium/media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir el Windows Defender Security Center, vaya a **Configuración** \> **Update &amp; security** \> **Windows Defender** \> haga clic en **Open Windows Defender Security Center** \> **Virus thread &amp; protection** \> **Virus &amp; threat protection configuración**.

5. Compruebe que todas las opciones estén atenuadas.

    ![La configuración de protección contra virus y amenazas está atenuada.](../business-premium/media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 para la documentación y los recursos empresariales](/admin)

[Establecimiento de configuraciones de dispositivos para Windows 10 equipos](../business-premium/m365bp-protection-settings-for-windows-10-devices.md)
 [Prácticas más seguras para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)
