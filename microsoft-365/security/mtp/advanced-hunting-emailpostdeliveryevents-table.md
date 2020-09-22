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
ms.openlocfilehash: d9d3ffad156d5a27f1931c3b6ec295b022dea296
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198018"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="00960-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="00960-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="00960-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="00960-105">**Applies to:**</span></span>
- <span data-ttu-id="00960-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="00960-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="00960-107">La `EmailPostDeliveryEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las acciones posteriores a la entrega realizadas en los mensajes de correo electrónico procesados por Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="00960-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="00960-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="00960-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="00960-109">Para obtener información detallada acerca de los tipos de eventos ( `ActionType` valores) admitidos por una tabla, use la [referencia de esquema integrada](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponible en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="00960-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="00960-110">Para obtener más información sobre los mensajes de correo electrónico individuales, también puede usar las [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tablas, y [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="00960-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="00960-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="00960-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="00960-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="00960-112">Column name</span></span> | <span data-ttu-id="00960-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="00960-113">Data type</span></span> | <span data-ttu-id="00960-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="00960-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="00960-115">datetime</span><span class="sxs-lookup"><span data-stu-id="00960-115">datetime</span></span> | <span data-ttu-id="00960-116">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="00960-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="00960-117">cadena</span><span class="sxs-lookup"><span data-stu-id="00960-117">string</span></span> | <span data-ttu-id="00960-118">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="00960-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="00960-119">string</span><span class="sxs-lookup"><span data-stu-id="00960-119">string</span></span> | <span data-ttu-id="00960-120">Identificador único del correo electrónico generado por Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00960-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="00960-121">cadena</span><span class="sxs-lookup"><span data-stu-id="00960-121">string</span></span> | <span data-ttu-id="00960-122">Identificador público para el correo electrónico que establece el sistema de correo electrónico de envío.</span><span class="sxs-lookup"><span data-stu-id="00960-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="00960-123">cadena</span><span class="sxs-lookup"><span data-stu-id="00960-123">string</span></span> | <span data-ttu-id="00960-124">Acción realizada en la entidad</span><span class="sxs-lookup"><span data-stu-id="00960-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="00960-125">string</span><span class="sxs-lookup"><span data-stu-id="00960-125">string</span></span> | <span data-ttu-id="00960-126">Tipo de actividad que ha desencadenado el evento: corrección manual, ZAP de Phish, ZAP de malware</span><span class="sxs-lookup"><span data-stu-id="00960-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="00960-127">string</span><span class="sxs-lookup"><span data-stu-id="00960-127">string</span></span> | <span data-ttu-id="00960-128">Indica si una acción ha desencadenado un administrador (manualmente o mediante la aprobación de una acción automatizada pendiente) o mediante algún mecanismo especial, como una ZAP o una entrega dinámica</span><span class="sxs-lookup"><span data-stu-id="00960-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="00960-129">string</span><span class="sxs-lookup"><span data-stu-id="00960-129">string</span></span> | <span data-ttu-id="00960-130">Resultado de la acción</span><span class="sxs-lookup"><span data-stu-id="00960-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="00960-131">cadena</span><span class="sxs-lookup"><span data-stu-id="00960-131">string</span></span> | <span data-ttu-id="00960-132">Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="00960-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="00960-133">cadena</span><span class="sxs-lookup"><span data-stu-id="00960-133">string</span></span> | <span data-ttu-id="00960-134">Ubicación en la que se entregó el correo electrónico: bandeja de entrada / carpeta, local / externo, correo no deseado, cuarentena, erróneo, descartado, elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="00960-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="00960-135">Tipos de eventos admitidos</span><span class="sxs-lookup"><span data-stu-id="00960-135">Supported event types</span></span>
<span data-ttu-id="00960-136">Esta tabla captura eventos con los siguientes `ActionType` valores:</span><span class="sxs-lookup"><span data-stu-id="00960-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="00960-137">**Corrección manual** : un administrador realizó manualmente una acción en un mensaje de correo electrónico después de que se entregó al buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="00960-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="00960-138">Esto incluye las acciones realizadas manualmente a través del [Explorador de amenazas](../office-365-security/threat-explorer.md) o las aprobaciones de [las acciones de investigación y respuesta automáticas (Air)](mtp-autoir-actions.md).</span><span class="sxs-lookup"><span data-stu-id="00960-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="00960-139">**Zap phish** : la [depuración automática de cero horas (ZAP)](../office-365-security/zero-hour-auto-purge.md) llevó a cabo una acción en un correo de suplantación de identidad tras la entrega.</span><span class="sxs-lookup"><span data-stu-id="00960-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="00960-140">**Zap de malware** : la depuración automática de cero horas (ZAP) llevó a cabo una acción en un mensaje de correo electrónico que contiene malware después de la entrega.</span><span class="sxs-lookup"><span data-stu-id="00960-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="00960-141">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="00960-141">Related topics</span></span>
- [<span data-ttu-id="00960-142">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="00960-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="00960-143">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="00960-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="00960-144">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="00960-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="00960-145">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="00960-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="00960-146">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="00960-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="00960-147">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="00960-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
