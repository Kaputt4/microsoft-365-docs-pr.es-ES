---
title: Validación de la configuración de protección de aplicaciones para equipos Con Windows 10
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
description: Obtenga información sobre cómo comprobar que la configuración de protección de aplicaciones De Microsoft 365 Empresa Premium surtió efecto en los dispositivos Windows 10 de los usuarios.
ms.openlocfilehash: 5ce28946c5df84ffe2bfac9d4cc52d4178996936
ms.sourcegitcommit: c216ffa5da8f431e4380bb133a234ae7d94144c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2022
ms.locfileid: "65893250"
---
# <a name="validate-device-protection-settings-for-windows-10-or-11-pcs"></a>Validación de la configuración de protección de dispositivos para equipos con Windows 10 o 11

> [!NOTE]
> Microsoft Defender para Empresas se está implementando para los clientes de Microsoft 365 Empresa Premium desde el 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para los dispositivos. [Más información sobre Defender para Empresas](../security/defender-business/mdb-overview.md).

## <a name="verify-that-windows-10-or-11-device-policies-are-set"></a>Compruebe que las directivas de dispositivo de Windows 10 o 11 están establecidas

Después de [configurar las directivas de dispositivo](../business-premium/m365bp-protection-settings-for-windows-10-devices.md), la directiva puede tardar hasta unas horas en surtir efecto en los dispositivos de los usuarios. Puede confirmar que las directivas surtieron efecto examinando varias pantallas de configuración de Windows en los dispositivos de los usuarios. Dado que los usuarios no podrán modificar la configuración de Windows Update y antivirus de Microsoft Defender en sus dispositivos Windows 10 o 11, muchas opciones se atenuarán.
  
1. Vaya a **Configuración** \> **Actualizar &amp; seguridad** \> **Opciones de reinicio de** **Windows Update** \> y confirme que toda la configuración está atenuada.

    ![Todas las opciones de reinicio están atenuadas.](../business-premium/media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vaya a **Configuración** \> **Actualizar &amp; seguridad** \> **Opciones avanzadas** de **Windows Update** \> y confirme que toda la configuración está atenuada.

    ![Las opciones de actualizaciones avanzadas de Windows están atenuadas.](../business-premium/media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Vaya a **Configuración Actualizar** \> **&amp; seguridad** \> Opciones \> **avanzadas** de **Windows Update** \> **Elija cómo se entregan las actualizaciones**.

    Confirme que puede ver el mensaje (en rojo) de que algunas configuraciones están ocultas o administradas por su organización y que todas las opciones están atenuadas.

    ![Elegir cómo se entregan las actualizaciones en la página indica que la organización oculta o administra la configuración.](../business-premium/media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir el Centro de seguridad de Windows Defender, vaya a **Configuración** \> **Actualizar &amp; seguridad** \> **De Windows Defender** \> haga clic en Abrir la **configuración de protección contra amenazas de virus &amp;** del Centro **&amp;** \> de seguridad de **Windows Defender**.\>

5. Compruebe que todas las opciones estén atenuadas.

    ![La configuración de protección contra virus y amenazas está atenuada.](../business-premium/media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-content"></a>Contenido relacionado

[Documentación y recursos de Microsoft 365 para empresas](/admin)

[Establecimiento de configuraciones de dispositivos para equipos](../business-premium/m365bp-protection-settings-for-windows-10-devices.md)
 Con Windows 10 [Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)

## <a name="next-objective"></a>Siguiente objetivo

[Revisión y edición de directivas de protección](m365bp-view-edit-create-mdb-policies.md)
