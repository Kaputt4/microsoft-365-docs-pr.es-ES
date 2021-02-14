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
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="dfb53-103">Configurar Otros desorden para su organización</span><span class="sxs-lookup"><span data-stu-id="dfb53-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="dfb53-104">[La Bandeja de entrada Con](../setup/configure-focused-inbox.md) foco reemplazará a Otros desordenes.</span><span class="sxs-lookup"><span data-stu-id="dfb53-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="dfb53-105">Más información: [Actualizar en la Bandeja de entrada Enfocados y nuestros planes para Desorden](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="dfb53-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="dfb53-106">Como administrador, puede que tenga que administrar la característica Otros desordenes en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfb53-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="dfb53-107">Para activar o desactivar la característica Otros desordenes para los usuarios de su organización, debe usar Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfb53-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="dfb53-108">(Los usuarios pueden activarla o desactivarla con estas instrucciones: [Desactivar/activar Otros correos en Outlook.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)</span><span class="sxs-lookup"><span data-stu-id="dfb53-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="dfb53-109">Consulte Usar [PowerShell con Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) y conectarse a [Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) para obtener más información sobre el uso de Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfb53-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="dfb53-110">Debe tener una cuenta que tenga al menos el rol de administrador del servicio de Exchange y la capacidad de conectarse a Exchange Online con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfb53-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="dfb53-111">Activar Desorden con Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfb53-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="dfb53-112">Puede habilitar Otros correos manualmente para un buzón ejecutando el cmdlet [Set-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834446)</span><span class="sxs-lookup"><span data-stu-id="dfb53-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="dfb53-113">También puede ver la configuración de Otros correos para los buzones de la organización ejecutando el cmdlet [Get-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834759)</span><span class="sxs-lookup"><span data-stu-id="dfb53-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="dfb53-114">Activar Otros desorden para un solo usuario llamado Allie Bellew</span><span class="sxs-lookup"><span data-stu-id="dfb53-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="dfb53-115">Desactivar Otros servicios con Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfb53-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="dfb53-116">Puede deshabilitar Otros correos manualmente para un buzón ejecutando el cmdlet [Set-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834446)</span><span class="sxs-lookup"><span data-stu-id="dfb53-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="dfb53-117">También puede ver la **configuración de Otros** correos para los buzones de la organización ejecutando el cmdlet [Get-Clutter.](https://go.microsoft.com/fwlink/?LinkID=834759)</span><span class="sxs-lookup"><span data-stu-id="dfb53-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="dfb53-118">Desactivar Otros desorden para un solo usuario llamado Allie Bellew:</span><span class="sxs-lookup"><span data-stu-id="dfb53-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="dfb53-119">Si usa PowerShell para crear usuarios en masa, deberá ejecutar [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) en el buzón de cada usuario para administrar Otros correos.</span><span class="sxs-lookup"><span data-stu-id="dfb53-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="dfb53-120">¿Cuándo se mostrará el modificador Despegar/Desactivar desorden a los usuarios de Outlook en la Web?</span><span class="sxs-lookup"><span data-stu-id="dfb53-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="dfb53-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="dfb53-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="dfb53-122">Como administrador, puede volver a habilitar Otros desorden con Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfb53-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="dfb53-123">Una vez hecho esto, la Bandeja de entrada Foco se desactivará y Otros desorden volverá a estar activo.</span><span class="sxs-lookup"><span data-stu-id="dfb53-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="dfb53-124">**Si usa Outlook en la Web con una suscripción a Microsoft 365 Empresa Premium:**</span><span class="sxs-lookup"><span data-stu-id="dfb53-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="dfb53-125">Si el usuario actualmente tiene Otros desorden habilitados:</span><span class="sxs-lookup"><span data-stu-id="dfb53-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="dfb53-126">Aparece la configuración de otros desordenes</span><span class="sxs-lookup"><span data-stu-id="dfb53-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="dfb53-127">Si el usuario tiene habilitada la Bandeja de entrada Centrada actualmente:</span><span class="sxs-lookup"><span data-stu-id="dfb53-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="dfb53-128">La configuración de otros desordenes no aparecerá</span><span class="sxs-lookup"><span data-stu-id="dfb53-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="dfb53-129">Si no está habilitada la Bandeja de entrada Desorden o Centrado:</span><span class="sxs-lookup"><span data-stu-id="dfb53-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="dfb53-130">Tanto Desorden como Bandeja de entrada Centrado aparecen como opciones en la configuración de correo del usuario</span><span class="sxs-lookup"><span data-stu-id="dfb53-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="dfb53-131">**Si usas Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="dfb53-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="dfb53-132">Si el usuario actualmente tiene Otros desorden habilitado:</span><span class="sxs-lookup"><span data-stu-id="dfb53-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="dfb53-133">Aparece la configuración de otros desordenes</span><span class="sxs-lookup"><span data-stu-id="dfb53-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="dfb53-134">Si el usuario tiene habilitada la Bandeja de entrada Enfocado actualmente:</span><span class="sxs-lookup"><span data-stu-id="dfb53-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="dfb53-135">La configuración de otros desordenes no aparecerá</span><span class="sxs-lookup"><span data-stu-id="dfb53-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="dfb53-136">Si no está habilitada la Bandeja de entrada Desorden o Centrado:</span><span class="sxs-lookup"><span data-stu-id="dfb53-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="dfb53-137">Tanto Desorden como Bandeja de entrada Centrado aparecen como opciones en la configuración de correo del usuario</span><span class="sxs-lookup"><span data-stu-id="dfb53-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="dfb53-138">Si el usuario habilitó la Bandeja de entrada Enfocado en algún momento del pasado:</span><span class="sxs-lookup"><span data-stu-id="dfb53-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="dfb53-139">La configuración de otros desordenes nunca aparecerá</span><span class="sxs-lookup"><span data-stu-id="dfb53-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="dfb53-140">De lo contrario,</span><span class="sxs-lookup"><span data-stu-id="dfb53-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="dfb53-141">Aparecerá la configuración de otros desordenes</span><span class="sxs-lookup"><span data-stu-id="dfb53-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="dfb53-142">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="dfb53-142">Related articles</span></span>
<span data-ttu-id="dfb53-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="dfb53-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="dfb53-144">Usar Otros correos para ordenar mensajes de prioridad baja en Outlook</span><span class="sxs-lookup"><span data-stu-id="dfb53-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="dfb53-145">Usar Otros correos para ordenar mensajes de prioridad baja en OWA</span><span class="sxs-lookup"><span data-stu-id="dfb53-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="dfb53-146">Desactivar Otros correos en Outlook</span><span class="sxs-lookup"><span data-stu-id="dfb53-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

