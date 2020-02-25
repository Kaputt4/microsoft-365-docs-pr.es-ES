---
title: Configurar otros correos para su organización
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Obtenga información sobre cómo habilitar o deshabilitar la característica otros correos para todos o algunos usuarios específicos de la organización mediante Exchange PowerShell. '
ms.openlocfilehash: 65aa614095ecbebaad3d7eb38af1e74166ce20ac
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255288"
---
# <a name="configure-clutter-for-your-organization"></a>Configurar otros correos para su organización

> [!TIP]
> La [bandeja de entrada prioritarios](../setup/configure-focused-inbox.md) va a reemplazar otros correos. Más información: [actualización de la bandeja de entrada prioritarios y nuestros planes de desorden](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Como administrador, es posible que tenga que administrar la característica otros correos en Office 365. Para activar o desactivar la característica otros correos para los usuarios de su organización, debe usar Exchange PowerShell. (Las personas pueden activarla o desactivarla siguiendo estas instrucciones: [desactivar o deshacer otros correos de Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)). 
  
Consulte [PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) y [Conéctese a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) para obtener más información sobre el uso de Exchange PowerShell. Debe tener una cuenta que tenga como mínimo el rol de administrador de servicios de Exchange y la capacidad de conectarse a Exchange Online con PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Volver a activar otros correos con Exchange PowerShell

Puede habilitar otros correos de forma manual para un buzón de correo mediante la ejecución del cmdlet [set-desorden](https://go.microsoft.com/fwlink/?LinkID=834446) . También puede ver la configuración de otros correos para los buzones de la organización mediante la ejecución del cmdlet [Get-desorden](https://go.microsoft.com/fwlink/?LinkID=834759) . 
  
Active otros correos para un solo usuario denominado Naiara Padilla
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Desactive el desorden con Exchange PowerShell

Puede deshabilitar el desorden manualmente para un buzón mediante la ejecución del cmdlet [set-desorden](https://go.microsoft.com/fwlink/?LinkID=834446) . También puede ver la configuración de **otros correos** para los buzones de la organización mediante la ejecución del cmdlet [Get-desorden](https://go.microsoft.com/fwlink/?LinkID=834759) . 
  
Desactive otros correos para un solo usuario denominado Naiara Padilla:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Si usa PowerShell para crear de forma masiva los usuarios, deberá ejecutar [set-desorden](https://go.microsoft.com/fwlink/?LinkID=834446) en el buzón de cada usuario para administrar otros correos. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>¿Cuándo se muestran los usuarios en Outlook en la web al cambiar el desorden?
<a name="bkmk_onoff"> </a>

Como administrador, puede volver a habilitar otros correos mediante Exchange PowerShell. Una vez hecho esto, se desactivará la bandeja de entrada prioritarios y el desorden volverá a estar activo. 
  
 **Si está usando Outlook en la web con una suscripción de Office 365 empresa:**
  
- Si el usuario tiene correos actualmente habilitados: 
    
  - La configuración de otros correos aparece
    
- Si el usuario tiene la bandeja de entrada prioritarios habilitada actualmente: 
    
  - La configuración de otros correos no aparecerá
    
- Si no hay otros correos o la bandeja de entrada prioritarios habilitada: 
    
  - Los correos y la bandeja de entrada prioritarios aparecen como opciones en la configuración de correo del usuario.
    
 **Si está usando Outlook.com:**
  
- Si el usuario tiene correos actualmente habilitados: 
    
  - La configuración de otros correos aparece
    
- Si el usuario tiene la bandeja de entrada prioritarios habilitada actualmente: 
    
  - La configuración de otros correos no aparecerá
    
- Si no hay otros correos o la bandeja de entrada prioritarios habilitada: 
    
  - Los correos y la bandeja de entrada prioritarios aparecen como opciones en la configuración de correo del usuario.
    
- Si el usuario habilitó la bandeja de entrada prioritarios en algún punto del pasado:
    
  - La configuración de otros correos nunca aparecerá
    
    Otra 
    
  - Aparecerá la configuración de otros correos
    
## <a name="related-articles"></a>Artículos relacionados
<a name="bkmk_onoff"> </a>

[Usar otros correos para ordenar los mensajes de prioridad baja en Outlook](https://support.office.com/article/7755ebf5-4585-469b-b1ab-8b12425c6b6b.aspx)
    
[Usar otros correos para ordenar los mensajes de prioridad baja en OWA](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[Desactivar otros correos en Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

