---
title: Tabla EmailPostDeliveryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre las acciones posteriores a la entrega realizadas en los correos electrónicos de Microsoft 365 en la tabla EmailPostDeliveryEvents del esquema de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailPostDeliveryEvents, identificador de mensaje de red, remitente, destinatario, identificador de datos adjuntos, nombre de datos adjuntos, veredicto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f4b34abdbfcbd6c3a2f142001a3d486485c86fcd
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515938"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="0174d-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="0174d-104">EmailPostDeliveryEvents</span></span>

<span data-ttu-id="0174d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0174d-105">**Applies to:**</span></span>
- <span data-ttu-id="0174d-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0174d-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0174d-107">La `EmailPostDeliveryEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las acciones posteriores a la entrega realizadas en los mensajes de correo electrónico procesados por Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0174d-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="0174d-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="0174d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0174d-109">Para obtener más información sobre los mensajes de correo electrónico individuales, también puede usar las [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tablas, y [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="0174d-109">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="0174d-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0174d-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0174d-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="0174d-111">Column name</span></span> | <span data-ttu-id="0174d-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0174d-112">Data type</span></span> | <span data-ttu-id="0174d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0174d-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0174d-114">datetime</span><span class="sxs-lookup"><span data-stu-id="0174d-114">datetime</span></span> | <span data-ttu-id="0174d-115">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="0174d-115">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="0174d-116">string</span><span class="sxs-lookup"><span data-stu-id="0174d-116">string</span></span> | <span data-ttu-id="0174d-117">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="0174d-117">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="0174d-118">string</span><span class="sxs-lookup"><span data-stu-id="0174d-118">string</span></span> | <span data-ttu-id="0174d-119">Identificador único del correo electrónico generado por Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0174d-119">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="0174d-120">string</span><span class="sxs-lookup"><span data-stu-id="0174d-120">string</span></span> | <span data-ttu-id="0174d-121">Identificador público para el correo electrónico que establece el sistema de correo electrónico de envío.</span><span class="sxs-lookup"><span data-stu-id="0174d-121">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="0174d-122">string</span><span class="sxs-lookup"><span data-stu-id="0174d-122">string</span></span> | <span data-ttu-id="0174d-123">Acción realizada en la entidad</span><span class="sxs-lookup"><span data-stu-id="0174d-123">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="0174d-124">string</span><span class="sxs-lookup"><span data-stu-id="0174d-124">string</span></span> | <span data-ttu-id="0174d-125">Tipo de actividad que ha desencadenado el evento: corrección manual, ZAP de Phish, ZAP de malware</span><span class="sxs-lookup"><span data-stu-id="0174d-125">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="0174d-126">string</span><span class="sxs-lookup"><span data-stu-id="0174d-126">string</span></span> | <span data-ttu-id="0174d-127">Indica si una acción ha desencadenado un administrador (manualmente o mediante la aprobación de una acción automatizada pendiente) o mediante algún mecanismo especial, como una ZAP o una entrega dinámica</span><span class="sxs-lookup"><span data-stu-id="0174d-127">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="0174d-128">string</span><span class="sxs-lookup"><span data-stu-id="0174d-128">string</span></span> | <span data-ttu-id="0174d-129">Resultado de la acción</span><span class="sxs-lookup"><span data-stu-id="0174d-129">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="0174d-130">string</span><span class="sxs-lookup"><span data-stu-id="0174d-130">string</span></span> | <span data-ttu-id="0174d-131">Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="0174d-131">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="0174d-132">cadena</span><span class="sxs-lookup"><span data-stu-id="0174d-132">string</span></span> | <span data-ttu-id="0174d-133">Ubicación en la que se entregó el correo electrónico: bandeja de entrada / carpeta, local / externo, correo no deseado, cuarentena, erróneo, descartado, elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="0174d-133">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="0174d-134">Tipos de eventos admitidos</span><span class="sxs-lookup"><span data-stu-id="0174d-134">Supported event types</span></span>
<span data-ttu-id="0174d-135">Esta tabla captura eventos con los siguientes `ActionType` valores:</span><span class="sxs-lookup"><span data-stu-id="0174d-135">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="0174d-136">**Corrección manual** : un administrador realizó manualmente una acción en un mensaje de correo electrónico después de que se entregó al buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="0174d-136">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="0174d-137">Esto incluye las acciones realizadas manualmente a través del [Explorador de amenazas](../office-365-security/threat-explorer.md) o las aprobaciones de [las acciones de investigación y respuesta automáticas (Air)](mtp-autoir-actions.md).</span><span class="sxs-lookup"><span data-stu-id="0174d-137">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="0174d-138">**Zap phish** : la [depuración automática de cero horas (ZAP)](../office-365-security/zero-hour-auto-purge.md) llevó a cabo una acción en un correo de suplantación de identidad tras la entrega.</span><span class="sxs-lookup"><span data-stu-id="0174d-138">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="0174d-139">**Zap de malware** : la depuración automática de cero horas (ZAP) llevó a cabo una acción en un mensaje de correo electrónico que contiene malware después de la entrega.</span><span class="sxs-lookup"><span data-stu-id="0174d-139">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0174d-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0174d-140">Related topics</span></span>
- [<span data-ttu-id="0174d-141">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="0174d-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0174d-142">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="0174d-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0174d-143">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="0174d-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0174d-144">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="0174d-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0174d-145">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="0174d-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0174d-146">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="0174d-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)