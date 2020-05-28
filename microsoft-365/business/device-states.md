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
ms.openlocfilehash: 90c11caa03249408ba2916d303bcb4a59fbcca8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400962"
---
# <a name="device-states"></a><span data-ttu-id="ebdca-103">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ebdca-103">Device states</span></span>

<span data-ttu-id="ebdca-104">Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.</span><span class="sxs-lookup"><span data-stu-id="ebdca-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="ebdca-106">**Estado**</span><span class="sxs-lookup"><span data-stu-id="ebdca-106">**Status**</span></span>|<span data-ttu-id="ebdca-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ebdca-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ebdca-108">Administrado por Intune</span><span class="sxs-lookup"><span data-stu-id="ebdca-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="ebdca-109">Administrado por Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="ebdca-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="ebdca-110">Pendiente de retirada</span><span class="sxs-lookup"><span data-stu-id="ebdca-110">Retire pending</span></span>  <br/> |<span data-ttu-id="ebdca-111">Microsoft 365 empresa Premium está preparándose para quitar datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ebdca-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="ebdca-112">Retirada en curso</span><span class="sxs-lookup"><span data-stu-id="ebdca-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="ebdca-113">Microsoft 365 empresa Premium está quitando actualmente los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ebdca-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="ebdca-114">Error de retirada</span><span class="sxs-lookup"><span data-stu-id="ebdca-114">Retire failed</span></span>  <br/> | <span data-ttu-id="ebdca-115">No se pudo completar la acción para quitar los datos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="ebdca-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="ebdca-116">Retirada cancelada</span><span class="sxs-lookup"><span data-stu-id="ebdca-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="ebdca-117">Se canceló la acción de retirada.</span><span class="sxs-lookup"><span data-stu-id="ebdca-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="ebdca-118">Borrado pendiente</span><span class="sxs-lookup"><span data-stu-id="ebdca-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="ebdca-119">Esperando a que se inicie el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="ebdca-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="ebdca-120">Borrado en curso</span><span class="sxs-lookup"><span data-stu-id="ebdca-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="ebdca-121">Se emitió el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="ebdca-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="ebdca-122">No se pudo completar el borrado</span><span class="sxs-lookup"><span data-stu-id="ebdca-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="ebdca-123">No se pudo restablecer la fábrica.</span><span class="sxs-lookup"><span data-stu-id="ebdca-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="ebdca-124">Borrado cancelado</span><span class="sxs-lookup"><span data-stu-id="ebdca-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="ebdca-125">Se canceló el borrado de la fábrica.</span><span class="sxs-lookup"><span data-stu-id="ebdca-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="ebdca-126">Incorrecto</span><span class="sxs-lookup"><span data-stu-id="ebdca-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="ebdca-127">Una acción está pendiente (o en curso), pero el dispositivo no se ha protegido durante más de 30 días.</span><span class="sxs-lookup"><span data-stu-id="ebdca-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="ebdca-128">Pendiente de eliminación</span><span class="sxs-lookup"><span data-stu-id="ebdca-128">Delete pending</span></span>  <br/> |<span data-ttu-id="ebdca-129">La acción de eliminación está pendiente.</span><span class="sxs-lookup"><span data-stu-id="ebdca-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="ebdca-130">Detectado</span><span class="sxs-lookup"><span data-stu-id="ebdca-130">Discovered</span></span>  <br/> |<span data-ttu-id="ebdca-131">Microsoft 365 empresa Premium ha detectado el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ebdca-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
