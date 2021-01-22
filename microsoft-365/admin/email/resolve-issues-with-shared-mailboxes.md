---
title: Resolver problemas con los buzones compartidos
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Pruebe estas soluciones si tiene problemas con buzones compartidos.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926491"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="80b61-103">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="80b61-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="80b61-104">Si ve mensajes de error al crear o usar un buzón compartido, pruebe estas posibles soluciones.</span><span class="sxs-lookup"><span data-stu-id="80b61-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="80b61-105">Error al crear buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="80b61-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="80b61-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="80b61-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="80b61-107">Si ve el mensaje de error, la dirección proxy "smtp:<shared mailbox name " ya está siendo utilizada por las direcciones proxy o **\> LegacyExchangeDN de " \<name> ". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span><span class="sxs-lookup"><span data-stu-id="80b61-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="80b61-108">Por ejemplo, supongamos que desea los buzones compartidos denominados info@domain1 y info@domain2.</span><span class="sxs-lookup"><span data-stu-id="80b61-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="80b61-109">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="80b61-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="80b61-110">Use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80b61-110">Use Windows PowerShell.</span></span> <span data-ttu-id="80b61-111">Consulte esta entrada de blog para obtener instrucciones: Crear buzones [compartidos con el mismo alias en dominios diferentes](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="80b61-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="80b61-112">Asigne al segundo buzón compartido un nombre diferente del principio para evitar el error.</span><span class="sxs-lookup"><span data-stu-id="80b61-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="80b61-113">A continuación, en el centro de administración, cambie el nombre del buzón compartido por el que desea que sea.</span><span class="sxs-lookup"><span data-stu-id="80b61-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="80b61-114">Error sobre no tener permisos de envío al usar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="80b61-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="80b61-115">Si creó un buzón compartido y, a continuación, intenta enviar un mensaje desde él, es posible que obtenga esto:</span><span class="sxs-lookup"><span data-stu-id="80b61-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="80b61-116">**No se pudo enviar este mensaje. No tiene permiso para enviar el mensaje en nombre del usuario especificado.**</span><span class="sxs-lookup"><span data-stu-id="80b61-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="80b61-117">Este mensaje aparece cuando Microsoft 365 está experimentando un problema de latencia de replicación.</span><span class="sxs-lookup"><span data-stu-id="80b61-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="80b61-118">Debería desaparecer en una hora aproximadamente, cuando la información sobre el nuevo buzón compartido (o usuario agregado) se replique en todos nuestros centros de datos.</span><span class="sxs-lookup"><span data-stu-id="80b61-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="80b61-119">Espere una hora y vuelva a intentarlo para enviar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="80b61-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="80b61-120">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="80b61-120">Related articles</span></span>

[<span data-ttu-id="80b61-121">Acerca de los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="80b61-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="80b61-122">Crear un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="80b61-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="80b61-123">Configurar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="80b61-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="80b61-124">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="80b61-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="80b61-125">Quitar la licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="80b61-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

