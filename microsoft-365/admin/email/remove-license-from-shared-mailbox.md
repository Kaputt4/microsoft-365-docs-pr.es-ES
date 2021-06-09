---
title: Quitar la licencia de un buzón compartido
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Quite una licencia de un buzón compartido para asignarla a otro usuario o devolver la licencia para que no la pague. '
ms.date: 05/11/2021
ms.openlocfilehash: dd2d99d762a4a68a9b0400353d64dabb536a891c
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821433"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="dbadc-103">Quitar la licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="dbadc-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="dbadc-104">Los buzones compartidos normalmente no requieren una licencia.</span><span class="sxs-lookup"><span data-stu-id="dbadc-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="dbadc-105">Siga estas instrucciones para quitar una licencia de un buzón compartido para que pueda asignarla a un usuario o devolver la licencia para que no pague una licencia que no necesite.</span><span class="sxs-lookup"><span data-stu-id="dbadc-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="dbadc-106">Se requiere una licencia en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="dbadc-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="dbadc-107">El buzón compartido tiene más de 50 GB de almacenamiento en uso.</span><span class="sxs-lookup"><span data-stu-id="dbadc-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="dbadc-108">El buzón compartido usa archivado local.</span><span class="sxs-lookup"><span data-stu-id="dbadc-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="dbadc-109">El buzón compartido se coloca en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="dbadc-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="dbadc-110">El buzón compartido tiene asignada una licencia de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="dbadc-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

## <a name="remove-the-license"></a><span data-ttu-id="dbadc-111">Quitar la licencia</span><span class="sxs-lookup"><span data-stu-id="dbadc-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="dbadc-112">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="dbadc-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="dbadc-113">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="dbadc-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="dbadc-114">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="dbadc-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

   > [!NOTE]
   > <span data-ttu-id="dbadc-115">Debe quitar la licencia de la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="dbadc-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="dbadc-116">No puede quitar la licencia de la página Buzón compartido porque las licencias son configuraciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="dbadc-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>
  
2. <span data-ttu-id="dbadc-117">Seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="dbadc-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="dbadc-118">Una de **las pestañas Licencias y Aplicaciones,** expanda **Licencias** y desactive la casilla de la licencia que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="dbadc-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="dbadc-119">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="dbadc-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="dbadc-120">Cuando vuelva a la **página Usuarios activos,** el estado del buzón compartido será **Sin licencia.**</span><span class="sxs-lookup"><span data-stu-id="dbadc-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="dbadc-121">Sigue pagando por la licencia.</span><span class="sxs-lookup"><span data-stu-id="dbadc-121">You're still paying for the license.</span></span> <span data-ttu-id="dbadc-122">Para dejar de pagar por ella, [quite la licencia de la suscripción](../../commerce/licenses/buy-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="dbadc-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="dbadc-123">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="dbadc-123">Related content</span></span>

<span data-ttu-id="dbadc-124">[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="dbadc-124">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="dbadc-125">[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="dbadc-125">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="dbadc-126">[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="dbadc-126">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="dbadc-127">[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="dbadc-127">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="dbadc-128">[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="dbadc-128">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>
