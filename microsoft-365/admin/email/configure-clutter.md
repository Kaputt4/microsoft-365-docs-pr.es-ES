---
title: Configurar desorden para su organización
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Obtenga información sobre cómo habilitar o deshabilitar la característica Desorden para todos los usuarios o específicos de la organización, mediante Exchange PowerShell. '
ms.openlocfilehash: 059fb8e626a0b05e0224fc89931453aaae43be0b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706121"
---
# <a name="configure-clutter-for-your-organization"></a>Configurar desorden para su organización

> [!TIP]
> [La Bandeja de entrada centrada](../setup/configure-focused-inbox.md) reemplazará a Clutter. Más información: [Actualizar la Bandeja de entrada centrada y nuestros planes para Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Como administrador, es posible que tenga que administrar la característica Desorden en Microsoft 365. Para activar y desactivar la característica Desorden para los usuarios de la organización, debe usar Exchange PowerShell. (Los individuos pueden activarlo o desactivarlo con estas instrucciones: [Desactivar/activar Desorden en Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).
  
Consulte [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Conectar to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener más información sobre Exchange PowerShell. Debe tener una cuenta que tenga al menos el rol de administrador Exchange servicio y la capacidad de conectarse a Exchange Online con PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Activar Clutter con Exchange PowerShell

Puede habilitar Clutter manualmente para un buzón ejecutando el cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter) También puede ver la configuración de desorden para buzones de su organización ejecutando el cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter) 
  
Activar Clutter para un solo usuario llamado Allie Bellew
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Desactivar Clutter con Exchange PowerShell

Puede deshabilitar Clutter manualmente para un buzón ejecutando el cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter) También puede ver la **configuración de desorden** para buzones de su organización ejecutando el cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter) 
  
Desactivar Clutter para un solo usuario llamado Allie Bellew:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Si usa PowerShell para crear masivamente los usuarios, deberá ejecutar [Set-Clutter](/powershell/module/exchange/set-clutter) en el buzón de cada usuario para administrar Clutter. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>¿Cuándo aparece el modificador de encendido y apagado Desorden a los usuarios Outlook en la web?
<a name="bkmk_onoff"> </a>

Como administrador, puede volver a habilitar Clutter con Exchange PowerShell. Una vez hecho esto, la Bandeja de entrada centrada se desactivará y El desorden volverá a estar activo. 
  
 **Si usas Outlook en la web con una Microsoft 365 Empresa Premium suscripción:**
  
- Si el usuario tiene actualmente clutter habilitado: 
    
  - Aparece la configuración de desorden
    
- Si el usuario tiene habilitada la Bandeja de entrada centrada actualmente: 
    
  - La configuración de desorden no aparecerá
    
- Si no está habilitada la Bandeja de entrada desordenada o centrada: 
    
  - Tanto Desorden como Bandeja de entrada centrada aparecen como opciones en el buzón de correo del usuario Configuración
    
 **Si usas Outlook.com:**
  
- Si el usuario tiene actualmente clutter habilitado: 
    
  - Aparece la configuración de desorden
    
- Si el usuario tiene habilitada la Bandeja de entrada centrada actualmente: 
    
  - La configuración de desorden no aparecerá
    
- Si no está habilitada la Bandeja de entrada desordenada o centrada: 
    
  - Tanto Desorden como Bandeja de entrada centrada aparecen como opciones en el buzón de correo del usuario Configuración
    
- Si el usuario ha habilitado la Bandeja de entrada centrada en algún momento del pasado:
    
  - La configuración de desorden nunca aparecerá
    
    De lo contrario, 
    
  - Aparecerá la configuración de desorden
    
## <a name="related-content"></a>Contenido relacionado

[Usar Clutter para ordenar los mensajes de](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) baja prioridad en Outlook (artículo)\
[Usar Desorden para ordenar mensajes de baja prioridad en OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (artículo)\
[Desactivar Desorden en Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (artículo)
