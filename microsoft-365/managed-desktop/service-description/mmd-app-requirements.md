---
title: Requisitos de la aplicación de escritorio administrada de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 94d51d7b28922a05c892eb4ffc14aee813a9069c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522030"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="84463-103">Requisitos de la aplicación de escritorio administrada de Microsoft</span><span class="sxs-lookup"><span data-stu-id="84463-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="84463-104">Microsoft Managed Desktop requiere que administremos los dispositivos con un enfoque específico para garantizar el rendimiento, la confiabilidad y la capacidad de servicio de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="84463-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span> <span data-ttu-id="84463-105">Si está seguro de que el enfoque que adopta el escritorio administrado de Microsoft para las áreas siguientes no funcionará para usted, puede solicitar una [excepción al plan de servicio](customizing.md).</span><span class="sxs-lookup"><span data-stu-id="84463-105">If you’re sure that the approach taken by Microsoft Managed Desktop for the areas below will not work for you, you can request an [exception to the service plan](customizing.md).</span></span>


|<span data-ttu-id="84463-106">Área de administración</span><span class="sxs-lookup"><span data-stu-id="84463-106">Management area</span></span>  |<span data-ttu-id="84463-107">Enfoque del escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="84463-107">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="84463-108">Configuración de dispositivos o administración de directivas</span><span class="sxs-lookup"><span data-stu-id="84463-108">Device configuration or policy management</span></span>     |  <span data-ttu-id="84463-109">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="84463-109">Microsoft Intune</span></span>       |
|<span data-ttu-id="84463-110">Administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="84463-110">Application management</span></span>     | <span data-ttu-id="84463-111">Microsoft Intune y portal de la compañía</span><span class="sxs-lookup"><span data-stu-id="84463-111">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="84463-112">Implementación de controladores</span><span class="sxs-lookup"><span data-stu-id="84463-112">Driver deployment</span></span>     |  <span data-ttu-id="84463-113">Controladores incluidos con el dispositivo, Windows Update o Intune</span><span class="sxs-lookup"><span data-stu-id="84463-113">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="84463-114">Seguridad del dispositivo</span><span class="sxs-lookup"><span data-stu-id="84463-114">Device security</span></span>     | <span data-ttu-id="84463-115">Consulte [seguridad de dispositivos](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="84463-115">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="84463-116">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="84463-116">Identity and access management</span></span>     | <span data-ttu-id="84463-117">Consulte [Administración de identidades y acceso](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="84463-117">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="84463-118">Seguridad de red</span><span class="sxs-lookup"><span data-stu-id="84463-118">Network security</span></span>     | <span data-ttu-id="84463-119">Consulte [seguridad de red](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="84463-119">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="84463-120">Seguridad de la información</span><span class="sxs-lookup"><span data-stu-id="84463-120">Information security</span></span>     |  <span data-ttu-id="84463-121">Consulte [seguridad](security.md#information-security) de la información</span><span class="sxs-lookup"><span data-stu-id="84463-121">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="84463-122">Recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="84463-122">Data recovery</span></span>     | <span data-ttu-id="84463-123">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="84463-123">OneDrive for Business</span></span>        |
|<span data-ttu-id="84463-124">Productividad principal</span><span class="sxs-lookup"><span data-stu-id="84463-124">Core productivity</span></span>     | <span data-ttu-id="84463-125">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="84463-125">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="84463-126">Explorador</span><span class="sxs-lookup"><span data-stu-id="84463-126">Browser</span></span>     | <span data-ttu-id="84463-127">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="84463-127">Microsoft Edge</span></span>        |




<span data-ttu-id="84463-128">Microsoft Managed Desktop puede supervisar otro software que se ejecuta en dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="84463-128">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="84463-129">Si afecta negativamente a la seguridad, el rendimiento o la confiabilidad del sistema, es posible que necesite solicitar una excepción al plan de servicio.</span><span class="sxs-lookup"><span data-stu-id="84463-129">If it negatively impacts system security, performance, or reliability, you might be required to request an exception to the service plan.</span></span>


