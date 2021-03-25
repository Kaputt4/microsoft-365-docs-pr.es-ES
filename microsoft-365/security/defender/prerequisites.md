---
title: Requisitos previos de Microsoft 365 Defender
description: Obtenga información sobre los requisitos de licencias, hardware y software y otras opciones de configuración para Microsoft 365 Defender
keywords: requisitos, requisitos previos, hardware, software, explorador, MTP, M365, licencia, E5, A5, EMS, compra
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f9904ecb5b9ab0a0f634903a5dc0ee3049d06b38
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074784"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="41d77-104">Requisitos previos de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41d77-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="41d77-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="41d77-105">**Applies to:**</span></span>
- <span data-ttu-id="41d77-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41d77-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="41d77-107">Obtenga información sobre las licencias y otros requisitos para el aprovisionamiento y el [uso de Microsoft 365 Defender](microsoft-365-defender.md).</span><span class="sxs-lookup"><span data-stu-id="41d77-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-365-defender.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="41d77-108">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="41d77-108">Licensing requirements</span></span>
<span data-ttu-id="41d77-109">Cualquiera de estas licencias le da acceso a las características de Microsoft 365 Defender en el Centro de seguridad de Microsoft 365 sin costo adicional:</span><span class="sxs-lookup"><span data-stu-id="41d77-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="41d77-110">Microsoft 365 E5 o A5</span><span class="sxs-lookup"><span data-stu-id="41d77-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="41d77-111">Microsoft 365 E5 Security o A5 Security</span><span class="sxs-lookup"><span data-stu-id="41d77-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="41d77-112">Windows 10 Enterprise E5 o A5</span><span class="sxs-lookup"><span data-stu-id="41d77-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="41d77-113">Enterprise Mobility + Security (EMS) E5 o A5</span><span class="sxs-lookup"><span data-stu-id="41d77-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="41d77-114">Office 365 E5 o A5</span><span class="sxs-lookup"><span data-stu-id="41d77-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="41d77-115">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="41d77-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="41d77-116">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="41d77-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="41d77-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="41d77-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="41d77-118">Defender para Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="41d77-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="41d77-119">Para obtener más información, vea los planes de servicio de [Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="41d77-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="41d77-120">¿Todavía no tiene licencia?</span><span class="sxs-lookup"><span data-stu-id="41d77-120">Don't have license yet?</span></span> [<span data-ttu-id="41d77-121">Probar o comprar una suscripción a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41d77-121">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="41d77-122">Comprobar las licencias existentes</span><span class="sxs-lookup"><span data-stu-id="41d77-122">Check your existing  licenses</span></span>
<span data-ttu-id="41d77-123">Vaya al Centro de administración de Microsoft 365 ([admin.microsoft.com](https://admin.microsoft.com/)) para ver las licencias existentes.</span><span class="sxs-lookup"><span data-stu-id="41d77-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="41d77-124">En el Centro de administración, vaya a **Facturación** > **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="41d77-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="41d77-125">Debe tener asignado el rol De administrador **de** facturación o Lector **global** en [Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver la información de licencia.</span><span class="sxs-lookup"><span data-stu-id="41d77-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="41d77-126">Si tiene problemas de acceso, póngase en contacto con un administrador global.</span><span class="sxs-lookup"><span data-stu-id="41d77-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="41d77-127">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="41d77-127">Required permissions</span></span>
<span data-ttu-id="41d77-128">Debe ser un administrador **global o** un administrador **de seguridad** en Azure Active Directory para activar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="41d77-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="41d77-129">Para obtener la lista de roles necesarios para usar Microsoft 365 Defender e información sobre cómo se regula el acceso a los datos, lea acerca de cómo administrar el acceso a [Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="41d77-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="41d77-130">Requisitos de los exploradores</span><span class="sxs-lookup"><span data-stu-id="41d77-130">Browser requirements</span></span>
<span data-ttu-id="41d77-131">Accede a Microsoft 365 Defender en el centro de seguridad de Microsoft 365 con Microsoft Edge, Internet Explorer 11 o cualquier explorador web compatible con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="41d77-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="41d77-132">Disponibilidad para GCC, GCC High y otras instituciones gubernamentales de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="41d77-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="41d77-133">Actualmente, Microsoft 365 Defender *no está* disponible para:</span><span class="sxs-lookup"><span data-stu-id="41d77-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="41d77-134">Nube de la comunidad gubernamental de ESTADOS UNIDOS (GCC)</span><span class="sxs-lookup"><span data-stu-id="41d77-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="41d77-135">Alta nube de la comunidad gubernamental de Estados Unidos (GCC High)</span><span class="sxs-lookup"><span data-stu-id="41d77-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="41d77-136">Departamento de Defensa de ESTADOS UNIDOS</span><span class="sxs-lookup"><span data-stu-id="41d77-136">US Department of Defense</span></span>
- <span data-ttu-id="41d77-137">Todas las instituciones gubernamentales de ESTADOS UNIDOS con licencias comerciales</span><span class="sxs-lookup"><span data-stu-id="41d77-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="41d77-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="41d77-138">Related topics</span></span>
- [<span data-ttu-id="41d77-139">Introducción a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41d77-139">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="41d77-140">Activar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41d77-140">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="41d77-141">Administrar el acceso y los permisos</span><span class="sxs-lookup"><span data-stu-id="41d77-141">Manage access and permissions</span></span>](m365d-permissions.md)
