---
title: Microsoft 365 Lighthouse de lista de inquilinos
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la lista de inquilinos.
ms.openlocfilehash: 05c6bf6c1b9529d05fac04c2d5c43802280cfbc9
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395339"
---
# <a name="microsoft-365-lighthouse-tenant-list-overview"></a><span data-ttu-id="b2f88-103">Microsoft 365 Lighthouse de lista de inquilinos</span><span class="sxs-lookup"><span data-stu-id="b2f88-103">Microsoft 365 Lighthouse tenant list overview</span></span>

> [!NOTE]
> <span data-ttu-id="b2f88-104">Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2f88-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="b2f88-105">Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="b2f88-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="b2f88-106">La Microsoft 365 Lighthouse de inquilinos proporciona información sobre los diferentes inquilinos con los que tiene un contrato, incluido el estado de incorporación de inquilinos con respecto a Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="b2f88-106">The Microsoft 365 Lighthouse tenant list provides insights into the different tenants you have a contract with, including tenant onboarding status relative to Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="b2f88-107">La lista de inquilinos también le permite etiquetar los inquilinos para proporcionar diferentes filtros a lo largo de Microsoft 365 Lighthouse y profundizar para obtener más información sobre un inquilino determinado y el estado de su plan de implementación.</span><span class="sxs-lookup"><span data-stu-id="b2f88-107">The tenant list also lets you tag tenants to provide different filters throughout Microsoft 365 Lighthouse, and drill down to learn more about a given tenant and the status of their deployment plan.</span></span>

<span data-ttu-id="b2f88-108">Después de que los inquilinos [cumplan Microsoft 365 Lighthouse requisitos](m365-lighthouse-requirements.md)de incorporación, su estado se mostrará **como Activo** en la lista de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="b2f88-108">After your tenants meet the [Microsoft 365 Lighthouse onboarding requirements](m365-lighthouse-requirements.md), their status will show as **Active** in the tenant list.</span></span>

<span data-ttu-id="b2f88-109">Para obtener acceso a la lista de inquilinos Microsoft 365 Lighthouse, seleccione **Inquilinos** en el panel de navegación izquierdo para abrir la página Inquilinos.</span><span class="sxs-lookup"><span data-stu-id="b2f88-109">To access the tenant list in Microsoft 365 Lighthouse, select **Tenants** in the left navigation pane to open the Tenants page.</span></span>

## <a name="tenant-status"></a><span data-ttu-id="b2f88-110">Estado del inquilino</span><span class="sxs-lookup"><span data-stu-id="b2f88-110">Tenant status</span></span>

<span data-ttu-id="b2f88-111">En la tabla siguiente se muestran los diferentes mensajes de estado y su significado.</span><span class="sxs-lookup"><span data-stu-id="b2f88-111">The following table shows the different status messages and their meaning.</span></span><br><br>

| <span data-ttu-id="b2f88-112">Mensaje de estado</span><span class="sxs-lookup"><span data-stu-id="b2f88-112">Status message</span></span> | <span data-ttu-id="b2f88-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2f88-113">Description</span></span> |
|--|--|
| <span data-ttu-id="b2f88-114">Activo</span><span class="sxs-lookup"><span data-stu-id="b2f88-114">Active</span></span> | <span data-ttu-id="b2f88-115">Se ha iniciado la incorporación y el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="b2f88-115">Onboarding and data flow has started.</span></span> |
| <span data-ttu-id="b2f88-116">En proceso</span><span class="sxs-lookup"><span data-stu-id="b2f88-116">In process</span></span> | <span data-ttu-id="b2f88-117">Inquilino detectado, pero no totalmente incorporado.</span><span class="sxs-lookup"><span data-stu-id="b2f88-117">Tenant discovered, but not fully onboarded.</span></span> |
| <span data-ttu-id="b2f88-118">Ineligible, DAP</span><span class="sxs-lookup"><span data-stu-id="b2f88-118">Ineligible, DAP</span></span> | <span data-ttu-id="b2f88-119">Se requiere la configuración de privilegios de administrador delegados (DAP).</span><span class="sxs-lookup"><span data-stu-id="b2f88-119">Delegated Admin Privileges (DAP) setup is required.</span></span> |
| <span data-ttu-id="b2f88-120">Ineligible, recuento de usuarios</span><span class="sxs-lookup"><span data-stu-id="b2f88-120">Ineligible, user count</span></span> | <span data-ttu-id="b2f88-121">El inquilino tiene más usuarios de los permitidos.</span><span class="sxs-lookup"><span data-stu-id="b2f88-121">Tenant has more users than allowed.</span></span> |
| <span data-ttu-id="b2f88-122">Ineligible, licencia</span><span class="sxs-lookup"><span data-stu-id="b2f88-122">Ineligible, license</span></span> | <span data-ttu-id="b2f88-123">El inquilino no tiene la licencia necesaria.</span><span class="sxs-lookup"><span data-stu-id="b2f88-123">Tenant does not have required license.</span></span> |
| <span data-ttu-id="b2f88-124">Inactivo</span><span class="sxs-lookup"><span data-stu-id="b2f88-124">Inactive</span></span> | <span data-ttu-id="b2f88-125">El espacio empresarial ya no está activo.</span><span class="sxs-lookup"><span data-stu-id="b2f88-125">Tenant is no longer active.</span></span> |

<span data-ttu-id="b2f88-126">Una vez inactivo un espacio empresarial, no puede realizar ninguna acción en el espacio empresarial mientras Microsoft 365 Lighthouse completa el proceso de inactivación.</span><span class="sxs-lookup"><span data-stu-id="b2f88-126">Once you inactivate a tenant, you can't take action on the tenant while Microsoft 365 Lighthouse completes the inactivation process.</span></span> <span data-ttu-id="b2f88-127">La inactivación puede tardar hasta 48 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="b2f88-127">It may take up to 48 hours for inactivation to complete.</span></span>

<span data-ttu-id="b2f88-128">Si decide reactivar un inquilino, los datos pueden tardar hasta 48 horas en volver a aparecer.</span><span class="sxs-lookup"><span data-stu-id="b2f88-128">If you decide to reactivate a tenant, it may take up to 48 hours for data to reappear.</span></span>

## <a name="tenant-tags"></a><span data-ttu-id="b2f88-129">Etiquetas de inquilino</span><span class="sxs-lookup"><span data-stu-id="b2f88-129">Tenant tags</span></span>

<span data-ttu-id="b2f88-130">Puede etiquetar los inquilinos del cliente con una etiqueta personalizada dentro de Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="b2f88-130">You can tag your customer tenants with a custom label within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="b2f88-131">Estas etiquetas se pueden usar para organizar los inquilinos y también pueden ayudarle a filtrar fácilmente las vistas e información existentes disponibles para conjuntos relevantes de inquilinos de clientes.</span><span class="sxs-lookup"><span data-stu-id="b2f88-131">These tags can be used to organize your tenants and can also help you easily filter the existing views and insights available to relevant sets of customer tenants.</span></span> <span data-ttu-id="b2f88-132">También puede administrar las etiquetas y los inquilinos a los que están asignados desde la página Inquilinos.</span><span class="sxs-lookup"><span data-stu-id="b2f88-132">You can also manage your tags and which tenants they're assigned to from the Tenants page.</span></span>

## <a name="related-content"></a><span data-ttu-id="b2f88-133">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="b2f88-133">Related content</span></span>

<span data-ttu-id="b2f88-134">[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="b2f88-134">[Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (article)</span></span>\
<span data-ttu-id="b2f88-135">[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)</span><span class="sxs-lookup"><span data-stu-id="b2f88-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>