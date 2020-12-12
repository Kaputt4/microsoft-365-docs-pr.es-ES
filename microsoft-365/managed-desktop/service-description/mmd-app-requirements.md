---
title: Requisitos de la aplicación de escritorio administrada de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659719"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="63fde-103">Requisitos de la aplicación de escritorio administrada de Microsoft</span><span class="sxs-lookup"><span data-stu-id="63fde-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="63fde-104">Microsoft Managed Desktop requiere que administremos los dispositivos con un enfoque específico para garantizar el rendimiento, la confiabilidad y la capacidad de servicio de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="63fde-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="63fde-105">Área de administración</span><span class="sxs-lookup"><span data-stu-id="63fde-105">Management area</span></span>  |<span data-ttu-id="63fde-106">Enfoque del escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="63fde-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="63fde-107">Configuración de dispositivos o administración de directivas</span><span class="sxs-lookup"><span data-stu-id="63fde-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="63fde-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="63fde-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="63fde-109">Administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="63fde-109">Application management</span></span>     | <span data-ttu-id="63fde-110">Microsoft Intune y portal de la compañía</span><span class="sxs-lookup"><span data-stu-id="63fde-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="63fde-111">Implementación de controladores</span><span class="sxs-lookup"><span data-stu-id="63fde-111">Driver deployment</span></span>     |  <span data-ttu-id="63fde-112">Controladores incluidos con el dispositivo, Windows Update o Intune</span><span class="sxs-lookup"><span data-stu-id="63fde-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="63fde-113">Seguridad del dispositivo</span><span class="sxs-lookup"><span data-stu-id="63fde-113">Device security</span></span>     | <span data-ttu-id="63fde-114">Consulte [seguridad de dispositivos](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="63fde-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="63fde-115">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="63fde-115">Identity and access management</span></span>     | <span data-ttu-id="63fde-116">Consulte [Administración de identidades y acceso](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="63fde-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="63fde-117">Seguridad de red</span><span class="sxs-lookup"><span data-stu-id="63fde-117">Network security</span></span>     | <span data-ttu-id="63fde-118">Consulte [seguridad de red](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="63fde-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="63fde-119">Seguridad de la información</span><span class="sxs-lookup"><span data-stu-id="63fde-119">Information security</span></span>     |  <span data-ttu-id="63fde-120">Consulte [seguridad](security.md#information-security) de la información</span><span class="sxs-lookup"><span data-stu-id="63fde-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="63fde-121">Recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="63fde-121">Data recovery</span></span>     | <span data-ttu-id="63fde-122">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="63fde-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="63fde-123">Productividad principal</span><span class="sxs-lookup"><span data-stu-id="63fde-123">Core productivity</span></span>     | <span data-ttu-id="63fde-124">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="63fde-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="63fde-125">Explorador</span><span class="sxs-lookup"><span data-stu-id="63fde-125">Browser</span></span>     | <span data-ttu-id="63fde-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="63fde-126">Microsoft Edge</span></span>        |




<span data-ttu-id="63fde-127">Microsoft Managed Desktop puede supervisar otro software que se ejecuta en dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="63fde-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="63fde-128">Si afecta negativamente a la administración de dispositivos, la seguridad de los dispositivos, el rendimiento o la confiabilidad, es posible que deba solicitar una [excepción al plan de servicio](customizing.md).</span><span class="sxs-lookup"><span data-stu-id="63fde-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
