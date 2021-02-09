---
title: Tabla EmailPostDeliveryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre las acciones posteriores a la entrega realizadas en los correos electrónicos de Microsoft 365 en la tabla EmailPostDeliveryEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailPostDeliveryEvents, id. de mensaje de red, remitente, destinatario, id. de datos adjuntos, nombre de datos adjuntos, veredicto de malware, veredicto de suplantación de identidad, recuento de datos adjuntos, recuento de vínculos, recuento de direcciones URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 774676e15e9018b13674149b6a2e147a91000814
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145504"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="e1fdc-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="e1fdc-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e1fdc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e1fdc-105">**Applies to:**</span></span>
- <span data-ttu-id="e1fdc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1fdc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e1fdc-107">La tabla del esquema de búsqueda avanzada contiene información sobre las acciones posteriores a la entrega realizadas en los mensajes de correo electrónico `EmailPostDeliveryEvents` procesados por Microsoft 365. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e1fdc-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="e1fdc-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="e1fdc-109">Para obtener información detallada acerca de los tipos de eventos (valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="e1fdc-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="e1fdc-110">Para obtener más información sobre mensajes de correo electrónico individuales, también puede usar [`EmailEvents`](advanced-hunting-emailevents-table.md) las [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tablas , [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) y.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="e1fdc-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e1fdc-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e1fdc-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="e1fdc-112">Column name</span></span> | <span data-ttu-id="e1fdc-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e1fdc-113">Data type</span></span> | <span data-ttu-id="e1fdc-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1fdc-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e1fdc-115">datetime</span><span class="sxs-lookup"><span data-stu-id="e1fdc-115">datetime</span></span> | <span data-ttu-id="e1fdc-116">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-116">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="e1fdc-117">cadena</span><span class="sxs-lookup"><span data-stu-id="e1fdc-117">string</span></span> | <span data-ttu-id="e1fdc-118">Identificador único del correo electrónico, generado por Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1fdc-118">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="e1fdc-119">cadena</span><span class="sxs-lookup"><span data-stu-id="e1fdc-119">string</span></span> | <span data-ttu-id="e1fdc-120">Identificador público para el correo electrónico que establece el sistema de correo electrónico de envío.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-120">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="e1fdc-121">cadena</span><span class="sxs-lookup"><span data-stu-id="e1fdc-121">string</span></span> | <span data-ttu-id="e1fdc-122">Acción realizada en la entidad</span><span class="sxs-lookup"><span data-stu-id="e1fdc-122">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="e1fdc-123">string</span><span class="sxs-lookup"><span data-stu-id="e1fdc-123">string</span></span> | <span data-ttu-id="e1fdc-124">Tipo de actividad que desencadenó el evento: corrección manual, PHISH ZAP, MALWARE ZAP</span><span class="sxs-lookup"><span data-stu-id="e1fdc-124">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="e1fdc-125">string</span><span class="sxs-lookup"><span data-stu-id="e1fdc-125">string</span></span> | <span data-ttu-id="e1fdc-126">Indica si un administrador desencadenó una acción (manualmente o mediante la aprobación de una acción automatizada pendiente) o mediante algún mecanismo especial, como un ZAP o una entrega dinámica</span><span class="sxs-lookup"><span data-stu-id="e1fdc-126">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="e1fdc-127">string</span><span class="sxs-lookup"><span data-stu-id="e1fdc-127">string</span></span> | <span data-ttu-id="e1fdc-128">Resultado de la acción</span><span class="sxs-lookup"><span data-stu-id="e1fdc-128">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="e1fdc-129">cadena</span><span class="sxs-lookup"><span data-stu-id="e1fdc-129">string</span></span> | <span data-ttu-id="e1fdc-130">Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-130">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="e1fdc-131">cadena</span><span class="sxs-lookup"><span data-stu-id="e1fdc-131">string</span></span> | <span data-ttu-id="e1fdc-132">Ubicación en la que se entregó el correo electrónico: bandeja de entrada / carpeta, local / externo, correo no deseado, cuarentena, erróneo, descartado, elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-132">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ReportId` | <span data-ttu-id="e1fdc-133">largo</span><span class="sxs-lookup"><span data-stu-id="e1fdc-133">long</span></span> | <span data-ttu-id="e1fdc-134">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-134">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e1fdc-135">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-135">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="e1fdc-136">Tipos de eventos admitidos</span><span class="sxs-lookup"><span data-stu-id="e1fdc-136">Supported event types</span></span>
<span data-ttu-id="e1fdc-137">En esta tabla se capturan eventos con los siguientes `ActionType` valores:</span><span class="sxs-lookup"><span data-stu-id="e1fdc-137">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="e1fdc-138">**Corrección manual:** un administrador tomó medidas manualmente en un mensaje de correo electrónico después de entregarlo al buzón de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-138">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="e1fdc-139">Esto incluye acciones realizadas manualmente a [través](../office-365-security/threat-explorer.md) del Explorador de amenazas o aprobaciones de acciones de investigación y [respuesta automatizadas (AIR).](mtp-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="e1fdc-139">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="e1fdc-140">**PHISH ZAP:** purga automática de cero horas [(ZAP)](../office-365-security/zero-hour-auto-purge.md) tomó medidas en un correo electrónico de suplantación de identidad después de la entrega.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-140">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="e1fdc-141">**Malware ZAP:** purga automática de cero horas (ZAP) tomó medidas en un mensaje de correo electrónico que contenía malware después de la entrega.</span><span class="sxs-lookup"><span data-stu-id="e1fdc-141">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e1fdc-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e1fdc-142">Related topics</span></span>
- [<span data-ttu-id="e1fdc-143">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="e1fdc-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e1fdc-144">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="e1fdc-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e1fdc-145">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="e1fdc-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e1fdc-146">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="e1fdc-146">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e1fdc-147">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="e1fdc-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e1fdc-148">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="e1fdc-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
