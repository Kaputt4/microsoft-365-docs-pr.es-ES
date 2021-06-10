---
title: Más información sobre la retención para Yammer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Más información sobre las directivas de retención que se aplican a Yammer.
ms.openlocfilehash: a8d047845b986029d393816982e6bede3db71485
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861568"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="2a372-103">Más información sobre la retención para Yammer</span><span class="sxs-lookup"><span data-stu-id="2a372-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="2a372-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="2a372-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="2a372-105">Esta característica se encuentra en versión preliminar y todavía no está disponible para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="2a372-105">This feature is in preview and not yet available for all customers.</span></span>

<span data-ttu-id="2a372-106">La información de este artículo complementa el contenido de [Más información sobre la retención](retention.md) porque tiene información que es específica de Yammer.</span><span class="sxs-lookup"><span data-stu-id="2a372-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="2a372-107">Para otras cargas de trabajo, vea:</span><span class="sxs-lookup"><span data-stu-id="2a372-107">For other workloads, see:</span></span>

- [<span data-ttu-id="2a372-108">Obtenga más información sobre la retención de SharePoint y OneDrive</span><span class="sxs-lookup"><span data-stu-id="2a372-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="2a372-109">Más información sobre las directivas de retención para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a372-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="2a372-110">Más información sobre las directivas de retención de Exchange</span><span class="sxs-lookup"><span data-stu-id="2a372-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="2a372-111">Qué se incluye para la retención y eliminación</span><span class="sxs-lookup"><span data-stu-id="2a372-111">What's included for retention and deletion</span></span>

<span data-ttu-id="2a372-112">Los siguientes elementos Yammer se pueden retener y eliminar mediante directivas de retención para los Yammer: chats y mensajes de canal.</span><span class="sxs-lookup"><span data-stu-id="2a372-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="2a372-113">En estos mensajes no se incluyen las reacciones de otras personas en forma de iconos gestuales.</span><span class="sxs-lookup"><span data-stu-id="2a372-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="2a372-114">Cómo funciona la retención con Yammer</span><span class="sxs-lookup"><span data-stu-id="2a372-114">How retention works with Yammer</span></span>

<span data-ttu-id="2a372-115">Puede usar una directiva de retención para conservar y eliminar mensajes de la comunidad y mensajes privados en Yammer.</span><span class="sxs-lookup"><span data-stu-id="2a372-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="2a372-116">Los mensajes privados se almacenan en una carpeta oculta en el buzón de cada usuario incluido en el mensaje, y los mensajes de la comunidad se almacenan en una carpeta oculta similar en el buzón de correo del grupo de la comunidad.</span><span class="sxs-lookup"><span data-stu-id="2a372-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="2a372-117">Los mensajes de Yammer no se ven afectados por las directivas de retención que se configuran para los buzones de los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="2a372-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="2a372-118">Si bien los mensajes de Yammer se almacenan en Exchange, estos datos de Yammer se incluyen solo por una directiva de retención que está configurada para los **mensajes de la comunidad de Yammer** y las ubicaciones de los **mensajes privados de Yammer**.</span><span class="sxs-lookup"><span data-stu-id="2a372-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="2a372-119">Si un usuario está incluido en una directiva de retención activa que retiene los datos de Yammer y usted elimina el buzón de un usuario incluido en esta directiva, dicho buzón se convierte en un [buzón inactivo](inactive-mailboxes-in-office-365.md) para retener los datos de Yammer.</span><span class="sxs-lookup"><span data-stu-id="2a372-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="2a372-120">Si no necesita retener los datos de Yammer del usuario, excluya la cuenta del usuario de la directiva de retención antes de eliminar su buzón.</span><span class="sxs-lookup"><span data-stu-id="2a372-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="2a372-121">Una vez que se configura una directiva de retención para los mensajes de Yammer, un trabajo de temporizador del servicio de Exchange evalúa de manera periódica los elementos de la carpeta oculta en la que se almacenan estos mensajes de Yammer.</span><span class="sxs-lookup"><span data-stu-id="2a372-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="2a372-122">El trabajo de temporizador tarda hasta siete días en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="2a372-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="2a372-123">Cuando el período de retención de estos elementos caduca, se trasladan a la carpeta SubstrateHolds, una carpeta oculta ubicada en cada buzón de usuario o grupo para almacenar los elementos "eliminados temporalmente" antes de que se eliminen de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="2a372-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="2a372-124">Debido al [primer principio de retención](retention.md#the-principles-of-retention-or-what-takes-precedence), la eliminación permanente siempre se suspende si el mismo elemento debe conservarse debido a otra directiva de retención o está en retención en eDiscovery por motivos legales o de investigación.</span><span class="sxs-lookup"><span data-stu-id="2a372-124">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="2a372-125">Una vez que se configura una directiva de retención para los mensajes de Yammer, las rutas que seguirá el contenido dependerán de si la directiva de retención se configura para retener y luego eliminar, solo para retener, o solo para eliminar.</span><span class="sxs-lookup"><span data-stu-id="2a372-125">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="2a372-126">Cuando la directiva de retención consiste en retener y luego eliminar:</span><span class="sxs-lookup"><span data-stu-id="2a372-126">When the retention policy is to retain and then delete:</span></span>

![Diagrama de flujo de retención de los mensajes de Yammer](../media/yammerretentionlifecycle.png)

<span data-ttu-id="2a372-128">Para las dos rutas en el diagrama:</span><span class="sxs-lookup"><span data-stu-id="2a372-128">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="2a372-129">Si el usuario **edita o elimina un mensaje de Yammer** durante el período de retención, el mensaje original se copia (si se edita) o se traslada (si se elimina) a la carpeta SubstrateHolds de manera inmediata.</span><span class="sxs-lookup"><span data-stu-id="2a372-129">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="2a372-130">El mensaje se almacena hasta que finaliza el período de retención y, luego, se elimina de forma permanente e inmediata.</span><span class="sxs-lookup"><span data-stu-id="2a372-130">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="2a372-131">**Si no se elimina un mensaje de Yammer**, o se editan mensajes actuales, el mensaje se traslada a la carpeta SubstrateHolds después de que el período de retención expire.</span><span class="sxs-lookup"><span data-stu-id="2a372-131">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="2a372-132">Esta acción tarda hasta siete días después de la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="2a372-132">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="2a372-133">Cuando un mensaje se encuentra en la carpeta SubstrateHolds, se elimina entonces de forma permanente e inmediata.</span><span class="sxs-lookup"><span data-stu-id="2a372-133">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a372-134">Los mensajes de la carpeta SubstrateHolds se pueden buscar con las herramientas de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2a372-134">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="2a372-135">Hasta antes de que los mensajes se eliminen de forma permanente (en la carpeta SubstrateHolds), aún se los puede encontrar con las herramientas de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2a372-135">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="2a372-136">Cuando la directiva de retención es de solo retención, o solo eliminación, las rutas de acceso de contenido son variaciones de retener y eliminar.</span><span class="sxs-lookup"><span data-stu-id="2a372-136">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="2a372-137">Rutas de contenido para la directiva de retención de solo retención</span><span class="sxs-lookup"><span data-stu-id="2a372-137">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="2a372-138">**Si se edita o elimina un mensaje de Yammer**: se crea, de manera inmediata, una copia del mensaje original en la carpeta SubstrateHolds y se retiene ahí hasta que expire el periodo de retención.</span><span class="sxs-lookup"><span data-stu-id="2a372-138">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="2a372-139">Luego, el mensaje se elimina de forma permanente e inmediata de la carpeta SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="2a372-139">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="2a372-140">**Si el mensaje de Yammer no se modifica ni se elimina** y se editan mensajes actuales durante el período de retención: no sucede nada antes ni después del período de retención. El mensaje permanece en su ubicación original.</span><span class="sxs-lookup"><span data-stu-id="2a372-140">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="2a372-141">Rutas de contenido para la directiva de retención de sólo eliminar</span><span class="sxs-lookup"><span data-stu-id="2a372-141">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="2a372-142">**Si el mensaje de Yammer no se elimina** durante el período de retención: al final del período de retención, el mensaje se mueve a la carpeta SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="2a372-142">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="2a372-143">Esta acción tarda hasta siete días después de la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="2a372-143">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="2a372-144">Luego, el mensaje se elimina de forma permanente e inmediata de la carpeta SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="2a372-144">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="2a372-145">**Si el usuario elimina el mensaje de Yammer** durante el período, el elemento se mueve inmediatamente a la carpeta SubstrateHolds, donde se eliminará de forma permanente e inmediata.</span><span class="sxs-lookup"><span data-stu-id="2a372-145">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="2a372-146">Mensajes y usuarios externos</span><span class="sxs-lookup"><span data-stu-id="2a372-146">Messages and external users</span></span>

<span data-ttu-id="2a372-147">De forma predeterminada, las directivas de retención para los mensajes del usuario de Yammer aplican a todos los usuarios de su organización, pero no aplica a los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="2a372-147">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="2a372-148">Puede aplicar una directiva de retención a usuarios externos con la opción **Elegir usuario** y especificando su cuenta.</span><span class="sxs-lookup"><span data-stu-id="2a372-148">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="2a372-149">En este momento, no se admiten usuarios invitados B2B de Azure.</span><span class="sxs-lookup"><span data-stu-id="2a372-149">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="2a372-150">Cuando un usuario deja la organización</span><span class="sxs-lookup"><span data-stu-id="2a372-150">When a user leaves the organization</span></span> 

<span data-ttu-id="2a372-151">Si un usuario deja la organización y se elimina su cuenta de Microsoft 365, los mensajes del usuario de Yammer que estén sujetos a la retención se almacenarán en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="2a372-151">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="2a372-152">Estos mensajes seguirán sujetos a cualquier directiva de retención que se haya aplicado al buzón antes de pasar a estado inactivo, y el contenido estará disponible para la búsqueda de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2a372-152">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="2a372-153">Para obtener más información, consulte [Buzones de correo inactivos en Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="2a372-153">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="2a372-154">Si el usuario ha guardado archivos en Yammer, consulte la [sección equivalente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) para SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2a372-154">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="2a372-155">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="2a372-155">Limitations</span></span>

<span data-ttu-id="2a372-156">Actualmente, las directivas de retención de Yammer se encuentran en versión preliminar y estamos trabajando continuamente para optimizar la funcionalidad de retención.</span><span class="sxs-lookup"><span data-stu-id="2a372-156">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="2a372-157">Mientras tanto, tenga en cuenta las siguientes limitaciones al usar la retención para los mensajes de la comunidad de Yammer y los mensajes privados:</span><span class="sxs-lookup"><span data-stu-id="2a372-157">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="2a372-158">Al seleccionar **Elegir usuarios** para la ubicación de los **mensajes del usuario de Yammer**, es posible que pueda ver a los invitados y a los usuarios sin buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="2a372-158">When you select **Choose users** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="2a372-159">Las directivas de retención no están diseñadas para estos usuarios, así que no los seleccione.</span><span class="sxs-lookup"><span data-stu-id="2a372-159">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="2a372-160">Instrucciones de configuración</span><span class="sxs-lookup"><span data-stu-id="2a372-160">Configuration guidance</span></span>

<span data-ttu-id="2a372-161">Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a las directivas y las etiquetas de retención](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="2a372-161">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="2a372-162">Si está listo para configurar una directiva de retención para Yammer, consulte [Crear y configurar directivas de retención](create-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2a372-162">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>