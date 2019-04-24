---
title: Estados de dispositivo
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Obtenga información sobre los Estados de dispositivos en Microsoft 365 Business.
ms.openlocfilehash: 15114835a5014f5bfac600eac79bcdffdaec481a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276997"
---
# <a name="device-states"></a><span data-ttu-id="d19f3-103">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="d19f3-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="d19f3-104">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="d19f3-104">Device states</span></span>

<span data-ttu-id="d19f3-105">Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.</span><span class="sxs-lookup"><span data-stu-id="d19f3-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="d19f3-107">**Estado**</span><span class="sxs-lookup"><span data-stu-id="d19f3-107">**Status**</span></span>|<span data-ttu-id="d19f3-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d19f3-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d19f3-109">Administrado por Intune</span><span class="sxs-lookup"><span data-stu-id="d19f3-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="d19f3-110">Administrado por Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="d19f3-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="d19f3-111">Pendiente de retirada</span><span class="sxs-lookup"><span data-stu-id="d19f3-111">Retire pending</span></span>  <br/> |<span data-ttu-id="d19f3-112">Microsoft 365 Business está en preparación para quitar los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d19f3-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="d19f3-113">Retirada en curso</span><span class="sxs-lookup"><span data-stu-id="d19f3-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="d19f3-114">Microsoft 365 Business está quitando actualmente los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d19f3-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="d19f3-115">Error de retirada</span><span class="sxs-lookup"><span data-stu-id="d19f3-115">Retire failed</span></span>  <br/> | <span data-ttu-id="d19f3-116">No se pudo completar la acción para quitar los datos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="d19f3-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="d19f3-117">Retirada cancelada</span><span class="sxs-lookup"><span data-stu-id="d19f3-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="d19f3-118">Se canceló la acción de retirar.</span><span class="sxs-lookup"><span data-stu-id="d19f3-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="d19f3-119">Borrado pendiente</span><span class="sxs-lookup"><span data-stu-id="d19f3-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="d19f3-120">Esperando a que se inicie el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="d19f3-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="d19f3-121">Borrado en curso</span><span class="sxs-lookup"><span data-stu-id="d19f3-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="d19f3-122">Se emitió el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="d19f3-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="d19f3-123">No se pudo completar el borrado</span><span class="sxs-lookup"><span data-stu-id="d19f3-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="d19f3-124">No se pudo realizar el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="d19f3-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="d19f3-125">Borrado cancelado</span><span class="sxs-lookup"><span data-stu-id="d19f3-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="d19f3-126">Se canceló el borrado de fábrica.</span><span class="sxs-lookup"><span data-stu-id="d19f3-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="d19f3-127">Incorrecto</span><span class="sxs-lookup"><span data-stu-id="d19f3-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="d19f3-128">Esto quiere decir que hay una acción pendiente (o en curso), pero el dispositivo no se registró en más de 30 días.</span><span class="sxs-lookup"><span data-stu-id="d19f3-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="d19f3-129">Pendiente de eliminación</span><span class="sxs-lookup"><span data-stu-id="d19f3-129">Delete pending</span></span>  <br/> |<span data-ttu-id="d19f3-130">La acción de eliminación está pendiente.</span><span class="sxs-lookup"><span data-stu-id="d19f3-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="d19f3-131">Detectado</span><span class="sxs-lookup"><span data-stu-id="d19f3-131">Discovered</span></span>  <br/> |<span data-ttu-id="d19f3-132">Microsoft 365 Business detectó el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d19f3-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
