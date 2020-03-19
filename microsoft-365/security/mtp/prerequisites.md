---
title: Requisitos previos de la Protección contra amenazas de Microsoft
description: Obtenga más información sobre las licencias, requisitos previos de hardware y software, y otras opciones de configuración que le ofrece Protección contra amenazas de Microsoft.
keywords: requisitos, requisitos previos, hardware, software, explorador, MTP, M365, licencia, E5, A5, EMS, compras
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c482e46cf51cbf11960c02663221df0c136b067c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857184"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="2f697-104">Requisitos previos de la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2f697-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="2f697-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2f697-105">**Applies to:**</span></span>
- <span data-ttu-id="2f697-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2f697-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2f697-107">Obtenga información sobre las licencias, los requisitos de hardware y software, y otras opciones de configuración para aprovisionar y usar la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f697-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2f697-108">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="2f697-108">Licensing requirements</span></span>
<span data-ttu-id="2f697-109">Para usar la protección contra amenazas de Microsoft, necesita una sola licencia o una combinación de licencias.</span><span class="sxs-lookup"><span data-stu-id="2f697-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span>

### <a name="single-license"></a><span data-ttu-id="2f697-110">Única licencia</span><span class="sxs-lookup"><span data-stu-id="2f697-110">Single license</span></span>
<span data-ttu-id="2f697-111">Puede usar *una* de las siguientes licencias:</span><span class="sxs-lookup"><span data-stu-id="2f697-111">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="2f697-112">Microsoft 365 E5 o A5</span><span class="sxs-lookup"><span data-stu-id="2f697-112">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="2f697-113">Seguridad de Microsoft 365 E5 o de la A5</span><span class="sxs-lookup"><span data-stu-id="2f697-113">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="2f697-114">Combinación de licencias</span><span class="sxs-lookup"><span data-stu-id="2f697-114">Combination of licenses</span></span>
<span data-ttu-id="2f697-115">También puede usar una combinación de licencias para suscripciones a E5 o A5 a Office 365, *Enterprise Mobility + Security (EMS)* y Windows.</span><span class="sxs-lookup"><span data-stu-id="2f697-115">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="2f697-116">La combinación de licencia debe incluir *todas* estas licencias:</span><span class="sxs-lookup"><span data-stu-id="2f697-116">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="2f697-117">Office 365 E5 o A5</span><span class="sxs-lookup"><span data-stu-id="2f697-117">Office 365 E5 or A5</span></span>
- <span data-ttu-id="2f697-118">*Enterprise Mobility + Security (EMS)* E5 o A5</span><span class="sxs-lookup"><span data-stu-id="2f697-118">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="2f697-119">Windows E5 o A5</span><span class="sxs-lookup"><span data-stu-id="2f697-119">Windows E5 or A5</span></span>

<span data-ttu-id="2f697-120">Para obtener más información, [vea los planes de servicio de Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="2f697-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="2f697-121">¿Todavía no tiene licencia?</span><span class="sxs-lookup"><span data-stu-id="2f697-121">Don't have license yet?</span></span> [<span data-ttu-id="2f697-122">Probar o comprar una suscripción a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f697-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="2f697-123">Comprobar las licencias existentes</span><span class="sxs-lookup"><span data-stu-id="2f697-123">Check your existing  licenses</span></span>
<span data-ttu-id="2f697-124">Vaya al centro de administración de 365 de Microsoft ([admin.Microsoft.com](https://admin.microsoft.com/)) para ver las licencias existentes.</span><span class="sxs-lookup"><span data-stu-id="2f697-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="2f697-125">En el Centro de administración, vaya a **Facturación** > **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="2f697-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="2f697-126">Debe tener asignado el rol de **Administrador de facturación** o de **lector global** [en Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver la información de licencia.</span><span class="sxs-lookup"><span data-stu-id="2f697-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="2f697-127">Si tiene problemas de acceso, póngase en contacto con un administrador global.</span><span class="sxs-lookup"><span data-stu-id="2f697-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="2f697-128">Requisitos de los exploradores</span><span class="sxs-lookup"><span data-stu-id="2f697-128">Browser requirements</span></span>
<span data-ttu-id="2f697-129">Acceda a Microsoft Threat Protection en el centro de seguridad de Microsoft 365 con Microsoft Edge, Internet Explorer 11 o cualquier explorador Web compatible con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="2f697-129">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="2f697-130">Microsoft Threat Protection para la comunidad de administración pública Cloud y la nube de la comunidad de administración de Estados Unidos de Microsoft Cloud High (GCC High) clientes</span><span class="sxs-lookup"><span data-stu-id="2f697-130">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="2f697-131">Actualmente, la protección contra amenazas de Microsoft no está disponible para los clientes de GCC y GCC High.</span><span class="sxs-lookup"><span data-stu-id="2f697-131">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="2f697-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2f697-132">Related topics</span></span>
- [<span data-ttu-id="2f697-133">Introducción a la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2f697-133">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="2f697-134">Habilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2f697-134">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
