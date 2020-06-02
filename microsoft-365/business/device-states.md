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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Obtenga información sobre los distintos Estados de los dispositivos en la lista acciones de dispositivos en la Página principal de administración de Microsoft 365 para empresas.
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471187"
---
# <a name="device-states"></a><span data-ttu-id="343e4-103">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="343e4-103">Device states</span></span>

<span data-ttu-id="343e4-104">Este artículo se aplica a Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="343e4-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="343e4-105">Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.</span><span class="sxs-lookup"><span data-stu-id="343e4-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="343e4-107">**Estado**</span><span class="sxs-lookup"><span data-stu-id="343e4-107">**Status**</span></span>|<span data-ttu-id="343e4-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="343e4-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="343e4-109">Administrado por Intune</span><span class="sxs-lookup"><span data-stu-id="343e4-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="343e4-110">Administrado por Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="343e4-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="343e4-111">Pendiente de retirada</span><span class="sxs-lookup"><span data-stu-id="343e4-111">Retire pending</span></span>  <br/> |<span data-ttu-id="343e4-112">Microsoft 365 empresa Premium está preparándose para quitar datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="343e4-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="343e4-113">Retirada en curso</span><span class="sxs-lookup"><span data-stu-id="343e4-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="343e4-114">Microsoft 365 empresa Premium está quitando actualmente los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="343e4-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="343e4-115">Error de retirada</span><span class="sxs-lookup"><span data-stu-id="343e4-115">Retire failed</span></span>  <br/> | <span data-ttu-id="343e4-116">No se pudo completar la acción para quitar los datos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="343e4-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="343e4-117">Retirada cancelada</span><span class="sxs-lookup"><span data-stu-id="343e4-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="343e4-118">Se canceló la acción de retirada.</span><span class="sxs-lookup"><span data-stu-id="343e4-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="343e4-119">Borrado pendiente</span><span class="sxs-lookup"><span data-stu-id="343e4-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="343e4-120">Esperando a que se inicie el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="343e4-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="343e4-121">Borrado en curso</span><span class="sxs-lookup"><span data-stu-id="343e4-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="343e4-122">Se emitió el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="343e4-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="343e4-123">No se pudo completar el borrado</span><span class="sxs-lookup"><span data-stu-id="343e4-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="343e4-124">No se pudo restablecer la fábrica.</span><span class="sxs-lookup"><span data-stu-id="343e4-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="343e4-125">Borrado cancelado</span><span class="sxs-lookup"><span data-stu-id="343e4-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="343e4-126">Se canceló el borrado de la fábrica.</span><span class="sxs-lookup"><span data-stu-id="343e4-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="343e4-127">Incorrecto</span><span class="sxs-lookup"><span data-stu-id="343e4-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="343e4-128">Una acción está pendiente (o en curso), pero el dispositivo no se ha protegido durante más de 30 días.</span><span class="sxs-lookup"><span data-stu-id="343e4-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="343e4-129">Pendiente de eliminación</span><span class="sxs-lookup"><span data-stu-id="343e4-129">Delete pending</span></span>  <br/> |<span data-ttu-id="343e4-130">La acción de eliminación está pendiente.</span><span class="sxs-lookup"><span data-stu-id="343e4-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="343e4-131">Detectado</span><span class="sxs-lookup"><span data-stu-id="343e4-131">Discovered</span></span>  <br/> |<span data-ttu-id="343e4-132">Microsoft 365 empresa Premium ha detectado el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="343e4-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
