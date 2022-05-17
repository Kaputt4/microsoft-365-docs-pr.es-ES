---
title: Configuración de Clutter para la organización
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Aprenda a habilitar o deshabilitar la característica Clutter para todos o usuarios específicos de la organización mediante Exchange PowerShell. '
ms.openlocfilehash: 64c11b2a8bbce3747727c458a4427f5c0e1b135b
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2022
ms.locfileid: "65437203"
---
# <a name="configure-microsoft-365-clutter-for-your-organization"></a>Configuración de Microsoft 365 Clutter para su organización

> [!TIP]
> [La Bandeja de entrada centrada](../setup/configure-focused-inbox.md) va a reemplazar a Clutter. Más información: [Actualización de la bandeja de entrada centrada y nuestros planes para Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Como administrador, es posible que tenga que administrar la característica Clutter en Microsoft 365. Para activar o desactivar la característica Clutter para los usuarios de la organización, debe usar Exchange PowerShell. (Los usuarios pueden activarlo o desactivarlo con estas instrucciones: [Desactivar o activar El desorden en Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).
  
Consulte [Uso de PowerShell con Exchange Online](/powershell/exchange/exchange-online-powershell) y [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener más información sobre el uso de Exchange PowerShell. Debe tener una cuenta que tenga al menos el rol de administrador del servicio Exchange y la capacidad de conectarse a Exchange Online con PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Activar Clutter con Exchange PowerShell

Puede habilitar Clutter manualmente para un buzón mediante la ejecución del cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter) . También puede ver la configuración de Clutter para los buzones de su organización mediante la ejecución del cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter) . 
  
Activar Clutter para un único usuario llamado Allie Bellew
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Desactivar el desorden mediante Exchange PowerShell

Puede deshabilitar Clutter manualmente para un buzón mediante la ejecución del cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter) . También puede ver la configuración de **Clutter** para los buzones de su organización mediante la ejecución del cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter) . 
  
Desactive Clutter para un único usuario llamado Allie Bellew:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Si usa PowerShell para crear de forma masiva los usuarios, deberá ejecutar [Set-Clutter](/powershell/module/exchange/set-clutter) en el buzón de cada usuario para administrar Clutter. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>¿Cuándo aparece el conmutador Clutter activado o desactivado a los usuarios de Outlook en la Web?
<a name="bkmk_onoff"> </a>

Como administrador, puede volver a habilitar Clutter mediante Exchange PowerShell. Una vez hecho esto, la Bandeja de entrada centrada se desactivará y Clutter volverá a estar activo. 
  
 **Si usa Outlook en la Web con una suscripción de Microsoft 365 Empresa Premium:**
  
- Si el usuario tiene actualmente El desorden habilitado: 
    
  - Aparece la configuración de desorden
    
- Si el usuario tiene habilitada la bandeja de entrada de Focused: 
    
  - La configuración de desorden no aparecerá
    
- Si no está habilitada la bandeja de entrada de Clutter o Focused: 
    
  - Tanto Clutter como Focused Inbox aparecen como opciones en mail Configuración del usuario
    
 **Si usa Outlook.com:**
  
- Si el usuario tiene actualmente El desorden habilitado: 
    
  - Aparece la configuración de desorden
    
- Si el usuario tiene habilitada la bandeja de entrada de Focused: 
    
  - La configuración de desorden no aparecerá
    
- Si no está habilitada la bandeja de entrada de Clutter o Focused: 
    
  - Tanto Clutter como Focused Inbox aparecen como opciones en mail Configuración del usuario
    
- Si el usuario ha habilitado la Bandeja de entrada centrada en algún momento del pasado:
    
  - La configuración de desorden nunca aparecerá
    
    Lo contrario 
    
  - Aparecerá la configuración de desorden
    
## <a name="related-content"></a>Contenido relacionado

[Use Clutter para ordenar mensajes de prioridad baja en Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (artículo)\
[Use Clutter para ordenar mensajes de prioridad baja en OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (artículo)\
[Desactivar el desorden en Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (artículo)
