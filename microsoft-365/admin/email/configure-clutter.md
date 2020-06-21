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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Obtenga información sobre cómo habilitar o deshabilitar la característica otros correos para todos o algunos usuarios específicos de la organización mediante Exchange PowerShell. '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780282"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="2ee11-103">Configurar otros correos para su organización</span><span class="sxs-lookup"><span data-stu-id="2ee11-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="2ee11-104">La [bandeja de entrada prioritarios](../setup/configure-focused-inbox.md) va a reemplazar otros correos.</span><span class="sxs-lookup"><span data-stu-id="2ee11-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="2ee11-105">Más información: [actualización de la bandeja de entrada prioritarios y nuestros planes de desorden](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="2ee11-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="2ee11-106">Como administrador, es posible que tenga que administrar la característica otros correos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ee11-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="2ee11-107">Para activar o desactivar la característica otros correos para los usuarios de su organización, debe usar Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ee11-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="2ee11-108">(Las personas pueden activarla o desactivarla siguiendo estas instrucciones: [desactivar o deshacer desorden en Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span><span class="sxs-lookup"><span data-stu-id="2ee11-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="2ee11-109">Consulte [PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) y [Conéctese a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) para obtener más información sobre el uso de Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ee11-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="2ee11-110">Debe tener una cuenta que tenga como mínimo el rol de administrador de servicios de Exchange y la capacidad de conectarse a Exchange Online con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ee11-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="2ee11-111">Volver a activar otros correos con Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ee11-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="2ee11-112">Puede habilitar otros correos de forma manual para un buzón de correo mediante la ejecución del cmdlet [set-desorden](https://go.microsoft.com/fwlink/?LinkID=834446) .</span><span class="sxs-lookup"><span data-stu-id="2ee11-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="2ee11-113">También puede ver la configuración de otros correos para los buzones de la organización mediante la ejecución del cmdlet [Get-desorden](https://go.microsoft.com/fwlink/?LinkID=834759) .</span><span class="sxs-lookup"><span data-stu-id="2ee11-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="2ee11-114">Active otros correos para un solo usuario denominado Naiara Padilla</span><span class="sxs-lookup"><span data-stu-id="2ee11-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="2ee11-115">Desactive el desorden con Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ee11-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="2ee11-116">Puede deshabilitar el desorden manualmente para un buzón mediante la ejecución del cmdlet [set-desorden](https://go.microsoft.com/fwlink/?LinkID=834446) .</span><span class="sxs-lookup"><span data-stu-id="2ee11-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="2ee11-117">También puede ver la configuración de **otros correos** para los buzones de la organización mediante la ejecución del cmdlet [Get-desorden](https://go.microsoft.com/fwlink/?LinkID=834759) .</span><span class="sxs-lookup"><span data-stu-id="2ee11-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="2ee11-118">Desactive otros correos para un solo usuario denominado Naiara Padilla:</span><span class="sxs-lookup"><span data-stu-id="2ee11-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="2ee11-119">Si usa PowerShell para crear de forma masiva los usuarios, deberá ejecutar [set-desorden](https://go.microsoft.com/fwlink/?LinkID=834446) en el buzón de cada usuario para administrar otros correos.</span><span class="sxs-lookup"><span data-stu-id="2ee11-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="2ee11-120">¿Cuándo se muestran los usuarios en Outlook en la web al cambiar el desorden?</span><span class="sxs-lookup"><span data-stu-id="2ee11-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="2ee11-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="2ee11-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="2ee11-122">Como administrador, puede volver a habilitar otros correos mediante Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ee11-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="2ee11-123">Una vez hecho esto, se desactivará la bandeja de entrada prioritarios y el desorden volverá a estar activo.</span><span class="sxs-lookup"><span data-stu-id="2ee11-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="2ee11-124">**Si está usando Outlook en la web con una suscripción de Microsoft 365 empresa Premium:**</span><span class="sxs-lookup"><span data-stu-id="2ee11-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="2ee11-125">Si el usuario tiene correos actualmente habilitados:</span><span class="sxs-lookup"><span data-stu-id="2ee11-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="2ee11-126">La configuración de otros correos aparece</span><span class="sxs-lookup"><span data-stu-id="2ee11-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="2ee11-127">Si el usuario tiene la bandeja de entrada prioritarios habilitada actualmente:</span><span class="sxs-lookup"><span data-stu-id="2ee11-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="2ee11-128">La configuración de otros correos no aparecerá</span><span class="sxs-lookup"><span data-stu-id="2ee11-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="2ee11-129">Si no hay otros correos o la bandeja de entrada prioritarios habilitada:</span><span class="sxs-lookup"><span data-stu-id="2ee11-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="2ee11-130">Los correos y la bandeja de entrada prioritarios aparecen como opciones en la configuración de correo del usuario.</span><span class="sxs-lookup"><span data-stu-id="2ee11-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="2ee11-131">**Si está usando Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="2ee11-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="2ee11-132">Si el usuario tiene correos actualmente habilitados:</span><span class="sxs-lookup"><span data-stu-id="2ee11-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="2ee11-133">La configuración de otros correos aparece</span><span class="sxs-lookup"><span data-stu-id="2ee11-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="2ee11-134">Si el usuario tiene la bandeja de entrada prioritarios habilitada actualmente:</span><span class="sxs-lookup"><span data-stu-id="2ee11-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="2ee11-135">La configuración de otros correos no aparecerá</span><span class="sxs-lookup"><span data-stu-id="2ee11-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="2ee11-136">Si no hay otros correos o la bandeja de entrada prioritarios habilitada:</span><span class="sxs-lookup"><span data-stu-id="2ee11-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="2ee11-137">Los correos y la bandeja de entrada prioritarios aparecen como opciones en la configuración de correo del usuario.</span><span class="sxs-lookup"><span data-stu-id="2ee11-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="2ee11-138">Si el usuario habilitó la bandeja de entrada prioritarios en algún punto del pasado:</span><span class="sxs-lookup"><span data-stu-id="2ee11-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="2ee11-139">La configuración de otros correos nunca aparecerá</span><span class="sxs-lookup"><span data-stu-id="2ee11-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="2ee11-140">Otra</span><span class="sxs-lookup"><span data-stu-id="2ee11-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="2ee11-141">Aparecerá la configuración de otros correos</span><span class="sxs-lookup"><span data-stu-id="2ee11-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="2ee11-142">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="2ee11-142">Related articles</span></span>
<span data-ttu-id="2ee11-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="2ee11-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="2ee11-144">Usar otros correos para ordenar los mensajes de prioridad baja en Outlook</span><span class="sxs-lookup"><span data-stu-id="2ee11-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="2ee11-145">Usar otros correos para ordenar los mensajes de prioridad baja en OWA</span><span class="sxs-lookup"><span data-stu-id="2ee11-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="2ee11-146">Desactivar otros correos en Outlook</span><span class="sxs-lookup"><span data-stu-id="2ee11-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

