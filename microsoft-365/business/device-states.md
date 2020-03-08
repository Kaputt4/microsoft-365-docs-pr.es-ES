---
title: Estados de dispositivo
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Obtenga información sobre los distintos Estados de los dispositivos en la lista acciones de dispositivos en la Página principal de administración de Microsoft 365 Business.
ms.openlocfilehash: bed1610814ca0d60adb4b4b3d0018e3e7e6d763f
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560828"
---
# <a name="device-states"></a><span data-ttu-id="fb2d6-103">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="fb2d6-103">Device states</span></span>

<span data-ttu-id="fb2d6-104">Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="fb2d6-106">**Estado**</span><span class="sxs-lookup"><span data-stu-id="fb2d6-106">**Status**</span></span>|<span data-ttu-id="fb2d6-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fb2d6-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fb2d6-108">Administrado por Intune</span><span class="sxs-lookup"><span data-stu-id="fb2d6-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="fb2d6-109">Administrado por Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-110">Pendiente de retirada</span><span class="sxs-lookup"><span data-stu-id="fb2d6-110">Retire pending</span></span>  <br/> |<span data-ttu-id="fb2d6-111">Microsoft 365 Business está en preparación para quitar los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-112">Retirada en curso</span><span class="sxs-lookup"><span data-stu-id="fb2d6-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="fb2d6-113">Microsoft 365 Business está quitando actualmente los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-114">Error de retirada</span><span class="sxs-lookup"><span data-stu-id="fb2d6-114">Retire failed</span></span>  <br/> | <span data-ttu-id="fb2d6-115">No se pudo completar la acción para quitar los datos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-116">Retirada cancelada</span><span class="sxs-lookup"><span data-stu-id="fb2d6-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="fb2d6-117">Se canceló la acción de retirada.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-118">Borrado pendiente</span><span class="sxs-lookup"><span data-stu-id="fb2d6-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="fb2d6-119">Esperando a que se inicie el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-120">Borrado en curso</span><span class="sxs-lookup"><span data-stu-id="fb2d6-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="fb2d6-121">Se emitió el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-122">No se pudo completar el borrado</span><span class="sxs-lookup"><span data-stu-id="fb2d6-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="fb2d6-123">No se pudo restablecer la fábrica.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-124">Borrado cancelado</span><span class="sxs-lookup"><span data-stu-id="fb2d6-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="fb2d6-125">Se canceló el borrado de la fábrica.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-126">Incorrecto</span><span class="sxs-lookup"><span data-stu-id="fb2d6-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="fb2d6-127">Una acción está pendiente (o en curso), pero el dispositivo no se ha protegido durante más de 30 días.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-128">Pendiente de eliminación</span><span class="sxs-lookup"><span data-stu-id="fb2d6-128">Delete pending</span></span>  <br/> |<span data-ttu-id="fb2d6-129">La acción de eliminación está pendiente.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="fb2d6-130">Detectado</span><span class="sxs-lookup"><span data-stu-id="fb2d6-130">Discovered</span></span>  <br/> |<span data-ttu-id="fb2d6-131">Microsoft 365 Business detectó el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
