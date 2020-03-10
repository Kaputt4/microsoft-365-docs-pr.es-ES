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
ms.openlocfilehash: 3e18759387525ec600c24f74c96d6cddf206fc82
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569050"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="7b926-104">Requisitos previos de la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b926-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="7b926-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7b926-105">**Applies to:**</span></span>
- <span data-ttu-id="7b926-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b926-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7b926-107">Obtenga información sobre las licencias, los requisitos de hardware y software, y otras opciones de configuración para aprovisionar y usar la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7b926-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7b926-108">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="7b926-108">Licensing requirements</span></span>
<span data-ttu-id="7b926-109">Para usar la protección contra amenazas de Microsoft, necesita *una* de las siguientes licencias o combinación de licencias:</span><span class="sxs-lookup"><span data-stu-id="7b926-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="7b926-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7b926-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="7b926-111">Seguridad de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7b926-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="7b926-112">Office 365 E5 y "Enterprise Mobility + Security E5 (EMS E5)" y Windows E5</span><span class="sxs-lookup"><span data-stu-id="7b926-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="7b926-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="7b926-113">Microsoft 365 A5</span></span>

<span data-ttu-id="7b926-114">Para obtener más información, [vea los planes de servicio de Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="7b926-114">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="7b926-115">¿Todavía no tiene licencia?</span><span class="sxs-lookup"><span data-stu-id="7b926-115">Don't have license yet?</span></span> [<span data-ttu-id="7b926-116">Probar o comprar una suscripción a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b926-116">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="7b926-117">Comprobar las licencias existentes</span><span class="sxs-lookup"><span data-stu-id="7b926-117">Check your existing  licenses</span></span>
<span data-ttu-id="7b926-118">Vaya al centro de administración de 365 de Microsoft ([admin.Microsoft.com](https://admin.microsoft.com/)) para ver las licencias existentes.</span><span class="sxs-lookup"><span data-stu-id="7b926-118">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="7b926-119">En el Centro de administración, vaya a **Facturación** > **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="7b926-119">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="7b926-120">Debe tener asignado el rol de **Administrador de facturación** o de **lector global** [en Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver la información de licencia.</span><span class="sxs-lookup"><span data-stu-id="7b926-120">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="7b926-121">Si tiene problemas de acceso, póngase en contacto con un administrador global.</span><span class="sxs-lookup"><span data-stu-id="7b926-121">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="7b926-122">Requisitos de los exploradores</span><span class="sxs-lookup"><span data-stu-id="7b926-122">Browser requirements</span></span>
<span data-ttu-id="7b926-123">Acceda a Microsoft Threat Protection en el centro de seguridad de Microsoft 365 con Microsoft Edge, Internet Explorer 11 o cualquier explorador Web compatible con HTML 5.</span><span class="sxs-lookup"><span data-stu-id="7b926-123">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b926-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7b926-124">Related topics</span></span>
- [<span data-ttu-id="7b926-125">Introducción a la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b926-125">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="7b926-126">Habilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b926-126">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
