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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Obtenga información sobre cómo habilitar o deshabilitar la característica Desorden para todos los usuarios o específicos de la organización, mediante Exchange PowerShell. '
ms.openlocfilehash: 91098047bdf2ab8190283990bdc6b0292e3e57ba
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393984"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="f8766-103">Configurar desorden para su organización</span><span class="sxs-lookup"><span data-stu-id="f8766-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="f8766-104">[La Bandeja de entrada centrada](../setup/configure-focused-inbox.md) reemplazará a Clutter.</span><span class="sxs-lookup"><span data-stu-id="f8766-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="f8766-105">Más información: [Actualizar la Bandeja de entrada centrada y nuestros planes para Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="f8766-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="f8766-106">Como administrador, es posible que tenga que administrar la característica Desorden en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8766-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="f8766-107">Para activar y desactivar la característica Desorden para los usuarios de la organización, debe usar Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8766-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="f8766-108">(Los individuos pueden activarlo o desactivarlo con estas instrucciones: [Desactivar/activar Desorden en Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span><span class="sxs-lookup"><span data-stu-id="f8766-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="f8766-109">Consulte [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Conectar to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener más información sobre Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8766-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="f8766-110">Debe tener una cuenta que tenga al menos el rol de administrador Exchange servicio y la capacidad de conectarse a Exchange Online con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8766-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="f8766-111">Activar Clutter con Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8766-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="f8766-112">Puede habilitar Clutter manualmente para un buzón ejecutando el cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter)</span><span class="sxs-lookup"><span data-stu-id="f8766-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="f8766-113">También puede ver la configuración de desorden para buzones de su organización ejecutando el cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter)</span><span class="sxs-lookup"><span data-stu-id="f8766-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="f8766-114">Activar Clutter para un solo usuario llamado Allie Bellew</span><span class="sxs-lookup"><span data-stu-id="f8766-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="f8766-115">Desactivar Clutter con Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8766-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="f8766-116">Puede deshabilitar Clutter manualmente para un buzón ejecutando el cmdlet [Set-Clutter.](/powershell/module/exchange/set-clutter)</span><span class="sxs-lookup"><span data-stu-id="f8766-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="f8766-117">También puede ver la **configuración de desorden** para buzones de su organización ejecutando el cmdlet [Get-Clutter.](/powershell/module/exchange/get-clutter)</span><span class="sxs-lookup"><span data-stu-id="f8766-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="f8766-118">Desactivar Clutter para un solo usuario llamado Allie Bellew:</span><span class="sxs-lookup"><span data-stu-id="f8766-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="f8766-119">Si usa PowerShell para crear masivamente los usuarios, deberá ejecutar [Set-Clutter](/powershell/module/exchange/set-clutter) en el buzón de cada usuario para administrar Clutter.</span><span class="sxs-lookup"><span data-stu-id="f8766-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="f8766-120">¿Cuándo se mostrará a los usuarios el modificador de encendido y apagado Clutter en Outlook en la Web?</span><span class="sxs-lookup"><span data-stu-id="f8766-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="f8766-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="f8766-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="f8766-122">Como administrador, puede volver a habilitar Clutter con Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8766-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="f8766-123">Una vez hecho esto, la Bandeja de entrada centrada se desactivará y El desorden volverá a estar activo.</span><span class="sxs-lookup"><span data-stu-id="f8766-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="f8766-124">**Si estás usando Outlook en la Web con una Microsoft 365 Empresa Premium suscripción:**</span><span class="sxs-lookup"><span data-stu-id="f8766-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="f8766-125">Si el usuario tiene actualmente clutter habilitado:</span><span class="sxs-lookup"><span data-stu-id="f8766-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="f8766-126">Aparece la configuración de desorden</span><span class="sxs-lookup"><span data-stu-id="f8766-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="f8766-127">Si el usuario tiene habilitada la Bandeja de entrada centrada actualmente:</span><span class="sxs-lookup"><span data-stu-id="f8766-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="f8766-128">La configuración de desorden no aparecerá</span><span class="sxs-lookup"><span data-stu-id="f8766-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="f8766-129">Si no está habilitada la Bandeja de entrada desordenada o centrada:</span><span class="sxs-lookup"><span data-stu-id="f8766-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="f8766-130">Tanto Desorden como Bandeja de entrada centrada aparecen como opciones en el buzón de correo del usuario Configuración</span><span class="sxs-lookup"><span data-stu-id="f8766-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="f8766-131">**Si usas Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="f8766-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="f8766-132">Si el usuario tiene actualmente clutter habilitado:</span><span class="sxs-lookup"><span data-stu-id="f8766-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="f8766-133">Aparece la configuración de desorden</span><span class="sxs-lookup"><span data-stu-id="f8766-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="f8766-134">Si el usuario tiene habilitada la Bandeja de entrada centrada actualmente:</span><span class="sxs-lookup"><span data-stu-id="f8766-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="f8766-135">La configuración de desorden no aparecerá</span><span class="sxs-lookup"><span data-stu-id="f8766-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="f8766-136">Si no está habilitada la Bandeja de entrada desordenada o centrada:</span><span class="sxs-lookup"><span data-stu-id="f8766-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="f8766-137">Tanto Desorden como Bandeja de entrada centrada aparecen como opciones en el buzón de correo del usuario Configuración</span><span class="sxs-lookup"><span data-stu-id="f8766-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="f8766-138">Si el usuario ha habilitado la Bandeja de entrada centrada en algún momento del pasado:</span><span class="sxs-lookup"><span data-stu-id="f8766-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="f8766-139">La configuración de desorden nunca aparecerá</span><span class="sxs-lookup"><span data-stu-id="f8766-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="f8766-140">De lo contrario,</span><span class="sxs-lookup"><span data-stu-id="f8766-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="f8766-141">Aparecerá la configuración de desorden</span><span class="sxs-lookup"><span data-stu-id="f8766-141">Clutter settings will appear</span></span>
    
## <a name="related-content"></a><span data-ttu-id="f8766-142">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f8766-142">Related content</span></span>

<span data-ttu-id="f8766-143">[Usar Clutter para ordenar los mensajes de](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) baja prioridad en Outlook (artículo)</span><span class="sxs-lookup"><span data-stu-id="f8766-143">[Use Clutter to sort low priority messages in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (article)</span></span>\
<span data-ttu-id="f8766-144">[Usar Desorden para ordenar mensajes de baja prioridad en OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f8766-144">[Use Clutter to sort low priority messages in OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (article)</span></span>\
<span data-ttu-id="f8766-145">[Desactivar Desorden en Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f8766-145">[Turn off Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (article)</span></span>
