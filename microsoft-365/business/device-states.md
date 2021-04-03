---
title: Estados de dispositivo
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Obtenga información sobre los distintos estados del dispositivo en la lista Acciones del dispositivo en la página Principal de administración de Microsoft 365 para empresas.
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578475"
---
# <a name="device-states"></a><span data-ttu-id="b9c7d-103">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b9c7d-103">Device states</span></span>

<span data-ttu-id="b9c7d-104">Este artículo se aplica a Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="b9c7d-105">Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="b9c7d-107">**Estado**</span><span class="sxs-lookup"><span data-stu-id="b9c7d-107">**Status**</span></span>|<span data-ttu-id="b9c7d-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b9c7d-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9c7d-109">Administrado por Intune</span><span class="sxs-lookup"><span data-stu-id="b9c7d-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="b9c7d-110">Administrado por Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-111">Pendiente de retirada</span><span class="sxs-lookup"><span data-stu-id="b9c7d-111">Retire pending</span></span>  <br/> |<span data-ttu-id="b9c7d-112">Microsoft 365 Empresa Premium se prepara para quitar los datos de la empresa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-113">Retirada en curso</span><span class="sxs-lookup"><span data-stu-id="b9c7d-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="b9c7d-114">Microsoft 365 Empresa Premium está quitando actualmente los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-115">Error de retirada</span><span class="sxs-lookup"><span data-stu-id="b9c7d-115">Retire failed</span></span>  <br/> | <span data-ttu-id="b9c7d-116">No se pudo completar la acción para quitar los datos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-117">Retirada cancelada</span><span class="sxs-lookup"><span data-stu-id="b9c7d-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="b9c7d-118">Se canceló la acción Retirar.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-119">Borrado pendiente</span><span class="sxs-lookup"><span data-stu-id="b9c7d-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="b9c7d-120">Esperando a que se inicie el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-121">Borrado en curso</span><span class="sxs-lookup"><span data-stu-id="b9c7d-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="b9c7d-122">Se emitió el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-123">No se pudo completar el borrado</span><span class="sxs-lookup"><span data-stu-id="b9c7d-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="b9c7d-124">No se pudo restablecer la fábrica.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-125">Borrado cancelado</span><span class="sxs-lookup"><span data-stu-id="b9c7d-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="b9c7d-126">Se canceló la eliminación de fábrica.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-127">Incorrecto</span><span class="sxs-lookup"><span data-stu-id="b9c7d-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="b9c7d-128">Una acción está pendiente (o en curso), pero el dispositivo no se ha registrado durante más de 30 días.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-129">Pendiente de eliminación</span><span class="sxs-lookup"><span data-stu-id="b9c7d-129">Delete pending</span></span>  <br/> |<span data-ttu-id="b9c7d-130">La acción de eliminación está pendiente.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="b9c7d-131">Detectado</span><span class="sxs-lookup"><span data-stu-id="b9c7d-131">Discovered</span></span>  <br/> |<span data-ttu-id="b9c7d-132">Microsoft 365 Empresa Premium ha detectado el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9c7d-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
