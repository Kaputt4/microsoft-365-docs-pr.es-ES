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
ms.openlocfilehash: b55e6a5d538ec28d195225e93797cea27afd2e8b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320216"
---
# <a name="device-states"></a><span data-ttu-id="28b19-103">Estados de dispositivo</span><span class="sxs-lookup"><span data-stu-id="28b19-103">Device states</span></span>

<span data-ttu-id="28b19-104">Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.</span><span class="sxs-lookup"><span data-stu-id="28b19-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="28b19-106">**Estado**</span><span class="sxs-lookup"><span data-stu-id="28b19-106">**Status**</span></span>|<span data-ttu-id="28b19-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="28b19-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28b19-108">Administrado por Intune</span><span class="sxs-lookup"><span data-stu-id="28b19-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="28b19-109">Administrado por Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="28b19-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="28b19-110">Pendiente de retirada</span><span class="sxs-lookup"><span data-stu-id="28b19-110">Retire pending</span></span>  <br/> |<span data-ttu-id="28b19-111">Microsoft 365 Business está en preparación para quitar los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28b19-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="28b19-112">Retirada en curso</span><span class="sxs-lookup"><span data-stu-id="28b19-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="28b19-113">Microsoft 365 Business está quitando actualmente los datos de la compañía del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28b19-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="28b19-114">Error de retirada</span><span class="sxs-lookup"><span data-stu-id="28b19-114">Retire failed</span></span>  <br/> | <span data-ttu-id="28b19-115">No se pudo completar la acción para quitar los datos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="28b19-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="28b19-116">Retirada cancelada</span><span class="sxs-lookup"><span data-stu-id="28b19-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="28b19-117">Se canceló la acción de retirada.</span><span class="sxs-lookup"><span data-stu-id="28b19-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="28b19-118">Borrado pendiente</span><span class="sxs-lookup"><span data-stu-id="28b19-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="28b19-119">Esperando a que se inicie el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="28b19-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="28b19-120">Borrado en curso</span><span class="sxs-lookup"><span data-stu-id="28b19-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="28b19-121">Se emitió el restablecimiento de fábrica.</span><span class="sxs-lookup"><span data-stu-id="28b19-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="28b19-122">No se pudo completar el borrado</span><span class="sxs-lookup"><span data-stu-id="28b19-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="28b19-123">No se pudo restablecer la fábrica.</span><span class="sxs-lookup"><span data-stu-id="28b19-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="28b19-124">Borrado cancelado</span><span class="sxs-lookup"><span data-stu-id="28b19-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="28b19-125">Se canceló el borrado de la fábrica.</span><span class="sxs-lookup"><span data-stu-id="28b19-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="28b19-126">Incorrecto</span><span class="sxs-lookup"><span data-stu-id="28b19-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="28b19-127">Una acción está pendiente (o en curso), pero el dispositivo no se ha protegido durante más de 30 días.</span><span class="sxs-lookup"><span data-stu-id="28b19-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="28b19-128">Pendiente de eliminación</span><span class="sxs-lookup"><span data-stu-id="28b19-128">Delete pending</span></span>  <br/> |<span data-ttu-id="28b19-129">La acción de eliminación está pendiente.</span><span class="sxs-lookup"><span data-stu-id="28b19-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="28b19-130">Detectado</span><span class="sxs-lookup"><span data-stu-id="28b19-130">Discovered</span></span>  <br/> |<span data-ttu-id="28b19-131">Microsoft 365 Business detectó el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28b19-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
