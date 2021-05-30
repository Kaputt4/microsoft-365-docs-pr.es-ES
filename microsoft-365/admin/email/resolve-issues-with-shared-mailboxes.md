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
description: Es posible que reciba errores al configurar buzones compartidos. Pruebe estas soluciones si tiene problemas con buzones compartidos.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706135"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="5c79b-104">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="5c79b-104">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="5c79b-105">Si ve mensajes de error al crear o usar un buzón compartido, pruebe estas posibles soluciones.</span><span class="sxs-lookup"><span data-stu-id="5c79b-105">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="5c79b-106">Error al crear buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="5c79b-106">Error when creating shared mailboxes</span></span>
<span data-ttu-id="5c79b-107"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="5c79b-107"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="5c79b-108">Si ve el mensaje de error, la dirección proxy "smtp:<nombre de buzón compartido" ya está siendo usada por las direcciones proxy o **\> LegacyExchangeDN de " \<name> ". Elija otra dirección de proxy,** significa que está intentando dar al buzón compartido un nombre que ya está en uso.</span><span class="sxs-lookup"><span data-stu-id="5c79b-108">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="5c79b-109">Por ejemplo, supongamos que desea los buzones compartidos denominados info@domain1 y info@domain2.</span><span class="sxs-lookup"><span data-stu-id="5c79b-109">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="5c79b-110">Hay dos formas de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="5c79b-110">There are two ways to do this:</span></span>

  - <span data-ttu-id="5c79b-111">Use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c79b-111">Use Windows PowerShell.</span></span> <span data-ttu-id="5c79b-112">Vea esta entrada de blog para obtener instrucciones: [Crear buzones compartidos con el mismo alias en dominios diferentes](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="5c79b-112">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="5c79b-113">Asigne al segundo buzón compartido un nombre diferente del inicio para evitar el error.</span><span class="sxs-lookup"><span data-stu-id="5c79b-113">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="5c79b-114">A continuación, en el Centro de administración, cambie el nombre del buzón compartido a lo que desea que sea.</span><span class="sxs-lookup"><span data-stu-id="5c79b-114">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="5c79b-115">Error sobre no tener permisos de envío al usar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="5c79b-115">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="5c79b-116">Si creó un buzón compartido y, a continuación, intenta enviar un mensaje desde él, puede obtener esto:</span><span class="sxs-lookup"><span data-stu-id="5c79b-116">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="5c79b-117">**No se pudo enviar este mensaje. No tiene permiso para enviar el mensaje en nombre del usuario especificado.**</span><span class="sxs-lookup"><span data-stu-id="5c79b-117">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="5c79b-118">Este mensaje aparece cuando Microsoft 365 está experimentando un problema de latencia de replicación.</span><span class="sxs-lookup"><span data-stu-id="5c79b-118">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="5c79b-119">Debería desaparecer en una hora aproximadamente, cuando la información sobre el nuevo buzón compartido (o usuario agregado) se replique en todos nuestros centros de datos.</span><span class="sxs-lookup"><span data-stu-id="5c79b-119">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="5c79b-120">Espere una hora y vuelva a intentar enviar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="5c79b-120">Wait an hour and then try again to send a message.</span></span>

## <a name="related-content"></a><span data-ttu-id="5c79b-121">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="5c79b-121">Related content</span></span>

<span data-ttu-id="5c79b-122">[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="5c79b-122">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="5c79b-123">[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="5c79b-123">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="5c79b-124">[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="5c79b-124">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="5c79b-125">[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="5c79b-125">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="5c79b-126">[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="5c79b-126">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>


    

