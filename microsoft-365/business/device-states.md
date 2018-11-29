---
title: Estados de dispositivo
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Obtenga información sobre los Estados de dispositivos en Microsoft 365 empresarial.
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871387"
---
# <a name="device-states"></a><span data-ttu-id="76e7a-103">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="76e7a-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="76e7a-104">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="76e7a-104">Device states</span></span>

<span data-ttu-id="76e7a-105">Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.</span><span class="sxs-lookup"><span data-stu-id="76e7a-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="76e7a-107">**Estado**</span><span class="sxs-lookup"><span data-stu-id="76e7a-107">**Status**</span></span>|<span data-ttu-id="76e7a-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="76e7a-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="76e7a-109">Administrado por Intune</span><span class="sxs-lookup"><span data-stu-id="76e7a-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="76e7a-110">Administrado por Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="76e7a-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="76e7a-111">Pendiente de retirada</span><span class="sxs-lookup"><span data-stu-id="76e7a-111">Retire pending</span></span>  <br/> |<span data-ttu-id="76e7a-112">Microsoft 365 Business está en preparación para quitar los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76e7a-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="76e7a-113">Retirada en curso</span><span class="sxs-lookup"><span data-stu-id="76e7a-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="76e7a-114">Microsoft 365 Business está quitando actualmente los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76e7a-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="76e7a-115">Error de retirada</span><span class="sxs-lookup"><span data-stu-id="76e7a-115">Retire failed</span></span>  <br/> | <span data-ttu-id="76e7a-116">No se pudo completar la acción para quitar los datos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="76e7a-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="76e7a-117">Retirada cancelada</span><span class="sxs-lookup"><span data-stu-id="76e7a-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="76e7a-118">Se canceló la acción de retirar.</span><span class="sxs-lookup"><span data-stu-id="76e7a-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="76e7a-119">Borrado pendiente</span><span class="sxs-lookup"><span data-stu-id="76e7a-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="76e7a-120">Esperando a que se inicie el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="76e7a-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="76e7a-121">Borrado en curso</span><span class="sxs-lookup"><span data-stu-id="76e7a-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="76e7a-122">Se emitió el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="76e7a-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="76e7a-123">No se pudo completar el borrado</span><span class="sxs-lookup"><span data-stu-id="76e7a-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="76e7a-124">No se pudo realizar el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="76e7a-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="76e7a-125">Borrado cancelado</span><span class="sxs-lookup"><span data-stu-id="76e7a-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="76e7a-126">Se canceló el borrado de fábrica.</span><span class="sxs-lookup"><span data-stu-id="76e7a-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="76e7a-127">Incorrecto</span><span class="sxs-lookup"><span data-stu-id="76e7a-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="76e7a-128">Esto quiere decir que hay una acción pendiente (o en curso), pero el dispositivo no se registró en más de 30 días.</span><span class="sxs-lookup"><span data-stu-id="76e7a-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="76e7a-129">Pendiente de eliminación</span><span class="sxs-lookup"><span data-stu-id="76e7a-129">Delete pending</span></span>  <br/> |<span data-ttu-id="76e7a-130">La acción de eliminación está pendiente.</span><span class="sxs-lookup"><span data-stu-id="76e7a-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="76e7a-131">Detectado</span><span class="sxs-lookup"><span data-stu-id="76e7a-131">Discovered</span></span>  <br/> |<span data-ttu-id="76e7a-132">Microsoft 365 Business detectó el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76e7a-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
