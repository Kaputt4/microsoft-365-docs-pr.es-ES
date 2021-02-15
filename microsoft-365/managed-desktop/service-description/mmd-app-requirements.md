---
title: Requisitos de aplicaciones de Escritorio administrado de Microsoft
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
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="08a9c-103">Requisitos de aplicaciones de Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="08a9c-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="08a9c-104">Escritorio administrado de Microsoft requiere que administremos dispositivos mediante un enfoque específico para garantizar el rendimiento, la confiabilidad y la capacidad de servicio de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="08a9c-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="08a9c-105">Área de administración</span><span class="sxs-lookup"><span data-stu-id="08a9c-105">Management area</span></span>  |<span data-ttu-id="08a9c-106">Enfoque de Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="08a9c-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="08a9c-107">Configuración de dispositivos o administración de directivas</span><span class="sxs-lookup"><span data-stu-id="08a9c-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="08a9c-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="08a9c-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="08a9c-109">Administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="08a9c-109">Application management</span></span>     | <span data-ttu-id="08a9c-110">Microsoft Intune y portal de empresa</span><span class="sxs-lookup"><span data-stu-id="08a9c-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="08a9c-111">Implementación de controladores</span><span class="sxs-lookup"><span data-stu-id="08a9c-111">Driver deployment</span></span>     |  <span data-ttu-id="08a9c-112">Controladores incluidos con el dispositivo, Windows Update o Intune</span><span class="sxs-lookup"><span data-stu-id="08a9c-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="08a9c-113">Seguridad del dispositivo</span><span class="sxs-lookup"><span data-stu-id="08a9c-113">Device security</span></span>     | <span data-ttu-id="08a9c-114">Consulta Seguridad [del dispositivo](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="08a9c-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="08a9c-115">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="08a9c-115">Identity and access management</span></span>     | <span data-ttu-id="08a9c-116">Ver administración [de identidades y acceso](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="08a9c-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="08a9c-117">Seguridad de red</span><span class="sxs-lookup"><span data-stu-id="08a9c-117">Network security</span></span>     | <span data-ttu-id="08a9c-118">Consulta [Seguridad de red](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="08a9c-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="08a9c-119">Seguridad de la información</span><span class="sxs-lookup"><span data-stu-id="08a9c-119">Information security</span></span>     |  <span data-ttu-id="08a9c-120">Vea [Seguridad de la información](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="08a9c-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="08a9c-121">Recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="08a9c-121">Data recovery</span></span>     | <span data-ttu-id="08a9c-122">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="08a9c-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="08a9c-123">Productividad principal</span><span class="sxs-lookup"><span data-stu-id="08a9c-123">Core productivity</span></span>     | <span data-ttu-id="08a9c-124">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="08a9c-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="08a9c-125">Explorador</span><span class="sxs-lookup"><span data-stu-id="08a9c-125">Browser</span></span>     | <span data-ttu-id="08a9c-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="08a9c-126">Microsoft Edge</span></span>        |




<span data-ttu-id="08a9c-127">Escritorio administrado de Microsoft puede supervisar otro software que se ejecuta en dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="08a9c-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="08a9c-128">Si afecta negativamente a la administración de dispositivos, la seguridad, el rendimiento o la confiabilidad de los dispositivos, es posible que deba solicitar una excepción [al plan de servicio.](customizing.md)</span><span class="sxs-lookup"><span data-stu-id="08a9c-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
