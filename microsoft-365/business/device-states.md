---
title: Estados de dispositivo
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Obtenga información sobre los Estados de dispositivos en Microsoft 365 Business.
ms.openlocfilehash: 06e5c800e6a104785c1fd0724223e05d7729722e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072728"
---
# <a name="device-states"></a><span data-ttu-id="f3428-103">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="f3428-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="f3428-104">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="f3428-104">Device states</span></span>

<span data-ttu-id="f3428-105">Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.</span><span class="sxs-lookup"><span data-stu-id="f3428-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="f3428-107">**Estado**</span><span class="sxs-lookup"><span data-stu-id="f3428-107">**Status**</span></span>|<span data-ttu-id="f3428-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f3428-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f3428-109">Administrado por Intune</span><span class="sxs-lookup"><span data-stu-id="f3428-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="f3428-110">Administrado por Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="f3428-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="f3428-111">Pendiente de retirada</span><span class="sxs-lookup"><span data-stu-id="f3428-111">Retire pending</span></span>  <br/> |<span data-ttu-id="f3428-112">Microsoft 365 Business está en preparación para quitar los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f3428-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="f3428-113">Retirada en curso</span><span class="sxs-lookup"><span data-stu-id="f3428-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="f3428-114">Microsoft 365 Business está quitando actualmente los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f3428-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="f3428-115">Error de retirada</span><span class="sxs-lookup"><span data-stu-id="f3428-115">Retire failed</span></span>  <br/> | <span data-ttu-id="f3428-116">No se pudo completar la acción para quitar los datos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="f3428-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="f3428-117">Retirada cancelada</span><span class="sxs-lookup"><span data-stu-id="f3428-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="f3428-118">Se canceló la acción de retirar.</span><span class="sxs-lookup"><span data-stu-id="f3428-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="f3428-119">Borrado pendiente</span><span class="sxs-lookup"><span data-stu-id="f3428-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="f3428-120">Esperando a que se inicie el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="f3428-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="f3428-121">Borrado en curso</span><span class="sxs-lookup"><span data-stu-id="f3428-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="f3428-122">Se emitió el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="f3428-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="f3428-123">No se pudo completar el borrado</span><span class="sxs-lookup"><span data-stu-id="f3428-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="f3428-124">No se pudo realizar el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="f3428-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="f3428-125">Borrado cancelado</span><span class="sxs-lookup"><span data-stu-id="f3428-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="f3428-126">Se canceló el borrado de fábrica.</span><span class="sxs-lookup"><span data-stu-id="f3428-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="f3428-127">Incorrecto</span><span class="sxs-lookup"><span data-stu-id="f3428-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="f3428-128">Esto quiere decir que hay una acción pendiente (o en curso), pero el dispositivo no se registró en más de 30 días.</span><span class="sxs-lookup"><span data-stu-id="f3428-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="f3428-129">Pendiente de eliminación</span><span class="sxs-lookup"><span data-stu-id="f3428-129">Delete pending</span></span>  <br/> |<span data-ttu-id="f3428-130">La acción de eliminación está pendiente.</span><span class="sxs-lookup"><span data-stu-id="f3428-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="f3428-131">Detectado</span><span class="sxs-lookup"><span data-stu-id="f3428-131">Discovered</span></span>  <br/> |<span data-ttu-id="f3428-132">Microsoft 365 Business detectó el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f3428-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
