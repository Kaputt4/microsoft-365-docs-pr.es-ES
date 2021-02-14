---
title: Configurar Otros desorden para su organización
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
description: 'Obtenga información sobre cómo habilitar o deshabilitar la característica Otros desordenes para todos los usuarios o para usuarios específicos de su organización, con Exchange PowerShell. '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780282"
---
# <a name="configure-clutter-for-your-organization"></a>Configurar Otros desorden para su organización

> [!TIP]
> [La Bandeja de entrada Con](../setup/configure-focused-inbox.md) foco reemplazará a Otros desordenes. Más información: [Actualizar en la Bandeja de entrada Enfocados y nuestros planes para Desorden](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Como administrador, puede que tenga que administrar la característica Otros desordenes en Microsoft 365. Para activar o desactivar la característica Otros desordenes para los usuarios de su organización, debe usar Exchange PowerShell. (Los usuarios pueden activarla o desactivarla con estas instrucciones: [Desactivar/activar Otros correos en Outlook.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
  
Consulte Usar [PowerShell con Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) y conectarse a [Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) para obtener más información sobre el uso de Exchange PowerShell. Debe tener una cuenta que tenga al menos el rol de administrador del servicio de Exchange y la capacidad de conectarse a Exchange Online con PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Activar Desorden con Exchange PowerShell

Puede habilitar Otros correos manualmente para un buzón ejecutando el cmdlet [Set-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834446) También puede ver la configuración de Otros correos para los buzones de la organización ejecutando el cmdlet [Get-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834759) 
  
Activar Otros desorden para un solo usuario llamado Allie Bellew
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Desactivar Otros servicios con Exchange PowerShell

Puede deshabilitar Otros correos manualmente para un buzón ejecutando el cmdlet [Set-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834446) También puede ver la **configuración de Otros** correos para los buzones de la organización ejecutando el cmdlet [Get-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834759) 
  
Desactivar Otros desorden para un solo usuario llamado Allie Bellew:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Si usa PowerShell para crear usuarios en masa, deberá ejecutar [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) en el buzón de cada usuario para administrar Otros correos. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>¿Cuándo se mostrará el modificador Despegar/Desactivar desorden a los usuarios de Outlook en la Web?
<a name="bkmk_onoff"> </a>

Como administrador, puede volver a habilitar Otros desorden con Exchange PowerShell. Una vez hecho esto, la Bandeja de entrada Foco se desactivará y Otros desorden volverá a estar activo. 
  
 **Si usa Outlook en la Web con una suscripción a Microsoft 365 Empresa Premium:**
  
- Si el usuario actualmente tiene Otros desorden habilitados: 
    
  - Aparece la configuración de otros desordenes
    
- Si el usuario tiene habilitada la Bandeja de entrada Centrada actualmente: 
    
  - La configuración de otros desordenes no aparecerá
    
- Si no está habilitada la Bandeja de entrada Desorden o Centrado: 
    
  - Tanto Desorden como Bandeja de entrada Centrado aparecen como opciones en la configuración de correo del usuario
    
 **Si usas Outlook.com:**
  
- Si el usuario actualmente tiene Otros desorden habilitado: 
    
  - Aparece la configuración de otros desordenes
    
- Si el usuario tiene habilitada la Bandeja de entrada Enfocado actualmente: 
    
  - La configuración de otros desordenes no aparecerá
    
- Si no está habilitada la Bandeja de entrada Desorden o Centrado: 
    
  - Tanto Desorden como Bandeja de entrada Centrado aparecen como opciones en la configuración de correo del usuario
    
- Si el usuario habilitó la Bandeja de entrada Enfocado en algún momento del pasado:
    
  - La configuración de otros desordenes nunca aparecerá
    
    De lo contrario, 
    
  - Aparecerá la configuración de otros desordenes
    
## <a name="related-articles"></a>Artículos relacionados
<a name="bkmk_onoff"> </a>

[Usar Otros correos para ordenar mensajes de prioridad baja en Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[Usar Otros correos para ordenar mensajes de prioridad baja en OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Desactivar Otros correos en Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

