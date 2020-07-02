---
title: Resolver conflictos de licencia
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Obtenga información sobre cómo resolver conflictos de licencia con su suscripción de Microsoft 365 para empresas.
ms.openlocfilehash: 2270fd3ad831ec0ad92ac4eddec5f08a1d07f8be
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015976"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="613cc-103">Resolver conflictos de licencia</span><span class="sxs-lookup"><span data-stu-id="613cc-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="613cc-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="613cc-104">The admin center is changing.</span></span> <span data-ttu-id="613cc-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="613cc-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="613cc-106">Le recomendamos que compre las licencias que necesita para su suscripción antes de crear nuevos usuarios.</span><span class="sxs-lookup"><span data-stu-id="613cc-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="613cc-107">De esa forma, se puede asignar una licencia a los nuevos usuarios al crear cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="613cc-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="613cc-108">Si ya asignó todas las licencias a los usuarios, pero algunas de las licencias han expirado, o si intenta quitar una licencia que ya se asignó a un usuario, se producirán conflictos de licencias.</span><span class="sxs-lookup"><span data-stu-id="613cc-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="613cc-109">Para obtener más información, vea [quitar licencias de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="613cc-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="613cc-110">¿Cómo puedo ver los conflictos de licencia?</span><span class="sxs-lookup"><span data-stu-id="613cc-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="613cc-111">En el centro de administración, vaya a **Billing** la > página <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de facturación.</span><span class="sxs-lookup"><span data-stu-id="613cc-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="613cc-112">En el centro de administración, vaya a **Billing** la > página <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">licencias</a> de facturación.</span><span class="sxs-lookup"><span data-stu-id="613cc-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="613cc-113">En el centro de administración, vaya a **Billing** la > página <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">licencias</a> de facturación.</span><span class="sxs-lookup"><span data-stu-id="613cc-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="613cc-114">Consulte la columna **Estado** para obtener información sobre el conflicto.</span><span class="sxs-lookup"><span data-stu-id="613cc-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="613cc-115">Si hay un conflicto, verá un mensaje de advertencia, lo que indica que uno o más usuarios necesitan una licencia válida.</span><span class="sxs-lookup"><span data-stu-id="613cc-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="613cc-116">Si no hay ningún conflicto, no verá la columna **Estado**.</span><span class="sxs-lookup"><span data-stu-id="613cc-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="613cc-117">¿Cómo puedo resolver los conflictos de licencia?</span><span class="sxs-lookup"><span data-stu-id="613cc-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="613cc-118">Para resolver los conflictos de licencia, puede [comprar más licencias](../../commerce/licenses/buy-licenses.md) o [quitar licencias de los usuarios que ya no las necesiten](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="613cc-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="613cc-119">De manera opcional, puede [eliminar una cuenta de usuario para liberar una licencia](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="613cc-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="613cc-120">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="613cc-120">Related articles</span></span>

[<span data-ttu-id="613cc-121">Asignar licencias a usuarios</span><span class="sxs-lookup"><span data-stu-id="613cc-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="613cc-122">Quitar licencias de usuarios</span><span class="sxs-lookup"><span data-stu-id="613cc-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
